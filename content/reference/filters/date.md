# Date filters
1. TOC
{:toc}


## iso8601(string)

Format date in iso8601 format.

~~~django
{{ rental.updated_at | iso8601 }}
~~~

Output (depending on date):

~~~django
2014-04-10
~~~