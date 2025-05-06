---
layout: page
title: 🙋 Staff
description: A listing of all methodology course staff.
nav_order: 7
---

# 🙋 Staff

See the [Office Hours](../office-hours) page for the office hours schedule. **If you'd like to meet with someone and can't make it to their office hours, feel free to send them an email to schedule an appointment.**

## Coordinator and Methodology Instructor

{% assign instructors = site.staffers | where: 'role', 'Instructor' %}
{% for staffer in instructors %}
{{ staffer }}
{% endfor %}


## Teaching Assistants

{% assign tas = site.staffers | where: 'role', 'Teaching Assistant' %}
{% for staffer in tas %}
{{ staffer }}
{% endfor %}
