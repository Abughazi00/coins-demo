<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>TikTok Coins Demo</title>

  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: Arial, Tahoma, sans-serif;
    }

    body {
      background: #f5f5f7;
      color: #161823;
    }

    .demo-banner {
      background: #fff3cd;
      color: #664d03;
      text-align: center;
      padding: 9px;
      font-size: 13px;
      font-weight: 700;
      border-bottom: 1px solid #ffe69c;
    }

    header {
      height: 68px;
      background: #fff;
      border-bottom: 1px solid #eee;
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 0 6%;
      position: sticky;
      top: 0;
      z-index: 10;
    }

    .logo {
      font-size: 23px;
      font-weight: 900;
      letter-spacing: -1px;
    }

    .logo span {
      color: #fe2c55;
    }

    .support {
      color: #555;
      font-size: 14px;
    }

    main {
      max-width: 900px;
      margin: 45px auto;
      padding: 0 20px;
    }

    .hero {
      background: #fff;
      border-radius: 22px;
      padding: 38px 30px;
      box-shadow: 0 8px 30px rgba(0,0,0,.06);
      text-align: center;
    }

    .hero h1 {
      font-size: 31px;
      margin-bottom: 12px;
    }

    .hero p {
      color: #777;
      font-size: 15px;
      margin-bottom: 28px;
    }

    .search-box {
      max-width: 600px;
      margin: auto;
      display: flex;
      background: #f1f1f2;
      border: 1px solid #ddd;
      border-radius: 13px;
      overflow: hidden;
      direction: ltr;
    }

    .search-box input {
      flex: 1;
      border: none;
      background: transparent;
      outline: none;
      padding: 17px;
      font-size: 16px;
      direction: ltr;
    }

    .search-box button {
      border: none;
      background: #161823;
      color: white;
      padding: 0 27px;
      cursor: pointer;
      font-weight: bold;
      font-size: 15px;
    }

    .search-box button:hover {
      background: #333;
    }

    .result {
      display: none;
      margin-top: 30px;
      background: #fafafa;
      border: 1px solid #eee;
      border-radius: 17px;
      padding: 25px;
      text-align: right;
    }

    .profile {
      display: flex;
      align-items: center;
      gap: 15px;
      direction: rtl;
    }

    .avatar {
      width: 65px;
      height: 65px;
      border-radius: 50%;
      background: linear-gradient(135deg,#25f4ee,#fe2c55);
      display: flex;
      align-items: center;
      justify-content: center;
      color: white;
      font-size: 24px;
      font-weight: bold;
    }

    .profile h3 {
      margin-bottom: 5px;
    }

    .profile span {
      color: #888;
      font-size: 14px;
      direction: ltr;
      display: inline-block;
    }

    .verified {
      color: #20a4f3;
      margin-right: 5px;
    }

    .coin-card {
      margin-top: 22px;
      background: #161823;
      color: white;
      border-radius: 18px;
      padding: 25px;
    }

    .coin-title {
      color: #aaa;
      font-size: 13px;
      margin-bottom: 8px;
    }

    .coin-value {
      font-size: 34px;
      font-weight: 900;
    }

    .coin-value small {
      font-size: 15px;
      color: #aaa;
    }

    .packages {
      display: grid;
      grid-template-columns: repeat(3,1fr);
      gap: 15px;
      margin-top: 25px;
    }

    .package {
      background: white;
      border: 1px solid #eee;
      border-radius: 15px;
      padding: 20px;
      text-align: center;
      transition: .2s;
    }

    .package:hover {
      transform: translateY(-3px);
      box-shadow: 0 8px 20px rgba(0,0,0,.07);
    }

    .coin-icon {
      font-size: 25px;
      margin-bottom: 8px;
    }

    .package strong {
      display: block;
      font-size: 20px;
      margin-bottom: 6px;
    }

    .package span {
      color: #777;
      font-size: 13px;
    }

    .notice {
      margin-top: 25px;
      padding: 15px;
      background: #f0f8ff;
      border: 1px solid #d8edff;
      border-radius: 12px;
      color: #35627c;
      font-size: 13px;
      line-height: 1.7;
    }

    .error {
      display: none;
      margin-top: 20px;
      color: #d71945;
      background: #fff0f3;
      padding: 13px;
      border-radius: 10px;
      font-size: 14px;
    }

    .features {
      display: grid;
      grid-template-columns: repeat(3,1fr);
      gap: 18px;
      margin-top: 25px;
    }

    .feature {
      background: white;
      padding: 23px;
      border-radius: 17px;
      text-align: center;
      border: 1px solid #eee;
    }

    .feature .icon {
      font-size: 27px;
      margin-bottom: 12px;
    }

    .feature h3 {
      font-size: 16px;
      margin-bottom: 7px;
    }

    .feature p {
      color: #888;
      font-size: 12px;
      line-height: 1.6;
    }

    footer {
      text-align: center;
      padding: 30px 15px;
      color: #999;
      font-size: 12px;
    }

    @media(max-width:650px) {
      .packages,
      .features {
        grid-template-columns: 1fr;
      }

      .hero {
        padding: 28px 18px;
      }

      .hero h1 {
        font-size: 25px;
      }

      .search-box button {
        padding: 0 18px;
      }
    }
  </style>
</head>

<body>

  <div class="demo-banner">
    DEMO — هذه صفحة تجريبية غير رسمية وليست تابعة لـ TikTok
  </div>

  <header>
    <div class="logo">
      Tik<span>Tok</span> Coins
    </div>

    <div class="support">
      مركز العملات التجريبي
    </div>
  </header>

  <main>

    <section class="hero">

      <h1>البحث عن حساب</h1>

      <p>
        أدخل اسم المستخدم لعرض معلومات العملات التجريبية
      </p>

      <div class="search-box">
        <input
          id="username"
          type="text"
          placeholder="@username"
          autocomplete="off"
        >

        <button onclick="searchUser()">
          بحث
        </button>
      </div>

      <div id="error" class="error">
        يرجى إدخال اسم مستخدم صحيح.
      </div>

      <div id="result" class="result">

        <div class="profile">

          <div class="avatar" id="avatar">
            U
          </div>

          <div>
            <h3 id="displayName">
              User
            </h3>

            <span id="handle">
              @username
            </span>

            <span class="verified">
              ✓
            </span>
          </div>

        </div>

        <div class="coin-card">

          <div class="coin-title">
            الرصيد التجريبي
          </div>

          <div class="coin-value">
            <span id="balance">12,450</span>
            <small> Coins</small>
          </div>

        </div>

        <div class="packages">

          <div class="package">
            <div class="coin-icon">🪙</div>
            <strong>70</strong>
            <span>Coins</span>
          </div>

          <div class="package">
            <div class="coin-icon">🪙</div>
            <strong>350</strong>
            <span>Coins</span>
          </div>

          <div class="package">
            <div class="coin-icon">🪙</div>
            <strong>1,400</strong>
            <span>Coins</span>
          </div>

        </div>

        <div class="notice">
          هذه البيانات تجريبية لأغراض التصميم فقط ولا تمثل رصيداً
          حقيقياً أو بيانات فعلية من TikTok.
        </div>

      </div>

    </section>

    <section class="features">

      <div class="feature">
        <div class="icon">🔎</div>
        <h3>بحث المستخدم</h3>
        <p>
          البحث التجريبي عن اسم المستخدم وعرض الحساب.
        </p>
      </div>

      <div class="feature">
        <div class="icon">🪙</div>
        <h3>Coins</h3>
        <p>
          عرض رصيد العملات والباقة التجريبية.
        </p>
      </div>

      <div class="feature">
        <div class="icon">🛡️</div>
        <h3>Demo آمن</h3>
        <p>
          لا يتم طلب كلمة مرور أو رمز تحقق أو بيانات دخول.
        </p>
      </div>

    </section>

  </main>

  <footer>
    Demo UI — Not affiliated with TikTok
  </footer>


  <script>

    function searchUser() {

      const input = document.getElementById("username");
      const result = document.getElementById("result");
      const error = document.getElementById("error");

      let username = input.value.trim();

      if (!username) {
        result.style.display = "none";
        error.style.display = "block";
        return;
      }

      error.style.display = "none";

      username = username.replace(/^@/, "");

      const formattedName =
        username.charAt(0).toUpperCase() +
        username.slice(1);

      document.getElementById("displayName").textContent =
        formattedName;

      document.getElementById("handle").textContent =
        "@" + username;

      document.getElementById("avatar").textContent =
        username.charAt(0).toUpperCase();

      /*
        بيانات تجريبية فقط.
        لا يوجد اتصال بـ TikTok.
      */

      const fakeBalance =
        Math.floor(Math.random() * 90000) + 1000;

      document.getElementById("balance").textContent =
        fakeBalance.toLocaleString();

      result.style.display = "block";

      result.scrollIntoView({
        behavior: "smooth",
        block: "center"
      });
    }

    document
      .getElementById("username")
      .addEventListener("keydown", function(event) {

        if (event.key === "Enter") {
          searchUser();
        }

      });

  </script>

</body>
</html>
