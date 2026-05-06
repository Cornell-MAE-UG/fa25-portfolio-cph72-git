---
layout: project
title: "SLF Rotating Bug Trap"
description: "A rotating trap designed to lure spotted lanternflies away from grape vines and reduce vineyard damage."
image: /assets/images/slf-trap-image.png
---

## MAE2250 Project: SLF Rotating Bug Trap

<img src="{{ site.baseurl }}/assets/images/slf-trap-image.png" alt="SLF Rotating Bug Trap" style="float: right; width: 280px; margin-left: 25px; margin-bottom: 15px; border-radius: 8px;">

This project focused on designing a low-cost, scalable rotating trap to reduce spotted lanternfly damage in vineyards. The trap uses attractants to lure SLF toward a rotating reaper wall, which guides them through a peg system and drops them into a collection chamber. By capturing the insects alive, the design may also improve luring effectiveness because SLF are attracted to each other’s scents. Prototype testing showed strong performance across peg guidance, chamber drop, and motorized rotation tests, supporting the design’s potential for future full-scale vineyard use.

<div style="clear: both;"></div>

## Project Milestones

<div class="milestone-links">
  <button onclick="openPDF('{{ site.baseurl }}/assets/pdfs/Client_Outline.pdf')">Client Pitch</button>
  <button onclick="openPDF('{{ site.baseurl }}/assets/pdfs/function_prototype.pdf')">Functional Prototype</button>
  <button onclick="openPDF('{{ site.baseurl }}/assets/pdfs/ODP6.pdf')">Client Report</button>
</div>

<div id="pdfModal" class="modal">
  <div class="modal-content">
    <span class="close" onclick="closePDF()">&times;</span>
    <iframe id="pdfFrame" src=""></iframe>
  </div>
</div>

<style>
.milestone-links {
  display: flex;
  flex-direction: column;
  gap: 10px;
  margin: 15px 0;
}

.milestone-links button {
  width: fit-content;
  padding: 8px 14px;
  border: none;
  border-radius: 6px;
  background-color: #3f4a6b;
  color: white;
  font-size: 16px;
  cursor: pointer;
}

.milestone-links button:hover {
  background-color: #2f3854;
}

.modal {
  display: none;
  position: fixed;
  z-index: 9999;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  overflow: hidden;
  background-color: rgba(0, 0, 0, 0.65);
}

.modal-content {
  position: relative;
  background-color: white;
  margin: 3% auto;
  padding: 20px;
  width: 85%;
  height: 85%;
  border-radius: 8px;
}

.close {
  position: absolute;
  right: 18px;
  top: 8px;
  font-size: 32px;
  font-weight: bold;
  cursor: pointer;
  color: #333;
}

#pdfFrame {
  width: 100%;
  height: 95%;
  border: none;
}
</style>

<script>
function openPDF(pdfPath) {
  document.getElementById("pdfFrame").src = pdfPath;
  document.getElementById("pdfModal").style.display = "block";
}

function closePDF() {
  document.getElementById("pdfFrame").src = "";
  document.getElementById("pdfModal").style.display = "none";
}

window.onclick = function(event) {
  const modal = document.getElementById("pdfModal");
  if (event.target === modal) {
    closePDF();
  }
}
</script>

<h2>Project Poster</h2>

<img src="{{ site.baseurl }}/assets/images/SLFCrushersPoster.png" 
     alt="SLF Crushers Poster" 
     style="width: 500px; max-width: 100%; height: auto; display: block; margin: 20px auto;">
