---
layout: page
title: projects
permalink: /projects/
description: Projects I am currently working on
nav: true
---

  <div class="projects-science">
  my scientific project<p></p>
  {% assign science_projects = site.projects | where:"category","science" %}
  {% for project in science_projects %}
        <div class="grid-item">
        {% if project.redirect %}
            <a href="{{ project.redirect }}" target="_blank">
        {% else %}
            <a href="{{ project.url | relative_url }}">
        {% endif %}
            <div class="card hoverable">
                {% if project.img %}
                    <img src="{{ project.img | relative_url }}" alt="project thumbnail">
                {% endif %}
                <div class="card-body">
                    <h2 class="card-title">{{ project.title }}</h2>
                    <p class="card-text">{{ project.description }}</p>
                </div>
            </div>
        </a>
        </div>
  {% endfor %}
  </div>

  <div class="projects-software">
  software I contribute to<p></p>
  (both programs are also used in the project above)<p></p>
  {% assign sorted_projects = site.projects | where:"category","software" %}
  {% for project in sorted_projects %}
  <div class="grid-item">
    {% if project.redirect %}
    <a href="{{ project.redirect }}" target="_blank">
    {% else %}
    <a href="{{ project.url | relative_url }}">
    {% endif %}
      <div class="card hoverable">
        {% if project.img %}
            <img src="{{ project.img | relative_url }}" alt="project thumbnail">
        {% endif %}
        <div class="card-body">
          <h2 class="card-title">{{ project.title }}</h2>
          <p class="card-text">{{ project.description }}</p>
          <div class="row ml-1 mr-1 p-0">
            {% if project.github %}
            <div class="github-icon">
              <div class="icon" data-toggle="tooltip" title="Code Repository">
                <a href="{{ project.github }}" target="_blank"><i class="fab fa-github gh-icon"></i></a>
              </div>
              {% if project.github_stars %}
              <span class="stars" data-toggle="tooltip" title="GitHub Stars">
                <i class="fas fa-star"></i>
                <span id="{{ project.github_stars }}-stars"></span>
              </span>
              {% endif %}
            </div>
            {% endif %}
            {% if project.gitlab %}
            <div class="gitlab-icon">
              <div class="icon" data-toggle="tooltip" title="Code Repository">
                <a href="{{ project.gitlab }}" target="_blank"><i class="fab fa-gitlab gl-icon"></i></a>
              </div>
            </div>
            {% endif %}
          </div>
        </div>
      </div>
    </a>
  </div>
{% endfor %}

</div>
