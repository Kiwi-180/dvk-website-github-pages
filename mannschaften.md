---
title: Unsere Mannschaften im RPDV
lead: In der RPDV-Saison 2026/27 starten 2 Teams für den DVK.
permalink: /mannschaften/
---

{% for team in site.data.teams.rpdv %}
{% include kader.html team=team %}
{% endfor %}
