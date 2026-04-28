# Objnews Alpha 

### Latest Articles
{% for item in site.articles %}
* [{{ item.title }}]({{ item.url }})
{% endfor %}
