<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>数値入力表示</title>
  <style>
    body {
      font-family: sans-serif;
      padding: 20px;
      background: #f5f5f5;
    }

    h1 {
      text-align: center;
      font-size: 24px;
    }

    .box {
      background: white;
      padding: 20px;
      border-radius: 12px;
      box-shadow: 0 2px 8px #ccc;
      max-width: 400px;
      margin: auto;
    }

    label {
      display: block;
      margin-top: 15px;
      font-size: 18px;
    }

    input {
      width: 100%;
      font-size: 20px;
      padding: 10px;
      margin-top: 5px;
      box-sizing: border-box;
    }

    .result {
      margin-top: 25px;
      font-size: 22px;
      line-height: 1.8;
      background: #eef;
      padding: 15px;
      border-radius: 10px;
    }
  </style>
</head>
<body>

  <h1>数値入力</h1>

  <div class="box">
    <label>
      lb =
      <input type="number" id="lb" oninput="updateDisplay()">
    </label>

    <label>
      lc =
      <input type="number" id="lc" oninput="updateDisplay()">
    </label>

    <label>
      f =
      <input type="number" id="f" oninput="updateDisplay()">
    </label>

    <div class="result" id="result">
      lb = <br>
      lc = <br>
      f =
    </div>
  </div>

  <script>
    function updateDisplay() {
      const lb = document.getElementById("lb").value;
      const lc = document.getElementById("lc").value;
      const f = document.getElementById("f").value;

      document.getElementById("result").innerHTML =
        `lb = ${lb}<br>
         lc = ${lc}<br>
         f = ${f}`;
    }
  </script>

</body>
</html>
