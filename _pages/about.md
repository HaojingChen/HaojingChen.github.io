---
permalink: /
author_profile: true
redirect_from:
  - /about/
  - /about.html
---
{% include about-homepage-header.html %}

<p>{{ site.data.profile.introduction | escape }}</p>

<h2 id="education">教育经历</h2>
<div class="experience-container">
{% for entry in site.data.profile.education %}
  <div class="experience-card">
    <div class="experience-info">
      <strong>{{ entry.institution | escape }}</strong>
      <span class="experience-date">{{ entry.dates | escape }} · {{ entry.status | escape }}</span>
      {{ entry.program | escape }}<br>
      {{ entry.details | escape }}
    </div>
  </div>
{% endfor %}
</div>

<h2 id="internships">科研实习</h2>
<div class="experience-container">
{% for entry in site.data.profile.internships %}
  <div class="experience-card">
    <div class="experience-info">
      <strong>{{ entry.institution | escape }}</strong>
      <span class="experience-date">{{ entry.dates | escape }}</span>
      {{ entry.role | escape }}<br>
      {{ entry.details | escape }}
    </div>
  </div>
{% endfor %}
</div>

<h2 id="works">研究经历</h2>
<p>{{ site.data.profile.interests | escape }}</p>
<div id="works-list">
  {% include profile-research.html %}
</div>

<script src="{{ '/assets/js/experience_layout.js' | relative_url }}" defer></script>
<style>
  .experience-info { overflow-wrap: anywhere; }
</style>
