<!DOCTYPE html>

<html>

<head>

&#x20; <title>My Calculator</title>

&#x20; <meta name="viewport" content="width=device-width, initial-scale=1.0">



&#x20; <style>

&#x20;   body {

&#x20;     margin: 0;

&#x20;     min-height: 100vh;

&#x20;     display: flex;

&#x20;     justify-content: center;

&#x20;     align-items: center;

&#x20;     background: #222;

&#x20;     font-family: Arial, sans-serif;

&#x20;   }



&#x20;   .calculator {

&#x20;     width: 300px;

&#x20;     padding: 20px;

&#x20;     border-radius: 20px;

&#x20;     background: #111;

&#x20;     box-shadow: 0 10px 30px rgba(0,0,0,0.5);

&#x20;   }



&#x20;   #display {

&#x20;     width: 100%;

&#x20;     height: 70px;

&#x20;     box-sizing: border-box;

&#x20;     margin-bottom: 15px;

&#x20;     padding: 10px;

&#x20;     border: none;

&#x20;     border-radius: 12px;

&#x20;     background: #333;

&#x20;     color: white;

&#x20;     font-size: 30px;

&#x20;     text-align: right;

&#x20;   }



&#x20;   .buttons {

&#x20;     display: grid;

&#x20;     grid-template-columns: repeat(4, 1fr);

&#x20;     gap: 10px;

&#x20;   }



&#x20;   button {

&#x20;     height: 60px;

&#x20;     border: none;

&#x20;     border-radius: 12px;

&#x20;     font-size: 22px;

&#x20;     cursor: pointer;

&#x20;   }



&#x20;   button:active {

&#x20;     transform: scale(0.95);

&#x20;   }



&#x20;   .operator {

&#x20;     background: #ff9500;

&#x20;     color: white;

&#x20;   }



&#x20;   .clear {

&#x20;     background: #d9534f;

&#x20;     color: white;

&#x20;   }



&#x20;   .equal {

&#x20;     background: #28a745;

&#x20;     color: white;

&#x20;   }

&#x20; </style>

</head>



<body>



&#x20; <div class="calculator">

&#x20;   <input type="text" id="display" value="0" readonly>



&#x20;   <div class="buttons">

&#x20;     <button class="clear" onclick="clearDisplay()">C</button>

&#x20;     <button onclick="deleteLast()">⌫</button>

&#x20;     <button class="operator" onclick="addOperator('%')">%</button>

&#x20;     <button class="operator" onclick="addOperator('/')">÷</button>



&#x20;     <button onclick="addNumber('7')">7</button>

&#x20;     <button onclick="addNumber('8')">8</button>

&#x20;     <button onclick="addNumber('9')">9</button>

&#x20;     <button class="operator" onclick="addOperator('\*')">×</button>



&#x20;     <button onclick="addNumber('4')">4</button>

&#x20;     <button onclick="addNumber('5')">5</button>

&#x20;     <button onclick="addNumber('6')">6</button>

&#x20;     <button class="operator" onclick="addOperator('-')">−</button>



&#x20;     <button onclick="addNumber('1')">1</button>

&#x20;     <button onclick="addNumber('2')">2</button>

&#x20;     <button onclick="addNumber('3')">3</button>

&#x20;     <button class="operator" onclick="addOperator('+')">+</button>



&#x20;     <button onclick="addNumber('0')">0</button>

&#x20;     <button onclick="addNumber('.')">.</button>

&#x20;     <button class="equal" onclick="calculate()">=</button>

&#x20;   </div>

&#x20; </div>



&#x20; <script>

&#x20;   let display = document.getElementById("display");



&#x20;   function addNumber(number) {

&#x20;     if (display.value === "0") {

&#x20;       display.value = number;

&#x20;     } else {

&#x20;       display.value += number;

&#x20;     }

&#x20;   }



&#x20;   function addOperator(operator) {

&#x20;     let last = display.value.slice(-1);



&#x20;     if ("+-\*/%".includes(last)) {

&#x20;       display.value = display.value.slice(0, -1) + operator;

&#x20;     } else {

&#x20;       display.value += operator;

&#x20;     }

&#x20;   }



&#x20;   function clearDisplay() {

&#x20;     display.value = "0";

&#x20;   }



&#x20;   function deleteLast() {

&#x20;     if (display.value.length > 1) {

&#x20;       display.value = display.value.slice(0, -1);

&#x20;     } else {

&#x20;       display.value = "0";

&#x20;     }

&#x20;   }



&#x20;   function calculate() {

&#x20;     try {

&#x20;       display.value = eval(display.value);

&#x20;     } catch {

&#x20;       display.value = "Error";

&#x20;     }

&#x20;   }

&#x20; </script>



</body>

</html>

