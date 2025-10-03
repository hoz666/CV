---
layout: archive
title: "Curriculum Vitae"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

<style>
/* Collapsible section styles */
.collapsible {
  background-color: #f8f9fa;
  color: #2c3e50;
  cursor: pointer;
  padding: 18px;
  width: 100%;
  border: none;
  text-align: left;
  outline: none;
  font-size: 1.1em;
  font-weight: 600;
  margin-top: 10px;
  border-radius: 5px;
  transition: 0.3s;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.collapsible:hover {
  background-color: #e9ecef;
}

.collapsible:after {
  content: '\002B';
  font-size: 1.3em;
  float: right;
}

.collapsible.active:after {
  content: "\2212";
}

.cv-content {
  padding: 0 18px;
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.3s ease-out;
  background-color: #ffffff;
}

.cv-content.show {
  padding: 18px;
  border-left: 3px solid #1a6ba8;
  margin-bottom: 15px;
}

/* Dark mode */
@media (prefers-color-scheme: dark) {
  .collapsible {
    background-color: rgba(255,255,255,0.05);
    color: #ffffff;
  }
  
  .collapsible:hover {
    background-color: rgba(255,255,255,0.1);
  }
  
  .cv-content {
    background-color: transparent;
  }
  
  .cv-content.show {
    border-left-color: #ffffff;
  }
}

.cv-item {
  margin-bottom: 1em;
  line-height: 1.6;
}

.cv-year {
  font-weight: 600;
  color: #1a6ba8;
}

@media (prefers-color-scheme: dark) {
  .cv-year {
    color: #ffffff;
  }
}
</style>

## Dr. Caterina Valeo, P.Eng.

**Professor, Mechanical Engineering**  
University of Victoria  
📧 valeo@uvic.ca

---

<button class="collapsible">Education</button>
<div class="cv-content">
  <div class="cv-item">
    <span class="cv-year">1998</span> • <strong>Ph.D.</strong> in Civil Engineering, McMaster University
  </div>
  <div class="cv-item">
    <span class="cv-year">1994</span> • <strong>M.Eng. (Thesis)</strong> in Civil Engineering, McMaster University
  </div>
  <div class="cv-item">
    <span class="cv-year">1992</span> • <strong>B.A.Sc.</strong> in Civil Engineering, University of Toronto
  </div>
  <div class="cv-item">
    <span class="cv-year">1990</span> • <strong>B.Sc.</strong> in Physics, University of Toronto
  </div>
</div>

<button class="collapsible">Work Experience</button>
<div class="cv-content">
  <div class="cv-item">
    <span class="cv-year">July 2015 - Present</span><br>
    <strong>Professor</strong>, Mechanical Engineering, University of Victoria<br>
    <em>Research focus: Environmental Informatics and Urban Water Resources Engineering</em>
  </div>
  <div class="cv-item">
    <span class="cv-year">December 2011 - Present</span><br>
    <strong>Adjunct Professor</strong>, Civil Engineering, University of Calgary
  </div>
  <div class="cv-item">
    <span class="cv-year">October 2011 - June 2015</span><br>
    <strong>Associate Professor</strong>, Mechanical Engineering, University of Victoria
  </div>
  <div class="cv-item">
    <span class="cv-year">July 2010 - September 2011</span><br>
    <strong>Professor</strong>, Civil Engineering, University of Calgary
  </div>
  <div class="cv-item">
    <span class="cv-year">2007 - July 2010</span><br>
    <strong>Associate Professor</strong>, Civil Engineering, University of Calgary
  </div>
  <div class="cv-item">
    <span class="cv-year">2003 - 2007</span><br>
    <strong>Associate Professor</strong>, Geomatics Engineering, University of Calgary
  </div>
  <div class="cv-item">
    <span class="cv-year">2000 - 2003</span><br>
    <strong>Assistant Professor</strong>, Geomatics Engineering, University of Calgary
  </div>
  <div class="cv-item">
    <span class="cv-year">1998 - 2000</span><br>
    <strong>Assistant Professor</strong>, Civil and Geological Engineering, University of Manitoba
  </div>
</div>

<button class="collapsible">Research Areas</button>
<div class="cv-content">
  <h3>🌊 Sustainable Development of Urban Water Resources</h3>
  <ul>
    <li>Low impact development (permeable pavements, bioretention cells)</li>
    <li>Stormwater management in Canadian climates</li>
    <li>Urban hydrology modeling</li>
  </ul>

  <h3>💧 Water Quality Modelling</h3>
  <ul>
    <li>Well water contamination assessment</li>
    <li>River and nearshore water quality</li>
    <li>Microbial contamination in water bodies</li>
  </ul>

  <h3>🛰️ Geomatics Technology</h3>
  <ul>
    <li>Remote sensing applications</li>
    <li>GIS tools for environmental modeling</li>
    <li>Snow cover and forest regeneration modeling</li>
  </ul>
</div>

<button class="collapsible">Skills & Expertise</button>
<div class="cv-content">
  <ul>
    <li>Environmental Informatics</li>
    <li>Hydrological Modeling</li>
    <li>Water Resources Engineering</li>
    <li>Remote Sensing & GIS</li>
    <li>Computational Fluid Dynamics</li>
  </ul>
</div>

<script>
// JavaScript for collapsible sections
var coll = document.getElementsByClassName("collapsible");
var i;

for (i = 0; i < coll.length; i++) {
  coll[i].addEventListener("click", function() {
    this.classList.toggle("active");
    var content = this.nextElementSibling;
    if (content.style.maxHeight){
      content.style.maxHeight = null;
      content.classList.remove("show");
    } else {
      content.style.maxHeight = content.scrollHeight + "px";
      content.classList.add("show");
    } 
  });
}
</script>

---

<div style="text-align: center; margin-top: 2em; padding: 1em; background: rgba(26, 107, 168, 0.05); border-radius: 5px;">
  <p><strong>📄 Full CV with complete publication list available upon request</strong></p>
  <p>For more details, visit my <a href="https://www.researchgate.net/profile/Caterina_Valeo">ResearchGate</a> or <a href="https://scholar.google.com/citations?user=eKd8-iEAAAAJ">Google Scholar</a> profile</p>
  <p>Contact: <a href="mailto:valeo@uvic.ca">valeo@uvic.ca</a></p>
</div>

* Field and Laboratory Research

Teaching
======
* **MECH 601**: Advanced Topics in Fluid Mechanics (Graduate)
  * University of Victoria
  * Topics: Turbulence modeling, CFD, environmental fluid mechanics
  
* **MECH 345**: Fluid Mechanics II (Undergraduate)
  * University of Victoria
  * Topics: Compressible flow, pipe networks, open channel hydraulics
  
* **Environmental Informatics & Urban Water Resources** (Special Topics)
  * University of Victoria
  * Integration of IT, environmental science, and engineering for sustainable water management
  
* **Stormwater Management & Low Impact Development** (Graduate Seminar)
  * University of Victoria
  * Focus on LID technologies and green infrastructure for Canadian climates

Publications
======
  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
Selected Graduate Student Supervision
======
* 15+ PhD students graduated
* 20+ Master's students graduated
* Research areas: urban water resources, water quality, environmental modeling, geomatics

Professional Designation
======
* Professional Engineer (PEng)
======
  <ul>{% for post in site.talks reversed %}
    {% include archive-single-talk-cv.html  %}
  {% endfor %}</ul>
  
Teaching
======
  <ul>{% for post in site.teaching reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
Service and leadership
======
* Currently signed in to 43 different slack teams
