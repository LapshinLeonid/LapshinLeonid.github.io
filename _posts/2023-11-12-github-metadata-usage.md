---
title: "Использование метаданных github в посте"
categories:
  - blog
---

Имя репозитория: {{ site.github.name }}

{% for repository in site.github.public_repositories %}
  * [{{ repository.name }}]({{ repository.html_url }})
{% endfor %}

