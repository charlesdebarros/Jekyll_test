---
layout: home
title: Blog
permalink: /blog/
---

<section class="blog_section layout_padding">
  <div class="container">
    <div class="heading_container">
      <h2>
        Latest Blog Entries
      </h2>
    </div>
    <div class="row">
      {%- for post in site.posts -%}
      <div class="col-md-6 col-lg-4 mx-auto">
        <div class="box">
          <div class="img-box">
            <!-- If customer.name = "anonymous" -->
            {% if post.image %}
            <img src="{{ post.image }}" alt="">
            {% endif %}
            {% if post.background %}
            <img src="{{ post.background }}" />
            {% endif %}
          </div>
          <div class="detail-box">
            <h5>
              {{ post.title }}
            </h5>
            <p>
              {{ post.content | markdownify | strip_html | truncatewords: 10 }}
            </p>
            <a href="{{ post.url }}">
              Read More
            </a>
          </div>
        </div>
      </div>
      {%- endfor -%}
    </div>
    {% include paginator.html %}
  </div>
</section>