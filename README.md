<!DOCTYPE html>
<html lang="ja">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>値表示</title>

<style>
body{
    margin:0;
    font-family:sans-serif;
    background:white;
}

/* 入力画面 */
#inputArea{
    padding:20px;
}

input{
    width:100%;
    font-size:24px;
    padding:10px;
    margin-bottom:15px;
    box-sizing:border-box;
}

button{
    width:100%;
    font-size:24px;
    padding:15px;
}

/* 結果画面 */
#resultArea{
    display:none;
    width:100vw;
    height:100vh;

    justify-content:center;
    align-items:center;

    font-size:8vw;
    font-weight:bold;
    text-align:center;
    line-height:1.8;
}

/* 横向き表示 */
.landscape{
    transform:rotate(90deg);
}
</style>
</head>

<body>

<div id="inputArea">
    <p>lb</p>
    <input type="number" id="lb">

    <p>lc</p>
    <input type="number" id="lc">

    <p>f</p>
    <input type="number" id="f">

    <button onclick="showResult()">表示</button>
</div>

<div id="resultArea">
    <div id="resultText" class="landscape"></div>
</div>

<script>
function showResult(){

    const lb = document.getElementById("lb").value;
    const lc = document.getElementById("lc").value;
    const f  = document.getElementById("f").value;

    document.getElementById("inputArea").style.display = "none";

    document.getElementById("resultArea").style.display = "flex";

    document.getElementById("resultText").innerHTML =
        `lb = ${lb}<br>
         lc = ${lc}<br>
         f = ${f}`;
}
</script>

</body>
</html>
