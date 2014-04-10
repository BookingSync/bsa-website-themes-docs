# Money filters
1. TOC
{:toc}

## money(amount, currency)

Add currency sign to price value.

~~~django
{{ search.min_price | money: search.currency }}
~~~
