<!DOCTYPE html>
<html lang="de">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>JBRS Technikteam</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f5f5f5;
      margin: 0;
      padding: 0;
    }

    .container {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background-color: #FF6600; /* Orange-Farbgestaltung */
    }

    .login-box {
      background-color: white;
      padding: 30px;
      border-radius: 10px;
      box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
      width: 300px;
    }

    h1 {
      text-align: center;
      color: #FF6600;
      margin-bottom: 20px;
    }

    label {
      font-size: 16px;
      margin-bottom: 8px;
      display: block;
    }

    input[type="text"],
    input[type="password"] {
      width: 100%;
      padding: 10px;
      margin-bottom: 20px;
      border-radius: 5px;
      border: 1px solid #ccc;
      font-size: 14px;
    }

    input[type="submit"] {
      width: 100%;
      padding: 10px;
      background-color: #FF6600;
      border: none;
      border-radius: 5px;
      color: white;
      font-size: 16px;
      cursor: pointer;
    }

    input[type="submit"]:hover {
      background-color: #e65c00;
    }

    .error {
      color: red;
      font-size: 14px;
      text-align: center;
    }
  </style>
</head>
<body>

  <div class="container">
    <div class="login-box">
      <h1>JBRS Technikteam</h1>
      <form id="loginForm">
        <label for="username">Benutzername</label>
        <input type="text" id="username" name="username" required>

        <label for="password">Passwort</label>
        <input type="password" id="password" name="password" required>

        <input type="submit" value="Einloggen">
      </form>
      <div class="error" id="error-message"></div>
    </div>
  </div>

  <script>
    const users = {
      "Frau Haberbeck": "Technik01720",
      "Jannis Twikler": "Technik2829",
      "Jannik": "Technik18263",
      "Admin": "Admin123",
      "Valentin Vollmer": "Technik8352",
      "Lukas Bühler": "Technik333"
    };

    document.getElementById('loginForm').addEventListener('submit', function (event) {
      event.preventDefault();

      const username = document.getElementById('username').value;
      const password = document.getElementById('password').value;
      const errorMessage = document.getElementById('error-message');

      // Überprüfe, ob Benutzername und Passwort übereinstimmen
      if (users[username] && users[username] === password) {
        window.location.href = "erfolgreich.html";  // Weiterleitung zu einer erfolgreichen Seite
      } else {
        errorMessage.textContent = "Benutzername oder Passwort ist falsch!";
      }
    });
  </script>

</body>
</html>
