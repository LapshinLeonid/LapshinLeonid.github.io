---
title: "Использование метаданных github в посте"
categories:
  - blog
---

Атрибуты текущего репозитория:
{% for repository in site.github.public_repositories %}
  {% if repository.name == site.repo_name %}
  Имя репозитория:          {{repository.name}}
  Описание:                 {{repository.description}}                
  URL-адрес:                {{repository.html_url}}
  Ссылка на профиль автора: {{repository.owner.url}}
  Аватарка автора:
  ![]({{repository.owner.url}})
  {% endif %}
{% endfor %} 

Перечень ссылок на мои публичные репозитории:

{% for repository in site.github.public_repositories %}
  {% if repository.name == site.repo_name %}
  TRUE
  {% endif %}
{% endfor %} 

