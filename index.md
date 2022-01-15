# Swift Blog

## Posts

<ul>
  {% for tag in site.tags %}
    <li>
      <a href="#{{ tag[0] | downcase }}">{{ tag[0] }}</a>
    </li>
  {% endfor %}
</ul>

{% for tag in site.tags %}
  <h3 id="{{ tag[0] | downcase }}">{{ tag[0] }}</h3>
  <ul>
    {% for post in tag[1] %}
      <li>
        <h1>
          <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        </h1>
        {{ post.excerpt }}
      </li>
    {% endfor %}
  </ul>
{% endfor %}
