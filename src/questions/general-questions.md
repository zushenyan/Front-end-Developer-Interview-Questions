---
title: General Questions
layout: layouts/page.njk
permalink: /questions/general-questions/index.html
---

# What did you learn yesterday/this week?

# What excites or interests you about coding?

I started coding when I was 14. In the beginning, I wanted to make games, and my brother happened to be an computer sicence student. Under his guidance, I learnt my first language --- C language. After C, I learnt and used Java for a few years. After that, I found programming is kind of interesting, so I tried out some other languages like PHP, Pyhton, C++, and finally I choose JavaScript as my main skill because I think web development is fun and in the future, the web application will be an main stream.

# What is a recent technical challenge you experienced and how did you solve it?

# When building a new web site or maintaining one, can you explain some techniques you have used to increase performance?

One of the technique I've done is putting the assets on CDN to have them cached by the browser. This technique can improve the network performance because

1. since the connection for each domain is limited by the browser, fetching data from other domain can share the load.
2. cache means the browser doesn't have to fetch again to get it.

# Can you describe some SEO best practices or techniques you have used lately?

In my last job, I was using React to build website, that meant we had to adapt SSR to enable SEO. This is importatnt since CSR can't be completely parsed by search engines' crawlers so apating SSR is necessary.

Other techniques I've used are

1. improving site loading speed.
2. add alt attribute to images.
3. injecting meta tags and description.

# Can you explain any common techniques or recent issues solved in regards to front-end security?

The most recent security issue I've encountered was CSP (Ccontent Security Policy) which is a HTTP header that could whitelist the script sources. DevOps forgot to whitelist the 3rd party script and caused our staging server to throw errors.

# What actions have you personally taken on recent projects to increase maintainability of your code?

I always try two things to increase maintainability

1. Separation concern. To make component owns their own logic. For example, UI components only own UI logic, while putting business logic in action module.
2. Write tests. Writing tests could improve the confidence of refactoring.

# Talk about your preferred development environment.

# Which version control systems are you familiar with?

# Can you describe your workflow when you create a web page?

Let's assume I just jump on another project owned by others. I would roughly go through the project to understand the convention or framework I need to get familiar with, and then I would try to understand the task assigned to me. Write the needed components, and finally assemble them together to make a web page.

# If you have 5 different stylesheets, how would you best integrate them into the site?

In the modern frontend development. The stylesheets should be processed by the post-CSS processor and bundler for optimization (either concatenating into single file or keep them separated in favor of HTTP2 multiplex) or adding necessary prefix to make them work on other platforms.

# Can you describe the difference between progressive enhancement and graceful degradation?

**Graceful degradation** Set the oldest platform as support target, but still support the latest version of platform for better UI experience.
**Progressive Enhancement** Set the latest platform as support target, but still support the oldest version of platform for necessary UI experience.

# How would you optimize a website's assets/resources?

Put them on CDN for optimizing network performance. Exporting images with webp format for maximum size compression.

# How many resources will a browser download from a given domain at a time?What are the exceptions?

In Chrome, it's 10. It varies by browsers.

# Name 3 ways to decrease page load (perceived or actual load time).

1. Providing placeholders.
2. `content-encoding`
3. prefetching pages.

# If you jumped on a project and they used tabs and you used spaces, what would you do?

Use `editorconfig` and linter to format that.

# Describe how you would create a simple slideshow page.

# If you could master one technology this year, what would it be?

# Explain the importance of standards and standards bodies.

I assume it's asking why do we need web standard. It helps either browser vendors to share the same foundation so everyone can build things without worrying too many differences between platforms. It is mainly to reduce development time for everyone.

# What is Flash of Unstyled Content? How do you avoid FOUC?

That means the CSS stylesheet is loaded after the browser renders the HTML, which leads to unstyle content. One of the possible fix is to firstly set HTML visibility to hidden and then set it to visible by adding an JS after `body`.

# Explain what ARIA and screenreaders are, and how to make a website accessible.

ARIA is a kind of attributes prefixed with `aria-` that makes the disabled to be able to access to your website. Developers can add attributes like `role` or `aria-valuenow` to make it accessible by the screenreader in order to help people with disabilities.

# Explain some of the pros and cons for CSS animations versus JavaScript animations.

The advantage of using with CSS animation is simpler to use, and the disadvnatage is no advanced control (stop, reverse, replay at will).

There is no difference in performance as both of them can access to GPU acceleration.

# What does CORS stand for and what issue does it address?

CORS stands for Cross-Origin Resource Sharing. It is a HTTP header that whitelists which specific domain can access to selected resrouces (e.g. images)

# How did you handle a disagreement with your boss or your collaborator?

I will try to tell the pros and cons of my approach, but I wouldn't stand my ground as long as they share their concern.

# What resources do you use to learn about the latest in front end development and design?

# What skills are needed to be a good front-end developer?

# What role do you see yourself?

# Explain the difference between cookies, session storage, and local storage?

cookies - it's a type of storage that can hold up to 4 MB sent by a server and keeps by the browser. It can be transmitted in text as a part of headers `cookie`.

session storage - a part of web storage. It can only persist the data before user closes the tab. Web storage cannot be shared across domains.

local storage - a part of webstorage. I can persist the data after user closes the tab. Web storage cannot be shared across domains.

# GraphQL vs Restful

Graphql - Pros

- single endpoint.
- single request for all the resources you need (no multiple request, redundant fields)
- no versioning

Graphql - Cons

- learning cruve.
- abandon application cache provided by browsers. You have to implement your own solution or looking for library for help.

# `trunk-based flow` vs `Gitflow`

![Gitflow](https://uploads.toptal.io/blog/image/129305/toptal-blog-image-1551794424851-b3d5928bc33edfc954ef460062e5cbcc.png)

pros

- features can be broken down into pieces for different teams to develop.

cons

- extra complexity to manage.
- slow to iterate a product.

![trunk-based](https://uploads.toptal.io/blog/image/129304/toptal-blog-image-1551794413174-f4139c4be533dc592d49f9a0bcc330f0.png)

pros

- easy to manage.
- fast to iterate a product.

cons

- might not work well if you have multiple teams to work on the same product.
