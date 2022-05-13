---
draft: false
title: My Notebox Shortcode
url: /hugo/notebox/
header_image: /uploads/notebox.jpg
header_image_wp: /uploads/notebox.webp
date: 2022-05-12T11:16:28+08:00
summary: An Easy to Use Text Box for Hugo, the Static Site Generator. Using TailwindCSS for Styling
description: Notebox - An Easy to Use Text Box for Hugo, the Static Site Generator. Using TailwindCSS for Styling and it's Easy to Change to Your Liking too
keywords:
  - notebox
slug: notebox-shortcode
---

## Notebox - A simple way to add note boxes

Note boxes are fine way to bring some color into your text. To make things a bit easier I tried the [martignoni/hugo-notice](https://github.com/martignoni/hugo-notice) shortcode.

That shortcode is very nice but the i18n format did not match my site well. My site isn't really multilingual, but I may have an *other* language page mixed in. 

So I fiddled together a similar looking [hugo notebox](https://github.com/4044ever/hugo-notebox). My site uses TailwindCSS, which I used for the boxes.

{{< notebox tip >}}
Text boxes are a great way to make an article more interesting with some colors!
{{< /notebox >}}

With the shortcode in place I just write: 

{{<highlight go-html-template >}}
{{</* notebox info */>}}
Now I can add an info box easily!
{{</* /notebox */>}} 
{{< /highlight>}}

And the output is: 

{{< notebox info >}}
Now I can add an info box easily!
{{< /notebox >}}  

But it goes on. With tip.de I can change the head to German. This is not automatic though, it works because it's setup that way in the shortcode. I can easily add more languages if I want to.

{{<highlight go-html-template >}}
{{</* notebox tip.de */>}}
Tip is Tipp in German, maybe not the most complex example. 
{{</* /notebox */>}} 
{{< /highlight>}}

{{< notebox tip.de >}}
Tip is Tipp in German, maybe not the most complex example. 
{{< /notebox >}}
<p>
{{< notebox warning >}}
This is a warning!
{{< /notebox >}}
<p>
{{< notebox note >}}
A note for you.
{{< /notebox >}}


<p>
{{< notebox info >}}
Some info for you
{{< /notebox >}}  
  <p>
{{< notebox trivia >}}
Funny note...
{{< /notebox >}}

  {{< graphcomment >}} 

