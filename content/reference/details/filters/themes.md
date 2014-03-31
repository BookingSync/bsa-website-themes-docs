# Themes filters
1. TOC
{:toc}

## Overview

Filters are used to manipulate output from tags. Filter operator is `|` and using that filters can be chained like:

~~~django
{{ rental.name | strip_html | truncate: 40 }}
~~~

Above example will remove HTML tags in input `rental.name` string and will truncate result to 40 characters. 

## Themes filters

BookingSync Liquid filters

### `t` filter

Use translation in template

~~~django
{{ "home.map.title" | t }}
~~~

Output (depending on language settings):

~~~django
Villas & Aparments
~~~
