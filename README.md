<!DOCTYPE html>
<html lang="ja">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>撮影条件表示</title>

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

/* 横向き表示 */
.landscape{
    transform:rotate(90deg);
}

/* 結果表示 */
#resultText{
    display:grid;
    grid-template-columns: 1fr 1fr;
    gap:20px 80px;

    font-size:9vw;
    font-weight:bold;
    text-align:left;
}

/* 戻るボタン */
#backButton{
    position:absolute;
    right:10px;
    bottom:10px;

    width:auto;
    font-size:12px;
    padding:4px 8px;
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

    <p>M</p>
    <input type="number" id="M" step="any">

    <p>シャッタースピード</p>
    <input type="text" id="SS" placeholder="例: 1/1000">

    <p>F値</p>
    <input type="number" id="Fnum" step="0.1">

    <p>ISO</p>
    <input type="number" id="ISO">

    <button onclick="showResult()">表示</button>

</div>

<div id="resultArea">

    <div class="landscape">
        <div id="resultText"></div>
    </div>

    <button id="backButton" onclick="goBack()">
        戻る
    </button>

</div>

<script>

function showResult(){

    const lb   = document.getElementById("lb").value;
    const lc   = document.getElementById("lc").value;
    const f    = document.getElementById("f").value;
    const M    = document.getElementById("M").value;
    const SS   = document.getElementById("SS").value;
    const Fnum = document.getElementById("Fnum").value;
    const ISO  = document.getElementById("ISO").value;

    document.getElementById("inputArea").style.display = "none";
    document.getElementById("resultArea").style.display = "flex";

    document.getElementById("resultText").innerHTML =
    `
    <div>lb=${lb}</div>
    <div>SS=${SS}</div>

    <div>lc=${lc}</div>
    <div>F=${Fnum}</div>

    <div>f=${f}</div>
    <div>ISO=${ISO}</div>

    <div>M=${M}</div>
    <div></div>
    `;
}

function goBack(){

    document.getElementById("resultArea").style.display = "none";
    document.getElementById("inputArea").style.display = "block";
}

</script>

</body>
</html>
