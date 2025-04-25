<!DOCTYPE html><html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Mini Cassino - Slot Machine</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #111;
      color: #fff;
      text-align: center;
      padding: 40px;
    }
    .slot-machine {
      display: flex;
      justify-content: center;
      margin-bottom: 20px;
    }
    .reel {
      font-size: 60px;
      margin: 0 15px;
      width: 60px;
      height: 60px;
      background: #222;
      border-radius: 10px;
      display: flex;
      justify-content: center;
      align-items: center;
    }
    button {
      padding: 12px 24px;
      font-size: 18px;
      border: none;
      border-radius: 8px;
      background: #f39c12;
      color: white;
      cursor: pointer;
    }
    #balance {
      margin-bottom: 20px;
      font-size: 20px;
    }
    .win {
      color: #2ecc71;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <h1>Caça-Níqueis Online</h1>
  <div id="balance">Saldo: 100 moedas</div>
  <div class="slot-machine">
    <div class="reel" id="reel1">?</div>
    <div class="reel" id="reel2">?</div>
    <div class="reel" id="reel3">?</div>
  </div>
  <button onclick="spin()">Girar (5 moedas)</button>
  <div id="result"></div>  <script>
    let balance = 100;
    const symbols = ["🍒", "🍋", "🍇", "🔔", "💎"];

    function spin() {
      if (balance < 5) {
        alert("Saldo insuficiente!");
        return;
      }

      balance -= 5;
      document.getElementById("balance").innerText = `Saldo: ${balance} moedas`;
      const r1 = symbols[Math.floor(Math.random() * symbols.length)];
      const r2 = symbols[Math.floor(Math.random() * symbols.length)];
      const r3 = symbols[Math.floor(Math.random() * symbols.length)];

      document.getElementById("reel1").innerText = r1;
      document.getElementById("reel2").innerText = r2;
      document.getElementById("reel3").innerText = r3;

      if (r1 === r2 && r2 === r3) {
        balance += 20;
        document.getElementById("result").innerHTML = `<p class='win'>VOCÊ GANHOU! +20 moedas</p>`;
      } else {
        document.getElementById("result").innerHTML = "";
      }
      document.getElementById("balance").innerText = `Saldo: ${balance} moedas`;
    }
  </script></body>
</html>
