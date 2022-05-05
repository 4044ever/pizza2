---
title: "Oat Bread"
date: 2021-10-07T10:06:39+08:00
draft: true
url: oat-bread
summary: 
---

# Oat Bread

This recipe I found in a [German website](https://www.ploetzblog.de/2015/09/19/reines-haferflockenbrot/). It's a bit tricky to bake. The outcome should very very low gluten. To make it gluten free you need a gluten-free starter (I think you can develope an oat starter) and gluten free oats.

{{< figure src="/oat-bread.jpg" alt="Oat Bread" width="50%" >}}

<div class="grid-container">
  <div class="grid-item">How many bread you want?</div>
  <div class="grid-item"><input type="number" id="howMany" name="howMany" value="2" onkeyup="showMsg()">pieces</div>
  <div class="grid-item">Size per bread (typically ~500g)</div>
  <div class="grid-item"><input type="number" id="weight" name="weight" value="500" onkeyup="showMsg()">g</div>
  </div>



<span id="Flour"></span><br>
<span id="Water"></span><br>
<span id="Salt"></span><br>
<span id="Yeast"></span><br>


<script type="text/javascript">

window.addEventListener( "load", showMsg());

function showMsg(){


  var many = document.getElementById('howMany').valueAsNumber;
  var weight = document.getElementById('weight').valueAsNumber;
  var water = document.getElementById('water').valueAsNumber;
  var yeast = document.getElementById('yeast').valueAsNumber;
  var salt = document.getElementById('salt').valueAsNumber;
 

  document.getElementById('intro').innerHTML = 'So you want to make '+ many + ' pizza of ' + weight + 'g each, here is what you need:<p>';
  document.getElementById('Flour').innerHTML = 'Flour: ' + ((many*weight) / (100 + water) * 100).toFixed(0) + 'g';
  document.getElementById('Water').innerHTML = 'Water: ' + ((many*weight) / (100 + water) ).toFixed(0) + 'g';
  document.getElementById('Salt').innerHTML = 'Salt: ' + (((many*weight) / (100 + water) * 100)/100 * salt).toFixed(1) + 'g';
  document.getElementById('Oil').innerHTML = 'Oil: ' + (((many*weight) / (100 + water) * 100)/100 ).toFixed(1) + 'g';
  document.getElementById('Yeast').innerHTML = 'Yeast: ' + (((many*weight) / (100 + water) * 100)/100 * yeast).toFixed(2) + 'g';
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
