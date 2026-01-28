## Classes

*Click on the class to see the week-by-week schedule.*

{% assign filtered_classes = site.classes | where: 'course', page.code %}
{% if filtered_classes.size > 0 %}
| Name | Time | Students | Duration (h) | Status |
| --- | --- | --- | --- | --- |
{% for class in filtered_classes %}{% assign course = site.courses | where: 'code', class.course | first %}| <a href="{{ class.url | prepend: site.baseurl}}"><strong>{{ class.name }}</strong></a> | {{ site.translations[site.lang].classes[class.name].time }} | {{ class.students }} | {{ course.duration }} | {{ class.status }}
{% endfor %}
{% else %}
No classes yet!
{% endif %}