---
title: "Использование метаданных github в посте"
categories:
  - blog
---

Имя репозитория: {{ site.github.github.public_repositories[1].name }}

URL: {{ site.github.github.public_repositories.URL }}



{% for repository in site.github.public_repositories %}
  {% if repository.name == site.repo_name %}
  * [{{ repository.name }}]({{ repository.html_url }})
  {% endif %}
{% endif %}

{% endfor %} 

1

Перечень ссылок на мои публичные репозитории:

{% for repository in site.github.public_repositories %}
  * [{{ repository.name }}]({{ repository.html_url }})
{% endfor %}