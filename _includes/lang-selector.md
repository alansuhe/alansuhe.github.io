{% assign langs  = "en|zh-Hans|zh-Hant|ja" | split: "|" %}
{% assign titles = "English|简体中文|繁體中文|日本語" | split: "|" %}
{% assign items  = "" | split: "" %}

{% for l in langs %}
  {% if l == include.lang %}
    {% assign item = titles[forloop.index0] %}
  {% else %}
    {% capture item %}<a href="{{ include.file }}.{{ l }}">{{ titles[forloop.index0] }}</a>{% endcapture %}
  {% endif %}
  {% assign items = items | push: item %}
{% endfor %}

{{ items | join: " | " }}