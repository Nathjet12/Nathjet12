<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Jeu de Billes</title>
<style>
    body {
        font-family: Arial, sans-serif;
        text-align: center;
    }
    #container {
        width: 300px;
        height: 300px;
        border: 1px solid black;
        position: relative;
        margin: 0 auto;
    }
    #ball {
        width: 20px;
        height: 20px;
        background-color: red;
        border-radius: 50%;
        position: absolute;
        bottom: 0;
        left: 50%;
        transform: translateX(-50%);
    }
</style>
</head>
<body>
    <h2>Ne fais pas tomber les billes !</h2>
    <div id="container">
        <div id="ball"></div>
    </div>
    <p>Utilisez les flèches pour déplacer le panier.</p>

    <script>
        document.addEventListener("keydown", function(event) {
            const ball = document.getElementById("ball");
            const container = document.getElementById("container");
            const containerRect = container.getBoundingClientRect();
            const ballRect = ball.getBoundingClientRect();
            const containerWidth = containerRect.width;
            const ballWidth = ballRect.width;

            const step = 10;

            if (event.key === "ArrowLeft") {
                if (ballRect.left > containerRect.left) {
                    ball.style.left = (ballRect.left - step) + "px";
                }
            } else if (event.key === "ArrowRight") {
                if (ballRect.right < containerRect.right) {
                    ball.style.left = (ballRect.left + step) + "px";
                }
            }
        });
    </script>
</body>
</html>
