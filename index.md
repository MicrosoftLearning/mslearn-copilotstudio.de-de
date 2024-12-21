---
title: Online gehostete Anweisungen
permalink: index.html
layout: home
---

# Copilot Studio-Übungen

Links zu Copilot Studio-Übungen auf Microsoft Learn sind unten aufgeführt.

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions/Labs'" %} {% for activity in labs  %}
- [{{ activity.lab.title }}]({{ site.github.url }}{{ activity.url }}) {% endfor %}
