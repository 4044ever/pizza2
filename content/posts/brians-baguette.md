---
draft: false
url: brians-baguette
title: "Brian's Baguettes"
header_image:  "/uploads/baguette.jpg"
header_image_wp:  "/uploads/baguette.webp"
date: 2021-09-23T21:16:28+08:00
summary: There are many baguette recipes, many bad ones, many good ones. Here is one that I like....
---

There are many baguette recipes, many bad ones, many good ones. Here is one. From the many good ones I picked Brian's. It's easy, straight forward, and most importantly it makes **really good** baguettes!

Some notes from my side=> The poolish is **essential!** The poolish will give you the amazing taste. 
The water content you **really** need to ajust to your flour! 1% can make a difference. Very soft/sticky dough is not nice to work with and can be very difficult to shape. Keep a log and don't switch flours.
Brian said malt is optional, yes, true - but malt does make a big difference and will get you those nice big crump holes. I use 1.8%. Very important, it must be **diastetic** malt. That the very light colored one. If it looks like chocolate powder it's the **wrong** one!

Brian explains pretty well how he shapes the baguettes and it's easy to follow. 
<p>

{{< youtube eQLTJLF89A4 >}}

## Ok, lets start....

<div class="text-blue-700 text-xl">Change the blue numbers to your liking!</div>  

<div class="grid-container bg-gray-500">
  <div class="grid-item bg-gray-500">How many baguettes you want?</div>
  <div class="grid-item bg-gray-900 "><input class="text-blue-700 font-bold" type="number" id="howMany" name="howMany" value="3" onkeyup="showMsg()">pieces</div>

  <div class="grid-item">Size per (typically 200-300g)</div>
  <div class="grid-item"><input class="text-blue-700 font-bold" type="number" id="weight" name="weight" value="250" onkeyup="showMsg()">g</div>
  <div class="grid-item">Flour in bakers math is always 100%</div>
  <div class="grid-item"></div>
  <div class="grid-item">Water (typically 65%)</div>
  <div class="grid-item"><input class="text-blue-700 font-bold" type="number" id="water" name="water" value="60" onkeyup="showMsg()">%</div>
  <div class="grid-item">Salt (typically 2%)</div>
  <div class="grid-item"><input class="text-blue-700 font-bold" type="number" id="salt" name="salt1" value="2" onkeyup="showMsg()">%</div>
  <div class="grid-item">Malt, diastetic (optional) (typically 0-3%) </div>
  <div class="grid-item"><input class="text-blue-700 font-bold" type="number" id="malt" name="malt" value="0" onkeyup="showMsg()">%</div>
  <div class="grid-item">Yeast (typically 0.40% dry yeast)</div>
  <div class="grid-item"><input class="text-blue-700 font-bold" type="number" id="yeast" name="yeast" value="0.40" onkeyup="showMsg()">%</div>
</div>

 
<span id="intro"><p></span>

**Poolish:**  
<span id="pFlour"></span><br>
<span id="pWater"></span><br>
A pinch of yeast

*<span id="totals"></span></p>*

**Main Dough**  
All of the poolish  
<span id="Flour"></span><br>
<span id="Water"></span><br>
<span id="Salt"></span><br>
<span id="Malt"></span><br>
<span id="Yeast"></span><br>
<span id="toti"></span><br>
<span id="More"></span><br>

<script type="text/javascript">
window.addEventListener( "load", showMsg());
function showMsg(){

// data from form
  var many    = document.getElementById('howMany').valueAsNumber;
  var weight  = document.getElementById('weight').valueAsNumber;
  var water   = document.getElementById('water').valueAsNumber;
  var yeast   = document.getElementById('yeast').valueAsNumber;
  var malt    = document.getElementById('malt').valueAsNumber;
  var salt    = document.getElementById('salt').valueAsNumber;
  let myText = "<p><hr><p>Mix the poolish roughly, cover it, let it rest in a warm place for 8~12 hours. You really just need a pinch of yeast. If it smells sour - it's good!</p><p>When the poolish is ready, mix all ingrediencies (including the poolish), add salt last, till smooth. -------- Will update it later. Please take the method from Brian's video.";

// calculate and send data to span
  document.getElementById('intro').innerHTML = 'So you want to make '+ many + ' baguettes of ' + weight + 'g each, here is what you need:<p>';
  document.getElementById('totals').innerHTML = 'In case you use a different poolish/pre-ferment ratio, note the totals: <span id=totFlour></span> and  <span id="totWater"></span>';
  document.getElementById('pFlour').innerHTML = 'Flour: ' + ((many*weight) * 0.16).toFixed(0) + 'g';
  document.getElementById('pWater').innerHTML = 'Water: ' + ((many*weight) * 0.16).toFixed(0) + 'g';
  document.getElementById('totFlour').innerHTML = 'Flour ' + (((many*weight) / (100 + water) * 100)  ).toFixed(0) + 'g';
  document.getElementById('totWater').innerHTML = 'Water ' + ((many*weight) / (100 + water) * (water) ).toFixed(0) + 'g';
  document.getElementById('Flour').innerHTML  = 'Flour: ' + (((many*weight) / (100 + water) * 100) - ((many*weight) * 0.16)  ).toFixed(0) + 'g';


  document.getElementById('Water').innerHTML  = 'Water: ' + ((many*weight) / (100 + water) * (water - 0) - ((many*weight) * 0.16)).toFixed(0) + 'g';
  document.getElementById('Salt').innerHTML   = 'Salt: ' + (((many*weight) / (100 + water) * 100)/100 * salt).toFixed(1) + 'g';
  document.getElementById('Malt').innerHTML   = 'Malt: ' + (((many*weight) / (100 + water) * 100)/100 * malt).toFixed(1) + 'g';
  document.getElementById('Yeast').innerHTML  = 'Yeast: ' + (((many*weight) / (100 + water) * 100)/100 * yeast).toFixed(2) + 'g (dry yeast)';
  document.getElementById('More').innerHTML   = myText;
  }
</script>

<script>
document.write(many);
document.write(weight);
document.write(water);
document.write(malt);
document.write(yeast);
document.write(totFlour);
</script>


  **Baking:**  
230°C/445°F Top/Bottom - with steam - 8 Minuten  
200°C/390°F Top/Bottom - no steam - 8 Minuten  

or if you have convection and steam:  
245°C/475°F hot air - with steam - 3 Minuten  
235°C/455°F hot air - no steam - 11 Minuten  

That setting works well with the Anova APO.


<style type="text/css">
input {
  width: 60px;
  text-align: right;
  padding: 3px !important;
}


input[type="number"]::-webkit-outer-spin-button, input[type="number"]::-webkit-inner-spin-button {
    -webkit-appearance: none !important;
    margin: 0 !important;
}
 
input[type="number"] {
    -moz-appearance: textfield !important;
}


.grid-container {
  display: grid;
  grid-template-columns: auto auto;
  grid-gap: 1px;
  background-color: #eeeeee;
  padding: 2px;
}

.grid-container > div {
  background-color: rgba(255, 255, 255, 0.9);
  text-align: left;
  padding: 2px 0;
  font-size: 17px;
}

.item5 {
  grid-column: 1 / span 2;
}

</style>

{{< graphcomment >}}