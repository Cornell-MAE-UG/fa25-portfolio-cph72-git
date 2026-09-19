---
layout: default
title: Resume
permalink: /resume/
---

<style>
  .resume-wrapper {
    width: 100%;
    max-width: 900px;
    margin: 0 auto;
    padding: 10px 0;
  }
  .resume-toolbar {
    display: flex;
    justify-content: flex-end;
    margin-bottom: 8px;
  }
  .resume-toolbar a {
    font-family: sans-serif;
    font-size: 14px;
    text-decoration: none;
    color: #333;
  }
  .resume-embed {
    width: 100%;
    height: 95vh;
    border: none;
    border-radius: 4px;
    display: block;
  }
</style>

<div class="resume-wrapper">
  <div class="resume-toolbar">
    <a href="{{ '/assets/Resume_ConnorHyde.pdf' | relative_url }}" download>⬇ Download PDF</a>
  </div>
  <iframe class="resume-embed" src="{{ '/assets/Resume_ConnorHyde.pdf' | relative_url }}#toolbar=0&navpanes=0"></iframe>
</div>
