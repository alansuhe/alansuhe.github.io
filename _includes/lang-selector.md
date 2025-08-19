{% assign langs   = "en|zh-Hans|zh-Hant|ja" | split: "|" %}
{% assign titles  = "English|简体中文|繁體中文|日文" | split: "|" %}
{% assign links   = "" | split: "" %}

{% for l in langs %}
  {% unless l == include.lang %}
    {% capture link %}[{{ titles[forloop.index0] }}]({{ include.file }}.{{ l }}){% endcapture %}
    {% assign links = links | push: link %}
  {% endunless %}
{% endfor %}

{{ links | join: " | " }}