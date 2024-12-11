# Calculator-demo <hr>
 This is my first git repository,using basic html and css make a Calculator.  
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Simple Calculator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f0f4f8;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }
    .calculator {
      background: #fff;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
      width: 300px;
    }
    .display {
      width: 100%;
      height: 50px;
      background: #e9ecef;
      border: none;
      border-radius: 5px;
      font-size: 1.5rem;
      text-align: right;
      padding: 5px 10px;
      margin-bottom: 15px;
    }
    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
    }
    button {
      height: 50px;
      font-size: 1.2rem;
      border: none;
      border-radius: 5px;
      background: #007bff;
      color: white;
      cursor: pointer;
      transition: background 0.2s;
    }
    button:hover {
      background: #0056b3;
    }
    .operator {
      background: #ffc107;
    }
    .operator:hover {
      background: #e0a800;
    }
  </style>
</head>
<body>
  <div class="calculator">
    <input type="text" class="display" id="display" disabled>
    <div class="buttons">
      <button onclick="appendValue('7')">7</button>
      <button onclick="appendValue('8')">8</button>
      <button onclick="appendValue('9')">9</button>
      <button class="operator" onclick="appendValue('/')">/</button>
      <button onclick="appendValue('4')">4</button>
      <button onclick="appendValue('5')">5</button>
      <button onclick="appendValue('6')">6</button>
      <button class="operator" onclick="appendValue('*')">*</button>
      <button onclick="appendValue('1')">1</button>
      <button onclick="appendValue('2')">2</button>
      <button onclick="appendValue('3')">3</button>
      <button class="operator" onclick="appendValue('-')">-</button>
      <button onclick="appendValue('0')">0</button>
      <button onclick="appendValue('.')">.</button>
      <button onclick="calculate()">=</button>
      <button class="operator" onclick="appendValue('+')">+</button>
      <button onclick="clearDisplay()" style="grid-column: span 4;">Clear</button>
    </div>
  </div>

  <script>
    function appendValue(value) {
      document.getElementById('display').value += value;
    }
    function clearDisplay() {
      document.getElementById('display').value = '';
    }
    function calculate() {
      try {
        const result = eval(document.getElementById('display').value);
        document.getElementById('display').value = result;
      } catch {
        document.getElementById('display').value = 'Error';
      }
    }
  </script>
</body>
</html>
