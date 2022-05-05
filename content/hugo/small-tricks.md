---
draft: false
title: "Small Tricks"
url: /hugo/small-tricks
header_image:  "/uploads/broetchen02.jpg"
header_image_wp:  "/uploads/broetchen02.webp"
date: 2022-02-10T21:16:28+08:00
summary: A collection of a few small helpful Hugo Tricks. 
---



A few small tricks not really worth having their own page:

  <details class="p-3 rounded-lg">
  <summary class="leading-6">Expand on click (yes you need to click here) </summary>

<div class="mt-3">
  <p class=" text-blue-800 ">You can do that simply and JS free with that structure:
  
  {{< highlight html >}}
  <details>  
  <summary>Some Header</summary>  
  <div>Some hidden text</div>  
  </details>
{{< /highlight >}}

   </p></div></details>

  <hr>

The classic Youtube shortcode: 

{{<highlight go-html-template>}}
{{</* youtube w7Ft2ymGmfc */>}}
{{< /highlight>}}

  <hr>

Open external link in a new tab. 
Typically you want external links to open in a new tab. Very easy!
1. Create `layouts/_default/_markup/render-link.html`
2. Add this line:

{{<highlight go-html-template>}}
<a href="{{ .Destination | safeURL }}"{{ with .Title}} title="{{ . }}"{{ end }}{{ if strings.HasPrefix .Destination "http" }} target="_blank"{{ end }}>{{ .Text | markdownify }}</a>
{{< /highlight>}}

That's all! Or nearly all. That shortcode works up to about Hugo 0.96 (March 2022), later version (tested with 0.97.3 ext) throw an error due to `markdownify`, so simply remove the `| markdownify` and you are fine again. 

{{<highlight go-html-template>}}
<a href="{{ .Destination | safeURL }}"{{ with .Title}} title="{{ . }}"{{ end }}{{ if strings.HasPrefix .Destination "http" }} target="_blank"{{ end }}>{{ .Text }}</a>
{{< /highlight>}}

External links will open in a new tab > [Source + Credit](https://agrimprasad.com/post/hugo-goldmark-markdown/#:~:text=Thus%2C%20if%20you%20want%20to,_blank%22%20attribute%20to%20the%20links.) - and local links will open in the same tab > [broetchen](/broetchen/)

  {{< graphcomment >}} 