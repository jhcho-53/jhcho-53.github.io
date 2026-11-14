---
layout: page
permalink: /publications/
title: publications
description:
nav: true
nav_order: 1
---

<!-- _pages/publications.md -->

<div class="publications">

<h2 class="bibliography">International Conference</h2>
{% bibliography --group_by none --query @*[category=international] %}

<h2 class="bibliography">Journal Articles</h2>
{% bibliography --group_by none --query @*[category=journal] %}

<h2 class="bibliography">Domestic Conference</h2>
{% bibliography --group_by none --query @*[category=domestic] %}

</div>
