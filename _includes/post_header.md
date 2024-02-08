<div style="display: grid; grid-template-columns: 1fr auto;">
    <small markdown="1">{% if page.previous %}[← {{ page.previous.title }}]({{ page.previous.url }}){% endif %}</small>
    <small markdown="1">{% if page.next %}[{{ page.next.title }} →]({{ page.next.url }}){% endif %}</small>
</div>
{{ page.title }}\
<sup>📅 {{ page.date | date: site.date_format }}</sup>
