---
draft: false
title: WEBP
url: /hugo/webp
header_image:  "/uploads/webp.jpg"
header_image_wp:  "/uploads/webp.webp"
date: 2022-02-19T21:16:28+08:00
summary: Convert automatically your JPG/PNG/GIF to the small *.webp format!
---


Convert automatically your JPG/PNG/GIF to the small *.webp format!

On websites you want to keep your image size as small as possible. webp is an extremely small, space saving, format. However, not all browsers can handle it. 

On your *.md page you add your existing image in this format:

{{<highlight go-html-template >}}
{{</* picture path="sample.jpg" */>}} /* minimal! - or full:
{{</* picture path="sample.jpg" alt="My image" width="300" height="150" */>}}
{{< /highlight>}}

The source image should be `assets/images/` and **not** in `static/uploads/` etc

<details>
<summary class="text-xl ">layouts/shortcodes/picture.html</summary>
<div>
{{< highlight go-html-template >}}

{{- $path := .Get "path" -}}
{{- $alt := .Get "alt" -}}
{{- $width := .Get "width" -}}
{{- $height := .Get "height " -}}

{{- $msg1 := "The %q shortcode requires a parameter named %q. See %s" -}}
{{- $msg2 := "The resource %q passed to the %q shortcode is not an image. See %s" -}}
{{- $msg3 := "The resource %q passed to the %q shortcode could not be found. See %s" -}}

{{ if not $path }}
  {{ errorf $msg1 .Name "path" .Position }}
{{ end }}

{{- with $i := resources.Get $path -}}
  {{- if eq $i.MediaType.MainType "image" -}}
    {{- if not $width -}}
      {{- $width = $i.Width -}}
    {{- end -}}
    {{- if not $height -}}
      {{- $height = $i.Height -}}
    {{- end -}}

    {{- $j := "" -}}
    {{- $w := "" -}}

    {{- if eq $i.MediaType "image/webp" -}}
      {{- $fitOptions := printf "%vx%v jpg" $width $height -}}
      {{- $j = $i.Fit $fitOptions -}}
      {{- $w = $i -}}
    {{- else if eq $i.MediaType "image/jpeg" -}}
      {{- $fitOptions := printf "%vx%v webp" $width $height -}}
      {{- $w = $i.Fit $fitOptions -}}
      {{- $j = $i -}}
    {{- else -}}
      {{- $fitOptions := printf "%vx%v jpg" $width $height -}}
      {{- $j = $i.Fit $fitOptions -}}
      {{- $fitOptions = printf "%vx%v webp" $width $height -}}
      {{- $w = $i.Fit $fitOptions -}}
    {{- end -}}

    <picture>
      <source srcset="{{ $w.RelPermalink }}" type="image/webp">
      <source srcset="{{ $j.RelPermalink }}" type="image/jpeg">
      <img src="{{ $j.RelPermalink }}" alt="{{ $alt }}" width="{{ $j.Width }}" height="{{ $j.Height }}">
    </picture>
  {{- else -}}
    {{- errorf $msg2 $path $.Name $.Position -}}
  {{- end -}}
{{- else -}}
  {{- errorf $msg3 $path .Name .Position -}}
{{- end -}}
{{- /* chomp */ -}}
{{< /highlight >}}
</div>
</details>



This shortcode converts your JPG/PNG/GIF automatically to webp & jpg format and Hugo reders your HTML to:

{{<highlight go-html-template >}}
<picture>
  <source srcset="/sample_hu1c281d6ad96666827d571a3c8f40b864_327575_533x400_fit_q75_h2_box_3.webp" type="image/webp">
  <source srcset="/sample_hu1c281d6ad96666827d571a3c8f40b864_327575_533x400_fit_q75_bgffffff_box_3.jpg" type="image/jpeg">
  <img src="/sample_hu1c281d6ad96666827d571a3c8f40b864_327575_533x400_fit_q75_bgffffff_box_3.jpg" alt="" width="533" height="400">
</picture>
<picture>
  <source srcset="/sample_hu1c281d6ad96666827d571a3c8f40b864_327575_300x400_fit_q75_h2_box_3.webp" type="image/webp">
  <source srcset="/sample_hu1c281d6ad96666827d571a3c8f40b864_327575_300x400_fit_q75_bgffffff_box_3.jpg" type="image/jpeg">
  <img src="/sample_hu1c281d6ad96666827d571a3c8f40b864_327575_300x400_fit_q75_bgffffff_box_3.jpg" alt="My image" width="300" height="225">
</picture>
{{< /highlight>}}


Credits and thanks to [jmooring](https://discourse.gohugo.io/u/jmooring), from this [source](https://discourse.gohugo.io/t/has-anyone-a-webp-shortcode/35391)


  {{< graphcomment >}} 