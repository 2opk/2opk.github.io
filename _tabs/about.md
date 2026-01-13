---
# the default layout is 'page'
icon: fas fa-user
order: 1
---

<div class="about-container">
  {% capture bio_content %}
    {{ site.data.about.bio | markdownify }}
  {% endcapture %}
  {% include about/section.html title="About Me" icon="fas fa-user-graduate" content=bio_content %}

  {% capture research_content %}
    <ul class="skill-list" style="list-style: none; padding: 0;">
      <li><strong>DL Compilers & Systems</strong>: TVM, MLIR, LLVM</li>
      <li><strong>Heterogeneous Computing</strong>: CUDA, PIM, Edge AI</li>
      <li><strong>System Optimization</strong>: Memory hierarchy, tensor program autotuning</li>
    </ul>
  {% endcapture %}
  {% include about/section.html title="Research Interests" icon="fas fa-search" content=research_content %}

  {% capture pub_content %}
    {% for pub in site.data.about.publications %}
    <div class="publication-item">
      <h3 class="pub-title">{{ pub.title }}</h3>
      <p class="pub-authors">{{ pub.authors }}</p>
      <p class="pub-venue"><em>{{ pub.venue }}</em></p>
    </div>
    {% endfor %}
  {% endcapture %}
  {% include about/section.html title="Publications" icon="fas fa-book" content=pub_content %}

  {% capture edu_content %}
    {% include about/education.html %}
  {% endcapture %}
  {% include about/section.html title="Education" icon="fas fa-graduation-cap" content=edu_content %}

  {% capture career_content %}
    {% include about/careers.html %}
  {% endcapture %}
  {% include about/section.html title="Career" icon="fas fa-briefcase" content=career_content %}

  {% capture skill_content %}
    {% include about/skills.html %}
  {% endcapture %}
  {% include about/section.html title="Skills" icon="fas fa-tools" content=skill_content %}

  {% capture project_content %}
    {% include about/projects.html %}
  {% endcapture %}
  {% include about/section.html title="Projects & Experiences" icon="fas fa-project-diagram" content=project_content %}
</div>
