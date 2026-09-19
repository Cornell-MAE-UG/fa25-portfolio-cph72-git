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
  .resume-wrapper.expanded {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    max-width: 100vw;
    height: 100vh;
    margin: 0;
    padding: 0;
    z-index: 9999;
    background: #fff;
  }
  .resume-toolbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 8px;
    padding: 0 4px;
  }
  .resume-toolbar a, .resume-toolbar button {
    font-family: sans-serif;
    font-size: 14px;
    text-decoration: none;
    color: #333;
    background: none;
    border: none;
    cursor: pointer;
    padding: 0;
  }
  .resume-toolbar button:hover, .resume-toolbar a:hover {
    color: #000;
  }
  .resume-embed {
    width: 100%;
    height: 92vh;
    border: none;
    display: block;
    background: #525659;
  }
  .expanded .resume-toolbar {
    padding: 8px 12px;
    background: #fff;
  }
  .expanded .resume-embed {
    height: calc(100vh - 40px);
  }
</style>

<div class="resume-wrapper" id="resumeWrapper">
  <div class="resume-toolbar">
    <a href="{{ '/assets/Resume_ConnorHyde.pdf' | relative_url }}" download>⬇ Download PDF</a>
    <button onclick="toggleExpand()" id="expandBtn">⛶ Expand</button>
  </div>
  <iframe
    class="resume-embed"
    id="resumeFrame"
    src="{{ '/assets/Resume_ConnorHyde.pdf' | relative_url }}#view=FitH&toolbar=1">
  </iframe>
</div>

<script>
  function toggleExpand() {
    const wrapper = document.getElementById('resumeWrapper');
    const btn = document.getElementById('expandBtn');
    wrapper.classList.toggle('expanded');
    btn.textContent = wrapper.classList.contains('expanded') ? '✕ Close' : '⛶ Expand';
  }
</script>
