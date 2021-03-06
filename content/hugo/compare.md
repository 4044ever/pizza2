---
draft: false
title: "Compare Images"
url: /hugo/compare
header_image:  "/uploads/compare1.jpg"
header_image_wp:  "/uploads/compare2.webp"
date: 2022-02-18T21:16:28+08:00
---

Compare two images with a slider. A nice feature for before/after images.
<!--more-->

There are quite a few scripts out there, I chose [sylvaincombes/jquery-images-compare](https://github.com/sylvaincombes/jquery-images-compare) because it had a styling I liked and it looked fairly easy to implement. 

Starting with the final result:


<div class="page-container">
<!-- Main div container -->
<div id="myImageCompare">
    <!-- The first div will be the front element, to prevent FOUC add a style="display: none;" -->
    <div style="display: none;">
        {{< picture path="images/black.jpg" alt="White" >}}
    </div>
    <!-- This div will be the back element -->
    <div>
         {{< picture path="images/black2.jpg" alt="Black" >}}
    </div>
</div>
</div>
{{< image-compare >}}

There are two ways to use this code on your MD page, first the intended way, you have two images you want to compare directly. (The images should have the same size and aspect ratio.)


{{< highlight html >}}
<!-- Main div container -->
<div id="myImageCompare">
    <!-- The first div will be the front element, to prevent FOUC add a style="display: none;" -->
    <div style="display: none;">
        <img src="uploads/black.jpg" alt="White">
    </div>
    <!-- This div will be the back element -->
    <div>
        <img src="uploads/black2.jpg" alt="Black">
    </div>
</div>
{{</* image-compare */>}}
{{< /highlight >}}

But if you have the [auto webp generator](/hugo/webp) running you can use the method below to auto-generate webp images - that still have the slider:

{{< highlight html >}}
<div class="page-container">
<!-- Main div container -->
<div id="myImageCompare">
    <!-- The first div will be the front element, to prevent FOUC add a style="display: none;" -->
    <div style="display: none;">
        {{</* picture path="images/black.jpg" alt="White" */>}}
    </div>
    <!-- This div will be the back element -->
    <div>
         {{</* picture path="images/black2.jpg" alt="Black" */>}}
    </div>
</div>
</div>
{{</* image-compare */>}}
{{< /highlight >}}


The shortcode is here:
<details>
<summary class="text-xl ">/layouts/shortcodes/image-compare.html</summary>
<div>
{{< highlight js >}}
<style type="text/css">
/* Images compare main container */
.images-compare-container {
    display: inline-block;
    position: relative;
    overflow: hidden;
}

/* Images compare front element */
.images-compare-before {
    will-change: clip;
    position: absolute;
    top: 0;
    left: 0;
    z-index: 2;
    pointer-events: none;
    overflow: hidden;
}

/* Images compare back element */
.images-compare-after {
    pointer-events: none;
}

/* Responsive image settings */
.images-compare-before img, .images-compare-after img {
    max-width: 100%;
    height: auto;
    display: block;
}

/* Separator (thin vertical blank line) */
.images-compare-separator {
    position: absolute;
    background: white;
    height: 100%;
    width: 1px;
    z-index: 4;
    left: 0;
    top: 0;
}

/* Drag handle (circle) */
.images-compare-handle {
    height: 38px;
    width: 38px;
    position: absolute;
    left: 50%;
    top: 50%;
    margin-left: -22px;
    margin-top: -22px;
    border: 3px solid white;
    -webkit-border-radius: 1000px;
    -moz-border-radius: 1000px;
    border-radius: 1000px;
    -webkit-box-shadow: 0 0 12px rgba(51, 51, 51, 0.5);
    -moz-box-shadow: 0 0 12px rgba(51, 51, 51, 0.5);
    box-shadow: 0 0 12px rgba(51, 51, 51, 0.5);
    z-index: 3;
    background: rgb(0, 0, 0);
    background: rgba(0, 0, 0, 0.7);
    cursor: pointer;
}

/* Drag handle arrows */
.images-compare-left-arrow, .images-compare-right-arrow {
    width: 0;
    height: 0;
    border: 6px inset transparent;
    position: absolute;
    top: 50%;
    margin-top: -6px;
}

.images-compare-left-arrow {
    border-right: 6px solid white;
    left: 50%;
    margin-left: -17px;
}

.images-compare-right-arrow {
    border-left: 6px solid white;
    right: 50%;
    margin-right: -17px;
}

/* Label */
.images-compare-label {
    font-family: sans-serif;
    text-transform: uppercase;
    font-weight: bold;
    position: absolute;
    top: 10px;
    left: 10px;
    z-index: 1;
    color: rgb(0, 0, 0);
    color: rgba(0, 0, 0, 0.4);
    background: rgb(255, 255, 255);
    background: rgba(255, 255, 255, 0.7);
    padding: 10px;
    border-radius: 5px;
    pointer-events: none;
    display: none;
}

.images-compare-container .images-compare-label {
    display: inherit;
}

.images-compare-before .images-compare-label {
    left: 10px;
}

.images-compare-after .images-compare-label {
    left: auto;
    right: 10px;
}
</style>

<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/jquery/2.2.4/jquery.min.js"></script>
<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/hammer.js/2.0.8/hammer.min.js"></script>
<script type="text/javascript">
!function(y,t){"use strict";var i="imagesCompare",u={initVisibleRatio:.5,interactionMode:"drag",animationDuration:400,animationEasing:"swing",addSeparator:!0,addDragHandle:!0,precision:4};function n(m,p){var a,e;m=y(m),(p=y.extend({},u,p)).roundFactor=parseInt("1"+(a="0",e=p.precision,String.prototype.repeat?a.repeat(e):(e=e||1,new Array(e+1).join(a)))),this._name=i;var g,n,f,h,l=1,v={width:0,height:0,maxWidth:0,maxHeight:0},w={initialised:"imagesCompare:initialised",changed:"imagesCompare:changed",resized:"imagesCompare:resized"};function r(){y(t).on("resize",function(a){g.css("clip",""),d(),c(l),m.trigger({type:w.resized,originalEvent:a})})}function o(){var a;"undefined"==typeof Hammer&&console.error("Please include the hammerjs library for drag support"),(a=new Hammer(m[0])).get("pan").set({direction:Hammer.DIRECTION_HORIZONTAL}),a.on("pan",function(a){var e=s(a.srcEvent.pageX);c(e)}),r()}function d(){var a=n.find("img").first();!function(a,e,t,i){void 0!==a&&(n=a,v.width=n);var n;void 0!==e&&(r=e,v.height=r);var r;void 0!==t&&(o=t,v.maxWidth=o);var o;void 0!==i&&(d=i,v.maxHeight=d);var d}(a.width(),a.height(),a.naturalWidth(),a.naturalHeight()),m.css("max-width",v.maxWidth+"px"),m.css("max-height",v.maxHeight+"px"),g.width(v.width),g.height(v.height)}function s(a){return function(a){1<(a=Math.round(a*p.roundFactor)/p.roundFactor)&&(a=1);a<0&&(a=0);return a}((a-m.offset().left)/g.width())}function x(a){return a=Math.round(a*p.roundFactor)/p.roundFactor,Math.round(g.width()*a)}function c(a,e,t,i){void 0===e&&(e=!1);var n,r,o,d,s=x(a);if(e){var c=t||p.animationDuration,u=i||p.animationEasing;return n=l,r=a,o=c,d=u,y(g).attr("ratio",n).animate({ratio:n},{duration:0}),y(g).stop().attr("ratio",n).animate({ratio:r},{duration:o,easing:d,step:function(a){var e=x(a);l=a,g.attr("ratio",a).css("clip","rect(0, "+e+"px, "+v.height+"px, 0)"),p.addSeparator&&f.css("left",e+"px"),p.addDragHandle&&h.css("left",e+"px")},done:function(a,e){var t=y(g).attr("ratio");m.trigger({type:w.changed,ratio:t,value:x(t),animate:!0,animation:a,jumpedToEnd:e})}}),void(l!=a&&m.trigger({type:w.changed,ratio:l,value:s,animate:e}))}g.stop().css("clip","rect(0, "+s+"px, "+v.height+"px, 0)"),p.addSeparator&&y(f).stop().css("left",s+"px"),p.addDragHandle&&h.css("left",s+"px"),l!=a&&m.trigger({type:w.changed,ratio:a,value:s,animate:e}),l=a}return function(){var a=m.find("img"),e=a.length,t=0;function i(){e<=t&&(m.addClass("images-compare-container"),m.css("display","inline-block"),g=m.find("> *:nth-child(1)"),n=m.find("> *:nth-child(2)"),g.addClass("images-compare-before"),g.css("display","block"),n.addClass("images-compare-after"),n.css("display","block"),p.addDragHandle&&(m.prepend("<div class='images-compare-handle'></div>"),(h=m.find(".images-compare-handle")).append("<span class='images-compare-left-arrow'></span>"),h.append("<span class='images-compare-right-arrow'></span>")),p.addSeparator&&(m.prepend("<div class='images-compare-separator'></div>"),f=m.find(".images-compare-separator")),d(),function(){switch(p.interactionMode=p.interactionMode.toLowerCase(),"drag"!=p.interactionMode&&"mousemove"!=p.interactionMode&&"click"!=p.interactionMode&&console.warn('No valid interactionMode found, valid values are "drag", "mousemove", "click"'),p.interactionMode){case"drag":o();break;case"mousemove":i=0,m.on("mousemove",function(a){a.preventDefault();var e=Date.now();if(i+1<e){i=e;var t=s(a.pageX);c(t)}}),m.on("mouseout",function(a){var e=s(a.pageX);c(e)}),r();break;case"click":m.on("click",function(a){var e=s(a.pageX);c(e)}),r();break;default:o()}var i}(),y(g).attr("ratio",p.initVisibleRatio),c(p.initVisibleRatio),m.trigger({type:w.initialised}))}a.each(function(){y(this)[0].complete?(e--,i()):(y(this).on("load",function(){t++,i()}),y(this).on("error",function(){t++,i()}))})}(),{setValue:function(a,e,t,i){return c(a,e,t,i),m},getValue:function(){return l},on:function(a,e){return m.on(a,e),m},off:function(a,e){return m.off(a,e),m},events:function(){return w}}}y.fn.imagesCompare=function(a){var e=y.extend(u,a);return this.each(function(){y.data(this,i)||y.data(this,i,new n(this,e))})}}(jQuery,window,document),function(e){var a,t,i=["Width","Height"];t=i.length;for(var n=0;n<t;n++)!function(a,i){e.fn[a]=a in document.createElement("img")?function(){return this[0][a]}:function(){var a,e=this[0],t=0;return"img"===e.tagName.toLowerCase()&&((a=document.createElement("img")).src=e.src,t=a[i]),t}}("natural"+(a=i[n]),a.toLowerCase())}(jQuery);
</script>

<script type="text/javascript">
    $('#myImageCompare').imagesCompare();
    </script>
    
    {{< /highlight >}}
</div>
</details>


  {{< graphcomment >}} 