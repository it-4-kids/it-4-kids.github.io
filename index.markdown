---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: page
---

{% assign languages = site.data.languages %}

{% for org in site.data.organizations %}
<div style="border:1px; border-style:solid; margin:10px 0px; padding:10px">
        <img src="{% if org.logo-url != null %}{{ org.logo-url }}{% else %}/assets/logos/kids4it.png{% endif %}">
        <a href="{{ org.website }}">{{ org.name }}</a>
        <br/>
        <span style="color:red">{{ org.slogan }}</span>
        <br/>
        {% if org.topics != null %}
            Themen:
            <ul style="margin:5px 0px">
                {% for topic in org.topics %}
                    <li style="display: inline-block; zoom:1">
                        {{ topic }}{% unless forloop.last %}, {% endunless %}
                    </li>
                {% endfor %}
            </ul>
            <br/>
        {% endif %}
        {% if org.languages != null %}
            Sprachen:
            <ul style="margin:5px 0px">
                {% for lang in org.languages %}
                    <li style="display: inline-block; zoom:1">
                        {{ languages[lang] }}{% unless forloop.last %}, {% endunless %}
                    </li>
                {% endfor %}
            </ul>
            <br/>
        {% endif %}
        Standorte:
        <ul style="margin:5px 0px">
            {% for location in org.locations %}
                <li style="display: inline-block; zoom:1">
                    {% if location[1] == null %}
                        {{ location[0] }}
                    {% else %}
                        <a href="{{ location[1] }}">{{ location[0] }}</a>
                    {% endif %}
                </li>
            {% endfor %}
        </ul>
</div>
{% endfor %}