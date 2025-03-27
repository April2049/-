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
