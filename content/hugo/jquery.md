---
draft: false
title: "jQuery"
url: /hugo/jquery
header_image:  "/uploads/jquery.jpg"
header_image_wp:  "/uploads/jquery.webp"
date: 2022-02-17T21:16:28+08:00
summary: Use jQuery links in the header only when you need them!
---


Use jQuery links in the header only when you need them!

To load the jQuery library from i.e. `https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js` takes DNS lookup time and loading time, reducing the page load speed. Wordpress often puts the jQuery CDN on every single page. With Hugo you can set it in a way only to show on pages where jQuery is required.

It's very easy. On your `*.md` add this command to the front matters:

{{<highlight html >}}
jquery: true
{{< /highlight>}}


This code will go in your `baseof.html`:
{{<highlight html >}}
{{ with .Params.jquery }} {{/* checks if the parameter exists */}}
OR 
{{ if eq .Params.jquery true }} {{/* checks if the boolean value of the parameter is set to true */}}
<--- jQuery script --->
{{ end }}
{{< /highlight>}}



<!--    {{< graphcomment >}}   -->