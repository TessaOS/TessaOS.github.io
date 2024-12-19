<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>TessaOS Alpha v1.5.3 - Login</title>
  <style>
    body {
      font-family: monospace;
      background-color: #000;
      color: #0f0;
      margin: 0;
      padding: 0;
    }

    .login-container {
      width: 100%;
      max-width: 600px;
      margin: 100px auto;
      padding: 20px;
      border: 1px solid #0f0;
      background-color: #111;
    }

    h1 {
      text-align: center;
    }

    .login-input {
      width: 100%;
      padding: 10px;
      margin: 10px 0;
      border: 1px solid #0f0;
      background-color: #333;
      color: #0f0;
      font-size: 16px;
    }

    .login-btn {
      width: 100%;
      padding: 10px;
      border: 1px solid #0f0;
      background-color: #444;
      color: #0f0;
      font-size: 16px;
      cursor: pointer;
    }

    .hidden {
      display: none;
    }

    .error {
      color: red;
    }
  </style>
</head>
<body>

  <div class="login-container">
    <h1>TessaOS Alpha v1.5.3</h1>
    <label for="username">Username:</label>
    <input type="text" id="username" class="login-input" placeholder="Enter Username">
    <label for="password">Password:</label>
    <input type="password" id="password" class="login-input" placeholder="Enter Password">
    <button class="login-btn" onclick="login()">Login</button>
    <div id="error-message" class="error hidden"></div>
  </div>

  <script>
    const users = {
      "Martin Greyfield": { username: "martin", password: "greyfield", access: "Admin" },
      "Roxanne C. Greyfield": { username: "roxanne", password: "greyr0ck", access: "Admin" },
      "Viktor K. Clarkes": { username: "viktor", password: "clark3s", access: "Developer/Admin" },
      "Sarah R. Terathes": { username: "sarah", password: "terathes1", access: "Developer/Admin" },
      "Sterling P. Mitchell": { username: "sterling", password: "mitchellP", access: "Security" },
      "Marcus Whitlock": { username: "marcus", password: "nevermore", access: "Special" }
    };

    function login() {
      const username = document.getElementById('username').value;
      const password = document.getElementById('password').value;
      const errorMessage = document.getElementById('error-message');

      if (username === "marcus" && password === "nevermore") {
        window.location.href = "https://www.youtube.com/channel/CerberusScience"; // Redirect to the YouTube channel
      } else {
        const user = Object.values(users).find(user => user.username === username && user.password === password);

        if (user) {
          errorMessage.classList.add('hidden');
          alert(`Welcome ${Object.keys(users).find(key => users[key] === user)}`);
          window.location.href = `${username.toLowerCase()}_account.html`; // Redirect to user-specific webpage
        } else {
          errorMessage.classList.remove('hidden');
          errorMessage.textContent = "Invalid Username or Password";
        }
      }
    }
  </script>

</body>
</html>
