---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

Research
------
- Prevision.io: I am working on the European project AIDOaRT (AI-augmented automation for efficient DevOps, a model-based framework for continuous development At RunTime in cyber-physical systems). Among others, we will develop at Previon.io explainability models to explain the ML/AI models that will be developed by other project partners. In parallel with this research, I conduct internal research to improve the ML/AI models used by our Paas. In addition, I propose and implement new ideas for applications development. I have 1/5 day for the latter mission.
- Thesis: During my Ph.D. thesis on worked on the development of new clustering algorithms for categorical data. My work was motivated by real-world applications of the new methods on health data which are mostly categorical. We first proposed the categorical evidential c-means, a categorical extension of the evidential c-means. This method uses the Dempster-Shafer theory of evidence to handle uncertainty in data. Second, we proposed the categorical fuzzy entropy c-means which is an extension of the fuzzy k-modes that uses the fuzzy sets theory to model cluster prototypes. The new methods are published in peer-review international conferences.

Peer-reviewed publications
======

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}
