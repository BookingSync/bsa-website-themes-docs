# Text filters
1. TOC
{:toc}

## html_format(source)

Two or more consecutive newlines(\n\n) are considered as a paragraph and wrapped in <p> tags. One newline (\n) is considered as a linebreak and a <br /> tag is appended. This method does not remove the newlines from the text.

~~~django
{{ rental.description | html_format }}
~~~

## autolink(source)

Twitter auto-link for usernames, lists, hashtags and URLs.

~~~django
{{ site.social.twitter.last_tweet.text | autolink }}
~~~
