{% for cat in site.category-list %}
### {{ cat }}
<ul>
  {% for page in site.pages %}
    {% if page.resource == true %}
      {% for pc in page.categories %}
        {% if pc == cat %}
          <li><a href="{{ page.url }}">{{ page.title }}</a></li>
        {% endif %}   <!-- cat-match-p -->
      {% endfor %}  <!-- page-category -->
    {% endif %}   <!-- resource-p -->
  {% endfor %}  <!-- page -->
</ul>
{% endfor %}  <!-- cat -->



{% for page in site.pages %}
{{ page.title}} | {{ page.last_modified_at | date: '%s' }}
{% endfor %}



<h1> poging 2 </h1>

  {% for page in site.pages %}{% if page.exclude != true %}<url>
{{site.canonical_domain}}{{site.baseurl}}{{ page.url }}
{{site.canonical_domain}}{{site.baseurl}}{{ item.url }}</loc>
{% endif %}{% endfor %}