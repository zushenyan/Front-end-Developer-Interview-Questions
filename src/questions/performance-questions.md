---
title: Performance Questions
layout: layouts/page.njk
permalink: /questions/performance-questions/index.html
---

# What tools would you use to find a performance bug in your code?

Mostly I use Chrome devtool to find potential perforamnce issues.

If it is a network performance issue, then I will run lighthouse to help me and fix the potential issues based on the given feedbacks.

It it is a runtime/application issue, I will run performance recording and analyzing generated graphs to see which function takes too long to complete.

# What are some ways you may improve your website's scrolling performance?

I assume it happens because there are some extra events which get triggered when the user scrolls. In that case, we can put throttle to the event source to limit how many events can be made.

# Explain the difference between layout, painting and compositing.

The order is executed in this `JS -> Style -> Layout -> Paint -> Composite`

`layouting` the browser starts calculating how much space an element should take and where it belongs to on the screen.

`painting` the browser starts filling the pixel of elements. For example text, borders, images, shadows. Things will be painted in layers.

`Composite` the browser stars arranging the order of previously painted layers otherwise elements could overlap each other.
