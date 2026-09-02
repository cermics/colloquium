---
layout: page
cover-img: /assets/images/coriolis-reunion.jpg
---

**See the <a href="https://calendar.google.com/calendar/embed?src=polytechnique.org_mtciqkdgk679fo5h6vig5nihjc%40group.calendar.google.com&amp;ctz=Europe%2FParis">Google Agenda of the colloquium</a>, and add the <a href="https://calendar.google.com/calendar/ical/polytechnique.org_mtciqkdgk679fo5h6vig5nihjc%40group.calendar.google.com/public/basic.ics">iCal url</a> to your calendar**

### Next session

<div class="post" style="text-align: center"><strong>TBA</strong></div>

<p style="text-align: center"><em>Date, hour Salle de séminaire du CERMICS</em></p>
<p style="text-align: center">
<span style="text-decoration: underline">Title</span></p>

### Past sessions

{% for link in site.data.colloquium %}
{% if link.next != "yes" %}
{% if link.sem == "scommun" %}
{{ link.date | date : "%B %-d %Y" }}{% if link.hour != "void" %}, {{ link.hour }}{% endif %}: **{{ link.AU }}**,  
{% if link.UN %}{{ link.UN }}  {% endif %}
{% if link.TI %}*{{ link.TI }}*.{% endif %}
{% for sublink in link.PROG %}
 - {{ sublink.hour }}: **{{ sublink.AU }}**,  
 {% if sublink.UN %}{{ sublink.UN }}  {% endif %}
 *{{ sublink.TI }}*. {% if sublink.slides %}<a href="{{ sublink.slides | relative_url }}">(slides), </a>{% endif %}
{% if sublink.abstract %}<a href="{{ sublink.abstract }}">(abstract)</a>{% endif %}
{% endfor %}
{% else %}
{{ link.date | date : "%B %-d %Y" }}{% if link.hour != "void" %}, {{ link.hour }}{% endif %}: **{{ link.AU }}**,  
{{ link.UN }},  
*{{ link.TI }}*. {% if link.slides %}<a href="{{ link.slides  | relative_url }}">(slides), </a>{% endif %}
{% if link.abstract %}<a href="{{ link.abstract }}">(abstract)</a>{% endif %}
{% if link.TIb %}*{{ link.TIb }}*. {% endif %}{% if link.slidesb %}<a href="{{ link.slidesb  | relative_url}}">(slides), </a>{% endif %}
{% if link.abstractb %}<a href="{{ link.abstractb }}">(abstract)</a>{% endif %}
{% if link.contents %}
<details markdown="1">
<summary>Abstract</summary>
{{ link.contents }}
</details>
{% endif %}
{% endif %}
{% endif %}

-------------------------
{% endfor %}


