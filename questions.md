---
layout: page
title: 'CF Icebreaker Questions'
permalink: /questions/
tags: [Ice Breaker, Icebreaker, Questions]
excerpt: Great questions designed to help people in small groups get to know one another. If you could live in any sitcom, which one would it be?
---

<h4>
Great questions designed to help people in small groups get to know one another.
</h4>

<ul>
{% for record in site.data.questions %}
  <li>
    {{ record.question }}
  </li>
{% endfor %}
</ul>

<p>
Editor, October 2008:<br>
I have disabled the Submit Question feature. Thanks for submitting all the great questions.
</p>

<p>
Editor, January 2016:<br>
This list has been available since 1998! (AKA Ice Breaker Questions.) I've updated the page using responsive design style so that the questions are easier to read on mobile devices.
</p>
