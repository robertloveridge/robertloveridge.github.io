---
layout: default
title: {{ site.name }}
---

<img src="../img/robert-loveridge.png" alt="Robert Loveridge" style="border-radius: 50%; width: 30%; float:left; margin: 20px;">

I am currently working for <a href="https://www.phocassoftware.com/">Phocas Software</a> as the **Customer Support Manager in EMEA**. I have many years of experience in Customer Support, Professional Serivces, Solution Design, Product Management, Software Development and line management of multiple teams.

I have worked for <a href="https://www.gainsight.com/">Gainsight</a>, The Customer Success Company as a Solutions Architect and prior to working at Gainsight, I was the **Head of Services at Upland Software** where I managed the department in EMEA from our Coventry office. My department had 5 teams (19 people in total) and I reported to the General Manager EMEA.

In a previous role (Product Management Team Lead) at <a href="https://uplandsoftware.com/adestra">Adestra</a>, I worked with the Head of Product Management and COO on the product roadmap, facilitating meetings with the commercial teams every month so they were kept up-to-date on the progress.

At Upland, my team had **revenue targets** to meet and my main focus was making sure that the projects we were managing were delivered on time and on budget. I acted as an escalation point for all clients who interacted with the team.

I have a **software development background** using Perl programming language and PostgreSQL database, Git and Subversion for Version Control, JIRA, Confluence and BitBucket for development framework and sprint planning.

When Upland Software acquired Adestra and <a href="https://uplandsoftware.com/rantandrave/">Rant & Rave</a>, I was involved in the employee consultations, so I have first hand experience with detailing out organisational changes in a sensitive manner.

I'm highly experienced in developing **custom reporting** and **data integrations**, having worked with many organisations on delivering technical solutions to real business challenges and goals.

I **enjoy mentoring**, problem solving and motivating myself, which I feel plays a key part in learning programming languages and creating bespoke solutions.

Having received **positive feedback** from Adestra's Leadership team and being seen as a reference point by other senior managers and colleagues across the organisation, I was voted Adestra's **employee of the year** in 2007, 2014, 2015, 2017 and 2018.


<!--div id="home">
  <h2>See my latest post...</h2>

  {% assign post = site.posts.first %}
  {% if post.title %}
      <a href="{{ site.url }}{{ post.url }}" title="Internal link to my blog post: {{ post.title }}">{{ post.title }}</a> posted on <span class="entry-date"><time datetime="{{ post.date | date_to_xmlschema }}" itemprop="datePublished"><strong>{{ post.date | date: "%B %d, %Y" }}</strong></time></span>
  {% endif %}

  <h2>Categories</h2>
  <ul>
  {% assign categories_list = site.categories %}
    {% if categories_list.first[0] == null %}
      {% for category in categories_list %}
        <li><a href="#{{ category }}">{{ category | capitalize }} ({{ site.tags[category].size }})</a></li>
      {% endfor %}
    {% else %}
      {% for category in categories_list %}
        <li><a href="#{{ category[0] }}">{{ category[0] | capitalize }} ({{ category[1].size }})</a></li>
      {% endfor %}
    {% endif %}
  {% assign categories_list = nil %}
  </ul>

  {% for tag in site.categories %}
    <h3 id="{{ tag[0] }}">{{ tag[0] | capitalize }}</h3>
    <ul>
      {% assign pages_list = tag[1] %}
      {% for post in pages_list %}
        {% if post.title != null %}
        {% if group == null or group == post.group %}
        <li><span class="entry-date"><time datetime="{{ post.date | date_to_xmlschema }}" itemprop="datePublished">{{ post.date | date: "%B %d, %Y" }}</time></span> - <a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
        {% endif %}
        {% endif %}
      {% endfor %}
      {% assign pages_list = nil %}
      {% assign group = nil %}
    </ul>
  {% endfor %}

</div-->
