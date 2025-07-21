# english-word
英単語学習サイト
<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <title>今日の英単語</title>
  <style>
    body {
      font-family: sans-serif;
      text-align: center;
      margin-top: 100px;
    }
    h1 {
      font-size: 2em;
      margin-bottom: 20px;
    }
    #word {
      font-size: 2em;
      font-weight: bold;
      margin-bottom: 10px;
    }
    #meaning {
      font-size: 1.2em;
      color: #333;
      display: none;
      margin-top: 10px;
    }
    button {
      margin-top: 20px;
      padding: 10px 20px;
      font-size: 1em;
      cursor: pointer;
    }
  </style>
</head>
<body>

  <h1>今日の英単語！</h1>
  <div id="word">Loading...</div>
  <div id="meaning">意味がここに表示されます</div>
  <button onclick="showMeaning()">答えを見る</button>

  <script>
    const words = [
      { word: "resilient", meaning: "回復力のある、弾力のある" },
      { word: "meticulous", meaning: "几帳面な、細かいことまで注意を払う" },
      { word: "serene", meaning: "穏やかな、静かな" },
      { word: "intricate", meaning: "複雑な、込み入った" },
      { word: "abundant", meaning: "豊富な、たくさんの" }
    ];

    // 今日の日付を使って毎日違う単語に
    const todayIndex = Math.floor(new Date().getTime() / (1000 * 60 * 60 * 24)) % words.length;
    const todayWord = words[todayIndex];

    document.getElementById("word").textContent = todayWord.word;

    function showMeaning() {
      const meaningDiv = document.getElementById("meaning");
      meaningDiv.textContent = todayWord.meaning;
      meaningDiv.style.display = "block";
    }
  </script>

</body>
</html>
