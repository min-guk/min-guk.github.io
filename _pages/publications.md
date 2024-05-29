---
layout: page
permalink: /publications/
title: publications
description: 
nav: true
nav_order: 2
---
<div class="publications">
  {% bibliography --group_by venue --query @*[venue=international conference]*%}
</div>

<div class="publications">
  {% bibliography --group_by venue --query @*[venue=international journal]*%}
</div>

<!-- _pages/publications.md -->
<div class="publications">
  {% bibliography --group_by venue --query @*[venue=domestic conference, year=2024]*%}
  {% bibliography --group_by none --query @*[venue=domestic conference, year=2022]*%}
</div>
