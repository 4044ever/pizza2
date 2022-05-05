---
draft: false
title: Brötchen
url: broetchen
header_image:  "/uploads/broetchen01.jpg"
header_image_wp:  "/uploads/broetchen01.webp"
date: 2021-09-23T13:16:28.000Z
head_text: 
description: So mache ich derzeit meine klassischen Brötchen. Click For More...
summary: So mache ich derzeit meine klassischen Brötchen. Das Geheimrezept dabei ist **Zeit** und ein Vorteig.
---




So mache ich derzeit meine klassischen Brötchen. Das Geheimrezept dabei ist **Zeit** und ein Vorteig. Die Sonntagsbrötchen fange ich schon am Freitag an. Auch wichtig ist ein "Poolish" - ein Vorteig aus Mehl, Wasser im Verhältnis 1:1 und ganz wenig Hefe. 

{{< picture path="images/semmel.jpg" alt="Brötchen" width="500" >}}

## Also los geht's....

<div class="text-blue-700 text-xl">Die blauen Zahlen kannst du anpassen!</div>  

<div class="grid-container">
  <div class="grid-item">Wie viele Brötchen sollen es werden?</div>
  <div class="grid-item"><input class="text-blue-700 font-bold" type="number" id="howMany" name="howMany" value="12" onkeyup="showMsg()">Stück</div>
  <div class="grid-item">Einzelgewicht (normal 80g)</div>
  <div class="grid-item"><input class="text-blue-700 font-bold" type="number" id="weight" name="weight" value="80" onkeyup="showMsg()">g</div>
  <div class="grid-item">Mehl ist immer 100%</div>
  <div class="grid-item"></div>
  <div class="grid-item">Wasser (da muss man sich hinloten)</div>
  <div class="grid-item"><input class="text-blue-700 font-bold" type="number" id="water" name="water" value="60" onkeyup="showMsg()">%</div>
  <div class="grid-item">Salz (Standart 2%)</div>
  <div class="grid-item"><input class="text-blue-700 font-bold" type="number" id="salt" name="salt1" value="2" onkeyup="showMsg()">%</div>
  <div class="grid-item">Hefe (normal 0.70% Trockenhefe)</div>
  <div class="grid-item"><input class="text-blue-700 font-bold" type="number" id="yeast" name="yeast" value="0.70" onkeyup="showMsg()">%</div>
</div>

 
<span id="intro"><p></span>
**Poolish/Vorteig:**  
<span id="pFlour"></span><br>
<span id="pWater"></span><br>
Hefe, eine Messerspitze

**Hauptteig**  
Den ganzen Vorteig  
<span id="Flour"></span><br>
<span id="Water"></span><br>
<span id="Salt"></span><br>
<span id="Yeast"></span><br>
<span id="More"></span><br>

<hr>
Hier ist mein Zeitplan f&uuml;r Sonntagsbrötchen:

**Freitag, morgens:**  
Morgens mische ich kurz den Vorteig mit einem L&ouml;ffel von Hand. Nur soweit dass alles nass ist. Klumpen sind kein Problem. Das stelle ich dann abgedeckt an einen warmen Ort. Der Vorteig wird sich mindestens verdoppeln - das Gef&auml;ss sollte also ausrechend gross sein. 
Es wird am Ende voller Blasen sein und sauer riechen - so soll auch sein!

**Freitag, abends:**  
Ich knete kurz und grob zusammen, Vorteig, Mehl und Wasser. Wenn alles nass ist bleibt der Teig eine Stunde abgedeckt stehen. Das nennt sich Autolyse. In der Zeit baut sich schon das Gluten auf und man bracht später weniger kneten.
Dann kneten, erst die Hefe zugeben, und gegen Ende das Salz. Ich knete ca. 5 Minuten.  

Dann geht der Teig in eine flache Sch&uuml;ssel und ich ziehe und falte ca. alle 20 Minuten, f&uuml;r ca. 1,5 bis 2 Stunden. Der Teig sollte schon etwas anspringen und sich ein wenig vergr&ouml;ssern. 
Dann geht der Teig abgedeckt, am besten in einem verschlossenen Container in den K&uuml;hlschrank - bis Sonntag!

**Sonntag:**  
Direkt aus dem K&uuml;hlschrank steche ich die Teiglinge ab, forme eine Kugel. Wer will kann nun mit Mohn, Sesam usw. bestreuen. Dann lasse ich die Teiglinge direkt auf dem Blech noch ca. 40 Minuten ruhen.  
Dann kommt der Einschnitt (wenn Teig am Messer klebt war der Wasseranteil noch zu hoch, also 1-2% weniger das n&auml;chste mal)  
**Backen:**  
230°C Ober/Unterhitze - mit Dampf - 8 Minuten  
200°C Ober/Unterhitze - OHNE Dampf - 8 Minuten  

Dauert zwar lange, der eigentliche Arbeiteinsatz ist aber minimal - und geschmacklich wird es sich lohnen!


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
  document.getElementById('intro').innerHTML = 'Du m&ouml;chstest also '+ many + ' Brötchen &aacute; ' + weight + 'g machen, folgendes brauchst du dazu::<p>';
  document.getElementById('pFlour').innerHTML = 'Mehl: ' + ((many*weight) * 0.16).toFixed(0) + 'g';
  document.getElementById('pWater').innerHTML = 'Wasser: ' + ((many*weight) * 0.16).toFixed(0) + 'g';
  document.getElementById('Flour').innerHTML  = 'Mehl: ' + (((many*weight) / (100 + water) * 100) - ((many*weight) * 0.16)  ).toFixed(0) + 'g';
  document.getElementById('Water').innerHTML  = 'Wasser: ' + ((many*weight) / (100 + water) * (water - 0) - ((many*weight) * 0.16)).toFixed(0) + 'g';
  document.getElementById('Salt').innerHTML   = 'Salz: ' + (((many*weight) / (100 + water) * 100)/100 * salt).toFixed(1) + 'g';
  document.getElementById('Yeast').innerHTML  = 'Hefe: ' + (((many*weight) / (100 + water) * 100)/100 * yeast).toFixed(2) + 'g (Trockenhefe, oder frische Hefe x 3)';
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