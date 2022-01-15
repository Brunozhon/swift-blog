# Swift Blog

## Posts

{% for tag in site.tags %}
  <h3>{{ tag[0] }}</h3>
  <ul>
    {% for post in tag[1] %}
      <li>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        {{ post.excerpt }}
      </li>
    {% endfor %}
  </ul>
{% endfor %}
