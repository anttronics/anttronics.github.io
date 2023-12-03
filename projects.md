---
title: Projects
---
TODO: maybe a short project list description here?

<div class="pageListWrapper">
  {% for item in site.projects %}
    <div class="pageListItem">
			<a class="pageListLink" href="{{ item.url }}">{{ item.title }}</a>
			{% if item.image %}
				<div class="pageListImage">
					<img src="{{item.image}}" alt="{{item.title}}" class="pageListImage">
				</div>
			{% endif %}
	      {{ item.excerpt }}
    </div>
  {% endfor %}
</div>

