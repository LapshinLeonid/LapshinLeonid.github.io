---
title: "Использование метаданных github в посте"
categories:
  - blog
---

{% for repository in site.github.public_repositories %}
  {% if repository.name == site.repo_name %}
  * [{{ repository.name }}]({{ repository.html_url }})
  {% endif %}
{% endfor %} 

1

Перечень ссылок на мои публичные репозитории:

{% for repository in site.github.public_repositories %}
  * [{{ repository.name }}]({{ repository.html_url }})
{% endfor %}