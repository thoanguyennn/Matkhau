<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <title>Kiểm tra mật khẩu</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 40px;
    }

    .password-container {
      position: relative;
      width: 300px;
    }

    input[type="password"], input[type="text"] {
      padding: 10px;
      width: 100%;
      margin-top: 10px;
      box-sizing: border-box;
    }

    .eye-icon {
      position: absolute;
      right: 10px;
      top: 18px;
      cursor: pointer;
      font-size: 20px;
      user-select: none;
    }

    ul {
      list-style: none;
      padding-left: 0;
      margin-top: 15px;
    }

    li {
      margin-bottom: 5px;
    }

    .valid {
      color: green;
    }

    .invalid {
      color: red;
    }

    #result {
      margin-top: 20px;
      font-weight: bold;
    }
  </style>
</head>
<body>

  <h2>🔐 Kiểm tra mật khẩu</h2>

  <label for="passwordInput">Nhập mật khẩu:</label>
  <div class="password-container">
    <input type="password" id="passwordInput" oninput="validatePassword()">
    <span class="eye-icon" id="eyeIcon" onclick="togglePasswordVisibility()">🙈</span>
  </div>

  <ul>
    <li id="length" class="invalid">• Ít nhất 8 ký tự</li>
    <li id="uppercase" class="invalid">• Có chữ in hoa (A-Z)</li>
    <li id="lowercase" class="invalid">• Có chữ thường (a-z)</li>
    <li id="number" class="invalid">• Có ít nhất một chữ số (0-9)</li>
    <li id="special" class="invalid">• Có ký tự đặc biệt (!@#$...)</li>
  </ul>

  <button onclick="checkPassword()">Kiểm tra mật khẩu</button>

  <div id="result"></div>

  <script>
    function togglePasswordVisibility() {
      const input = document.getElementById("passwordInput");
      const eyeIcon = document.getElementById("eyeIcon");

      if (input.type === "password") {
        input.type = "text";
        eyeIcon.textContent = "👁️"; // Mắt mở
      } else {
        input.type = "password";
        eyeIcon.textContent = "🙈"; // Mắt nhắm
      }
    }

    function validatePassword() {
      const password = document.getElementById("passwordInput").value;

      const length = document.getElementById("length");
      const uppercase = document.getElementById("uppercase");
      const lowercase = document.getElementById("lowercase");
      const number = document.getElementById("number");
      const special = document.getElementById("special");

      // Kiểm tra từng tiêu chí
      length.className = password.length >= 8 ? "valid" : "invalid";
      uppercase.className = /[A-Z]/.test(password) ? "valid" : "invalid";
      lowercase.className = /[a-z]/.test(password) ? "valid" : "invalid";
      number.className = /[0-9]/.test(password) ? "valid" : "invalid";
      special.className = /[!@#$%^&*()_\-+={}[\]|:;"'<>,.?/]/.test(password) ? "valid" : "invalid";

      // Xóa kết quả cũ khi đang nhập
      document.getElementById("result").innerHTML = "";
    }

    function checkPassword() {
      const password = document.getElementById("passwordInput").value;
      const resultDiv = document.getElementById("result");

      const isValid =
        password.length >= 8 &&
        /[A-Z]/.test(password) &&
        /[a-z]/.test(password) &&
        /[0-9]/.test(password) &&
        /[!@#$%^&*()_\-+={}[\]|:;"'<>,.?/]/.test(password);

      if (isValid) {
        resultDiv.innerHTML = "✅ Mật khẩu hợp lệ!";
        resultDiv.className = "valid";
      } else {
        resultDiv.innerHTML = "❌ Mật khẩu chưa đáp ứng đủ các tiêu chí.";
        resultDiv.className = "invalid";
      }
    }
  </script>

</body>
</html>
