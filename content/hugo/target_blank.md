---
draft: false
title: "Open Link in New Tab"
url: /hugo/target-blank
header_image:  "/uploads/target_blank.jpg"
header_image_wp:  "/uploads/target_blank.webp"
date: 2022-04-23T21:16:28+08:00
summary: Open a link in a new tab is something Hugo does not do natively, here is a code to fix that...
---

Hugo does not open links natively in a new tab. This code will help you to achive that - with one line of code!

1. Create `layouts/_default/_markup/render-link.html`
2. Add this line for pre Hugo 0.96:

{{<highlight go-html-template>}}
<a href="{{ .Destination | safeURL }}"{{ with .Title}} title="{{ . }}"{{ end }}{{ if strings.HasPrefix .Destination "http" }} target="_blank"{{ end }}>{{ .Text | markdownify }}</a>
{{< /highlight>}}

or, in case you use Hugo 0.96 or newer:

{{<highlight go-html-template>}}
<a href="{{ .Destination | safeURL }}"{{ with .Title}} title="{{ . }}"{{ end }}{{ if strings.HasPrefix .Destination "http" }} target="_blank"{{ end }}>{{ .Text }}</a>
{{< /highlight>}}

That's all! If you get an error that points to `markdownify` - check your Hugo version!

External links will now open in a new tab > [Source + Credit](https://agrimprasad.com/post/hugo-goldmark-markdown/#:~:text=Thus%2C%20if%20you%20want%20to,_blank%22%20attribute%20to%20the%20links.) - and local links will open in the same tab > [br&ouml;tchen](/broetchen/)

  {{< graphcomment >}} 