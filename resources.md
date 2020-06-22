---
title: Resources
---

<div class="jumbotron text-center" style="/* background-color: white !important; */padding: 1.5rem 0rem;margin-bottom: -1.5rem;background-color: #f28b20;border-radius: 0rem;">
<div class="container"> 
    <div class="container-fluid text-center" style="padding: 1.2rem 0rem;color: white;">
<h1 style="display: inline-block;padding-top: .3125rem;margin-right: 1rem;font-size: 2.35rem;">
<img src="https://i.imgur.com/BzyiJXJ.png" style="
    max-width: 55px;
    margin-right: 12px;
    margin-bottom: 10px;
"> Resources
</h1>
</div>
</div>
</div>

<div class="jumbotron" style="background-color: white;">
<div class="container text-center"> 

<h1> Overzicht resources pagina`s </h1>

{% for page in site.pages %}{% if page.exclude != true %}
<ul>
<li><a href="{{ page.url }}">{{ page.title }}</a></li>
</ul>
{% endif %}{% endfor %}


</div>
</div>