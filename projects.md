---
title: Projects
---
TODO: More work still to be done...

<div class="pageListWrapper">
  {% for project in site.projects %}
    <div class="pageListItem">
			<a class="pageListLink" href="{{ project.url }}">{{ project.title }}</a>
			{% if project.project_image %}
				<div class="pageListProjectImage">
					<img src="{{project.project_image}}" alt="{{project.title}}" class="pageListProjectImage">
				</div>
			{% endif %}
	      {{ project.excerpt }}
    </div>
  {% endfor %}
</div>

