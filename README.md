<!DOCTYPE html>
<html lang="bn">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>প্রতিদিন আয়</title>

  <style>
    *{box-sizing:border-box}
    body{
      margin:0;
      font-family:Arial,sans-serif;
      background:#0f1117;
      color:white;
    }
    .app{
      max-width:480px;
      margin:auto;
      min-height:100vh;
      padding:18px;
    }
    .top{
      text-align:center;
      margin:15px 0 20px;
    }
    .top h1{margin:0 0 6px}
    #userName{color:#aeb6c8}

    .balance{
      background:#1b2030;
      padding:25px;
      border-radius:20px;
      text-align:center;
    }
    .balance p{
      color:#aeb6c8;
      margin:0 0 8px;
    }
    .balance h2{
      margin:0;
      font-size:35px;
    }

    .menu{
      display:grid;
      grid-template-columns:1fr 1fr;
      gap:12px;
      margin-top:20px;
    }

    button{
      border:0;
      border-radius:15px;
      padding:20px 10px;
      font-size:16px;
      color:white;
      background:#252b3b;
    }
    button:active{transform:scale(.97)}

    #content{
      margin-top:20px;
      padding:20px;
      background:#181d29;
      border-radius:15px;
      display:none;
    }
  </style>
</head>

<body>

<div class="app">

  <div class="top">
    <h1>💰 প্রতিদিন আয়</h1>
    <div id="userName">Telegram User</div>
  </div>

  <div class="balance">
    <p>আপনার ব্যালেন্স</p>
    <h2>৳0.00</h2>
  </div>

  <div class="menu">
    <button onclick="showPage('tasks')">📋 কাজ</button>
    <button onclick="showPage('referral')">👥 রেফার</button>
    <button onclick="showPage('withdraw')">💸 Withdraw</button>
    <button onclick="showPage('profile')">👤 Profile</button>
  </div>

  <div id="content"></div>

</div>

<script>
  // Telegram Mini App থেকে ব্যবহারকারীর নাম নেওয়া
  const tg = window.Telegram && window.Telegram.WebApp;

  if (tg) {
    tg.ready();
    tg.expand();

    const user = tg.initDataUnsafe?.user;

    if (user) {
      let name = user.first_name || "User";

      if (user.last_name) {
        name += " " + user.last_name;
      }

      document.getElementById("userName").textContent =
        "👋 স্বাগতম, " + name;
    }
  }

  function showPage(page) {
    const content = document.getElementById("content");
    content.style.display = "block";

    if(page === "tasks"){
      content.innerHTML = `
        <h2>📋 আজকের কাজ</h2>
        <p>এখানে আপনার উপলব্ধ কাজগুলো দেখা যাবে।</p>
        <button>🎁 কাজ শুরু করুন</button>
      `;
    }

    if(page === "referral"){
      content.innerHTML = `
        <h2>👥 রেফারেল</h2>
        <p>বন্ধুদের আমন্ত্রণ করুন এবং রেফারেল বোনাস সংগ্রহ করুন।</p>
      `;
    }

    if(page === "withdraw"){
      content.innerHTML = `
        <h2>💸 Withdraw</h2>
        <p>আপনার ব্যালেন্স থেকে Withdraw request দেওয়ার ব্যবস্থা এখানে থাকবে।</p>
      `;
    }

    if(page === "profile"){
      content.innerHTML = `
        <h2>👤 Profile</h2>
        <p>Telegram থেকে আপনার তথ্য এখানে দেখা যাবে।</p>
      `;
    }
  }
</script>

</body>
</html>
