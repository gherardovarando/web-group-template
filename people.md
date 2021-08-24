---
layout: default
title: people 
weight: 2
---




{% for role in site.roles %} 
{% assign people = site.people | where: 'role', role.id %}
<h2> {{ role.title }}s </h2>
<div class="flex-container">
{% for atom in people  %}
<div class="flex-item"> 

<div class="flex-container"> 
<div class="flex-item" style="flex:35%"> 
<img src="{{atom.img | relative_url }}" alt = "image of {{atom.name}}" style="height:122px;">
</div>
<div class="flex-item" style="flex:55%"> 
<strong> 
{% if atom.link %}
<a href="{{atom.link}}"> {{atom.name}} </a> 
{% else if atom.published %}
<a href="{{atom.url}}"> {{atom.name}} </a>
{% else %}
{{atom.name}}
{% endif %}
</strong>

<p> {{ atom.excerpt }} </p> 
</div>
</div>

</div>
{% endfor %}
</div>
{% endfor %}

