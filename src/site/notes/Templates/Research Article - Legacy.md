---
{"dg-publish":true,"permalink":"/templates/research-article-legacy/"}
---
 

{% for t in tags %}{% if t.tag not in ['review', 'meta_analysis', 'number_one', 'model', 'synthesis', 'thesis', 'data/plots'] %}[[{{t.tag}}\|{{t.tag}}]]{% endif %}{% if not loop.last %} {% endif %}{% endfor %}

{% set seen_texts = [] %}
{% for annotation in annotations -%}
  {%- if annotation.annotatedText and annotation.annotatedText not in seen_texts -%}
    {% set seen_texts = seen_texts + [annotation.annotatedText] %}
    {% if 'Green' in annotation.colorCategory %}
> <span style="color: #90EE90">{{ annotation.annotatedText }}</span>
    {% elif 'Yellow' in annotation.colorCategory %}
> <span style="color: #F9E076">{{ annotation.annotatedText }}</span>
    {% endif %}
  {%- endif %}
{% endfor %}
