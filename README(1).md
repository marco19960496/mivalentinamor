<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>¿Quieres ser mi Valentín?</title>
    <style>
        /* Estilos generales */
        body {
            text-align: center;
            font-family: 'Brush Script MT', cursive;
            background-color: #ffcccb;
            overflow: hidden;
            margin: 0;
        }

        .container {
            margin-top: 100px;
        }

        h1 {
            font-size: 50px;
            color: #d63384;
        }

        .heart {
            font-size: 50px;
            color: red;
            animation: heartbeat 1s infinite alternate;
        }

        @keyframes heartbeat {
            from { transform: scale(1); }
            to { transform: scale(1.2); }
        }

        /* Botones */
        .buttons {
            margin-top: 30px;
        }

        .btn {
            font-size: 25px;
            padding: 12px 25px;
            margin: 10px;
            border: none;
            cursor: pointer;
            border-radius: 10px;
            font-family: 'Brush Script MT', cursive;
        }

        .yes {
            background-color: #ff4d4d;
            color: white;
        }

        .no {
            background-color: #333;
            color: white;
            position: absolute;
        }

        /* Flores animadas */
        .flower {
            position: absolute;
            width: 50px;
            height: 50px;
            background: url('https://i.imgur.com/oCkEbrA.png') no-repeat center;
            background-size: cover;
            animation: fall linear infinite;
        }

        @keyframes fall {
            0% { transform: translateY(-100px) rotate(0deg); opacity: 1; }
            100% { transform: translateY(100vh) rotate(360deg); opacity: 0; }
        }

        /* Música */
        audio {
            display: none;
        }
    </style>
</head>
<body>

    <audio id="music" autoplay loop>
        <source src="cancion.mp3" type="audio/mp3">
        Tu navegador no soporta el audio.
    </audio>

    <div class="container">
        <h1>¿Quieres ser mi Valentín? ❤️</h1>
        <p class="heart">💖</p>
        <div class="buttons">
            <button class="btn yes" onclick="yesAnswer()">Sí 💕</button>
            <button class="btn no" id="noBtn" onmouseover="moveNoButton()">No 💔</button>
        </div>
    </div>

    <script>
        function yesAnswer() {
            alert("¡Sabía que dirías que sí! 💖🥰");
        }

        function moveNoButton() {
            let btn = document.getElementById("noBtn");
            let x = Math.random() * (window.innerWidth - 100);
            let y = Math.random() * (window.innerHeight - 50);
            btn.style.left = x + "px";
            btn.style.top = y + "px";
        }

        // Crear flores animadas
        function createFlowers() {
            for (let i = 0; i < 15; i++) {
                let flower = document.createElement("div");
                flower.classList.add("flower");
                document.body.appendChild(flower);
                flower.style.left = Math.random() * window.innerWidth + "px";
                flower.style.animationDuration = (Math.random() * 3 + 2) + "s";
                flower.style.animationDelay = Math.random() * 5 + "s";
            }
        }

        createFlowers();
    </script>

</body>
</html>
