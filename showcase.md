---
title: Showcase
---
TODO: More work still to be done...

<div class="pageListWrapper">
  {% for item in site.showcase %}
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
