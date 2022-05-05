---
draft: false
title: "Hard Rolls"
url: hard-rolls
header_image:  "/uploads/broetchen02.jpg"
header_image_wp:  "/uploads/broetchen02.webp"
date: 2022-02-04T21:16:28+08:00
summary: A German classic - Brötchen! The secret to very good ones is **time** and a poolish.
---



A German classic - Brötchen! The secret to very good ones is **time** and a poolish. My Sunday brötchen I start already on Friday. Very important is a "Poolish", a pre-ferment - made from just flour and water in a 1:1 ratio, and a tiny bit yeast. 

{{< figure src="/semmel.jpg" alt="Brötchen" width="50%" >}}

## Let's start....

<div class="text-blue-700 text-xl">Change the blue numbers to your liking!</div>  

<div class="grid-container">
  <div class="grid-item">How many Brötchen you want to make?</div>
  <div class="grid-item"><input class="text-blue-700 font-bold" type="number" id="howMany" name="howMany" value="12" onkeyup="showMsg()">pcs.</div>
  <div class="grid-item">Single weight (typically 80g)</div>
  <div class="grid-item"><input class="text-blue-700 font-bold" type="number" id="weight" name="weight" value="80" onkeyup="showMsg()">g</div>
  <div class="grid-item">Flour is always 100%</div>
  <div class="grid-item"></div>
  <div class="grid-item">Water (may need to adjust to your flour)</div>
  <div class="grid-item"><input class="text-blue-700 font-bold" type="number" id="water" name="water" value="60" onkeyup="showMsg()">%</div>
  <div class="grid-item">Salt (standard 2%)</div>
  <div class="grid-item"><input class="text-blue-700 font-bold" type="number" id="salt" name="salt1" value="2" onkeyup="showMsg()">%</div>
  <div class="grid-item">Yeast (typically 0.80% dry yeast)</div>
  <div class="grid-item"><input class="text-blue-700 font-bold" type="number" id="yeast" name="yeast" value="0.80" onkeyup="showMsg()">%</div>
</div>

 
<span id="intro"><p></span>
**Poolish:**  
<span id="pFlour"></span><br>
<span id="pWater"></span><br>
Yeast, a pinch

**Main Dough**  
All of the Poolish  
<span id="Flour"></span><br>
<span id="Water"></span><br>
<span id="Salt"></span><br>
<span id="Yeast"></span><br>
<span id="More"></span><br>

<hr>
My timing for Sunday brötchen:

**Friday, morning:**  
In the morning I mix the poolish/pre-ferment. Just with a spoon or from hand. The 1:1 mix is very easy and fast to mix. I keep it coverred in a warm (but not too hot) place. The poolish should double and will develop a sour smell. Not really pleasant, but it's correct. 

**Friday, evening:**  
I knead all together - but not yeast & salt! Just enough till everything is wet. Then let it rest for one hour. It's called **autolyse**. The gluten will start to build already and you don't have to knead much later.
After one hour I knead again, add first the yeast, then the salt - roughly for 5 Minutes.

Next the dough goes to a shallow container where I stretch and fold it every about 20 Minutes for 1.5 to 2 hours. By this time the dough should get a little puffy. When done I put it in a oiled container and the dough goes to the fridge till Sunday. 

**Sunday:**  
Directly from the fridge I take the chosen size (for me about 80g) and shape them to a ball. Here I can add poppy seed, oats, sesame or whatever. Next I let them rest for about 40 Minutes. Preheat the oven, then scoring and baking
 
If the dough sticks to the knife while scoring use 1-2% less water next time. A wet blade helps too.

**Baking:**  
230°C/445°F Top/Bottom - with steam - 8 Minuten  
200°C/390°F Top/Bottom - no steam - 8 Minuten  

or if you have convection and steam:  
245°C/475°F hot air - with steam - 3 Minuten  
235°C/455°F hot air - no steam - 11 Minuten  

That setting works well with the Anova APO.

Ok, this takes 2 days, but the actual work is minimal. 


<script type="text/javascript">
window.addEventListener( "load", showMsg());
function showMsg(){

// data from form
  var many    = document.getElementById('howMany').valueAsNumber;
  var weight  = document.getElementById('weight').valueAsNumber;
  var water   = document.getElementById('water').valueAsNumber;
  var yeast   = document.getElementById('yeast').valueAsNumber;
  var salt    = document.getElementById('salt').valueAsNumber;
  let myText = "";

// calculate and send data to span
  document.getElementById('intro').innerHTML = 'So you want to make '+ many + ' Brötchen of ' + weight + 'g each. You need:<p>';
  document.getElementById('pFlour').innerHTML = 'Flour: ' + ((many*weight) * 0.16).toFixed(0) + 'g';
  document.getElementById('pWater').innerHTML = 'Water: ' + ((many*weight) * 0.16).toFixed(0) + 'g';
  document.getElementById('Flour').innerHTML  = 'Flour: ' + (((many*weight) / (100 + water) * 100) - ((many*weight) * 0.16)  ).toFixed(0) + 'g';
  document.getElementById('Water').innerHTML  = 'Water: ' + ((many*weight) / (100 + water) * (water - 0) - ((many*weight) * 0.16)).toFixed(0) + 'g';
  document.getElementById('Salt').innerHTML   = 'Salt: ' + (((many*weight) / (100 + water) * 100)/100 * salt).toFixed(1) + 'g';
  document.getElementById('Yeast').innerHTML  = 'Yeast: ' + (((many*weight) / (100 + water) * 100)/100 * yeast).toFixed(2) + 'g (dry yeast, or fresh yeast x 3)';
  document.getElementById('More').innerHTML   = myText;
  }
</script>

<script>
document.write(many);
document.write(weight);
document.write(water);
document.write(malt);
document.write(yeast);
</script>


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