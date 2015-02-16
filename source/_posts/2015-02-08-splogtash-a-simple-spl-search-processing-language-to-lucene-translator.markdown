---
layout: post
title: "splogTASH - SPL to Lucene translator"
date: 2015-02-08 12:59:41 -0500
comments: true
categories:
- Technology
- Linux
- web operations
tags:
- splunk
- logstash
- kibana
- lucene
---



Recently I took part in the migration of Splunk over to ELK (Elastic Search/Logstash/Kibana). One of the main road-blocks with this migration was the syntax changes that were introduce since the query language was different in the new system. 

Splunk uses a proprietary language called "search processing language" or SPL for short. Kibana and the ELK stack make use of Apache Lucene. These two languages are not difficult by themselves, but converting queries over from SPL to Lucene is not always a trivial task.   

I wanted to find an easy way of converting Splunk queries over to Lucene, so I started working on a translator.

 
<h3>What is splogTASH?</h3>


<img src="https://raw.githubusercontent.com/dyurk/splogtash/master/public/splogstash_screenshot.png">

splogTASH is a <a href="http://www.sinatrarb.com/">Sinatra</a> application that translates queries depending on the definitions provided. The main definitions are stored in a JSON formatted file <a href="https://github.com/dyurk/splogTASH/blob/master/helpers/lucene.json">`/helpers/lucene.json`</a>.  

```json ../helpers/lucene.json
{
	"lucene": {
		"/data/syslog/current/web/info.log": "web_info_log AND",
		"/data/syslog/current/web/access.log": "web_access_log AND",
		"/data/syslog/current/web/error.log": "web_error_log AND",
		"source=": "type:",
		"uri=": "request_uri:",
		"uri_path=": "request_uri:",
		"http_response=": "reponse:",
		"=": ":"
	},
	"pre_lucene": {
		"| where eventcount >": "min_doc_count:",
		"transaction ": " agg:terms field:",
		"stats count by ": " agg:stats field:"
		}
}
```

As you can see there are two objects in the schema, <em>lucene</em> and <em>pre_lucene</em>. Since splogTASH takes the whole inputed query and tokenizes each matching term, I added <em>pre_lucene</em> to easily convert before tokenizations. This comes in handy when dealing with complex queries that do aggregations for example.

Under the <em>lucene</em> object we see an example for a web info log: 

``` json
"/data/syslog/current/web/info.log": "web_info_log AND"
```
Here we are saying that any time we match <strong>"/data/syslog/current/web/info.log"</strong>, we want <strong>"web_info_log AND"</strong> in return. It's as simple as that, to add your own definitions follow the patter of "term" : "definition". 


Lastly, I would like to point out the main splogtash.rb file (line 39-48):

``` ruby ../splogtash.rb https://github.com/dyurk/splogTASH/blob/master/splogtash.rb#L31-L50 
        # post processing
        inputs.split.each do |query|
          queries << query
        end
        queries.each do |q|
          temp_var = String.new
          temp_var = q.dup
          lucene.each {|f, u| temp_var.gsub!(f, u)}
          case temp_var
          when /AND/
               temp_var = temp_var.delete('"')
          when /!/
               temp_var = temp_var.delete("!").insert(0, "-")
          when /\//
               temp_var = temp_var.gsub!("/","\\\/")
          end
          lucenyze << temp_var
        end
        rtg << lucenyze.join(' ')
        return rtg
      end
```
In the post-processing section there is a case statement which handles global translations. In this example I'm cleaning the query by escaping "/" and also replacing "!" with "-" (exclusions).

After a query has been converted we can then click on the translated query to test on Kibana. You might be interested in customizing the URL to best fit you. Look at `../views/search.erb`, replace "kibana.initech.com".

``` html ../views/search.erb https://github.com/dyurk/splogTASH/blob/master/views/search.erb#L9
<div class="panel panel-success">
  <div class="panel-body">
<pre> <a href="https://kibana.initech.com/#/dashboard/file/logstash.json?from=5m&query=<%= h @escaped_input %>"><%= @input %></a></pre>
  </div>
</div>
```

<h3>Try it yourself!</h3>
It's real simple to get started. The source can be found on my GitHub page: https://github.com/dyurk/splogTASH

``` bash
$ git clone git@github.com:dyurk/splogTASH.git
$ cd splogTASH/ && rackup -p 8080
```

Now go to http://localhost:8080

<em>Patches welcome!! </em>
