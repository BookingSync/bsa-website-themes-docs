# Liquid markup
1. TOC
{:toc}

## Two types of Liquid tags

### Logic tag

Used for loops/conditionals blocks within templates

~~~django
{% for rental in rentals %}
... do something ...
{% endfor %}
~~~

### Render tag

Used to render data within template

~~~django
{{ rental.name }}
~~~

## Conditional

### `if` statement

If `true` then do something:

~~~django
{% if rental.description %}
Warm and sunny!
{% endif %}
~~~

~~~django
{% if rental.name == 'Bali' %}
Welcome to heaven!
{% endif %}
~~~

### `unless` statement

If `not true` then do something:

~~~django
{% unless rental.name == 'swamps' %}
Welcome to Bahamas!
{% endif %}
~~~

### Operators

* `==` equal to
* `!=` noto equal to
* `>` greater then
* `<` less than
* `>=` greater or equal than
* `<=` less than
* `or` `true` or `false` ==> `true`
* `and` `true` and `false` ==> `false`
* `contains` `true` can be used on a string to check for a substring or used on an array to check if it includes element 

## `for` loop

Repeat part of code:

~~~django
{% for rental in rentals %}
{{ rental.name }}
{% endif %}
~~~

Inside `for` loop few helpers are available:

* `forloop.length` will render length of entire loop
* `forloop.index` will render index of current element
* `forloop.index0` will render index of current element
* `forloop.rindex` will render number of items left to iterate
* `forloop.rindex0` will render number of items left to iterate
* `forloop.first` `true` if this is first iteration
* `forloop.last` `true` if this is last iteration

## `include` snippet

Snippets can be included into templates.

~~~django
{% include 'snippets/search_bar' %}
~~~
