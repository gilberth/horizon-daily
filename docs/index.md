---
layout: default
title: Horizon Daily
---

# Horizon Daily

Resúmenes sobre cloud, ciberseguridad e inteligencia artificial, generados con [Horizon](https://github.com/Thysrael/Horizon).

Los resúmenes se generan con IA. Consulta las fuentes originales para verificar los datos.

## Informes

{% for post in site.posts %}
- [{{ post.date | date: "%d/%m/%Y" }} — {{ post.title }}]({{ post.url | relative_url }})
{% else %}
Todavía no hay informes publicados.
{% endfor %}
