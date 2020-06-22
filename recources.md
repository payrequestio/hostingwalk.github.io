{% for cat in site.category-list %}
### {{ cat }}
<ul>
 {% for page in site.pages %}{% if page.exclude != true %}
          <li><a href="{{ page.url }}">{{ page.title }}</a></li>
    {% endif %}   <!-- resource-p -->
  {% endfor %}  <!-- page -->
</ul>
{% endfor %}  <!-- cat -->



{% for page in site.pages %}
{{ page.title}} | {{ page.last_modified_at | date: '%s' }}
{% endfor %}



<h1> poging 2 </h1>

  {% for page in site.pages %}{% if page.exclude != true %}

{{site.canonical_domain}}{{site.baseurl}}{{ page.url }}
{{site.canonical_domain}}{{site.baseurl}}{{ item.url }}
{% endif %}{% endfor %}