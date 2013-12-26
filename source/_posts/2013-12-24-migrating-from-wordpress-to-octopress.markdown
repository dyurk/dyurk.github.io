---
layout: post
title: "Migrating from WordPress to Octopress"
date: 2013-12-24 22:45:54 -0500
comments: true
categories:
- Technology
- Linux
- web operations
tags:
- wordpress
- octropress
- GitHub
- pages
---

For some time I have looked at moving away from Wordpress for numerous reasons (That would be for another post!). I took a look at various platforms, but most fell short of expectations. Either they were too bloated, troublesome to manage or they lack some core features. I played around with <a href="http://jekyllrb.com/">Jekyll</a> and I liked the initial idea. But, after doing more research I found <a href="http://octopress.org/">Octopress</a> and I was quite happy with the final result.

Since you can host your blog from GitHub pages, my original plan was to first get a working copy running. After everything looked well, I would point my domain name to GitHub. This is how I did it...

<h3>First Step: Get all data out of Wordpress</h3>
This step was easy, just log-on to Wordpress' admin page and initiate an <a href="http://en.blog.wordpress.com/2006/06/12/xml-import-export/">XML export</a>. This is optional, but for the database export I decided that it would be easier to just do a MySQL dump and then do an import on my local MySQL instance.

All of the static files will need to be moved. If you are hosting them somewhere else you will only have to worry about the <strong>wp-content</strong> folder. This folder contains all of your plug-ins, themes, and images. In reality all we need is the images, in my case I deleted the rest except the images which were under the <em>uploads</em> folder.

<h3>Install Octopress</h3>
Again, this step is easy and very well <a href="http://octopress.org/docs/setup/">documented</a>. If you are hosting on GitHub you will need to create a new repository that follows the correct naming convention.

```
github_username.github.io
```

For example, my repo is <strong>dyurk.github.io</strong>.

<h3>Importing your data to Octopress</h3>

You will need to install the jekyll-import gem:
```bash
$ gem install jekyll-import
```

In the directory where you have your `wordpress.xml` file run the following:

```bash
$ ruby -rubygems -e 'require "jekyll-import";
    JekyllImport::Importers::WordPress.run({
      "dbname"   => "wordpress_db",
      "user"     => "user",
      "password" => "pass",
      "host"     => "localhost",
      "prefix"   => "wp_",
      "clean_entities" => true,
      "comments"       => true,
      "categories"     => true,
      "tags"           => true,
      "more_excerpt"   => true,
      "more_anchor"    => true,
      "status"         => ["publish"]
    })'
```
This will create a <strong>_post</strong> directory. Which will need to be move to <strong>octopress/source/</strong>.

Keep in mind that any `<code>` tags will need to be replace by backticks. Any snippets or tags specific to Wordpress will most likely break formatting.

Finally, for the static content in the <strong>wp-content</strong> folder, I decided to move the entire directory under <strong>octopress/source/</strong>. That way I don't have to update the code and SEO does not take a hit.

<h3>Custom domain and 404s</h3>

If you own a domain that you would like to use for your GitHub hosted blog. Basically, all you need is an A record pointing to <em>204.232.175.78</em> and a file under <strong>octopress/source/</strong> name `CNAME`. In this file add your domain name like so:

```console .../octopress/source/CNAME
www.dyurk.com
```

To gracefully handle 404s I decided to redirect to the homepage. To add a custom 404 page just create a file under the <strong>source/</strong> directory. The file must be named `404.html`. Here is my file:

```html .../octopress/source/404.html
<html>
        <head>
        <meta http-equiv="refresh" content="0; url=http://dyurk.com/" />
        </head>
<body>
</body>

</html>
```

<h3>Conclusion</h3>

After the DNS changes take effect the blog should be accessible via the domain name. If you are looking to customize your blog I recommend reading Octopress' documentation on the topic: http://octopress.org/docs/theme/. 

As a side note, if you need to moved your working copy to a new computer or just need to re-create it, you will need to do the following:

Clone the <em>source</em> branch:
```bash
$ git clone -b source git@github.com:username/username.github.io.git octopress 
```
Bundle install and setup GitHub pages:
```bash
$ gem install bundler
$ sudo gem install bundler
$ rbenv rehash && bundle install && rake setup_github_pages
```
Now fetch the master branch:
```bash
$ cd _deploy
$ git fetch —all
$ git reset --hard origin/master
```   




