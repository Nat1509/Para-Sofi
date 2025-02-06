<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>¿Quieres ser mi San Valentín?</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #ffe6f2;
            color: #ff3366;
            overflow: hidden;
        }
        .container {
            margin-top: 20%;
            position: relative;
        }
        h1 {
            font-size: 2.5em;
        }
        p {
            font-size: 1.5em;
        }
        button {
            font-size: 1.2em;
            padding: 10px 20px;
            margin: 20px;
            border: none;
            cursor: pointer;
            border-radius: 5px;
        }
        .yes-btn {
            background-color: #ff3366;
            color: white;
        }
        .no-btn {
            background-color: #ddd;
            color: black;
        }
        .heart {
            position: absolute;
            font-size: 2em;
            color: red;
            animation: floatUp 3s linear infinite;
        }
        @keyframes floatUp {
            0% {
                transform: translateY(100vh);
                opacity: 1;
            }
            100% {
                transform: translateY(-10vh);
                opacity: 0;
            }
        }
        #finalMessage {
            font-size: 2em;
            font-weight: bold;
            color: #ff0033;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <div class="container" id="question">
        <h1>¿QUIERES SER MI SAN VALENTÍN?</h1>
        <button class="yes-btn" onclick="showLove()">Sí, siempre sí</button>
        <button class="no-btn" onclick="moveNoButton()" id="no-btn">No</button>
    </div>

    <div class="container" id="loveMessage" style="display: none;">
        <h1>Gracias por tantos momentos lindos y por permitirme estar siempre a tu lado.</h1>
        <p>Te amo más que a nadie y siempre te voy a cuidar el alma, cuerpito y corazón ❤️</p>
        <p id="finalMessage">Te amo mi Sofi</p>
    </div>

    <script>
        function showLove() {
            document.getElementById("question").style.display = "none";
            document.getElementById("loveMessage").style.display = "block";
            generateHearts();
        }

        function moveNoButton() {
            let noBtn = document.getElementById("no-btn");
            noBtn.style.position = "absolute";
            noBtn.style.top = Math.random() * window.innerHeight + "px";
            noBtn.style.left = Math.random() * window.innerWidth + "px";
        }

        function generateHearts() {
            for (let i = 0; i < 20; i++) {
                let heart = document.createElement("div");
                heart.innerHTML = "❤️";
                heart.classList.add("heart");
                heart.style.left = Math.random() * window.innerWidth + "px";
                heart.style.top = Math.random() * window.innerHeight + "px";
                heart.style.animationDuration = (Math.random() * 2 + 3) + "s";
                document.body.appendChild(heart);

                setTimeout(() => {
                    heart.remove();
                }, 3000);
            }
            setTimeout(generateHearts, 1000);
        }
    </script>
</body>
</html>
