<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>BUSINESS REPORT Hub</title>

<style>
body {
font-family: Arial;
margin: 0;
background: #f4f6fb;
text-align: center;
}

header {
background: #4b49ac;
color: white;
padding: 20px;
}

section {
padding: 30px;
}

.card {
background: white;
padding: 20px;
margin: 20px;
border-radius: 10px;
box-shadow: 0 0 10px rgba(0,0,0,0.1);
}

input, select {
padding: 10px;
width: 80%;
margin: 8px;
}

button {
padding: 12px 25px;
border: none;
border-radius: 5px;
cursor: pointer;
background: #25D366;
color: white;
}

.payment {
background: orange;
}

.total {
font-size: 18px;
font-weight: bold;
color: green;
}
</style>
</head>

<body>

<header>
<h1>BUSINESS REPORT Hub</h1>
<p>Loan & Business Project Report Services</p>
</header>

<section>

<div class="card">
<h2>Select Plan</h2>

<select id="price" onchange="calculateGST()">
<option value="2999">Basic Plan - ₹2999 + GST</option>
<option value="4999">Advance Plan - ₹4999 + GST</option>
</select>

<p id="gst"></p>
<p class="total" id="total"></p>

</div>

<div class="card">
<h2>Order Project Report</h2>

<input type="text" id="name" placeholder="Your Name"><br>
<input type="text" id="mobile" placeholder="Mobile Number"><br>
<input type="text" id="business" placeholder="Business Type"><br>

<button onclick="sendWhatsApp()">Send Order on WhatsApp</button>

<br><br>

<button class="payment" onclick="payUPI()">
Pay Advance
</button>

</div>

</section>

<script>

function calculateGST() {

let price = document.getElementById("price").value;
let gst = price * 0.18;
let total = Number(price) + gst;

document.getElementById("gst").innerText = "GST (18%): ₹" + gst.toFixed(0);
document.getElementById("total").innerText = "Total Amount: ₹" + total.toFixed(0);

}

calculateGST();

function sendWhatsApp() {

let name = document.getElementById("name").value;
let mobile = document.getElementById("mobile").value;
let business = document.getElementById("business").value;
let price = document.getElementById("price").value;

let gst = price * 0.18;
let total = Number(price) + gst;

let message = `Hello, I want Project Report
Name: ${name}
Mobile: ${mobile}
Business: ${business}
Plan Price: ₹${price}
GST: ₹${gst.toFixed(0)}
Total: ₹${total.toFixed(0)}`;

window.open(`https://wa.me/916376576447?text=${encodeURIComponent(message)}`, "_blank");

}

function payUPI() {

window.open("upi://pay?pa=pramodvarma80031@axl&pn=Business Report Hub&cu=INR");

}

</script>

</body>
</html>
