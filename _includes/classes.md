## Classes

{% assign filtered_classes = site.classes | where: 'course', page.code %}
{% if filtered_classes.size > 0 %}
| Name | Time | Students | Duration | Status |
| --- | --- | --- | --- | --- |
{% for class in filtered_classes %}| [**{{ class.name }}**]({{ class.url }}) | {{ class.time }} | {{ class.students }} | {{ class.start }} – {{ class.end }} | {{ class.status }}{% endfor %}
{% else %}
No classes yet!
{% endif %}