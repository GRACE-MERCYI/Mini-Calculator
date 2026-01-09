<img width="1024" height="768" alt="Image2" src="https://github.com/user-attachments/assets/6d80f20f-4d31-4fc0-9785-6b30f193d9f5" />
<img width="1024" height="768" alt="Image1" src="https://github.com/user-attachments/assets/38108b88-d14c-478b-814f-0aca7dcc1c54" />
CALCULATOR MINI-PROJECT
Source Code
index.html
<!DOCTYPE html>
<html>
<head>
<title>Calculator</title>
<link rel="stylesheet" href="style.css">
</head>
<body>
<div class="calculator">
<input type="text" id="result" readonly>
<div class="buttons">
<button onclick="clearResult()">C</button>
<button onclick="deleteLast()">DEL</button>
<button onclick="appendValue('/')">/</button>
<button onclick="appendValue('*')">*</button>
<button onclick="appendValue('7')">7</button>
<button onclick="appendValue('8')">8</button>
<button onclick="appendValue('9')">9</button>
<button onclick="appendValue('-')">-</button>
<button onclick="appendValue('4')">4</button>
<button onclick="appendValue('5')">5</button>
<button onclick="appendValue('6')">6</button>
<button onclick="appendValue('+')">+</button>
<button onclick="appendValue('1')">1</button>
<button onclick="appendValue('2')">2</button>
<button onclick="appendValue('3')">3</button>
<button onclick="calculate()">=</button>
<button onclick="appendValue('0')" class="zero">0</button>
<button onclick="appendValue('.')">.</button>
</div>
</div>
<script src="script.js"></script>
</body>
</html>
style.css
body {
display: flex;
justify-content: center;
align-items: center;
height: 100vh;
font-family: Arial;
background: #f2f2f2;
}
.calculator {
background: white;
padding: 20px;
border-radius: 10px;
box-shadow: 0 0 10px gray;
}
#result {
width: 100%;
height: 40px;
margin-bottom: 10px;
font-size: 18px;
text-align: right;
}
.buttons {
display: grid;
grid-template-columns: repeat(4, 60px);
gap: 10px;
}
button {
height: 45px;
font-size: 16px;
}
.zero {
grid-column: span 2;
}
script.js
let result = document.getElementById("result");

function appendValue(value) {
result.value += value;
}

function clearResult() {
result.value = "";
}

function deleteLast() {
result.value = result.value.slice(0, -1);
}

function calculate() {
try {
result.value = eval(result.value);
} catch {
result.value = "Error";
}
}
