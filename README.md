<!DOCTYPE html>
<html>
<head>
<title>PRO GAMER SENSI DASHBOARD</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>

body{
  margin:0;
  font-family:Arial;
  background:#020617;
  color:white;
}

/* TOP BAR */
.topbar{
  background:#020617;
  padding:15px;
  text-align:center;
  font-weight:bold;
  font-size:18px;
  letter-spacing:2px;
  border-bottom:1px solid #22c55e;
  box-shadow:0 0 15px #22c55e;
}

/* DASHBOARD GRID */
.container{
  display:grid;
  grid-template-columns:1fr;
  gap:15px;
  padding:15px;
}

/* CARD STYLE */
.card{
  background:#0f172a;
  padding:15px;
  border-radius:15px;
  box-shadow:0 0 10px #22c55e;
}

/* INPUT STYLE */
input{
  width:100%;
  padding:12px;
  margin-top:10px;
  border-radius:10px;
  border:none;
  background:#020617;
  color:#22c55e;
  box-shadow:0 0 8px #22c55e inset;
}

/* BUTTON */
button{
  width:100%;
  padding:14px;
  margin-top:15px;
  border:none;
  border-radius:12px;
  font-weight:bold;
  background:#22c55e;
  color:black;
  cursor:pointer;
  box-shadow:0 0 20px #22c55e;
}

button:hover{
  transform:scale(1.05);
}

/* OUTPUT */
.output{
  text-align:left;
  line-height:1.6;
  font-size:15px;
}

.highlight{
  color:#22c55e;
  font-weight:bold;
}

</style>
</head>

<body>

<div class="topbar">🔥 PRO GAMER CONTROL PANEL</div>

<div class="container">

<div class="card">
<h3>📱 Device Setup</h3>
<input id="device" placeholder="Device Name">
<input id="processor" type="number" placeholder="Processor Score">
<input id="ram" type="number" placeholder="RAM">
</div>

<div class="card">
<h3>⚙️ Performance</h3>
<input id="fps" type="number" placeholder="FPS">
<input id="dpi" type="number" placeholder="DPI">
<input id="storage" type="number" placeholder="Storage">
</div>

<div class="card">
<h3>🎯 Control</h3>
<input id="fire" type="number" placeholder="Fire Button %">
<button onclick="generate()">⚡ Generate Pro Sensi</button>
</div>

<div class="card output" id="output">
🚀 Your pro sensi will appear here...
</div>

</div>

<script>
function generate(){

let score = 150;

let device = document.getElementById("device").value.toLowerCase();
if(device.includes("iphone")) score += 20;
if(device.includes("samsung")) score += 15;
if(device.includes("vivo")) score += 10;

let proc = parseInt(document.getElementById("processor").value)||6000;
if(proc >= 8000) score += 30;
else if(proc >= 7000) score += 20;
else score -= 10;

let fps = parseInt(document.getElementById("fps").value)||60;
if(fps >= 90) score += 30;
else if(fps >= 60) score += 15;

let dpi = parseInt(document.getElementById("dpi").value)||380;
if(dpi >= 400) score += 10;

let ram = parseInt(document.getElementById("ram").value)||6;
if(ram >= 8) score += 12;

let fire = parseInt(document.getElementById("fire").value)||50;
if(fire <= 40) score += 10;

function cap(x){
 return Math.max(0, Math.min(200, Math.round(x)));
}

document.getElementById("output").innerHTML = `
🔥 <span class="highlight">PRO SETTINGS READY</span><br><br>

General: ${cap(score)}<br>
Red Dot: ${cap(score-10)}<br>
2x Scope: ${cap(score-25)}<br>
4x Scope: ${cap(score-40)}<br>
Sniper: ${cap(score-70)}<br>
Free Look: ${cap(score-50)}<br><br>

🎯 <span class="highlight">Fire:</span> ${fire}%<br>
📱 <span class="highlight">Device:</span> ${device.toUpperCase()}<br><br>

💀 Headshot Mode Activated
`;

}
</script>

</body>
</html>
