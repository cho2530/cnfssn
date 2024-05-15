<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Confessions of the Heart</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background: linear-gradient(to bottom right, #ff99cc, #66ccff);
            overflow: hidden;
            position: relative;
            height: 100vh;
        }
        .heart {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            color: #ff4d4d;
            cursor: pointer;
            font-size: 200px;
            transition: transform 0.3s ease-in-out;
        }
        .confession-container {
            display: none;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background-color: rgba(255, 255, 255, 0.8);
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            z-index: 1;
        }
        .confession {
            font-size: 24px;
            line-height: 1.6;
            margin: 20px 0;
        }
        .confetti {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
        }
        .heart-burst {
            position: absolute;
            width: 30px;
            height: 30px;
            background-image: url('https://i.imgur.com/QBLHjkz.png'); /* Confetti heart image */
            background-size: contain;
            animation: heartBurst 3s linear infinite; /* Looping animation */
        }
        @keyframes heartBurst {
            0% { transform: scale(0); opacity: 1; }
            100% { transform: scale(1.5); opacity: 0; }
        }
    </style>
</head>
<body>
    <div class="heart" id="heart">&hearts;</div>
    <div class="confession-container" id="confession-container">
        <div class="confession">
            <p>"Every moment with you feels like a dream come true."</p>
        </div>
        <div class="confession">
            <p>"You make my heart skip a beat every time I see you."</p>
        </div>
        <div class="confession">
            <p>"I never believed in love at first sight until I met you."</p>
        </div>
        <div class="confession">
            <p>"You're the missing piece I've been searching for all my life."</p>
        </div>
    </div>
    <div class="confetti" id="confetti"></div>

    <script>
        const heart = document.getElementById('heart');
        const confessionContainer = document.getElementById('confession-container');
        const confettiContainer = document.getElementById('confetti');

        heart.addEventListener('click', function() {
            heart.style.transform = 'scale(1.5)';
            confessionContainer.style.display = 'block';
            generateConfetti();
        });

        function generateConfetti() {
            for (let i = 0; i < 30; i++) {
                const heartBurst = document.createElement('div');
                heartBurst.classList.add('heart-burst');
                heartBurst.style.left = Math.random() * window.innerWidth + 'px';
                heartBurst.style.top = Math.random() * window.innerHeight + 'px';
                confettiContainer.appendChild(heartBurst);
            }
        }
    </script>
</body>
</html>
