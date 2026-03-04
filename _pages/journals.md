---
layout: default
---

<article class="journal-entry">
  <header class="journal-header">
    <h1 class="post-title">{{ page.title }}</h1>
    <div class="journal-meta">
      <time datetime="{{ page.date | date_to_xmlschema }}">
        <i class="fas fa-calendar-day"></i> {{ page.date | date: "%B %-d, %Y" }}
      </time>
      {% if page.author %}
        <span class="journal-author"> | By {{ page.author }}</span>
      {% endif %}
    </div>
  </header>

  <hr class="journal-divider">

  <div class="journal-content post-body">
    {{ content }}
  </div>

  <footer class="journal-footer">
    <div class="advocacy-note">
      <p><strong>Researcher's Note:</strong> This entry is part of my ongoing advocacy journal. 
      Observations are based on personal experience and current clinical data as of 2026.</p>
    </div>
    
    <div class="journal-nav">
      {% if page.previous.url %}
        <a class="prev" href="{{ page.previous.url | relative_url }}">← Previous Entry</a>
      {% endif %}
      <a href="{{ '/journals/' | relative_url }}" class="back-link">Journal Archive</a>
      {% if page.next.url %}
        <a class="next" href="{{ page.next.url | relative_url }}">Next Entry →</a>
      {% endif %}
    </div>
  </footer>
</article>
