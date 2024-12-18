<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Détection des Cookies</title>
    <style>
        /* Styles généraux */
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 0;
            background: linear-gradient(to right, #6a11cb, #2575fc);
            color: #fff;
            text-align: center;
            display: flex;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
        }

        /* Conteneur principal */
        .container {
            background-color: #ffffff;
            color: #333;
            border-radius: 15px;
            padding: 30px;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
            max-width: 500px;
            animation: fadeIn 1.5s ease-in-out;
        }

        /* Titre principal */
        h1 {
            font-size: 2rem;
            margin-bottom: 20px;
            color: #6a11cb;
        }

        /* Texte descriptif */
        p {
            font-size: 1.1rem;
            margin-bottom: 15px;
        }

        /* Liste des cookies */
        .cookie-list {
            margin-top: 20px;
            font-size: 1rem;
            color: #555;
            text-align: left;
            line-height: 1.8;
        }

        /* Animation d'apparition */
        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(-20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
    </style>
</head>
<body>
    <!-- Conteneur principal -->
    <div class="container">
        <h1>Détection des Cookies 🍪</h1>
        <p>Nous avons détecté les cookies suivants :</p>
        <div class="cookie-list" id="cookieList">
            <!-- Les cookies apparaîtront ici -->
        </div>
    </div>

    <!-- Script JavaScript -->
    <script>
        // Fonction pour récupérer et afficher les cookies
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

        // Appel de la fonction au chargement de la page
        window.onload = detectCookies;
    </script>
</body>
</html>
