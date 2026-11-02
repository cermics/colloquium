---
layout: page
cover-img: /assets/images/coriolis-reunion.jpg
---

**See the <a href="https://calendar.google.com/calendar/embed?src=polytechnique.org_mtciqkdgk679fo5h6vig5nihjc%40group.calendar.google.com&amp;ctz=Europe%2FParis">Google Agenda of the colloquium</a>, and add the <a href="https://calendar.google.com/calendar/ical/polytechnique.org_mtciqkdgk679fo5h6vig5nihjc%40group.calendar.google.com/public/basic.ics">iCal url</a> to your calendar**

### Next session

{% assign has_next = false %}
{% for link in site.data.colloquium %}
{% if link.next == true or link.next == "yes" %}
{% assign has_next = true %}
<div class="post" style="text-align: center"><strong>{{ link.AU }}</strong>{% if link.UN %}<br>{{ link.UN }}{% endif %}</div>

<p style="text-align: center"><em>{{ link.date | date: "%-d %B %Y" }}{% if link.hour and link.hour != "void" %}, {{ link.hour }}{% endif %}, {{ link.room | default: "Salle de séminaire du CERMICS" }}</em></p>
<p style="text-align: center"><span style="text-decoration: underline">{{ link.TI | default: "Title TBA" }}</span></p>
{% if link.contents %}
<details markdown="1">
<summary>Abstract</summary>

{{ link.contents }}

</details>
{% endif %}
{% endif %}
{% endfor %}
{% unless has_next %}
<div class="post" style="text-align: center"><strong>TBA</strong></div>
{% endunless %}

### Past sessions

{% for link in site.data.colloquium %}
{% unless link.next == true or link.next == "yes" %}
{% if link.sem == "scommun" %}
{{ link.date | date: "%-d %B %Y" }}{% if link.hour and link.hour != "void" %}, {{ link.hour }}{% endif %}: **{{ link.AU }}**{% if link.UN %}<br>{{ link.UN }}{% endif %}{% if link.TI %}<br>*{{ link.TI }}*{% endif %}
{% for sublink in link.PROG %}
- {{ sublink.hour }}: **{{ sublink.AU }}**{% if sublink.UN %}, {{ sublink.UN }}{% endif %}<br>*{{ sublink.TI }}*{% if sublink.slides %} [(slides)]({{ sublink.slides | relative_url }}){% endif %}{% if sublink.abstract %} [(abstract)]({{ sublink.abstract | relative_url }}){% endif %}
{% endfor %}
{% else %}
{{ link.date | date: "%-d %B %Y" }}{% if link.hour and link.hour != "void" %}, {{ link.hour }}{% endif %}: **{{ link.AU }}**{% if link.UN %}<br>{{ link.UN }}{% endif %}<br>
*{{ link.TI }}*{% if link.slides %} [(slides)]({{ link.slides | relative_url }}){% endif %}{% if link.abstract %} [(abstract)]({{ link.abstract | relative_url }}){% endif %}{% if link.TIb %}<br>
*{{ link.TIb }}*{% if link.slidesb %} [(slides)]({{ link.slidesb | relative_url }}){% endif %}{% if link.abstractb %} [(abstract)]({{ link.abstractb | relative_url }}){% endif %}{% endif %}{% if link.note %}<br>
<em>{{ link.note }}</em>{% endif %}
{% if link.contents %}
<details markdown="1">
<summary>Abstract</summary>

{{ link.contents }}

</details>
{% endif %}
{% endif %}

-------------------------
{% endunless %}
{% endfor %}
