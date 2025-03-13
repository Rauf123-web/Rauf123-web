# Rauf123-web

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel = "stylesheet" href = "styles.css">
    <title>Rauf Simple Calculator</title>
    <link rel = "stylesheet" href = "styles.css">
    <style>
        
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f0f0f0;
            margin: 0;
        }
        .calculator-container {
            text-align: center;
            background-color: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
        }
        /* Blinking effect using CSS animation */
        .title {
            font-size: 24px;
            margin-bottom: 20px;
            color: green;
            animation: blink 1s infinite step-start;
        }

        @keyframes blink {
            50% {
                opacity: 0;
            }
        }

        .calculator {
            display: inline-block;
            text-align: center;
        }
        .calculator input {
            width: 200px;
            height: 40px;
            font-size: 18px;
            text-align: right;
            padding: 10px;
            margin-bottom: 10px;
        }
        .calculator button {
            width: 40px;
            height: 40px;
            font-size: 18px;
            margin: 5px;
            cursor: pointer;
            background-color: #f0f0f0;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        .calculator button:hover {
            background-color: #ddd;
        }
        .calculator button:active {
            background-color: #bbb;
        }
        .calculator button.clear {
            width: 85px;
        }
        .calculator button.full-width {
            width: 100%;
        }
    </style>
    
</head>
<body>
    <div class="calculator-container">
        <div class="title">Rauf Simple Calculator</div>
        <div class="calculator">
            <input id="display" type="text" disabled>
            <div>
                <button onclick="appendToDisplay('7')">7</button>
                <button onclick="appendToDisplay('8')">8</button>
                <button onclick="appendToDisplay('9')">9</button>
                <button onclick="appendToDisplay('/')">/</button>
            </div>
            <div>
                <button onclick="appendToDisplay('4')">4</button>
                <button onclick="appendToDisplay('5')">5</button>
                <button onclick="appendToDisplay('6')">6</button>
                <button onclick="appendToDisplay('*')">*</button>
            </div>
            <div>
                <button onclick="appendToDisplay('1')">1</button>
                <button onclick="appendToDisplay('2')">2</button>
                <button onclick="appendToDisplay('3')">3</button>
                <button onclick="appendToDisplay('-')">-</button>
            </div>
            <div>
                <button onclick="appendToDisplay('0')">0</button>
                <button onclick="appendToDisplay('.')">.</button>
                <button class="clear" onclick="clearDisplay()">C</button>
                <button onclick="appendToDisplay('+')">+</button>
            </div>
            <div>
                <button class="full-width" onclick="calculateResult()">=</button>
            </div>
        </div>
    </div>

    <script>

        // Function to append numbers and operators to the display
        function appendToDisplay(value) {
            document.getElementById('display').value += value;
        }

        // Function to clear the display
        function clearDisplay() {
            document.getElementById('display').value = '';
        }

        // Function to calculate the result
        function calculateResult() {
            let display = document.getElementById('display');
            try {
                // Use eval to evaluate the expression
                display.value = eval(display.value);
            } catch (error) {
                display.value = 'Error';
            }
        }
    </script>
    <script src = "index.js"></script>
</body>
</html>

 
