---
layout: default
title: seminars
weight: 5
---

## Seminars 


Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum



<table class = "talks"> 
  <tr class = "title">
    <th>Date</th>
    <th>Location</th>
    <th>Title</th>
    <th>Speaker</th>
    <th>Affiliation</th>
  </tr>
        {% assign sorted = site.talks | reverse %}
	{% for post in sorted %}
        {% capture nowunix %}{{'now' | date: '%s'}}{% endcapture %}
        {% capture posttime %}{{post.date | date: '%s'}}{% endcapture %} 
	<tr {% if posttime < nowunix %} class = "past" {% endif %}>
           <th> {% if post.date %}<time datetime="{{ post.date }}">{{ post.date | date: "%A, %-d %B %Y %H:%M  (%Z | UTC%z)" }}</time>  {% endif %}</th>
           <th> {% if post.link %}  
                   <a href="{{ post.link }}"> {{ post.location }} </a> 
                {% else %} {{ post.location }} {% endif %} </th>
           <th>
		<a href="{{ post.url }}">{{ post.title }}</a>
  </th>
           <th> {{ post.speaker }} </th>
           <th> {{ post.affiliation }} </th>
	</tr>
	{% endfor %}
</table>




