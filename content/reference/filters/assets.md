# Assets filters
1. TOC
{:toc}

## stylesheet_url(input)

Return url for user created stylesheets, input can be:

* filename - add specified user created stylesheet as minified file
* 'global.css' string - add all user created stylesheets as one minified file

~~~django
{{ 'global.css' | stylesheet_url }}
~~~
~~~django
{{ 'my_style.css' | stylesheet_url }}
~~~

## javascript_url(input)

Return url for user created scripts, input can be:

* filename - add specified user created script as minified file
* 'global.css' string - add all user created scripts as one minified file

~~~django
{{ 'global.js' | javascript_url }}
~~~
~~~django
{{ 'my_script.js' | javascript_url }}
~~~

## img_url(input)

Return url for user created uploaded image file.

~~~django
{{ 'my_image.jpg' | img_url }}
~~~


## global_asset_url(input)

Return URL for global assets

~~~django
{{ 'application.css' | global_asset_url }}
~~~


## script_tag(url)

Add script HTML tag for given URL

~~~django
{{ 'global.js' | javascript_url | script_tag }}
~~~

Output:

~~~html
<script src="/given/url" type="text/javascript"></script>
~~~

## stylesheet_tag(url, media="all")

Add link HTML tag for given URL, media type can be passed.

~~~django
{{ 'global.css' | stylesheet_url | stylesheet_tag: 'all' }}
~~~

Output:

~~~html
<link href="/given/url" rel="stylesheet" type="text/css"  media="#{media}"  />
~~~

##  img_tag(url, alt="")

Add img HTML tag for given URL, image alt can be passed.

~~~django
{{ 'my_image.jpg' | img_url | img_tag: 'Image description' }}
~~~

Output:

~~~html
<img src="/given/url" alt="#{alt}" />
~~~
