---
title: "Использование метаданных github в посте"
categories:
  - blog
---
{% for repository in site.github.public_repositories %}
  {% if repository.name == site.repo_name %}
  TRUE
  {% endif %}
{% endfor %} 


Перечень ссылок на мои публичные репозитории:

1

{% for repository in site.github.public_repositories %}
  * [{{ repository.name }}]({{ repository.html_url }})
{% endfor %}
