<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login and Signup</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background: #000;
            color: #fff;
        }
        .container {
            text-align: center;
            background: rgba(255, 255, 255, 0.1);
            padding: 20px;
            border-radius: 15px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
        }
        h1 {
            font-size: 2.5em;
            margin-bottom: 20px;
        }
        h1 .highlight {
            color: #e74c3c;
            font-weight: bold;
        }
        button {
            margin: 10px;
            padding: 15px 30px;
            font-size: 16px;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            background: #e74c3c;
            color: #fff;
            transition: background 0.3s, transform 0.2s;
        }
        button:hover {
            background: #c0392b;
            transform: scale(1.1);
        }
        .register-button {
            display: none;
            margin-top: 20px;
            padding: 15px 30px;
            font-size: 16px;
            background: #e74c3c;
            color: #fff;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            transition: background 0.3s, transform 0.2s;
        }
        .register-button:hover {
            background: #c0392b;
            transform: scale(1.1);
        }
    </style>
    <script>
        function navigateTo(page) {
            window.location.href = page;
        }

        function login() {
            const username = prompt("아이디를 입력하세요:");
            const password = prompt("비밀번호를 입력하세요:");

            if (username === "junesung0302" && password === "wild7186") {
                window.location.href = "welcome.html";
            } else if (username === "junesung0302" && password === "wild7186!!") {
                window.location.href = "special_welcome.html";
            } else {
                alert("아이디 또는 비밀번호가 잘못되었습니다.");
            }
        }

        function showRegisterButton() {
            const registerButton = document.getElementById("registerButton");
            registerButton.style.display = "block";
        }

        // Automatically show register button for the special user
        window.onload = function() {
            const params = new URLSearchParams(window.location.search);
            if (params.get("user") === "special") {
                showRegisterButton();
            }
        };
    </script>
</head>
<body>
    <div class="container">
        <h1>발로란트 최저가 <span class="highlight">X샵</span>에 오신 것을 환영합니다!</h1>
        <button onclick="navigateTo('signup.html')">회원가입</button>
        <button onclick="login()">로그인</button>
        <button id="registerButton" class="register-button">등록</button>
    </div>
</body>
</html>
