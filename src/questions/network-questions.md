---
title: Network Questions
layout: layouts/page.njk
permalink: /questions/network-questions/index.html
---

- Traditionally, why has it been better to serve site assets from multiple domains?

Because browsers put the limit on requests number per domain. For example Chrome limits the requests in 10. Using CDN could bypass this restriction.

- Do your best to describe the process from the time you type in a website's URL to it finishing loading on your screen.

1. You type the `foobar.com` in the browser search bar.
2. The browser will check if it is in cache. If it is, then skip to browser rendering step.
3. The browser will start looking for the real IP address in this order

   a. browser cache
   
   b. os cache
   
   c. router cache
   
   d. ISP cache
   
4. If none of them has IP address, then the ISP will initiate a recursive DNS query between DNS servers. It will look for domain in this order

   a. `.` root domain
   
   b. `edu`, `org`, `com` top-level domain
   
   c. `microsoft.com`, `wikipedia.org` second-level domain
   
   d. `download.microsoft.com`, `www.wikipedia.org` thrid-level domain
   
5. if it finds an IP address, then the browser will start establishing TCP connection between server through handshaking.
6. the browser sends an HTTP request to the server.
7. the server handles the request and sends an HTTP response.
8. the browser parses the content of HTTP resonse and display it.

- What are the differences between Long-Polling, Websockets and Server-Sent Events?

`long-polling` is an JavaScript technique for older version of browsers to simulate the behaviour of two-way communication like websocket. Basically it uses a recursive function to await a fetch request indefinitely.

`websockets` is a realtime, bi-directional communication between the client and the server. It's a different protocol and the connection, unlike HTTP connection will get closed in a time period, websocket connection will last until it is closed.

`server-sent events` is a one-way communication. It is up to the server to decide when to send the message to the client. The client will have to subscribe to the server to get hooked with the server.

- Explain the following request and response headers:
  - Diff. between Expires, Date, Age and If-Modified-...
  - Do Not Track
  - Cache-Control
  - Transfer-Encoding
  - ETag
  - X-Frame-Options

`expires` indicates that after the time the response is considered stale.

`date` the time the message was sent.

`age` the elapsed time of the response which has been in a proxy cache.

`if-modified-since` if the request has not been modified since, the repsonse will be `304`. If not, then the server will send back with `200`, only if it has been last modified after the given time.

`DNT` indicates the user privacy preference.

`cache-contorl` indicates the cache preference of the response or request.

`transfer-encoding` specifies the encoding method for transfering payload body to the user.

`etag` the version of the resourece.

`x-frame-options` indifcate if the browser are allowed to render pages in `<iframe>`, `<object>`, `<embed>`.

- What are HTTP methods? List all HTTP methods that you know, and explain them.
- What is domain pre-fetching and how does it help with performance?

If a resource is likely clicked by the user, then we pre-download and cache it before the user clicks. It helps the performance by performing it before it happens.

- What is a CDN and what is the benefit of using one?
