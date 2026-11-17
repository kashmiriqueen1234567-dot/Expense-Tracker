<!DOCTYPE html>
<html>
<head>
<title>Mera Kharcha - Expense Tracker</title>
<style>
body { font-family: Arial; background: #f2f2f2; text-align: center; }
.box { background: white; width: 90%; max-width: 400px; margin: 20px auto; padding: 20px; border-radius: 15px; }
input, select { width: 90%; padding: 10px; margin: 5px; border-radius: 8px; border: 1px solid #ccc; }
button { background: #4CAF50; color: white; padding: 10px 20px; border: none; border-radius: 8px; }
li { background: #eee; padding: 10px; margin: 5px; list-style: none; border-radius: 8px; }
</style>
</head>
<body>

<div class="box">
<h2>💰 Mera Kharcha Tracker</h2>
<h3>Total Kharcha: Rs. <span id="total">0</span></h3>

<input type="text" id="name" placeholder="Kis cheez pe kharcha? Eg: Khana">
<input type="number" id="amount" placeholder="Kitne paise? Eg: 200">

<select id="category">
<option>Khana</option>
<option>Bus / Petrol</option>
<option>Books</option>
<option>Shopping</option>
<option>Other</option>
</select>

<br><br>
<button onclick="addExpense()">Add Karo +</button>

<ul id="list"></ul>
</div>

<script>
let total = 0;
function addExpense() {
  let name = document.getElementById("name").value;
  let amount = document.getElementById("amount").value;
  let cat = document.getElementById("category").value;

  if(name == "" || amount == "") {
    alert("Pehle naam aur paise likho!");
    return;
  }

  total = total + Number(amount);
  document.getElementById("total").innerText = total;

  let li = document.createElement("li");
  li.innerText = name + " - Rs." + amount + " (" + cat + ")";
  document.getElementById("list").appendChild(li);

  document.getElementById("name").value = "";
  document.getElementById("amount").value = "";
}
</script>

</body>
</html># Expense-Tracker