{% assign langs  = include.langs | default: "en|zh-Hans|zh-Hant|ja" | split: "|" %}
{% assign titles = include.titles | default: "English|简体中文|繁體中文|日本語" | split: "|" %}
{% assign items  = "" | split: "" %}

{% for l in langs %}
  {% if l == include.lang %}
    {% assign item = titles[forloop.index0] %}
  {% else %}
    {% capture item %}<a href="{{ include.file }}.{{ l }}{{ include.extension }}">{{ titles[forloop.index0] }}</a>{% endcapture %}
  {% endif %}
  {% assign items = items | push: item %}
{% endfor %}

{{ items | join: " | " }}