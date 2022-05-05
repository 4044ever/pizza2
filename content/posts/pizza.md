---
title: "Pizza Pizza Pizza!"
url: pizza
header_image:  "/uploads/pizza.jpg"
header_image_wp:  "/uploads/pizza.webp"
date: 2021-09-18T23:10:08+08:00
draft: false
summary: Your pizza dough calculator for Neapolitan style hand shaped pizza. 
---



Your pizza dough calculator for Neapolitan style hand shaped pizza. 

The recipe will adjust depending on how many pizza you plan to make, and how much gram dough per piece. For a &#x2300;~25-30cm/10-12" pizza I typically use 250g.

After you put the dough in the fridge you can leave it there for a few days. Taste is getting better after 1 day, 1-3 days is the optimum. I had some dough for 6 days and it was fine.

<div class="text-blue-700 text-xl">Change the blue numbers to your liking!</div>  

<div class="grid-container">
  <div class="grid-item">How many pizza you want?</div>
  <div class="grid-item"><input class="text-blue-700 font-bold" type="number" id="howMany" name="howMany" value="3" onkeyup="showMsg()">pieces</div>
  <div class="grid-item">Size per (typically 200-300g)</div>
  <div class="grid-item"><input class="text-blue-700 font-bold" type="number" id="weight" name="weight" value="250" onkeyup="showMsg()">g</div>
  <div class="grid-item">Flour in bakers math is always 100%</div>
  <div class="grid-item"></div>
  <div class="grid-item">Water (typically 60%)</div>
  <div class="grid-item"><input class="text-blue-700 font-bold" type="number" id="water" name="water" value="60" onkeyup="showMsg()">%</div>
  <div class="grid-item">Salt (typically 2%)</div>
  <div class="grid-item"><input class="text-blue-700 font-bold" type="number" id="salt" name="salt1" value="2" onkeyup="showMsg()">%</div>
  <div class="grid-item">Oil (optional) (typically 0-5%) </div>
  <div class="grid-item"><input class="text-blue-700 font-bold" type="number" id="oil" name="oil" value="0" onkeyup="showMsg()">%</div>
  <div class="grid-item">Yeast (typically 0.05% dry yeast)</div>
  <div class="grid-item"><input class="text-blue-700 font-bold" type="number" id="yeast" name="yeast" value="0.05" onkeyup="showMsg()">%</div>
</div>

 
<span id="intro"><p></span>
<span id="Flour"></span><br>
<span id="Water"></span><br>
<span id="Salt"></span><br>
<span id="Oil"></span><br>
<span id="Yeast"></span><br>
<span id="more"></span><br>


New to hand shaping? Think it's difficult? Well, it's easy with a **very relaxed dough**. And following that recipe and method it will be relaxed. Bake-with-Jack Jack has a nice video about the different techniques you can use:<p>

{{< youtube y57rDnAMVrQ >}}

Or why not make some more dough than you need and freeze them? Jack also explains how this is done:

{{< youtube w01ilX33u-A >}}

<script type="text/javascript">

window.addEventListener( "load", showMsg());

function showMsg(){


  var many = document.getElementById('howMany').valueAsNumber;
  var weight = document.getElementById('weight').valueAsNumber;
  var water = document.getElementById('water').valueAsNumber;
  var yeast = document.getElementById('yeast').valueAsNumber;
  var oil = document.getElementById('oil').valueAsNumber;
  var salt = document.getElementById('salt').valueAsNumber;
  let myText = "<p><hr><p>The method is simple, but takes some time.</p> <p>Mix all ingrediencies till smooth. Keep is covered at room temperature for 8-12 hours (depends really on your room temperature, I have 30°C in summer and 8 hours are fine). If you can do some stretch and folds (I can not because I leave it overnight). When ready do a stretch and fold, and after that place the dough covered in the fridge.</p><p>About 3 hours before you plan to make pizza take the dough from the fridge, dust with flour and make "+ many + " balls, "+ weight + "g each. Let them rest outside the fridge.<p>When you start making pizza you can them easily shape by hand. The dough will be very relaxed and easy to shape. Put your toppings and bake!";


 


  document.getElementById('intro').innerHTML = 'So you want to make '+ many + ' pizza of ' + weight + 'g each, here is what you need:<p>';
  document.getElementById('Flour').innerHTML = 'Flour: ' + ((many*weight) / (100 + water) * 100).toFixed(0) + 'g';
  document.getElementById('Water').innerHTML = 'Water: ' + ((many*weight) / (100 + water) * (water - oil)).toFixed(0) + 'g';
  document.getElementById('Salt').innerHTML = 'Salt: ' + (((many*weight) / (100 + water) * 100)/100 * salt).toFixed(1) + 'g';
  document.getElementById('Oil').innerHTML = 'Oil: ' + (((many*weight) / (100 + water) * 100)/100 * oil).toFixed(1) + 'g';
  document.getElementById('Yeast').innerHTML = 'Yeast: ' + (((many*weight) / (100 + water) * 100)/100 * yeast).toFixed(2) + 'g';
  document.getElementById('more').innerHTML = myText;
  }

</script>


<script>
document.write(many);
document.write(weight);
document.write(water);
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