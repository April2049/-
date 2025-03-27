<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>生日惊喜</title>
  <style>
    body, html {
      margin: 0;
      padding: 0;
      font-family: 'Arial Rounded MT Bold', sans-serif;
      width: 100%;
      height: 100%;
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
      background: linear-gradient(to bottom, #ff004f, #ffcccb);
      color: #fff;
      padding: 2rem;
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
    .page2 {
      background: linear-gradient(135deg, #ffe6f0, #d6f5ff);
      color: #333;
      flex-direction: column;
      align-items: center;
      padding: 2rem;
      overflow-y: auto;
    }
    .title {
      font-size: 2.5rem;
      font-weight: bold;
      margin-bottom: 1rem;
      animation: float 2s ease-in-out infinite;
    }
    .nickname {
      font-size: 1.2rem;
      color: #ff3399;
      margin-bottom: 2rem;
    }
    .wish {
      background-color: #fff;
      padding: 1.5rem;
      border-radius: 1rem;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      max-width: 500px;
      line-height: 1.6;
      text-align: center;
      margin-bottom: 2rem;
    }
    .next-btn {
      margin-top: 1.5rem;
      padding: 0.6rem 1.2rem;
      font-size: 1rem;
      border: none;
      border-radius: 1rem;
      background-color: #ff6699;
      color: white;
      cursor: pointer;
    }
    .page4 {
      display: none;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: 1rem;
      background-color: #000;
    }
    .album-container {
      width: 90%;
      max-width: 600px;
      position: relative;
    }
    .album-container img {
      width: 100%;
      border-radius: 1rem;
      box-shadow: 0 0 12px rgba(255,255,255,0.3);
      margin-bottom: 1rem;
      animation: fadeIn 1s ease-in-out;
    }
    @keyframes fadeIn {
      from { opacity: 0; transform: scale(0.95); }
      to { opacity: 1; transform: scale(1); }
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

  <div class="page page2" id="page2">
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
    <button class="next-btn" onclick="goToPage(4)">📸 看回忆照片集锦</button>
  </div>

  <div class="page page4" id="page4">
    <div class="album-container" id="album"></div>
  </div>

  <script>
    function goToPage(n) {
      document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
      document.getElementById('page' + n).classList.add('active');
    }

    const albumImgs = [
      '1c2fb066897ae0cf2230e3c348a5f11.jpg',
      '2f2138afbdfdc758c44289f00bf84ec.jpg',
      '41f3767c9bf570246b5e38c4ed180de.jpg',
      '47d821175970a7a67b822673323139b.jpg',
      '80a118a5a002ab1d449ad1df1b1512c.jpg',
      '213f37cd01a254a3d7263f95daab0e8.jpg',
      '816f7e02481dd9bfdb966a9da61bf13.jpg',
      '4289d719e279ad9b548e2bd2da60423.jpg',
      'd497b603d2924931ec68c42377f8614.jpg',
      'eebe5597020da1e93abdf0d7e56b558.jpg'
    ];

    let albumIndex = 0;
    function showAlbum() {
      const container = document.getElementById('album');
      const img = document.createElement('img');
      img.src = albumImgs[albumIndex];
      container.innerHTML = '';
      container.appendChild(img);
      albumIndex = (albumIndex + 1) % albumImgs.length;
    }

    setInterval(() => {
      if (document.getElementById('page4').classList.contains('active')) {
        showAlbum();
      }
    }, 2500);
  </script>
</body>
</html>
