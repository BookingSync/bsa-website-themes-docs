# Liquid filters
1. TOC
{:toc}

## Overview

Filters are used to manipulate output from tags. Filter operator is `|` and using that filters can be chained like:

~~~django
{{ rental.name | strip_html | truncate: 40 }}
~~~

Above example will remove HTML tags in input `rental.name` string and will truncate result to 40 characters. 

## Liquid filters

Default Liquid filters

### escape(input)

Escape string:

~~~django
{{ rental.description | escape }}
~~~

### append(input)

Append substring to a source string

~~~django
{{ 'main' | append: '.css' }}
~~~

Output:

~~~django
main.css
~~~

### prepend(input)

Prepend substring to a source string

~~~django
{{ '.jpg' | prepend: 'main' }}
~~~

Output:

~~~django
main.jpg
~~~

### size(input)

Calculate size of variable

~~~django
{{ 'size of this string is 25' | size }}
~~~

Output:

~~~django
25
~~~

### join(input, operator='')

Join array elements into string

~~~django
{{ rental.names | join: ', '}}
~~~

Output:

~~~django
Bahamas, Bali, Hawaii
~~~

### downcase(input)

~~~django
{{ 'BAHAMAS' | downcase }}
~~~

Output:

~~~django
bahamas
~~~

### upcase(input)

~~~django
{{ 'bahamas' | upcase }}
~~~

Output:

~~~django
BAHAMAS
~~~

### strip_html

Strip HTML tags in string

~~~django
{{ '<b>Jamaica is <br />the best</b>' | strip_html }}
~~~

Output:

~~~django
Jamaica is the best
~~~

### strip_newlines

Strip all `\n` in a string

~~~django
{{ 'I\n like\n Cuba' | strip_newlines }}
~~~

Output:

~~~django
I like Cuba
~~~

### truncate(input, characters=100)

Truncate a string down to N characters. 

~~~django
{{ 'Very long string about vacations ... ' | truncate: 9 }}
~~~

Output:

~~~django
Very long
~~~

### truncatewords(input, words=15)

Truncate a string down to N words. 

~~~django
{{ 'A lot of words about Bahamas' | truncatewords: 4 }}
~~~

Output:

~~~django
A lot of words
~~~

### date(input, format)

Format a date

~~~django
{{ rental.checkin.date | date: "%Y-%m-%d"}}
~~~

Output:

~~~django
2014-03-25
~~~

Possible format options are:

* `%a` - The abbreviated weekday name ("Sun")
* `%A` - The full weekday name ("Sunday")
* `%b` - The abbreviated month name ("Jan")
* `%B` - The full month name ("January")
* `%c` - The preferred local date and time representation
* `%d` - Day of the month (01..31)
* `%H` - Hour of the day,24-hour clock (00..23)
* `%I` - Hour of the day,12-hour clock (01..12)
* `%j` - Day of the year (001..366)
* `%m` - Month of the year (01..12)
* `%M` - Minute of the hour (00..59)
* `%p` - Meridian indicator ("AM" or "PM")
* `%S` - Second of the minute (00..60)
* `%U` - Week number of the current year, starting with the first Sunday as the first day of the first week (00..53)
* `%W` - Week number of the current year, starting with the first Monday as the first day of the first week (00..53)
* `%w` - Day of the week (Sunday is 0,0..6)
* `%x` - Preferred representation for the date alone,no time
* `%X` - Preferred representation for the time alone,no date
* `%y` - Year without a century (00..99)
* `%Y` - Year with century
* `%Z` - Time zone name
* `%%` - Literal "%" character

### first(array)

Get first element of array

~~~django
{{ ['bahamas', 'bali', 'hawaii'] | first }}
~~~

Output:

~~~django
bahamas
~~~

### last(array)

Get last element of array

~~~django
{{ ['bahamas', 'bali', 'hawaii'] | last }}
~~~

Output:

~~~django
hawaii
~~~

### newline_to_br

Inserts a `<br />` linebreak tag in front of every `\n` linebreak character.

~~~django
{{ 'String\n with \n new \n lines' | newline_to_br }}
~~~

Output:

~~~django
String<br />\n with <br />\n new <br />\n lines
~~~

### replace(input, substring, replacement)

Will replace all occurrences of a string with another.

~~~django
{{ 'Bahamas are boring and Warsaw is boring' | replace: 'boring', 'awesome!'}}
~~~

Output:

~~~django
Bahamas are awesome! and Warsaw is awesome!
~~~

### replace_first(input, substring, replacement)

Will replace the first occurrence of a string with another.

~~~django
{{ 'Bahamas are boring and Warsaw is boring' | replace_first: 'boring', 'awesome!'}}
~~~

Output:

~~~django
Bahamas are awesome! and Warsaw is boring
~~~

### remove(input, substring)

Removes all occurrences of the substring from the input.

~~~django
{{ 'Bahamas are boring and Warsaw is boring' | remove: 'boring'}}
~~~

Output:

~~~django
Bahamas are and Warsaw is
~~~

### remove_first(input, substring)

Removes first occurrence of the substring from the input.

~~~django
{{ 'Bahamas are boring and Warsaw is boring' | remove_first: 'boring'}}
~~~

Output:

~~~django
Bahamas are and Warsaw is boring
~~~

### plus(input, operand)

Gets the result of adding input to operand. When strings are passed, it parses strings as integers before adding.

~~~django
Showing {{ paginate.current_offset }}-{{ paginate.current_offset | plus: paginate.page_size }} rentals
~~~

Output:

~~~django
Showing 20-100 rentals
~~~

### minus(input, operand)

Gets the result of subtracting input from operand. When strings are passed, it parses strings as integers before adding.

~~~django
{{ rental.price | minus: 20 }}
~~~

Output (assuming `rental.price` equal '100'):

~~~django
80
~~~
