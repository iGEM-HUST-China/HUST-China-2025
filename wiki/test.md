---
title: Test Page
feature_text: |
  ## Test Page
  Welcome to iGEM HUST-China 2025 wiki! It's still under construction. Please stay tuned for more information.
feature_image: "https://static.igem.wiki/teams/5175/test-resources/test-image-1300x400.jpg"
excerpt: "Welcome to iGEM HUST-China 2025 wiki! It's still under construction. Please stay tuned for more information."
permalink: /test/

# Multiple Figures
images01:
  - src: https://static.igem.wiki/teams/5175/test-resources/test-pic-left.jpeg
    alt: Yunli
    caption: Yunli
  - src: https://static.igem.wiki/teams/5175/test-resources/test-pic-middle.jpeg
    alt: High-Cloud Quintet
    caption: High-Cloud Quintet
  - src: https://static.igem.wiki/teams/5175/test-resources/test-pic-right.jpeg
    alt: March 7th
    caption: March 7th

images02:
  - src: https://static.igem.wiki/teams/5175/test-resources/test-pic-left.jpeg
    alt: Yunli
    caption: Yunli
  - src: https://static.igem.wiki/teams/5175/test-resources/test-pic-right.jpeg
    alt: March 7th
    caption: March 7th
---

> **Warning:** This is a test page. Please ignore it.

## Pictures embedded in the page

### Single

{% include figure.html image="https://static.igem.wiki/teams/5175/test-resources/test-pic-center.jpeg" alt="March 7th" caption="March 7th" %}

{% include figure.html image="https://static.igem.wiki/teams/5175/test-resources/test-pic-center.jpeg" alt="March 7th" caption="March 7th" %}

### Multiple

#### Left, Middle, Right

{% include figure3.html images=page.images01 %}

#### Left, Right

{% include figure2.html images=page.images02 %}

## Buttons

{% include button.html link="../" text="Go back to Home Page" %}

{% include button.html link="../resources/" text="Go to Resources Page" %}

## MathJax

### Inline Math

The formula $E=mc^2$ is well-known.

### Pseudo-Block Math

<center>$\int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}$</center>

### Block Math
<center>
  $$
  \begin{aligned}
  \int_{-\infty}^{\infty} e^{-x^2} dx &= \sqrt{\pi} \\
  \sum_{i=1}^{n} i &= \frac{n(n+1)}{2}
  \end{aligned}
  $$
</center>

---

<center>
   $$
    \left\{
      \begin{aligned}
      \int_{-\infty}^{\infty} e^{-x^2} dx &= \sqrt{\pi} \\
      \sum_{i=1}^{n} i &= \frac{n(n+1)}{2}
      \end{aligned}
    \right.
    $$
</center>

## Table

其它文字112

<figcaption class="caption table_caption">Test table1</figcaption>

| 被代替/很少使用的标签 | 说明                             |
| --------------------- | -------------------------------- |
| dir                   | 定义目录列表，应用ul代替         |
| acronym               | 定义首字母缩写，应用abbr代替     |
| applet                | 定义嵌入的applet,应用object代替  |
| isindex               | 定义与文档相关的可搜索索引       |
| frame                 | 定义frameset中的一个特定的框架   |
| frameset              | 定义一个框架集                   |
| noframes              | 为那些不支持框架的浏览器显示文本 |

其它文字123

<figcaption class="caption table_caption">Test table2</figcaption>

| 被代替/很少使用的标签 | 说明                             |
| --------------------- | -------------------------------- |
| dir                   | 定义目录列表，应用ul代替         |
| acronym               | 定义首字母缩写，应用abbr代替     |
| frame                 | 定义frameset中的一个特定的框架   |
| frameset              | 定义一个框架集                   |
| noframes              | 为那些不支持框架的浏览器显示文本 |

其它文字234

<center>
  <iframe title="Grand Jamboree 2024 | Keynotes" width="560" height="315" src="https://video.igem.org/video-playlists/embed/rC8gBRRXYLypxdqne7JgH6" allow="fullscreen" sandbox="allow-same-origin allow-scripts allow-popups allow-forms" style="border: 0px;"></iframe>
</center>

## Members

{% include members.html %}


{% include members-people.html 
   name="Mualani" 
   description="One of the shining stars of the People of the Springs' new generation of young quides. If you've come to Natlan for sightseeing, there's no better companion you could choose." 
   image="https://fastcdn.hoyoverse.com/content-v2/hk4e/125394/15252d1fb7f5cb3b5f6441f507abfefd_638784673605744288.png" 
   image_position="left" %}

{% include members-people.html 
   name="Kinich"
   description="A saurian hunter who accompanies the one who calls himself Dragonlord. He often accepts commissions that no one else wants, and is equally skilled at appraising the price." 
   image="https://fastcdn.hoyoverse.com/content-v2/hk4e/125716/e0cfc13a904c1fc542924ae1e4d61da5_7486504169372511290.png" 
   image_position="right" %}
