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
{{ site.email }}
~~~

## `twitter` variable

Variable holds twitter user account and tweets

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

## `time` variable

Variable holds date/time helpers.

### `today`

Prints todays date.

~~~django
{{ time.today }}
~~~

### `tomorrow`

Prints tomorrows date.

~~~django
{{ time.tomorrow }}
~~~

## `search` variable

Search variable holds helpers related to search results and building search form.

### `display_type`

Render current display type for results, can be one of `map`, `photos` or `list`; default: `photos`

~~~django
{{ search.display_type }}
~~~

### `search_url`

Render URL for search action.

~~~django
{{ search.search_url }}
~~~

### `display_list_url`

Render URL to display search results as list.

~~~django
{{ search.display_list_url }}
~~~

### `display_photos_url`

Render URL to display search results as photos.

~~~django
{{ search.display_photos_url }}
~~~

### `display_map_url`

Render URL to display search results as map.

~~~django
{{ search.display_map_url }}
~~~

### `rentals`

An array of rentals returned by search action.
Each array element is `rental` variable.

~~~django
{% for rental in search.rentals %}
{{ rental.basic_details }}
{% endif %}
~~~

### `destinations`

An array of selected destinations in search form.
Each array element is a `destination` variable.
If none selected returns empty array.

~~~django
{% for destination in search.destinations %}
{{ destination.name }}
{% endif %}
~~~

### `checkin`

Checkin date.

~~~django
{{ search.checkin }}
~~~

### `checkout`

Checkout date.

~~~django
{{ search.checkout }}
~~~

### `guests`

Array of number of guests field in search form.
Each element is a `guest` variable.

~~~django
{% for guest in search.guests %}
{{ guest.count }}
{% endif %}
~~~

### `min_price`

Minimum price selected in search form.

~~~django
{{ search.min_price }}
~~~

### `max_price`

Maximum price selected in search form.

~~~django
{{ search.max_price }}
~~~

### `absolute_min_price`

Absolute limit for minimum price, default `0`

~~~django
{{ search.absolute_min_price }}
~~~

### `absolute_max_price`

Absolute limit for maximum price.

~~~django
{{ search.absolute_max_price }}
~~~

### `currency`

Current currency.

~~~django
{{ search.currency }}
~~~

### `rental_types`

Array of selected rental types.
Each element is a `rental_type` variable.
If none selected returns empty array.

~~~django
{% for rental_type in search.rental_types %}
{{ renatl_type.name }}
{% endif %}
~~~

### `amenities`

Array of selected amenities.
Each element is a `amenity` variable.
If none selected returns empty array.

~~~django
{% for amenity in search.amenities %}
{{ amenity.name }}
{% endif %}
~~~

### `rental_ids`

String of rental IDs separated with ` ` (whitespace)

~~~django
{{ search.rental_ids }}
~~~

