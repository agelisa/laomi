<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>¿Quieres volver a hablar?</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: Arial, sans-serif;
            background-image: url('bicha.jpg');
            background-size: cover;
            background-position: center;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            color: white;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .container {
            background-color: rgba(0, 0, 0, 0.5);
            padding: 20px;
            border-radius: 10px;
        }

        h1 {
            font-size: 3rem;
            font-weight: bold;
            margin-bottom: 10px;
        }

        p {
            font-size: 0.8rem;
            color: lightgray;
            margin-bottom: 20px;
        }

        .buttons {
            display: flex;
            justify-content: space-around;
            margin-top: 20px;
        }

        .button {
            background-color: black;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1rem;
            transition: background-color 0.3s;
        }

        .button:hover {
            background-color: #444;
        }

        @keyframes float {
            0% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-10px);
            }
            100% {
                transform: translateY(0);
            }
        }

        .emoji {
            font-size: 3rem; /* Tamaño de los emojis */
            position: absolute;
            animation: float 6s infinite;
        }

        .emoji:nth-child(1) { top: 5%; left: 10%; animation-duration: 6s; }
        .emoji:nth-child(2) { top: 25%; left: 75%; animation-duration: 7s; }
        .emoji:nth-child(3) { top: 45%; left: 60%; animation-duration: 8s; }
        .emoji:nth-child(4) { top: 70%; left: 10%; animation-duration: 6.5s; } /* Ajustado más lejos */
        .emoji:nth-child(5) { top: 10%; left: 80%; animation-duration: 7.5s; } /* Ajustado más lejos */

        .confetti {
            position: fixed;
            width: 100%;
            height: 100%;
            pointer-events: none;
            display: none;
            z-index: 9999;
        }

        .confetti-piece {
            width: 10px;
            height: 20px;
            background-color: hsl(var(--hue), 100%, 50%);
            position: absolute;
            top: 0;
            opacity: 0.8;
            transform-origin: left;
            animation: fall linear infinite;
        }

        @keyframes fall {
            0% { transform: rotateZ(15deg) rotateY(0deg) translate(0, -100%); }
            100% { transform: rotateZ(15deg) rotateY(720deg) translate(100vw, 100vh); }
        }
    </style>
</head>
<body>

    <!-- Aquí se agrega la música de fondo -->
    <audio autoplay loop>
        <source src="audio/fondo.mp3" type="audio/mpeg">
        Tu navegador no soporta la reproducción de audio.
    </audio>

    <div class="container">
        <h1>¿Quieres volver a hablar?</h1>
        <p>Te vi y me puse nervioso</p>
        <div class="buttons">
            <button class="button" id="yes-button">Sí</button>
            <button class="button" id="no-button">No</button>
        </div>
    </div>

    <!-- Emojis distribuidos -->
    <div class="emoji">😸</div>
    <div class="emoji">🍦</div>
    <div class="emoji">🥋</div>
    <div class="emoji">🥭</div>
    <div class="emoji">🎶</div>

    <div class="confetti" id="confetti"></div>

    <script>
        document.getElementById('yes-button').addEventListener('click', function() {
            const confetti = document.getElementById('confetti');
            confetti.style.display = 'block';
            for (let i = 0; i < 100; i++) {
                const confettiPiece = document.createElement('div');
                confettiPiece.classList.add('confetti-piece');
                confettiPiece.style.setProperty('--hue', Math.random() * 360);
                confettiPiece.style.left = Math.random() * 100 + 'vw';
                confettiPiece.style.animationDuration = Math.random() * 3 + 2 + 's';
                confetti.appendChild(confettiPiece);
            }
            setTimeout(function() {
                window.location.href = 'https://wa.me/2722133139';
            }, 3000);
        });

        document.getElementById('no-button').addEventListener('click', function() {
            window.location.href = 'https://www.youtube.com/watch?v=UejnB9xCAAM';
        });
    </script>
</body>
</html>
