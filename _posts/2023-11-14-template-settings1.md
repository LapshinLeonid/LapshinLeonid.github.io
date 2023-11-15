---
title: "Настройка шаблона 1"
excerpt_separator: <!--more-->
importance-tier : 1
categories:
  - blog
  - web-development
---

Выдержка из этого поста ограничена этим абзацем.
<!--more-->

* Загрузил аватарку в `/assets/images/`
* Удалил лишние ссылки в `config.yml`, пофиксил те, что есть, изменил путь к аве. Ава имеет расширение:
(обращение к параметру статического файла)

{% for file in site.static_files %}
 {% if file.basename == 'avatar' %}
        {{file.extname}}
 {% endif %}
{% endfor %}

* Изменил кол-во постов, отображаемых на страницы (paginator)
* Вставил изображение с google drive. Вот оно:
![](https://drive.google.com/uc?export=view&id=1_IHE7IEcpVHvpbMfFto0TGd3_5WkTcDx)
* Научился делать ссылки на посты. Вот одна из них - [{{site.posts[1].title}}]({{site.posts[1].url}}).
* Научился ограничивать/увеличивать выдержку из постов (для отображения на главной). У этого поста выдержка ограничена первым пунктом списка. Вот она же вставленная через объект Liquid: 
> {{page.excerpt}}
* Пример использования данных. Перечисление ip из рандомного, скачанного в интернете `.yml` файла:
    {% for node in site.data.example.all.children.control_nodes.hosts%}  
    * {{node[1].management_network.network1.ip}}
    {% endfor %}
