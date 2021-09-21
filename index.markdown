---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: page
---

{% for org in site.data.organizations %}
<div style="border:1px; border-style:solid; margin:10px 0px; padding:10px">
  <img src="/assets/logos/kids4it.png">
  <a href="{{ org.website }}">{{ org.name }}</a>
  <br/>  
  <span style="color:red">{{ org.slogan }}</span>
  <br/>
  Standorte: <ul style="margin:5px 0px">
  {% for location in org.locations %}
    <li style="display: inline-block; zoom:1"><a href="{{ location[1] }}">{{ location[0] }}</a></li>
  {% endfor %}
  </ul>
</div>
{% endfor %}