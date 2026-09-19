---
layout: default
title: Resume
permalink: /resume/
---

<style>
  .resume-wrapper {
    width: 100%;
    max-width: 860px;
    margin: 0 auto;
    padding: 20px 0;
  }

  .resume-toolbar {
    display: flex;
    justify-content: flex-end;
    margin-bottom: 10px;
  }

  .resume-toolbar a {
    font-family: sans-serif;
    font-size: 14px;
    text-decoration: none;
    color: #333;
  }

  .resume-embed {
    width: 100%;
    height: 90vh;
    border: 1px solid #ddd;
    border-radius: 4px;
  }
</style>

<div class="resume-wrapper">
  <div class="resume-toolbar">
    <a href="{{ '/assets/Resume_ConnorHyde.pdf' | relative_url }}" download>⬇ Download PDF</a>
  </div>
  <iframe class="resume-embed" src="{{ '/assets/Resume_ConnorHyde.pdf' | relative_url }}"></iframe>
</div>
```

This just embeds the PDF as a scrollable window on the page with a download link in the corner. No modal, no auto-open.
