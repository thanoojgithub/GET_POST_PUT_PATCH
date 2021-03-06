# GET_POST_PUT_PATCH
HTTP Methods



The GET Method :
/test/demo_form.do?name1=value1&name2=value2

GET requests can be cached
GET requests remain in the browser history
GET requests can be bookmarked
GET requests should never be used when dealing with sensitive data
GET requests have length restrictions
GET requests should be used only to retrieve data


The POST Method
Note that the query string (name/value pairs) is sent in the HTTP message body of a POST request:

POST /test/demo_form.asp HTTP/1.1
Host: w3schools.com
name1=value1&name2=value2

POST requests are never cached
POST requests do not remain in the browser history
POST requests cannot be bookmarked
POST requests have no restrictions on data length

BACK button/Reload	 - 
GET is Harmless	
POST Data will be re-submitted (the browser should alert the user that the data are about to be re-submitted)


use POST to create resources, or use PUT to update resources.

Use PUT when you can update a resource completely through a specific resource. For instance, if you know that an article resides at http://example.org/article/1234, you can PUT a new resource representation of this article directly through a PUT on this URL.

If you do not know the actual resource location, for instance, when you add a new article, but do not have any idea where to store it, you can POST it to an URL, and let the server decide the actual URL.

PUT /article/1234 

HTTP/1.1
<article>
    <title>red stapler</title>
    <price currency="eur">12.50</price>
</article>
POST /articles 

HTTP/1.1
<article>
    <title>blue stapler</title>
    <price currency="eur">7.50</price>
</article>

HTTP/1.1 
201 Created
Location: /articles/63636



POST to a URL creates a child resource at a server defined URL.
Eg. /items/1

PUT to a URL creates/replaces the resource in its entirety at the client defined URL.
PUT replaces the resource at the known url if it already exists, so sending the same request twice has no effect. In other words, calls to PUT are idempotent.

PATCH to a URL updates part of the resource at that client defined URL.