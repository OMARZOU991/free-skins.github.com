# free-skins.github.com
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Détection des Cookies</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 50px;
            background-color: #f4f4f9;
        }
        .container {
            padding: 20px;
            border: 1px solid #ccc;
            background: #fff;
            border-radius: 10px;
            display: inline-block;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
        }
        h1 {
            color: #333;
        }
        p {
            font-size: 16px;
        }
        .cookie-list {
            margin-top: 20px;
            color: #555;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Détection des Cookies</h1>
        <p>Nous avons détecté les cookies suivants :</p>
        <div class="cookie-list" id="cookieList">
            <!-- Les cookies apparaîtront ici -->
        </div>
    </div>

    <script>
        // Fonction pour récupérer tous les cookies
        function detectCookies() {
            const cookieList = document.getElementById("cookieList");
            const cookies = document.cookie;

            if (cookies) {
                const cookieArray = cookies.split('; ');
                cookieList.innerHTML = "<ul>" + cookieArray.map(cookie => "<li>" + cookie + "</li>").join('') + "</ul>";
            } else {
                cookieList.textContent = "Aucun cookie détecté.";
            }
        }

        // Exécuter la fonction dès que la page se charge
        window.onload = detectCookies;
    </script>
</body>
</html>
