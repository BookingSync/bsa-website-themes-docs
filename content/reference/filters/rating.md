# Rating filters
1. TOC
{:toc}

## convert_stars(rating)

Calculate rating to be used when displayed in stars,
formula used: 

~~~
(rating * 2) * 10
~~~

~~~django
{{ rental.rating | convert_stars }}
~~~
