# Global variables

These variables can be used and accessed from any file in your theme:

1. TOC
{:toc}

## `site` variable

Variable holds site specific attributes:

### `name`

Render Site name

~~~django
{{ site.name }}
~~~

### `slogan`

Render Site slogan

~~~django
{{ site.slogan }}
~~~

### `description`

Render Site description

~~~django
{{ site.description }}
~~~

### `email`

Render Site global defined e-mail

~~~django
{{ site.name }}
~~~

## `twitter` variable

variable holds twitter user account and tweets

### `user`

Get tweeter user.

~~~django
{{ twitter.user }}
~~~

### `tweets`

Get last 10 tweets for user.

~~~django
{% for tweet in twitter.tweets %}
{{ tweet.text }}
{{ tweet.created_at }}
{% endfor %}
~~~

### `last_tweet`

Get last tweet

~~~django
{{ twitter.last_tweet.text }}
{{ twitter.last_tweet.created_at }}
~~~
