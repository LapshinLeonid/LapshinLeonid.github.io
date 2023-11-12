---
title: "Использование метаданных github в посте"
categories:
  - blog
---

Имя репозитория: {{ site.github.github.public_repositories.name }}

URL: {{ site.github.github.public_repositories.URL }}

{% for repository in site.github.public_repositories %}
  * [{{ repository.name }}]({{ repository.html_url }})
{% endfor %}

