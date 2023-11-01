<!DOCTYPE html>
<html>
<head>
    <title>Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
        }

        .calculator {
            width: 300px;
            margin: 0 auto;
            border: 1px solid #ccc;
            border-radius: 5px;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
            padding: 10px;
        }

        .screen {
            height: 40px;
            border: 1px solid #ccc;
            border-radius: 5px;
            text-align: right;
            padding: 5px;
            margin-bottom: 10px;
            font-size: 20px;
        }

        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            grid-gap: 5px;
        }

        .button {
            height: 50px;
            border: 1px solid #ccc;
            border-radius: 5px;
            text-align: center;
            font-size: 20px;
            cursor: pointer;
        }

        .button:hover {
            background-color: #eee;
        }

        .button.operator {
            background-color: #f2f2f2;
        }

        .button.clear {
            background-color: #ff9999;
        }

        .button.equal {
            background-color: #99ff99;
        }
    </style>
</head>
<body>
    <div class="calculator">
        <div class="screen" id="display">0</div>
        <div class="buttons">
            <div class="button" onclick="addToScreen('7')">7</div>
            <div class="button" onclick="addToScreen('8')">8</div>
            <div class="button" onclick="addToScreen('9')">9</div>
            <div class="button operator" onclick="addToScreen('+')">+</div>
            <div class="button" onclick="addToScreen('4')">4</div>
            <div class="button" onclick="addToScreen('5')">5</div>
            <div class="button" onclick="addToScreen('6')">6</div>
            <div class="button operator" onclick="addToScreen('-')">-</div>
            <div class="button" onclick="addToScreen('1')">1</div>
            <div class="button" onclick="addToScreen('2')">2</div>
            <div class="button" onclick="addToScreen('3')">3</div>
            <div class="button operator" onclick="addToScreen('*')">*</div>
            <div class="button" onclick="addToScreen('0')">0</div>
            <div class="button" onclick="addToScreen('.')">.</div>
            <div class="button clear" onclick="clearScreen()">C</div>
            <div class="button operator equal" onclick="calculate()">=</div>
        </div>
    </div>

    <script>
        let screenValue = "";

        function addToScreen(value) {
            screenValue += value;
            document.getElementById("display").innerText = screenValue;
        }

        function clearScreen() {
            screenValue = "";
            document.getElementById("display").innerText = "0";
        }

        function calculate() {
            try {
                screenValue = eval(screenValue);
                document.getElementById("display").innerText = screenValue;
            } catch (error) {
                document.getElementById("display").innerText = "Error";
                screenValue = "";
            }
        }
    </script>
</body>
</html>
