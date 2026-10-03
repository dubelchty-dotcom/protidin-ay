<!DOCTYPE html>
<html lang="bn">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>প্রতিদিন আয়</title>

  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #0f1117;
      color: white;
    }

    .app {
      max-width: 480px;
      margin: auto;
      min-height: 100vh;
      padding: 20px;
    }

    .header {
      text-align: center;
      padding: 20px 0;
    }

    .header h1 {
      margin: 0;
      font-size: 28px;
    }

    .balance {
      margin-top: 20px;
      padding: 25px;
      border-radius: 20px;
      background: #1b2030;
      text-align: center;
    }

    .balance p {
      margin: 0 0 8px;
      color: #aeb6c8;
    }

    .balance h2 {
      margin: 0;
      font-size: 34px;
    }

    .menu {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 12px;
      margin-top: 20px;
    }

    button {
      border: 0;
      border-radius: 15px;
      padding: 18px 10px;
      font-size: 16px;
      color: white;
      background: #252b3b;
    }

    button:active {
      transform: scale(0.97);
    }

    .info {
      margin-top: 25px;
      padding: 18px;
      background: #181d29;
      border-radius: 15px;
      text-align: center;
      color: #c7ccda;
    }
  </style>
</head>

<body>

  <div class="app">

    <div class="header">
      <h1>💰 প্রতিদিন আয়</h1>
    </div>

    <div class="balance">
      <p>আপনার ব্যালেন্স</p>
      <h2>৳0.00</h2>
    </div>

    <div class="menu">
      <button>📋 কাজ</button>
      <button>👥 রেফার</button>
      <button>💸 Withdraw</button>
      <button>👤 Profile</button>
    </div>

    <div class="info">
      🎯 কাজ সম্পন্ন করুন এবং রিওয়ার্ড সংগ্রহ করুন।
    </div>

  </div>

</body>
</html>
