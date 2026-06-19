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
    margin-top:10px;
}

/* 結果画面 */
#resultArea{
    display:none;
    width:100vw;
    height:100vh;
    justify-content:center;
    align-items:center;
    position:relative;
}

/* 数値表示を横向き */
.landscape{
    transform:rotate(90deg);
    text-align:center;
}

/* 結果文字 */
#resultText{
    font-size:15vw;
    font-weight:bold;
    line-height:1.4;
}

/* 戻るボタン */
#backButton{
    position:fixed;
    top:10px;
    right:10px;

    width:auto;
    padding:12px 8px;

    font-size:20px;

    writing-mode:vertical-rl;

    z-index:1000;
}
</style>
</head>

<body>

<!-- 入力画面 -->
<div id="inputArea">

    <p>lb</p>
    <input type="number" id="lb">

    <p>lc</p>
    <input type="number" id="lc">

    <p>f</p>
    <input type="number" id="f">

    <button onclick="showResult()">表示</button>

</div>

<!-- 結果画面 -->
<div id="resultArea">

    <button id="backButton" onclick="goBack()">
        戻る
    </button>

    <div class="landscape">
        <div id="resultText"></div>
    </div>

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

function goBack(){

    document.getElementById("resultArea").style.display = "none";
    document.getElementById("inputArea").style.display = "block";

    /* 入力欄を毎回空にする場合は下を有効化
    document.getElementById("lb").value = "";
    document.getElementById("lc").value = "";
    document.getElementById("f").value = "";
    */
}

</script>

</body>
</html>
