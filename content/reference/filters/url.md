# Url filters
1. TOC
{:toc}

## url_encode(source)

Encode given string as URL

~~~django
{{ 'Villa Boubouki - Charming seafront villa on a beautiful relaxing area' | t }}
~~~

Output:

~~~django
Villa%20Boubouki%20-%20Charming%20seafront%20villa%20on%20a%20beautiful%20relaxing%20area
~~~

## active(source, request_url)

If source and request_url match returns 'active' string to be used 
for mark active element e.g. current selected menu/tag

~~~django
<li class="{{ item.url | active: current_page.url }}">
~~~

Output (if item.url is current page)

~~~django
<li class="active">
~~~
