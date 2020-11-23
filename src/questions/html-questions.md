---
title: HTML Questions
layout: layouts/page.njk
permalink: /questions/html-questions/index.html
---

# What does a `doctype` do?

It's a type declaration for browser client to tell them how they should parse this document.

# How do you serve a page with content in multiple languages?

1. Provide a tag `<meta charset="utf-8" />` in HTML document.
2. Send server response along with `Accept-Lanugage` header.
3. There is also an HTML attribute called `lang` to teel browser which section uses which language.

# What kind of things must you be wary of when designing or developing for multilingual sites?

1. Character encoding
2. Character overflow
3. Writing direction. (e.g. LTR, RTL)

# What are `data-` attributes good for?

It's a customizable attribute for developers to save specific data in a DOM object. For example, we can attach an attribute named `data-foobar` for a `div`, and later we can mutate the value with JS.

# Consider HTML5 as an open web platform. What are the building blocks of HTML5?

1. more semantic tags.
2. multimedia API (video/audio).
3. web worker API.
4. data storage API.

# Describe the difference between a `cookie`, `sessionStorage` and `localStorage`.

# Describe the difference between `<script>`, `<script async>` and `<script defer>`.

1. `<script>` will be fetched and executed when the browser runs into it and it blocks document rendering.
2. `<script async>` will be fetched but the browser do it with document rendering in parallel, and execute it latter as soon as done fetching.
3. `<script defer>` will be fetched but only be executed when the whole document rendering has been done.

# Why is it generally a good idea to position CSS `<link>`s between `<head></head>` and JS `<script>`s just before `</body>`? Do you know any exceptions?

Because we want our stylesheets to be loaded as soon as possible. For `<script>` putting right after the `</body>` is because we want to run script only after DOM elements get constructed. Other exceptions are putting 3rd parties `<script>` in `<head>` because we want them to be loaded for better integration purpose.

# What is progressive rendering?

It's a technique that loads document content gradually.

# Why you would use a `srcset` attribute in an image tag? Explain the process the browser uses when evaluating the content of this attribute.

It will be used with responsiveness. A developer can define the it with `srcset="600.jpg 600w, 800.jpg 800w"` to tell browser to switch to which image source to provide the best user experience.

# Have you used different HTML templating languages before?

I have only had used EJS along with nodejs or PHP's built-in HTML templating support.

# What is the difference between `canvas` and `svg`?

`Canvas` is a single element that can be used with JS to render complicated, GPU intensive content. It is usually used with multi-media or gaming purpose.

`svg` is a format that describes a set of geometry in XML. It will be parsed and displayed by the browser.
