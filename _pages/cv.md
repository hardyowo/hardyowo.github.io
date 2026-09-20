---
layout: single
title: "CV"
permalink: /cv/
wide: true
redirect_from:
  - /resume
---

<div class="cv">
  <input type="radio" name="cv-lang" id="cv-en" class="cv__radio" checked>
  <input type="radio" name="cv-lang" id="cv-vi" class="cv__radio">
  <div class="cv__bar">
    <span class="cv__tabs">
      <label class="cv__tab cv__tab--en" for="cv-en">English</label>
      <label class="cv__tab cv__tab--vi" for="cv-vi">Tiếng Việt</label>
    </span>
    <span class="cv__dlwrap">
      <a class="cv__dl cv__dl--en" href="{{ '/files/CV_English.pdf' | relative_url }}" download><svg class="cv__dl-ic" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><path d="M12 4v11M8 11l4 4 4-4M5 20h14"/></svg><span>Download PDF</span></a>
      <a class="cv__dl cv__dl--vi" href="{{ '/files/CV_Vietnamese.pdf' | relative_url }}" download><svg class="cv__dl-ic" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><path d="M12 4v11M8 11l4 4 4-4M5 20h14"/></svg><span>Tải xuống PDF</span></a>
    </span>
  </div>
  <div class="cv__stack">
    <iframe class="cv__doc cv__doc--en" src="{{ '/files/CV_English.pdf' | relative_url }}" title="Curriculum Vitae (English version)"></iframe>
    <iframe class="cv__doc cv__doc--vi" src="{{ '/files/CV_Vietnamese.pdf' | relative_url }}" title="Sơ yếu lý lịch (Vietnamese version)"></iframe>
  </div>
</div>
