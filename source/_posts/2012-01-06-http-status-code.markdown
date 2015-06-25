---
layout: post
status: publish
published: true
title: HTTP Status Code
author: DYURK
author_login: admin
author_email: null@dev.com
wordpress_id: 653
wordpress_url: http://d87studios.com/blog/?p=653
date: 2012-01-06 17:21:09.000000000 -05:00
categories:
- Technology
tags:
- http
- status code
comments: []
---
The first digit of the Status-Code defines the class of response. The last two digits do not have any categorization role. There are 5 values for the first digit:

<strong>1xx</strong>: Informational - Not used, but reserved for future use

This class of status code indicates a provisional response,   consisting only of the Status-Line and optional headers, and is   terminated by an empty line. HTTP/1.0 does not define any 1xx status   codes and they are not a valid response to a HTTP/1.0 request.   However, they may be useful for experimental applications which are   outside the scope of this specification.

<strong>2xx</strong>: Success - The action was successfully received, understood, and accepted.

This class of status code indicates that the client's request was   successfully received, understood, and accepted.

<strong>3xx</strong>: Redirection - Further action must be taken in order to complete the request

This class of status code indicates that further action needs to be taken by the user agent in order to fulfill the request. The action required may be carried out by the user agent without interaction with the user if and only if the method used in the subsequent request is GET or HEAD. A user agent should never automatically redirect a request more than 5 times, since such re-directions usually indicate an infinite loop.

<strong>4xx</strong>: Client Error - The request contains bad syntax or cannot be fulfilled o 5xx: Server Error - The server failed to fulfill an apparently valid request

The 4xx class of status code is intended for cases in which the client seems to have erred. If the client has not completed the request when a 4xx code is received, it should immediately cease sending data to the server. Except when responding to a HEAD request, the server should include an entity containing an explanation of the error situation, and whether it is a temporary or permanent condition. These status codes are applicable to any request method.

<strong>5xx</strong>: Server Error - The server failed to fulfill an apparently valid request

Response status codes beginning with the digit "5" indicate cases in which the server is aware that it has erred or is incapable of performing the request. If the client has not completed the request when a 5xx code is received, it should immediately cease sending data to the server. Except when responding to a HEAD request, the server should include an entity containing an explanation of the error situation, and whether it is a temporary or permanent condition. These response codes are applicable to any request method and there are no required header fields.

&nbsp;

Source: <a href="http://www.rfc-editor.org/rfc/rfc1945.txt">http://www.rfc-editor.org/rfc/rfc1945.txt</a>

&nbsp;
