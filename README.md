<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <title>Friction Duel 摩擦メーター ver.2.0</title>
    <style>body{font-family:Arial;color:#ff3300;background:black;}</style>
</head>
<body>
    <h1>🔥 Friction Duel 運測定スタート！</h1>
    <button onclick="frictionMeter()">5秒で測る！</button>
    <script>
        function frictionMeter() {
            let a = prompt("選択A（例: 告白する）");
            let b = prompt("選択B（例: しない）");
            let q1 = parseInt(prompt("Q1. " + a + "やりたい度 (0-10)")) || 5;
            let q2 = parseInt(prompt("Q2. 失敗後悔度 (0-10)")) || 5;
            let q3 = parseInt(prompt("Q3. 今すぐ決めろ！ A+5 中0 B-5")) || 0;
            let score = q1 - q2 + q3 * 1.5;
            let ratioA = Math.round(50 + score * 4);
            let finalA = Math.min(100, Math.max(0, ratioA));
            let finalB = 100 - finalA;
            alert(a + " " + finalA + "% vs " + b + " " + finalB + "%\n予測: " + (finalA > 50 ? a : b) + " 勝ち確🔥\n#FrictionDuel");
        }
    </script>
</body>
</html>
