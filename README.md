# calculator
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Simple Calculator</title>
  <style>
    body { font-family: Arial, sans-serif; background: #f4f4f4; padding: 2rem; }
    h1 { text-align: center; }
    #calculator { max-width: 400px; margin: 2rem auto; background: white; padding: 1rem; border-radius: 8px; box-shadow: 0 0 10px rgba(0,0,0,0.1); }
    #display { width: 100%; font-size: 2rem; text-align: right; padding: 0.5rem; margin-bottom: 1rem; }
    #buttons { display: grid; grid-template-columns: repeat(4, 1fr); gap: 10px; }
    button { font-size: 1.5rem; padding: 1rem; border: none; background: #eee; border-radius: 5px; cursor: pointer; }
    button:hover { background: #ddd; }
    .clear { background: red; color: white; grid-column: span 4; }
  </style>
</head>
<body>
  <h1>Simple Calculator</h1>
  <div id="calculator">
    <input type="text" id="display" disabled>
    <div id="buttons">
      <button onclick="press('7')">7</button>
      <button onclick="press('8')">8</button>
      <button onclick="press('9')">9</button>
      <button onclick="press('/')">/</button>
      <button onclick="press('4')">4</button>
      <button onclick="press('5')">5</button>
      <button onclick="press('6')">6</button>
      <button onclick="press('*')">*</button>
      <button onclick="press('1')">1</button>
      <button onclick="press('2')">2</button>
      <button onclick="press('3')">3</button>
      <button onclick="press('-')">-</button>
      <button onclick="press('0')">0</button>
      <button onclick="press('.')">.</button>
      <button onclick="calculate()">=</button>
      <button onclick="press('+')">+</button>
      <button class="clear" onclick="clearDisplay()">C</button>
    </div>
  </div>

  <script>
    let display = document.getElementById('display');
    function press(value) {
      display.value += value;
    }
    function calculate() {
      try {
        display.value = eval(display.value);
      } catch (e) {
        display.value = 'Error';
      }
    }
    function clearDisplay() {
      display.value = '';
    }
  </script>
</body>
</html>
