<!DOCTYPE html>
<html lang="cs">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Online Tenisová Hra</title>
    <style>
        #game-area {
            width: 800px;
            height: 400px;
            border: 1px solid black;
            position: relative;
            margin: 0 auto;
        }
        .paddle {
            width: 10px;
            height: 100px;
            background-color: black;
            position: absolute;
        }
        #ball {
            width: 10px;
            height: 10px;
            background-color: red;
            border-radius: 50%;
            position: absolute;
        }
    </style>
</head>
<body>
    <h1 style="text-align: center;">Online Tenisová Hra</h1>
    <div id="game-area">
        <div id="paddle1" class="paddle" style="left: 0;"></div>
        <div id="paddle2" class="paddle" style="right: 0;"></div>
        <div id="ball"></div>
    </div>
    <script>
        const gameArea = document.getElementById('game-area');
        const paddle1 = document.getElementById('paddle1');
        const paddle2 = document.getElementById('paddle2');
        const ball = document.getElementById('ball');

        let paddle1Y = 150, paddle2Y = 150;
        let ballX = 395, ballY = 195;
        let ballSpeedX = 5, ballSpeedY = 3;

        function update() {
            // Pohyb pálek
            document.addEventListener('keydown', (e) => {
                if (e.key === 'w' && paddle1Y > 0) paddle1Y -= 10;
                if (e.key === 's' && paddle1Y < 300) paddle1Y += 10;
                if (e.key === 'ArrowUp' && paddle2Y > 0) paddle2Y -= 10;
                if (e.key === 'ArrowDown' && paddle2Y < 300) paddle2Y += 10;
            });

            // Pohyb míčku
            ballX += ballSpeedX;
            ballY += ballSpeedY;

            // Odraz od horní a dolní hranice
            if (ballY <= 0 || ballY >= 390) ballSpeedY = -ballSpeedY;

            // Odraz od pálek
            if ((ballX <= 10 && ballY > paddle1Y && ballY < paddle1Y + 100) ||
                (ballX >= 780 && ballY > paddle2Y && ballY < paddle2Y + 100)) {
                ballSpeedX = -ballSpeedX;
            }

            // Aktualizace pozic
            paddle1.style.top = paddle1Y + 'px';
            paddle2.style.top = paddle2Y + 'px';
            ball.style.left = ballX + 'px';
            ball.style.top = ballY + 'px';

            requestAnimationFrame(update);
        }

        update();
    </script>
</body>
</html>
