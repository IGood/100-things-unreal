---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

#layout: home
---

Below is a list of all posts created so far for the [{{ site.title }}]({{ site.url }}) blog.

Total number of posts = {{ site.posts.size }}

{% for post in site.posts %}
- [{{ post.title }}]({{ post.url }})
{% endfor %}

---

#### Tags ({{ site.tags.size }})

{% assign tags = site.tags | sort %}
{% for tag in tags %}
<u>{{ tag[0] }}</u>
{% for post in tag[1] %}
- [{{ post.title }}]({{ post.url | prepend: site.baseurl }})
{% endfor %}
{% endfor %}
