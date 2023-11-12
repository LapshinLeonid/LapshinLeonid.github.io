---
title: "Использование метаданных github в посте"
categories:
  - blog
---


Перечень ссылок на мои публичные репозитории:

{% for repository in site.github.public_repositories %}
  * [{{ repository.name }}]({{ repository.html_url }})
{% endfor %}
