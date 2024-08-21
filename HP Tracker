<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hit Point Counter</title>
    <style>
        body {
            background-color: black;
            color: white;
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .container {
            text-align: center;
            border: 2px solid white;
            padding: 20px;
            border-radius: 10px;
        }
        input {
            width: 50px;
            padding: 5px;
            margin: 5px;
            text-align: center;
            border: none;
            border-radius: 5px;
        }
        button {
            padding: 10px 20px;
            margin: 10px;
            background-color: #333;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        button:hover {
            background-color: #555;
        }
        .hp-bar {
            width: 100%;
            background-color: #555;
            border-radius: 5px;
            margin-bottom: 10px;
        }
        .hp-fill {
            height: 30px;
            background-color: green;
            width: 100%;
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Hit Point Counter</h1>
        
        <div class="hp-bar">
            <div id="hp-fill" class="hp-fill"></div>
        </div>
        
        <p>Max HP: <span id="max-hp">100</span></p>
        <p>Current HP: <span id="current-hp">100</span></p>

        <input type="number" id="damage-input" placeholder="Damage" value="0">
        <button onclick="dealDamage()">Deal Damage</button>
        
        <input type="number" id="heal-input" placeholder="Heal" value="0">
        <button onclick="heal()">Heal</button>

        <p>Set Max HP: <input type="number" id="max-hp-input" value="100">
        <button onclick="setMaxHP()">Set</button></p>
    </div>

    <script>
        let maxHP = 100;
        let currentHP = 100;

        function updateDisplay() {
            document.getElementById('max-hp').innerText = maxHP;
            document.getElementById('current-hp').innerText = currentHP;
            
            let hpPercentage = (currentHP / maxHP) * 100;
            document.getElementById('hp-fill').style.width = hpPercentage + '%';
            if (hpPercentage <= 25) {
                document.getElementById('hp-fill').style.backgroundColor = 'red';
            } else if (hpPercentage <= 50) {
                document.getElementById('hp-fill').style.backgroundColor = 'orange';
            } else {
                document.getElementById('hp-fill').style.backgroundColor = 'green';
            }
        }

        function dealDamage() {
            let damage = parseInt(document.getElementById('damage-input').value);
            currentHP = Math.max(currentHP - damage, 0); // Prevents HP from going below 0
            updateDisplay();
        }

        function heal() {
            let healAmount = parseInt(document.getElementById('heal-input').value);
            currentHP = Math.min(currentHP + healAmount, maxHP); // Prevents HP from exceeding maxHP
            updateDisplay();
        }

        function setMaxHP() {
            maxHP = parseInt(document.getElementById('max-hp-input').value);
            currentHP = Math.min(currentHP, maxHP); // Ensures current HP doesn't exceed new max HP
            updateDisplay();
        }

        updateDisplay(); // Initial display update
    </script>
</body>
</html>
