---
title: "Использование метаданных GitHub в посте"
importance-tier : 2
categories:
  - blog
  - web-development
---
## Атрибуты текущего репозитория
{% for repository in site.github.public_repositories %}
  {% if repository.name == site.repo_name %}
  Имя репозитория:          {{repository.name}} 

  Описание:                 {{repository.description}} 

  URL-адрес:                [{{repository.html_url}}]({{repository.html_url}})  

  Ссылка на профиль автора: [{{repository.owner.html_url}}]({{repository.owner.html_url}})  
  
  Аватарка автора:
  ![]({{repository.owner.avatar_url}})
  {% endif %}
{% endfor %} 

## Перечень ссылок на мои публичные репозитории

{% for repository in site.github.public_repositories %}
* [{{repository.name}}]({{repository.html_url}})
{% endfor %} 
 

