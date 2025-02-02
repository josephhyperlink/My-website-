<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Joshua ❤️ Dilna</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            background: linear-gradient(135deg, #ff9a9e, #fad0c4);
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            font-family: 'Poppins', sans-serif;
        }

        h1 {
            color: #fff;
            font-size: 60px;
            text-align: center;
            text-shadow: 0 0 20px #ff007f, 0 0 30px #ff1493;
            animation: glow 2s ease-in-out infinite alternate;
            position: relative;
            z-index: 2;
        }

        @keyframes glow {
            from {
                text-shadow: 0 0 10px #ff007f, 0 0 20px #ff1493;
            }
            to {
                text-shadow: 0 0 30px #ff007f, 0 0 50px #ff1493;
            }
        }

        .heart {
            position: absolute;
            width: 50px;
            height: 50px;
            background-color: red;
            transform: rotate(-45deg);
            animation: pop 1.5s infinite ease-in-out;
        }

        .heart::before,
        .heart::after {
            content: "";
            position: absolute;
            width: 50px;
            height: 50px;
            background-color: red;
            border-radius: 50%;
        }

        .heart::before {
            top: -25px;
            left: 0;
        }

        .heart::after {
            left: 25px;
            top: 0;
        }

        @keyframes pop {
            0%, 100% {
                transform: scale(1) rotate(-45deg);
            }
            50% {
                transform: scale(1.3) rotate(-45deg);
            }
        }

        /* Floating Hearts */
        .floating-heart {
            position: absolute;
            top: 100vh;
            animation: floatUp 6s infinite ease-in-out;
            opacity: 0.9;
        }

        @keyframes floatUp {
            0% {
                transform: translateY(0) scale(0.8);
                opacity: 0.9;
            }
            100% {
                transform: translateY(-120vh) scale(1.2);
                opacity: 0;
            }
        }

        /* Sparkles */
        .sparkle {
            position: absolute;
            width: 6px;
            height: 6px;
            background: white;
            border-radius: 50%;
            box-shadow: 0 0 8px white;
            animation: sparkle 3s infinite ease-in-out;
        }

        @keyframes sparkle {
            0%, 100% {
                opacity: 0;
                transform: scale(0.5);
            }
            50% {
                opacity: 1;
                transform: scale(1.5);
            }
        }
    </style>
</head>
<body>
    <h1>Joshua ❤️ Dilna</h1>

    <!-- Popping Heart -->
    <div class="heart"></div>

    <!-- Floating Hearts & Sparkles -->
    <script>
        function createFloatingHeart() {
            const heart = document.createElement('div');
            heart.classList.add('heart', 'floating-heart');
            heart.style.left = Math.random() * window.innerWidth + 'px';
            heart.style.animationDuration = (4 + Math.random() * 3) + 's';
            document.body.appendChild(heart);

            setTimeout(() => {
                heart.remove();
            }, 6000);
        }

        function createSparkle() {
            const sparkle = document.createElement('div');
            sparkle.classList.add('sparkle');
            sparkle.style.left = Math.random() * window.innerWidth + 'px';
            sparkle.style.top = Math.random() * window.innerHeight + 'px';
            sparkle.style.animationDuration = (2 + Math.random() * 2) + 's';
            document.body.appendChild(sparkle);

            setTimeout(() => {
                sparkle.remove();
            }, 3000);
        }

        setInterval(createFloatingHeart, 500);
        setInterval(createSparkle, 300);
    </script>
</body>
</html>
