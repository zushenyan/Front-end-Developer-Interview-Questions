---
title: CSS Questions
layout: layouts/page.njk
permalink: /questions/css-questions/index.html
---

# What is CSS selector specificity and how does it work?

It's a priority mechanism that lets the browser to decide which element that should be styled. For example, the priority is listed in descended:

1. `!important`
2. `#` for id
3. `.foobar`, `:hover`, `[type="aaa"]` class or psuedo class selector
4. `h1` type selector

# What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why?

`resetting` removes all the browser built-in styles.
`normalizing` makes all the browser built-in styles stay consistent.
Normally I would use `normalizing` because I don't want to "re-style" styles again.

# Describe Floats and how they work.

This property places an element on the right or left of its container. The element will be removed from the normal flow and make the surrounding text wrap around it. A way to remove the wrapping feature is to do clearfix with `clear: both` in the next element.

# Describe z-index and how stacking context is formed.

It's an attribute to put an element before or after other elements. There is a caveat which is elements with different `display` mode will be put in different `z-index` collection.

# Describe BFC (Block Formatting Context) and how it works.

BFC is a context that follows block layout rules. Except for the outmost `html` tag as the initial BFC, deveopers can create an new BFC with CSS rules below:

1. `position: aboslute`
2. `display: inline-block`
3. `float: right` or `float: left`
4. and so on.

# What are the various clearing techniques and which is appropriate for what context?

1. `clear: both`
2. `overflow: auto` or `overflow: hidden`

# How would you approach fixing browser-specific styling issues?

One way is to use JS to detect browser and make related change. The other way is to use browser specific prefix to fix that.

# How do you serve your pages for feature-constrained browsers? What techniques/processes do you use?

Progressive enhancement or graceful degradation. With these approaches we can cover most platforms without abandoning.

# What are the different ways to visually hide content (and make it available only for screen readers)?

1. `display: none`
2. `visible: hidden`
3. `opacity: 0`

# Have you ever used a grid system, and if so, what do you prefer?

Yes, this makes layouting much more flexible. If we don't consider IE 11 then this is something modern front-end developers should consider.

# Have you used or implemented media queries or mobile specific layouts/CSS?

Yes. You will have to define the device boundary with media queries `@media screen (max-width: 600px)` to make you application responsive.

# Are you familiar with styling SVG?

I've tried several times because of business requirement.

# Can you give an example of an `@media` property other than `screen`?

1. `all` for all devices.
2. `print` for printer.
3. `speech` for screen reader.

# What are some of the "gotchas" for writing efficient CSS?

1. long selector chain will slow the performance down.
2. some CSS properties may trigger repaint.

# What are the advantages/disadvantages of using CSS preprocessors? Describe what you like and dislike about the CSS preprocessors you have used.

Pros:

1. Some preprocessors provide extra syntaxes to make the code shorter.
2. Some of them would automatically add browser prefix to properties.
3. Some will resolve the naming conflict by creating namespace or adding hash to your classes.

Cons:

1. Developers will have to learn new syntaxes.
2. Extra overhead to be maintained as new tool is introduced.

# How would you implement a web design comp that uses non-standard fonts?

Use `@font-face` or use font service link like Google Fonts.

# Explain how a browser determines what elements match a CSS selector.

There are 4 types of selectors and the priority is listed in the following order:

1. `#` id selector
2. `.foobar`, `:hover`, `[type=audio]` class and pseudo class selector
3. `h1` type selector

And combinators:

1. ` ` space for descendant
2. `>` child selector
3. `+` adjacent sibling selector
4. `~` general sibling selector

The browser will start searching matched selectors from top to down, parent to children elements and apply styles to them.

# Describe pseudo-elements and discuss what they are used for.

`:after` and `:before` are the common psuedo-elements, they will act as a part of their host element. Usually they will be used as a decoration to their host if developers don't want to create additional elements.

# Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in different box models.

Box model consists of its content, `padding`, `border` and `margin`. The order is from inside to outside. It acts like a box so it is called "box model." If we want to change the display mode we cant do `box-sizing: border-box` or `box-sizing: content-box`.

# What does `* { box-sizing: border-box; }` do? What are its advantages?

To include `border` as a part of `width` and `height`.

# What is the CSS `display` property and can you give a few examples of its use?

1. `display: none` for not rendering the element.
2. `display: block` to most common way to display elements.
3. `display: inline` to make the element flow as text.
4. `display: flex` enable flexbox layout.

# What's the difference between inline and inline-block?

`inline-block` will make an line break and layout the following element in the next line, however, `inline` will not have this behaviour.

# What's the difference between the "nth-of-type()" and "nth-child()" selectors?

`nth-of-type` it matches elements of given type. For example `p:nth-of-type(4n)` will only match for every 4 of `p`
`nth-child` it matches elements of given number, regardless its type. Fro example `p:nth-child(4n)` will match every 4 element of its descendant inside.

# What's the difference between a relative, fixed, absolute and statically positioned element?

1. `position: static` The element will be positioned normally according to the flow of document. `top`, `right`, `left`, `bottom` and `z-index` will have no effect.
2. `position: relative` Pretty much the same as `static` but now `top`, `right`, `left`, `bottom` and `z-index` take effect, and it will offset according to its parent.
3. `posiiton: absolute` The element doesn't follow the normal flow of document and its position will be based on the nearest ancestor that is set to `relative`.
4. `position: fixed` The element will be positioned according to the viewport instead of document.

# What existing CSS frameworks have you used locally, or in production? How would you change/improve them?

# Have you used CSS Grid?

# Can you explain the difference between coding a web site to be responsive versus using a mobile-first strategy?

The only difference is what kind of device you want to support at initial. It's either writing the media query, feature for desktop or mobile first. According to my experience, I don't feel many difference.

# Have you ever worked with retina graphics? If so, when and what techniques did you use?

One of the possible problem we might face is the image is not high resolition enough. To resolve this, we can either use `media` with `device-pixel-ratio` to decide what we are going to show or use `srcset` to load the best resolution for a specific resolution.

# Is there any reason you'd want to use `translate()` instead of _absolute positioning_, or vice-versa? And why?

Only when I want to shift an element without changing the `position` to `absolute`. When we are animating elements, it is very common to use `translate` instead.

# How is clearfix css property useful?

Only when we are working with elements with `float`, otherwise clearfix is not common in modern frontend development.

# Can you explain the difference between px, em and rem as they relate to font sizing?

`px` acts as an absolute unit for font size.
`em` means to change the size according to its nearest ancestor.
`rem` means to change the size according to its document.

# Can you give an example of a pseudo class? Can you provide an example use case for a pseudo class?

`:hover` when you want to change the style while mouse hovering.

# What is the difference between a block level element and an inline element. Can you provide examples of each type of element?

`block` elements by default will be placed on the new line. `inline` elements, on the other hand, will be placed on the same line.

For example

```
<div>aaa</div>
<span>bbb</span>
<span>ccc</span>
<div>ddd</div>
```

Will be displayed as

```
aaa
bbb ccc
ddd
```
