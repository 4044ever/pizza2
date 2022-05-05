---
draft: false
title: "GraphComment"
url: /hugo/graphcomment
header_image:  "/uploads/graphcomment.jpg"
header_image_wp:  "/uploads/graphcomment.webp"
date: 2022-02-16T21:16:28+08:00
---

A good alternative for a comment system is [GraphComment](https://graphcomment.com/). Their free tier account is quite useable. <!--more-->It's not as cluttered as Disqus.




<details>
<summary class="text-xl ">/layouts/shortcodes/graphcomment.html</summary>
<div>
{{< highlight html >}}
    <div id="graphcomment"></div>
    <script type="text/javascript">

    /* - - - CONFIGURATION VARIABLES - - - */

    var __semio__params = {
        graphcommentId: "YOUR-GRAPHCOMMENT-PAGE-ID-HERE", // make sure the id is yours

        behaviour: {
        // HIGHLY RECOMMENDED
        //  uid: "...", // uniq identifer for the comments thread on your page (ex: your page id)
        },

        // configure your variables here

    }

    /* - - - DON'T EDIT BELOW THIS LINE - - - */

    function __semio__onload() {
        __semio__gc_graphlogin(__semio__params)
    }


    (function() {
        var gc = document.createElement('script'); gc.type = 'text/javascript'; gc.async = true;
        gc.onload = __semio__onload; gc.defer = true; gc.src = 'https://integration.graphcomment.com/gc_graphlogin.js?' + Date.now();
        (document.getElementsByTagName('head')[0] || document.getElementsByTagName('body')[0]).appendChild(gc);
    })();
    </script>
    {{< /highlight >}}
</div>
</details>

On your *.md page put this one line of code where you want the comment box to appear:

{{<highlight go-html-template >}}
{{</* graphcomment */>}}
{{< /highlight>}}



  {{< graphcomment >}} 

  <div id="cusdis_thread"
  data-host="https://cusdis.com"
  data-app-id="b01a8123-5fef-4d29-80a0-4139b7e0a232"
  data-page-id="{{ PAGE_ID }}"
  data-page-url="{{ scale-pizza.netlify.app/hugo/graphcomment }}"
  data-page-title="{{ GraphComment }}"
></div>
<script async defer src="https://cusdis.com/js/cusdis.es.js"></script>