---
layout: layouts/post.liquid
author: cat_a_flame
date: Created
pageTitle: z-index hell
lead: "`z-index` is something that can measure one's frustration. The amount of digits represent the fact that the developer tried to position the `div` above the content, but failed miserably."
badcode: '.my-class {z-index: 122828282882;}'
goodcode: '.my-class {position: absolute; z-index: 2;}'
---

<div class="article-section">

{{ lead }}

## Bad example

```css
{{ badcode | prettyCSS | safe }}
```
</div>
<div class="article-section list-section">

## What is the problem and how to fix it

- `z-index` is only can be used with `absolute`, `fixed`, `relative` or `sticky` `positions`. In my example, this line is missing.
- `z-index` has a maximum value which is **2147483648**, the maximum positive value for a 32-bit signed binary integer in computing (the example has +2 integers).
- If you don't change anything on your content's z-axis value, adding 2 or 3 has the same effect as 100 or 10000. Adding huge numbers can lead to hard maintainability.
</div>

<div class="article-section">

## Good example

```css
{{ goodcode | prettyCSS | safe }}
```
</div>

<div class="article-section resources-section">

## Resources
- [z-index property on MND](https://developer.mozilla.org/en-US/docs/Web/CSS/z-index)
- [Understanding CSS z-index](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index)
- [2147483648 on Wikipedia](https://en.wikipedia.org/wiki/2,147,483,647#In_computing)
</div>