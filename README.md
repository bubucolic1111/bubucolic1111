<!DOCTYPE html>
<html lang="zh-Hant">
<head>
  <meta charset="UTF-8">
  <title>TOEIC 倒數時鐘</title>
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/flipdown@0.3.2/dist/flipdown.min.css">
  <style>
    body { font-family: sans-serif; background: #f4f4f4; text-align: center; padding: 2em; }
    h1 { color: #ff8800; }
  </style>
</head>
<body>
  <h1>🕒 TOEIC 倒數時鐘</h1>
  <div id="flipdown" class="flipdown"></div>

  <script src="https://cdn.jsdelivr.net/npm/flipdown@0.3.2/dist/flipdown.min.js"></script>
  <script>
    // 設定考試日：2025/7/27 00:00
    var examDate = new Date("2025-07-27T00:00:00").getTime() / 1000;

    new FlipDown(examDate)
      .start()
      .ifEnded(() => {
        document.body.innerHTML += '<p>📝 TOEIC 已經結束！</p>';
      });
  </script>
</body>
</html>
