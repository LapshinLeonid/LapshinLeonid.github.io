---
title: "Дебаггинг Jekyll"
importance-tier : 2
categories:
  - blog
  - web-development
---

Изначально я пытался дебажить, пользуя логом в GitHub Actions. Сам лог выглядит следующим образом:

```
Logging at level: debug Configuration file: /github/workspace/./_config.yml GitHub Pages: github-pages v228 GitHub Pages: jekyll v3.9.3 Theme: 
jekyll-theme-primer Theme source: /usr/local/bundle/gems/jekyll-theme-primer-0.6.0 Requiring: jekyll-github-metadata Requiring: jekyll-seo-tag Requiring:
jekyll-paginate Requiring: jekyll-sitemap Requiring: jekyll-gist Requiring: jekyll-feed Requiring: jemoji Requiring: jekyll-include-cache Requiring:
jekyll-coffeescript Requiring: jekyll-commonmark-ghpages Requiring: jekyll-github-metadata Requiring: jekyll-relative-links Requiring:
jekyll-optional-front-matter Requiring: jekyll-readme-index Requiring: jekyll-default-layout Requiring: jekyll-titles-from-headings Requiring:
jekyll-remote-theme GitHub Metadata: Initializing... Source: /github/workspace/. Destination: /github/workspace/./_site Incremental build: disabled.
Enable with --incremental Generating... Theme: mmistakes/minimal-mistakes Theme source: /tmp/jekyll-remote-theme-20231112-9-jf6lxu Remote Theme: Using
theme mmistakes/minimal-mistakes Remote Theme: Downloading https://codeload.github.com/mmistakes/minimal-mistakes/zip/HEAD to /tmp/
jekyll-remote-theme-20231112-9-3n4se0.zip Remote Theme: Unzipping /tmp/jekyll-remote-theme-20231112-9-3n4se0.zip to /tmp/
jekyll-remote-theme-20231112-9-jf6lxu EntryFilter: excluded /Gemfile Reading: _posts/2023-11-12-github-metadata-usage.md Generating:
JekyllOptionalFrontMatter::Generator finished in 0.000170909 seconds. Generating: JekyllReadmeIndex::Generator finished in 0.00274234 seconds. Generating:
Jekyll::Paginate::Pagination finished in 0.000751138 seconds. Generating: Jekyll::JekyllSitemap finished in 0.00469754 seconds. Jekyll Feed: Generating
feed for posts Generating: JekyllFeed::Generator finished in 0.000943548 seconds. Generating: JekyllRelativeLinks::Generator finished in 7.1004e-05
seconds. Generating: JekyllDefaultLayout::Generator finished in 0.000308616 seconds. Generating: JekyllTitlesFromHeadings::Generator finished in 2.
5802e-05 seconds. Rendering: _posts/2023-11-12-github-metadata-usage.md Pre-Render Hooks: _posts/2023-11-12-github-metadata-usage.md Rendering Liquid:
_posts/2023-11-12-github-metadata-usage.md github-pages 228 | Error: Liquid syntax error (line 11): 'endif' is not a valid delimiter for for tags. use
endfor Remote Theme: Cleaning up /tmp/jekyll-remote-theme-20231112-9-jf6lxu
```

Сообщение об ошибке соответственно все, что идет после `| Error:`

Так работать практически невозможно, поэтому я решил установить Jekyll локально на Win 10. 

## Локальная установка Jekyll
1. Установите Ruby + devkit с [официального сайта](https://rubyinstaller.org/downloads/)
2. После установки должна открыться командная строка, там необходимо выбрать пункт `MSYS2 and MINGW development tool chain`, если этого не произошло - используйте команду `ridk install`
3. После этого выполните команду `gem install github-pages bundler`
4. Перейдите в директорию вашего проекта используя `cd` и выполните `jekyll serve`
5. Откройте локальную версию сайта используя адрес [http://localhost:4000/](http://localhost:4000/). Все вносимые изменения будут обрабатываться в реальном времени, при возникновении ошибок вы увидите их в консоли.

У меня возникли ошибки при первой компиляции и мне пришлось доставить некоторые гемы используя `gem install` при возникновении ошибки `Could not find gem...`. Также потребовалось прописать команду `bundle add webrick`, чтобы пофиксить `cannot load such file -- webrick`.

Дебажить локально стало намного удобнее. Также это избавило репозиторий от множества лишних коммитов с исправлением ошибок.

Я использую IDE VS Code, для него нашлось достаточно удобное расширение - [Jekyll Run](https://marketplace.visualstudio.com/items?itemName=Dedsec727.jekyll-run). Хотя вместо использования расширения достаточно прописать `jekyll serve` во вкладке `Terminal`.