<div style="display: grid; grid-template-columns: 1fr auto;">
    <small markdown="1">{% if page.previous %}[← {{ page.previous.title }}]({{ page.previous.url | prepend: site.baseurl }}){% endif %}</small>
    <small markdown="1">{% if page.next %}[{{ page.next.title }} →]({{ page.next.url | prepend: site.baseurl }}){% endif %}</small>
</div>
**{{ page.title }}**\
<sup>📅 {{ page.date | date_to_string: "ordinal", "US" }}</sup>
