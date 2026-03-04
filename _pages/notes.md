---
layout: default
---

<div class="notes-container">
  <header class="notes-header">
    <h1 class="content-subhead">Research Notes & Snippets</h1>
    <p><small>Ongoing observations and clinical data summaries by Tommy T. Douglas.</small></p>
  </header>

  <hr>

  <div class="notes-feed">
    {% assign sorted_notes = site.notes | sort: 'date' | reverse %}
    {% for note in sorted_notes %}
      <div class="note-item" style="margin-bottom: 30px; border-bottom: 1px dashed #ccc; padding-bottom: 15px;">
        <h3 style="margin-bottom: 5px;">
          <a href="{{ note.url | relative_url }}">{{ note.title }}</a>
        </h3>
        <p class="note-meta" style="font-size: 0.85rem; color: #666;">
          <i class="fas fa-sticky-note"></i> Recorded on: {{ note.date | date: "%B %-d, %Y" }}
        </p>
        <div class="note-excerpt" style="font-style: italic; color: #444;">
          {{ note.content | strip_html | truncate: 200 }}
        </div>
      </div>
    {% endfor %}
  </div>
</div>
