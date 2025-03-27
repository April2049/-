<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>生日快乐，洁儒！</title>
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body, html {
      width: 100%;
      height: 100%;
      font-family: 'Arial Rounded MT Bold', sans-serif;
      overflow: hidden;
    }
    .page {
      display: none;
      width: 100%;
      height: 100%;
      position: absolute;
      top: 0;
      left: 0;
    }
    .active {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: 2rem;
    }
    #page1 {
      background: linear-gradient(to bottom, #ff004f, #ffcccb);
      color: white;
    }
    .pdd-box {
      background-color: #fff;
      color: #ff004f;
      padding: 2rem;
      border-radius: 1.5rem;
      text-align: center;
      box-shadow: 0 4px 12px rgba(0,0,0,0.2);
      animation: pop 0.6s ease;
    }
    .pdd-box h1 {
      font-size: 2rem;
      margin-bottom: 1rem;
    }
    .pdd-box p {
      font-size: 1.2rem;
      margin-bottom: 2rem;
    }
    .pdd-box button {
      background-color: #ff004f;
      color: #fff;
      border: none;
      padding: 0.8rem 1.5rem;
      border-radius: 1rem;
      font-size: 1.1rem;
      cursor: pointer;
    }

    @keyframes pop {
      0% { transform: scale(0.6); opacity: 0; }
      100% { transform: scale(1); opacity: 1; }
    }

    #page2 {
      background: linear-gradient(135deg, #ffe6f0, #d6f5ff);
      color: #333;
      flex-direction: column;
      align-items: center;
      padding: 2rem;
      overflow-y: auto;
    }

    .title {
      font-size: 2.2rem;
      font-weight: bold;
      margin-bottom: 1rem;
      animation: float 2s ease-in-out infinite;
    }

    @keyframes float {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-6px); }
    }

    .nickname {
      font-size: 1rem;
      color: #ff3399;
      margin-bottom: 1.2rem;
    }

    .wish {
      background-color: #fff;
      padding: 1.5rem;
      border-radius: 1rem;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      max-width: 480px;
      line-height: 1.6;
      text-align: center;
      margin-bottom: 2rem;
    }

    .next-btn {
      padding: 0.6rem 1.2rem;
      font-size: 1rem;
      border: none;
      border-radius: 1rem;
      background-color: #ff6699;
      color: white;
      cursor: pointer;
    }
  </style>
</head>
<body>

  <div class="page active" id="page1">
    <div class="pdd-box">
      <h1>🎁 恭喜你获得生日惊喜红包 🎁</h1>
      <p>点开看看谁给你送了祝福吧～</p>
      <button onclick="goToPage(2)">立即开启</button>
    </div>
  </div>

  <div class="page" id="page2">
    <div class="title">🎉 生日快乐，洁儒！ 🎉</div>
    <div class="nickname">aka 圆圆 / 水牛 / 莽夫</div>
    <div class="wish">
      又又又又又生日快乐啦！！！！！<br>
      可惜不能和你一起过 T^T<br><br>
      Anyway，祝你新的一岁：<br>
      笑得比花甜，头疼脑热 say byebye，<br>
      事业顺畅又不卷，朋友成天在身旁，<br>
      最好桃花找上门（非烂桃花），<br>
      心态王者，躺赢就行！<br><br>
      爱与真诚，相约相伴～❤️
    </div>
    <button class="next-btn" onclick="goToPage(3)">🎮 打个游戏再继续！</button>
  </div>
  <style>
    #page3 {
      background: #ffe;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }

    .game-board {
      display: grid;
      grid-template-columns: repeat(3, 100px);
      grid-gap: 20px;
      margin-top: 2rem;
    }

    .hole {
      width: 100px;
      height: 100px;
      background: #ddd;
      border-radius: 50%;
      overflow: hidden;
      position: relative;
    }

    .mole {
      width: 100%;
      height: 100%;
      object-fit: cover;
      border-radius: 50%;
      cursor: pointer;
      position: absolute;
      top: 0;
      left: 0;
      animation: popUp 0.2s ease;
    }

    @keyframes popUp {
      from { transform: scale(0.3); opacity: 0; }
      to { transform: scale(1); opacity: 1; }
    }

    .score-board {
      margin-top: 1rem;
      font-size: 1.2rem;
    }

    .game-btn {
      margin-top: 1.2rem;
      padding: 0.5rem 1.2rem;
      background: #f36;
      border: none;
      border-radius: 0.8rem;
      color: white;
      font-weight: bold;
      cursor: pointer;
    }
  </style>

  <div class="page" id="page3">
    <h2>🐹 打地鼠小游戏 🐹</h2>
    <div class="score-board">得分: <span id="score">0</span> ｜剩余时间: <span id="timer">15</span>s</div>
    <div class="game-board" id="board"></div>
    <button class="game-btn" onclick="startGame()">开始游戏</button>
    <button class="game-btn" onclick="goToPage(4)">看照片集锦 📸</button>
  </div>

  <script>
    const moleImgs = [
      "7e4d4c247603941b4dc5f46a73d5f16.jpg",
      "97bd3a9c3484370a0b7abf04eb1582b.jpg",
      "491dea697278a7f9904cccaaa2edc96.jpg",
      "ebe41c32432cab7f0e90cff2208efeb.jpg"
    ];

    let score = 0;
    let time = 15;
    let timerInterval, moleInterval;

    function startGame() {
      score = 0;
      time = 15;
      document.getElementById("score").innerText = score;
      document.getElementById("timer").innerText = time;

      const board = document.getElementById("board");
      board.innerHTML = '';
      for (let i = 0; i < 9; i++) {
        const hole = document.createElement("div");
        hole.classList.add("hole");
        board.appendChild(hole);
      }

      timerInterval = setInterval(() => {
        time--;
        document.getElementById("timer").innerText = time;
        if (time <= 0) endGame();
      }, 1000);

      moleInterval = setInterval(showMole, 600);
    }

    function showMole() {
      const holes = document.querySelectorAll(".hole");
      holes.forEach(h => h.innerHTML = '');
      const i = Math.floor(Math.random() * holes.length);
      const img = document.createElement("img");
      img.src = moleImgs[Math.floor(Math.random() * moleImgs.length)];
      img.classList.add("mole");
      img.onclick = () => {
        score++;
        document.getElementById("score").innerText = score;
        img.remove();
      };
      holes[i].appendChild(img);
    }

    function endGame() {
      clearInterval(timerInterval);
      clearInterval(moleInterval);
      alert("游戏结束！你的得分是：" + score);
    }
  </script>
