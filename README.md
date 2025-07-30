........<!DOCTYPE html>
<html lang="bn">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Mustak Bank - মজা</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f4f6f8;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      margin: 0;
    }
    .container {
      background: white;
      padding: 30px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      width: 90%;
      max-width: 400px;
      text-align: center;
    }
    h1 {
      color: #d62828;
    }
    input {
      width: 100%;
      padding: 10px;
      margin: 10px 0;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    button {
      padding: 10px 20px;
      background-color: #0077b6;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    .otp, .withdraw-form {
      display: none;
    }
    .balance {
      font-size: 24px;
      color: green;
      margin: 20px 0;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Mustak Bank</h1>
    <div class="balance">ব্যালেন্স: ₹১,০০,০০,০০০</div>

    <div class="phone-form">
      <input type="tel" id="phone" placeholder="আপনার ফোন নম্বর দিন" required />
      <button onclick="sendOtp()">OTP নিন</button>
    </div>

    <div class="otp">
      <p>আপনার OTP: <strong id="show-otp"></strong></p>
      <input type="text" id="otp-input" placeholder="OTP লিখুন" />
      <button onclick="verifyOtp()">OTP যাচাই করুন</button>
    </div>

    <div class="withdraw-form">
      <input type="number" placeholder="টাকার পরিমাণ লিখুন" />
      <input type="text" placeholder="অ্যাকাউন্ট নম্বর লিখুন" />
      <button onclick="prankWithdraw()">উত্তোলন</button>
    </div>
  </div>

  <script>
    const otp = Math.floor(100000 + Math.random() * 900000); // ৬ সংখ্যার OTP তৈরি

    function sendOtp() {
      const phone = document.getElementById("phone").value;
      if (!phone.match(/^\d{10}$/)) {
        alert("সঠিক ১০ সংখ্যার ফোন নম্বর লিখুন।");
        return;
      }
      document.querySelector(".phone-form").style.display = "none";
      document.querySelector(".otp").style.display = "block";
      document.getElementById("show-otp").textContent = otp;
    }

    function verifyOtp() {
      const enteredOtp = document.getElementById("otp-input").value;
      if (enteredOtp == otp) {
        document.querySelector(".otp").style.display = "none";
        document.querySelector(".withdraw-form").style.display = "block";
      } else {
        alert("ভুল OTP! আবার চেষ্টা করুন।");
      }
    }

    function prankWithdraw() {
      alert("😂 এটা একটা মজা! তুমি সত্যি টাকা তুলতে পারবে না!");
    }
  </script>
</body>
</html>
