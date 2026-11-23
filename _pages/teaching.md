---
layout: page
title: teaching
permalink: /teaching/
description: Teaching philosophy, experience, and courses taught.
nav: true
nav_order: 6
display_categories: [Undergraduate, Graduate]
horizontal: false
---

<!-- Teaching Philosophy Stylesheet -->
<link rel="stylesheet" href="/assets/css/teaching-philosophy.css">

<!-- ======================================================
     TEACHING PHILOSOPHY
     ====================================================== -->

<section class="teaching-philosophy" aria-labelledby="teaching-philosophy-title">

  <!-- Introduction -->
  <div class="philosophy-hero">

    <div class="philosophy-eyebrow">
      <i class="fa-solid fa-graduation-cap"></i>
      MY TEACHING PHILOSOPHY
    </div>

    <h2 id="teaching-philosophy-title">
      Teaching for Understanding, Independence, and Responsibility
    </h2>

    <p>
      I believe teaching is more than transferring knowledge.
      My goal is to help students develop strong conceptual
      foundations, practical judgment, intellectual curiosity,
      and the confidence to learn independently.
      I strive to create a supportive and inclusive environment
      where students feel comfortable asking questions,
      challenging assumptions, and applying their knowledge
      to meaningful problems.
    </p>

    <div class="philosophy-quote">
      <i class="fa-solid fa-quote-left"></i>
      <span>
        AI should accelerate learning, not replace it.
      </span>
    </div>

  </div>

  <!-- Teaching Principles -->
  <div class="philosophy-principles">

    <div class="philosophy-card">
      <div class="philosophy-icon">
        <i class="fa-solid fa-brain"></i>
      </div>

      <h3>Conceptual Understanding</h3>

      <p>
        I connect abstract concepts to concrete examples,
        realistic scenarios, and practical applications,
        emphasizing why and when a solution works
        rather than memorization alone.
      </p>
    </div>

    <div class="philosophy-card">
      <div class="philosophy-icon">
        <i class="fa-solid fa-comments"></i>
      </div>

      <h3>Active Learning and Reasoning</h3>

      <p>
        Through questions, discussions, and problem-solving
        activities, I encourage students to evaluate alternatives,
        justify decisions, and understand technical trade-offs.
      </p>
    </div>

    <div class="philosophy-card">
      <div class="philosophy-icon">
        <i class="fa-solid fa-handshake"></i>
      </div>

      <h3>Inclusive Learning and Mentorship</h3>

      <p>
        I aim to create a respectful environment where students
        with different backgrounds and experiences feel
        supported, valued, and confident seeking guidance.
      </p>
    </div>

    <div class="philosophy-card">
      <div class="philosophy-icon">
        <i class="fa-solid fa-arrows-rotate"></i>
      </div>

      <h3>Reflection and Continuous Improvement</h3>

      <p>
        I use student feedback, classroom experiences,
        formative assessments, and self-reflection
        to continually refine my teaching approaches
        and learning activities.
      </p>
    </div>

  </div>

  <!-- Responsible AI -->
  <div class="philosophy-ai">

    <div class="philosophy-ai-icon">
      <i class="fa-solid fa-robot"></i>
    </div>

    <div>
      <h3>Preparing Students for an AI-Assisted Future</h3>

      <p>
        I encourage students to use emerging AI tools
        critically and responsibly, without sacrificing
        independent reasoning or foundational knowledge.
        Students should first understand the problem,
        attempt solutions themselves, use AI selectively
        for support, and remain able to explain and
        evaluate their decisions.
      </p>
    </div>

  </div>

</section>

<!-- ======================================================
     COURSES TAUGHT
     ====================================================== -->

<h2 style="margin-top: 45px; margin-bottom: 10px;">
  <i class="fa-solid fa-book-open"
     style="color: var(--global-theme-color); margin-right: 8px;"></i>
  Courses Taught
</h2>

<p style="margin-bottom: 25px;">
  Selected undergraduate and graduate courses that I have taught,
  with details about course content, teaching approaches,
  assessment, and student learning experiences.
</p>

<!-- Original al-folio Teaching Collection -->
<div class="projects">

{% if site.enable_project_categories and page.display_categories %}

  <!-- Display categorized teaching -->
  {% for category in page.display_categories %}

    {% assign categorized_teaching = site.teaching | where: "category", category %}
    {% assign sorted_teaching = categorized_teaching | sort: "importance" %}

    {% if sorted_teaching.size > 0 %}

      <a id="{{ category }}" href="#{{ category }}">
        <h2 class="category">{{ category }}</h2>
      </a>

      {% if page.horizontal %}

        <div class="container">
          <div class="row row-cols-1 row-cols-md-2">
            {% for project in sorted_teaching %}
              {% include teaching_horizontal.liquid %}
            {% endfor %}
          </div>
        </div>

      {% else %}

        <div class="row row-cols-1 row-cols-md-3">
          {% for project in sorted_teaching %}
            {% include teaching.liquid %}
          {% endfor %}
        </div>

      {% endif %}

    {% endif %}

  {% endfor %}

{% else %}

  <!-- Display teaching without categories -->
  {% assign sorted_teaching = site.teaching | sort: "importance" %}

  {% if page.horizontal %}

    <div class="container">
      <div class="row row-cols-1 row-cols-md-2">
        {% for project in sorted_teaching %}
          {% include teaching_horizontal.liquid %}
        {% endfor %}
      </div>
    </div>

  {% else %}

    <div class="row row-cols-1 row-cols-md-3">
      {% for project in sorted_teaching %}
        {% include teaching.liquid %}
      {% endfor %}
    </div>

  {% endif %}

{% endif %}

</div>
