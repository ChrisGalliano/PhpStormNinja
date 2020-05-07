---
layout: default
title: Home
nav_order: 1
permalink: /
---

PhpStorm Ninja
==============

В этом репозитории я постараюсь собрать самые крутые и полезные фишки и настройки PhpStorm.
Если о чем-то забыл упомянуть - feel free to make a pull request. :smile:

Документация в красивом виде доступна тут [https://chrisgalliano.github.io/PhpStormNinja](https://chrisgalliano.github.io/PhpStormNinja)


---


#### Thank you to the contributors of PhpStorm Ninja!

<ul class="list-style-none">
{% for contributor in site.github.contributors %}
  <li class="d-inline-block mr-1">
     <a href="{{ contributor.html_url }}"><img src="{{ contributor.avatar_url }}" width="32" height="32" alt="{{ contributor.login }}"/></a>
  </li>
{% endfor %}
</ul>