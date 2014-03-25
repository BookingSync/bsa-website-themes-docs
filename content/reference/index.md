# Themes Reference

1. TOC
{:toc}

## Liquid

Themes on site uses [Liquid](http://liquidmarkup.org) templating system with additional specific features. Thanks to Liquid designers can easly create cutom themes using `logic` and `render` markup.

## Example usage

~~~django
<article class="rental">
  <a href="{{ rental.url }}">
    <figure>
      <span class="img-wrapper rentalSlider rsDefault">
       {% for photo in rental.photos %}
          {% if forloop.index == 1 %}
            <img src="{{ photo.thumb_url }}" alt="{{ rental.headline }}" class='img-responsive' />
          {% else %}
            <span href="{{ photo.thumb_url }}"></span>
          {% endif %}
        {% endfor %}
      </span>
      <figcaption>
        <h2>{{ rental.headline | truncate: 200 }}</h2>
        <span class="description">{{ rental.basic_details }}</span>
        <p class="summary">{{ rental.summary }}</p>
        <ul class="amenities list-inline fa-ul">
          {{ rental.amenities }}
        </ul>
        <span class="price">
          {% include 'snippets/rental_price' %}
        </span>
      </figcaption>
    </figure>
  </a>
</article>
~~~

This example shows how to: 

* render template using `{{ }}` tags
* use for loop using {{ for photo on rental.photos }}
* including snippets with `{% include %} tag` 
* use {{ | truncate: 200 }} filter

For more details how to use all those goodies check Reference on the right navigation panel.