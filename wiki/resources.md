---
title: Resources of Website
feature_text: |
  ## iGEM HUST-China 2025
  Welcome to iGEM HUST-China 2025 wiki! It's still under construction. Please stay tuned for more information.
feature_image: "https://static.igem.wiki/teams/5175/test-resources/test-image-1300x400.jpg"
excerpt: "Welcome to iGEM HUST-China 2025 wiki! It's still under construction. Please stay tuned for more information."
permalink: /resources/
---

# Heading 1
我是Heading 1的内容
## Heading 2
我是Heading 2的内容
### Heading 3
我是Heading 3的内容
#### Heading 4
我是Heading 4的内容
##### Heading 5
我是Heading 5的内容
###### Heading 6

<small>A small element</small>

[A link](https://david.darn.es "A link")

Lorem ipsum dolor sit amet, consectetur adip* isicing elit, sed do eiusmod *tempor incididunt ut labore et dolore magna aliqua.

Duis aute irure dolor in [A link](https://david.darn.es "A link") reprehenderit in voluptate velit esse cillum **bold text** dolore eu fugiat nulla pariatur. Excepteur span element sint occaecat cupidatat non proident, sunt _italicised text_ in culpa qui officia deserunt mollit anim id `some code` est laborum.

* An item
* An item
* An item
* An item
* An item

1. Item one
2. Item two
3. Item three
4. Item four
5. Item five

> A simple blockquote

Some HTML...

``` html
<blockquote cite="http://www.imdb.com/title/tt0284978/quotes/qt1375101">
  <p>You planning a vacation, Mr. Sullivan?</p>
  <footer>
    <a href="http://www.imdb.com/title/tt0284978/quotes/qt1375101">Sunways Security Guard</a>
  </footer>
</blockquote>
```

...CSS...

``` css
blockquote {
  text-align: center;
  font-weight: bold;
}
blockquote footer {
  font-size: .8rem;
}
```

...and JavaScript

``` js
const blockquote = document.querySelector("blockquote")
const bolden = (keyString, string) =>
  string.replace(new RegExp(keyString, 'g'), '<strong>'+keyString+'</strong>')

blockquote.innerHTML = bolden("Mr. Sullivan", blockquote.innerHTML)
```

```
我是普通代码框
1
2
3
4
5
```

`Single line of code`

## HTML Includes

### Contact form

``` html
{% raw %}{% include site-form.html %}{% endraw %}
```

### Demo map embed

``` html
{% raw %}{% include map.html id="XXXXXX" title="Coffee shop map" %}{% endraw %}
```

### Button include


<!-- {% include button.html text="A button" link="https://david.darn.es" %}

{% include button.html text="A button with icon" link="https://twitter.com/daviddarnes" icon="twitter" %} -->

``` html
{% raw %}{% include button.html text="A button" link="https://david.darn.es" %}
{% include button.html text="A button with icon" link="https://twitter.com/daviddarnes" icon="twitter" %}{% endraw %}
```

### Icon include

``` html
{% raw %}{% include icon.html id="twitter" title="twitter" %}
[{% include icon.html id="linkedin" title="twitter" %}](https://www.linkedin.com/in/daviddarnes){% endraw %}
```

### Video include

``` html
{% raw %}{% include video.html title="Your Video title" url="iGEM Universe Video URL" caption="Your Video Caption" %}{% endraw %}
```

Copy the video URL from the iGEM Universe and paste it in the `url` attribute.

{% include figure.html image="https://static.igem.wiki/teams/5175/test-resources/video-upload-manual.png" caption="Manual of Uploading Videos" %}

### Image includes


``` html
{% raw %}{% include figure.html image="https://picsum.photos/600/800?image=894" caption="Image with caption" width="300" height="800" %}

{% include figure.html image="https://picsum.photos/600/800?image=894" caption="Right aligned image" position="right" width="300" height="800" %}

{% include figure.html image="https://picsum.photos/600/800?image=894" caption="Left aligned image" position="left" width="300" height="800" %}

{% include figure.html image="https://picsum.photos/1600/800?image=894" alt="Image with just alt text" %}{% endraw %}
```

#### Images with caption

Take styles in `Members` as example:

``` html
{% raw %}
{% include members.html %}

{% include members-people.html 
   name="Mualani" 
   description="One of the shining stars of the People of the Springs' new generation of young quides. If you've come to Natlan for sightseeing, there's no better companion you could choose." 
   image="https://fastcdn.hoyoverse.com/content-v2/hk4e/125394/15252d1fb7f5cb3b5f6441f507abfefd_638784673605744288.png" 
   image_position="left" %}

{% include members-people.html 
   name="Kinich" 
   description="A saurian hunter who accompanies the one who calls himself 'Dragonlord'. He often accepts commissions that no one else wants, and is equally skilled at appraising the price." 
   image="https://fastcdn.hoyoverse.com/content-v2/hk4e/125716/e0cfc13a904c1fc542924ae1e4d61da5_7486504169372511290.png" 
   image_position="right" %}
{% endraw %}
```

> Remember not to use "" in the `description` attribute.