---
title: "Basic Servlets Structure"
layout: post
tag:
- Java
- Servlets
comments: true
author: nurulfajar
---

outlines a basic servlet that handles GET requests. GET requests, for those
unfamiliar with HTTP, are the usual type of browser requests for Web pages. A
browser generates this request when the user enters a URL on the address line, follows
a link from a Web page, or submits an HTML form that either does not specify a METHOD or specifies METHOD="GET". Servlets can also easily handle POST requests, which are generated when someone submits an HTML form that specifies
METHOD="POST".

### Example Servlet Template
```java
import java.io.*;
import javax.servlet.*;
import javax.servlet.http.*;
public class ServletTemplate extends HttpServlet {
 public void doGet(HttpServletRequest request,
 HttpServletResponse response)
 throws ServletException, IOException {

 // Use "request" to read incoming HTTP headers
 // (e.g., cookies) and query data from HTML forms.

 // Use "response" to specify the HTTP response status
 // code and headers (e.g., the content type, cookies).

 PrintWriter out = response.getWriter();
 // Use "out" to send content to browser.
 }
}
```

### Hello World
```java
import java.io.*;
import javax.servlet.*;
import javax.servlet.http.*;
public class HelloWorld extends HttpServlet {
 public void doGet(HttpServletRequest request,
 HttpServletResponse response)
 throws ServletException, IOException {
 PrintWriter out = response.getWriter();
 out.println("Hello World");
 }
}
```
