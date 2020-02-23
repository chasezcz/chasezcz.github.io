---
layout: page
title: About
description: 生命不息，奋斗不止
keywords: Chase Zhang, Chengze Zhang, 张成泽
comments: true
menu: 关于
permalink: /about/
---

我是张成泽，热爱科技，坚信代码可以改变世界。

大道三千，我择于此。

Believe in Science, Respect gods.

## 联系

{% for website in site.data.social %}
* {{ website.sitename }}：[@{{ website.name }}]({{ website.url }})
{% endfor %}

* Email: chengze1996@gmail.com

## Skill Keywords

{% for category in site.data.skills %}
### {{ category.name }}
<div class="btn-inline">
{% for keyword in category.keywords %}
<button class="btn btn-outline" type="button">{{ keyword }}</button>
{% endfor %}
</div>
{% endfor %}
