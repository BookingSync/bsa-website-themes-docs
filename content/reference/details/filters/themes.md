# Themes filters
1. TOC
{:toc}


## t(string)

Use translation in template

~~~django
{{ "home.map.title" | t }}
~~~

Output (depending on language settings):

~~~django
Villas & Aparments
~~~

## category_photo_url(photo, size = 'normal')

Dispaly category photo in wanted size.  

~~~django
{{ category.photos.first | category_photo_url: 'normal' }}
~~~

## money(amount, currency)

Add currency sign to price value.

~~~django
{{ search.min_price | money: search.currency }}
~~~

## rental_photo_url(photo, size = 'normal')

Display rental photo in wanted size.

~~~django
{{ photo | rental_photo_url: 'thumb' }}
~~~
