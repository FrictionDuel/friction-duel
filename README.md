<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Friction Duel 摩擦メーター ver.2.0</title>
    <style>
        body {font-family: Arial, sans-serif; background: black; color: #ff3300; text-align: center; padding: 50px;}
        h1 {font-size: 2.5em; margin: 20px;}
        button {font-size: 1.5em; padding: 15px 30px; background: #ff3300; color: white; border: none; border-radius: 10px; cursor: pointer;}
        button:hover {background: #ff5500;}
    </style>
</head>
<body>
    <h1>フリクションデュエル<br>運測定スタート！</h1>
    <button onclick="frictionMeter()">5秒で運を測る！</button>

    <script>
        function frictionMeter() {
            let a = prompt("【選択A】例：告白する");
            if (!a) return;
            let b = prompt("【選択B】例：しない");
            if (!b) return;
            
            let q1 = parseInt(prompt("Q1. " + a + " をやりたい度 (0-10)")) || 5;
            let q2 = parseInt(prompt("Q2. 失敗したら後悔しそう度 (0-10)")) || 5;
            let q3 = parseInt(prompt("Q3. 今すぐ決めろ！\nA寄り=+5 / 中間=0 / B寄り=-5")) || 0;
            
            let score = q1 - q2 + (q3 * 1.5);
            let rateA = Math.round(50 + score * 4);
            let A = Math.min(100, Math.max(0, rateA));
            let B = 100 - A;
            
            let result = a + " " + A + "% vs " + b + " " + B + "%\n";
            result += "最終予測 → " + (A > B ? a : b) + " 勝ち確🔥\n";
            result += "#FrictionDuel でシェアしてね！";
            
            alert(result);
        }
    </script>
</body>
</html>
