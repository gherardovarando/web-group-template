---
layout: default
title: People 
weight: 2
---




{% for role in site.data.people.roles %} 
{% assign people = site.people | where: 'role', role.id %}
<h2> {{ role.title }}s </h2>
<div class="flex-container">
{% for atom in people  %}
<div class="flex-item"> 

<div class="flex-container"> 
<div class="flex-item" style="flex:35%"> 
<img src="{{site.baseurl}}/{{atom.img}}" alt = "image of {{atom.name}}" style="height:122px;">
</div>
<div class="flex-item" style="flex:55%"> 
<strong> {{ atom.name }} </strong>

<p> {{ atom.content }} </p> 
</div>
</div>

</div>
{% endfor %}
</div>
{% endfor %}

