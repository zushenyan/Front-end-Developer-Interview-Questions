---
title: CSS Questions
layout: layouts/page.njk
permalink: /questions/css-questions/index.html
---

- What is CSS selector specificity and how does it work?

It's a priority mechanism that lets the browser to decide which element that should be styled. For example, the priority is listed in descended:

1. `!important`
2. `#` for id
3. `.foobar`, `:hover`, `[type="aaa"]` class or psuedo class selector
4. `h1` type selector

- What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why?

`resetting` removes all the browser built-in styles.
`normalizing` makes all the browser built-in styles stay consistent.
Normally I would use `normalizing` because I don't want to "re-style" styles again.

- Describe Floats and how they work.

This property places an element on the right or left of its container. The element will be removed from the normal flow and make the surrounding text wrap around it. A way to remove the wrapping feature is to do clearfix with `clear: both` in the next element.

- Describe z-index and how stacking context is formed.

It's an attribute to put an element before or after other elements. There is a caveat which is elements with different `display` mode will be put in different `z-index` collection.

- Describe BFC (Block Formatting Context) and how it works.

BFC is a context that follows block layout rules. Except for the outmost `html` tag as the initial BFC, deveopers can create an new BFC with CSS rules below:

1. `position: aboslute`
2. `display: inline-block`
3. `float: right` or `float: left`
4. and so on.

- What are the various clearing techniques and which is appropriate for what context?

1. `clear: both`
2. `overflow: auto` or `overflow: hidden`

- How would you approach fixing browser-specific styling issues?

One way is to use JS to detect browser and make related change. The other way is to use browser specific prefix to fix that.

- How do you serve your pages for feature-constrained browsers?
  - What techniques/processes do you use?

Progressive enhancement or graceful degradation. With these approaches we can cover most platforms without abandoning.

- What are the different ways to visually hide content (and make it available only for screen readers)?

1. `display: none`
2. `visible: hidden`
3. `opacity: 0`

- Have you ever used a grid system, and if so, what do you prefer?

Yes, this makes layouting much more flexible. If we don't consider IE 11 then this is something modern front-end developers should consider.

- Have you used or implemented media queries or mobile specific layouts/CSS?

Yes. You will have to define the device boundary with media queries `@media screen (max-width: 600px)` to make you application responsive.

- Are you familiar with styling SVG?

I've tried several times because of business requirement.

- Can you give an example of an `@media` property other than `screen`?
- What are some of the "gotchas" for writing efficient CSS?
- What are the advantages/disadvantages of using CSS preprocessors?
  - Describe what you like and dislike about the CSS preprocessors you have used.
- How would you implement a web design comp that uses non-standard fonts?
- Explain how a browser determines what elements match a CSS selector.
- Describe pseudo-elements and discuss what they are used for.
- Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in different box models.
- What does `* { box-sizing: border-box; }` do? What are its advantages?
- What is the CSS `display` property and can you give a few examples of its use?
- What's the difference between inline and inline-block?
- What's the difference between the "nth-of-type()" and "nth-child()" selectors?
- What's the difference between a relative, fixed, absolute and statically positioned element?
- What existing CSS frameworks have you used locally, or in production? How would you change/improve them?
- Have you used CSS Grid?
- Can you explain the difference between coding a web site to be responsive versus using a mobile-first strategy?
- Have you ever worked with retina graphics? If so, when and what techniques did you use?
- Is there any reason you'd want to use `translate()` instead of _absolute positioning_, or vice-versa? And why?
- How is clearfix css property useful?
- Can you explain the difference between px, em and rem as they relate to font sizing?
- Can you give an example of a pseudo class? Can you provide an example use case for a pseudo class?
- What is the difference between a block level element and an inline element. Can you provide examples of each type of element?
