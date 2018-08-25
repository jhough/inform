---
layout: page
title: Writing Archive
permalink: /writing/
---

<!--
  <h1 class="page-heading">Posts</h1>
-->


```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```


  <ul class="post-list">
    {% for post in site.posts %}
      <li>
        <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>
<!--
        <h2>
-->
          <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
          {{ post.excerpt }}
<!--
        </h2>
-->
      </li>
    {% endfor %}
  </ul>

