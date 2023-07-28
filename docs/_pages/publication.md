---
permalink: /publications/
author_profile: true
defaults:
  # _pages
  - scope:
      path: ""
      type: pages
    values:
      layout: single
      author_profile: true
---

<!-- ## Published Papers -->

<h2> Published Papers </h2>

<div class="pub-container">
  <strong>[1]</strong>
  <div class="pub-content">
      <h3>Development of a Reliable Method for General Aviation Flight Phase Identification</h3>

      <p><strong>Journal:</strong> IEEE Transactions on Intelligent Transportation Systems, Vol 23, No. 8, Page 11729-11738, Aug 2022</p>

      <p><strong>Authors:</strong> Qilei Zhang, John H. Mott, Mary E. Johnson, John A. Springer</p>

      <p><strong>Notes:</strong> <a href="https://polytechnic.purdue.edu/newsroom/identifying-flight-phase-times-predict-harmful-emissions-noise-pollution">Links to Media Coverage</a></p>

      <a href="https://doi.org/10.1109/TITS.2021.3106774"><button class="pdf-button">PDF</button></a>
      <button class="pdf-button collapsible">Abstract</button>
      <div class="content">
        <p>Abstract content goes here...</p>
      </div>
  </div>
  <div class="pub-image">
      <img src="/assets/images/publication1.png" alt="Publication Image">
  </div>
</div>

<div class="pub-container">
  <strong>[2]</strong>
  <div class="pub-content">
      
      <h3>Development of a Reliable Method for General Aviation Flight Phase Identification</h3>

      <p><strong>Journal:</strong> IEEE Transactions on Intelligent Transportation Systems, Vol 23, No. 8, Page 11729-11738, Aug 2022</p>

      <p><strong>Authors:</strong> Qilei Zhang, John H. Mott, Mary E. Johnson, John A. Springer</p>

      <p><strong>Notes:</strong> <a href="https://polytechnic.purdue.edu/newsroom/identifying-flight-phase-times-predict-harmful-emissions-noise-pollution">Links to Media Coverage</a></p>

      <a href="https://doi.org/10.1109/TITS.2021.3106774"><button class="pdf-button">PDF</button></a>
      <button class="pdf-button collapsible">Abstract</button>
      <div class="content">
        <p>Abstract content goes here...</p>
      </div>
  </div>
  <div class="pub-image">
      <img src="/assets/images/publication1.png" alt="Publication Image">
  </div>
</div>


<script>
var coll = document.getElementsByClassName("collapsible");
var i;

for (i = 0; i < coll.length; i++) {
  coll[i].addEventListener("click", function() {
    this.classList.toggle("active");
    var content = this.nextElementSibling;
    if (content.style.display === "none") {
      content.style.display = "block";
    } else {
      content.style.display = "none";
    }
  });
}
</script>
