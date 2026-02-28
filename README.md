<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>CSC Kerala Portal</title>
<meta name="viewport" content="width=device-width,initial-scale=1">

<style>
body{font-family:Segoe UI;margin:0;background:#eef2f7}
header{background:linear-gradient(90deg,#0a4da3,#0f75ff);color:#fff;padding:15px;text-align:center}
.container{padding:20px}
.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:15px}
.card{background:#fff;padding:18px;border-radius:12px;text-align:center;box-shadow:0 3px 12px rgba(0,0,0,.15);transition:.3s}
.card:hover{transform:translateY(-5px)}
a{text-decoration:none;color:#0a4da3;font-weight:bold}
h2{background:#0a4da3;color:#fff;padding:8px;border-radius:6px}
footer{background:#0a4da3;color:#fff;text-align:center;padding:12px;margin-top:40px}
input,button,select{padding:8px;margin:5px;border-radius:6px;border:1px solid #ccc}
button{background:#0a4da3;color:#fff;border:none;cursor:pointer}
button:hover{background:#083a7c}
#adminPanel{display:none;background:#fff;padding:15px;border-radius:10px;margin-top:15px}
</style>
</head>

<body>

<header>
<h1 id="title">CSC Kerala Portal</h1>
<p id="subtitle">All Services in One Platform</p>

<select onchange="changeLang(this.value)">
<option value="en">English</option>
<option value="ml">Malayalam</option>
</select>
</header>

<div class="container">

<!-- SEARCH -->
<input type="text" id="search" placeholder="Search Service..." onkeyup="searchService()">

<!-- LOGIN -->
<div id="loginBox">
<h2>Login</h2>
<input id="user" placeholder="Username">
<input id="pass" type="password" placeholder="Password">
<button onclick="login()">Login</button>
<p id="loginMsg"></p>
</div>

<!-- ADMIN PANEL -->
<div id="adminPanel">
<h2>Admin Panel</h2>
<p>Welcome Admin ✅</p>
<button onclick="logout()">Logout</button>
</div>

<!-- SERVICES -->
<h2>India Services</h2>
<div class="grid" id="services">

<div class="card"><a href="https://uidai.gov.in" target="_blank">Aadhaar</a></div>
<div class="card"><a href="https://www.incometax.gov.in" target="_blank">Income Tax</a></div>
<div class="card"><a href="https://www.passportindia.gov.in" target="_blank">Passport</a></div>
<div class="card"><a href="https://parivahan.gov.in" target="_blank">Driving Licence</a></div>
<div class="card"><a href="https://www.irctc.co.in" target="_blank">Railway</a></div>
<div class="card"><a href="https://www.epfindia.gov.in" target="_blank">EPFO</a></div>

</div>

<h2>Kerala Services</h2>
<div class="grid">

<div class="card"><a href="https://edistrict.kerala.gov.in" target="_blank">eDistrict</a></div>
<div class="card"><a href="https://civilsupplieskerala.gov.in" target="_blank">Ration Card</a></div>
<div class="card"><a href="https://keralapsc.gov.in" target="_blank">PSC</a></div>
<div class="card"><a href="https://ksmart.lsgkerala.gov.in" target="_blank">KSMART</a></div>
<div class="card"><a href="https://erekha.kerala.gov.in" target="_blank">Land Records</a></div>

</div>

<h2>Banking</h2>
<div class="grid">
<div class="card"><a href="https://www.onlinesbi.sbi" target="_blank">SBI</a></div>
<div class="card"><a href="https://canarabank.com" target="_blank">Canara Bank</a></div>
<div class="card"><a href="https://www.unionbankofindia.co.in" target="_blank">Union Bank</a></div>
</div>

<!-- SERVICE FORM -->
<h2>Service Request</h2>

<form onsubmit="submitForm(event)">
<input placeholder="Name" required>
<input placeholder="Phone" required>
<input placeholder="Service Needed" required>
<button type="submit">Submit</button>
</form>

<p id="formMsg"></p>

</div>

<footer>
© 2026 CSC Kerala Portal
</footer>

<script>

/* SEARCH */
function searchService(){
let input=document.getElementById("search").value.toLowerCase();
let cards=document.querySelectorAll(".card");
cards.forEach(card=>{
card.style.display=card.innerText.toLowerCase().includes(input)?"block":"none";
});
}

/* LOGIN */
function login(){
let u=document.getElementById("user").value;
let p=document.getElementById("pass").value;

if(u==="admin" && p==="1234"){
document.getElementById("loginBox").style.display="none";
document.getElementById("adminPanel").style.display="block";
}else{
document.getElementById("loginMsg").innerText="Invalid Login";
}
}

function logout(){
location.reload();
}

/* FORM */
function submitForm(e){
e.preventDefault();
document.getElementById("formMsg").innerText="Request Submitted ✅";
}

/* LANGUAGE */
function changeLang(lang){

if(lang==="ml"){
title.innerText="സി എസ് സി കേരള പോർട്ടൽ";
subtitle.innerText="എല്ലാ സർവീസുകളും ഒരേ സ്ഥലത്ത്";
}
else{
title.innerText="CSC Kerala Portal";
subtitle.innerText="All Services in One Platform";
}

}
</script>

</body>
</html>
