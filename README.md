<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TessaOS Alpha v1.5.3</title>
    <style>
        body {
            background-color: black;
            color: #00FF00;
            font-family: "Courier New", Courier, monospace;
            margin: 0;
            padding: 0;
        }

        .container {
            margin-top: 50px;
            text-align: center;
        }

        input {
            background-color: black;
            color: #00FF00;
            border: 1px solid #00FF00;
            padding: 5px;
        }

        #output {
            margin-top: 20px;
            text-align: left;
            white-space: pre;
        }

        .hidden {
            display: none;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>TessaOS Alpha v1.5.3</h1>
        <p>Enter username and password:</p>
        <input type="text" id="username" placeholder="Username" />
        <input type="password" id="password" placeholder="Password" />
        <button onclick="checkLogin()">Login</button>
        <div id="output"></div>
    </div>

    <script>
        const users = {
            "Martin Greyfield": {
                username: "MartinGrey",
                password: "Greyfield123",
                accessLevel: "Admin"
            },
            "Roxanne C. Greyfield": {
                username: "RoxanneC",
                password: "Roxanne456",
                accessLevel: "Admin"
            },
            "Viktor K. Clarkes": {
                username: "ViktorK",
                password: "Viktor789",
                accessLevel: "Developer/Admin"
            },
            "Sarah R. Terathes": {
                username: "SarahR",
                password: "Sarah101",
                accessLevel: "Developer/Admin"
            },
            "Sterling P. Mitchell": {
                username: "SterlingP",
                password: "Sterling500",
                accessLevel: "Security"
            },
            "Marcus": {
                username: "Marcus",
                password: "Nevermore",
                accessLevel: "Special Access"
            }
        };

        function checkLogin() {
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;
            const output = document.getElementById('output');
            
            // Check if the user is Marcus with special access
            if (username === "Marcus" && password === "Nevermore") {
                window.location.href = "https://www.youtube.com/channel/UCXXXXXX"; // Link to Cerberus Science YouTube channel
                return;
            }

            let userFound = false;
            for (const user in users) {
                if (users[user].username === username && users[user].password === password) {
                    userFound = true;
                    output.innerHTML = `Welcome, ${user}!<br>Access Level: ${users[user].accessLevel}`;
                    redirectToUserPage(user);
                    break;
                }
            }

            if (!userFound) {
                output.innerHTML = "Incorrect username or password.";
            }
        }

        function redirectToUserPage(user) {
            const userPages = {
                "Martin Greyfield": "/MartinGreyfield.html",
                "Roxanne C. Greyfield": "/RoxanneGreyfield.html",
                "Viktor K. Clarkes": "/ViktorClarkes.html",
                "Sarah R. Terathes": "/SarahTerathes.html",
                "Sterling P. Mitchell": "/SterlingMitchell.html"
            };

            if (userPages[user]) {
                window.location.href = userPages[user];
            }
        }
    </script>
</body>
</html>

