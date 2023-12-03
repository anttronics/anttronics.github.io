---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---
- *"The lights in my model are too bright. I wish I could dim them."*
- *"I would like flashing lights for my police cars"*
- *"It would be nice to be able to..."*

Do you also have an idea for your model? Then check if we already have a suitable solution in our [project list][projects]. If we don't, you can simply [submit your idea][newidea] for discussion and we can work together to make it a reality.


<div class="pageListWrapper">
  {% for item in site.posts %}
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



[projects]: /projects
[newidea]: /newidea

