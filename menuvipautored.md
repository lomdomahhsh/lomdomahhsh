<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Đăng Nhập và Menu Chức Năng</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #121212; /* Nền đen */
            color: white; /* Văn bản màu trắng */
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .login-container {
            background-color: #333; /* Màu nền tối cho form đăng nhập */
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 2px 10px rgba(255, 255, 255, 0.1);
            width: 300px;
            text-align: center;
        }
        .login-container input {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border: 1px solid #555;
            border-radius: 5px;
            background-color: #444;
            color: white;
        }
        .login-container button {
            width: 100%;
            padding: 10px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        .login-container button:hover {
            background-color: #45a049;
        }
        .menu {
            display: none;
            background-color: #333;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 2px 10px rgba(255, 255, 255, 0.1);
            width: 300px;
            text-align: center;
        }
        .menu button {
            width: 100%;
            padding: 10px;
            margin: 5px 0;
            background-color: #2196F3;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        .menu button:hover {
            background-color: #0b7dda;
        }
        .color-code {
            display: none;
            margin-top: 20px;
            padding: 10px;
            background-color: #1c313a;
            border: 1px solid #0097a7;
            border-radius: 5px;
            color: #00796b;
        }
    </style>
</head>
<body>

    <!-- Login Form -->
    <div class="login-container" id="loginForm">
        <h2>Đăng Nhập</h2>
        <input type="password" id="password" placeholder="Nhập mật khẩu" required>
        <label>
            <input type="checkbox" id="rememberMe"> Nhớ tôi
        </label>
        <button onclick="login()">Đăng Nhập</button>
    </div>

    <!-- Menu -->
    <div class="menu" id="menu">
        <h2>Chọn Chức Năng</h2>
        <button onclick="toggleColorCodes(1)">AimLock😈</button>
        <button onclick="toggleColorCodes(2)">NhạyTâm⚡</button>
        <button onclick="toggleColorCodes(3)">AimBot🐉</button>
        <button onclick="toggleColorCodes(4)">SupPerConFing🦑</button>
        <button onclick="toggleColorCodes(5)">Siêu BossMáy📱</button>
        <button onclick="toggleColorCodes(6)">ByPassAntiban🥑</button>
        <!-- Thêm nút mở game FreeFire -->
        <button onclick="openFreeFire()">Mở FreeFire</button>
    </div>

    <!-- Bảng Mã Màu -->
    <div class="color-code" id="colorCodeDisplay"></div>

    <script>
        const correctPassword = "09042012";  // Mật khẩu đúng
        const loginForm = document.getElementById('loginForm');
        const menu = document.getElementById('menu');
        const colorCodeDisplay = document.getElementById('colorCodeDisplay');

        // Hàm đăng nhập
        function login() {
            const password = document.getElementById('password').value;
            const rememberMe = document.getElementById('rememberMe').checked;

            if (password === correctPassword) {
                if (rememberMe) {
                    localStorage.setItem('rememberMe', 'true');
                }
                loginForm.style.display = 'none';
                menu.style.display = 'block';
            } else {
                alert('Mật khẩu không đúng!');
            }
        }

        // Kiểm tra nếu người dùng đã "Nhớ tôi"
        if (localStorage.getItem('rememberMe') === 'true') {
            loginForm.style.display = 'none';
            menu.style.display = 'block';
        }

        // Hàm Code chức năng
        function toggleColorCodes(chucNang) {
            let colorCodes = [
            "style@aimlock$dyop#", 
            "style@nhaytam$dyop#",
            "style@aimbot$dyop#", 
            "style@supperconfig$dyop#",
            "style@sieubossmay$dyop#",
            "style@matranao$dyop#"
            ];
            colorCodeDisplay.style.display = 'block';
            colorCodeDisplay.innerHTML = `Code của chức năng ${chucNang}: <br> ${colorCodes[chucNang - 1]}`;
        }

        // Hàm mở FreeFire
        function openFreeFire() {
            // Kiểm tra nền tảng hệ điều hành của thiết bị
            if (/android/i.test(navigator.userAgent)) {
                // Link cho Android
                window.location.href = "https://play.google.com/store/apps/details?id=com.dts.freefireth";
            } else if (/iPhone|iPad|iPod/i.test(navigator.userAgent)) {
                // Link cho iOS
                window.location.href = "https://apps.apple.com/us/app/free-fire/id1482452547";
            } else {
                alert("Chức năng chỉ có sẵn trên Android và iOS.");
            }
        }
    </script>

</body>
</html>
