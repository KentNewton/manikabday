<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday, Manika! 🎉</title>
    <style>
        body {
            text-align: center;
            background: linear-gradient(135deg, #ff9a9e, #fad0c4);
            font-family: Arial, sans-serif;
            overflow-x: hidden;
            position: relative;
        }
        .container {
            margin-top: 50px;
        }
        button {
            background-color: #ff4081;
            color: white;
            border: none;
            padding: 15px 30px;
            font-size: 18px;
            margin: 10px;
            cursor: pointer;
            border-radius: 10px;
        }
        button:hover {
            background-color: #f50057;
        }
        .hidden {
            display: none;
            margin-top: 20px;
            font-size: 20px;
            color: #880e4f;
        }
        canvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            pointer-events: none;
        }
        @keyframes sparkle {
            0% { opacity: 0; }
            50% { opacity: 1; }
            100% { opacity: 0; }
        }
        .sparkle {
            position: absolute;
            width: 5px;
            height: 5px;
            background-color: white;
            border-radius: 50%;
            opacity: 0;
            animation: sparkle 1.5s infinite;
        }
    </style>
</head>
<body>
    <audio id="bg-music" loop autoplay>
        <source src="Unwritten pages.mp3" type="audio/mpeg">
        Your browser does not support the audio element.
    </audio>

    <canvas id="confettiCanvas"></canvas>

    <div class="container">
        <h1 style="font-size: 48px; text-align: center; margin-top: 20vh;">🎂 Happy Birthday, Manika! 🎂</h1>
        <p>Click on the surprises below to reveal them! 🎁</p>

        <button onclick="toggleMessage('message1')">🎁 Open Your Gift</button>
        <p id="message1" class="hidden">You're an amazing person, and I hope this year brings you endless joy! 💖</p>

        <button onclick="openMiniPlayer('https://open.spotify.com/playlist/0p1pubyAVKeZDSAms7hokR')">🎶 Play Hindi Playlist</button>

        <button onclick="openMiniPlayer('https://open.spotify.com/playlist/57k8j6wMoPpSX36s1uj94O')">🎶 Play English Playlist</button>

        <button onclick="generateCompliment()">💖 Get Compliments</button>
        <p id="compliment" class="hidden"></p>

        <button onclick="toggleMessage('message4')">🔑 Unlock the Secret</button>
        <p id="message4" class="hidden">Cher Manika, je vous aime beaucoup et je prie Dieu que vous ne connaissez pas le français. 😉</p>

        <button id="music-toggle" onclick="toggleMusic()" style="position: absolute; top: 10px; right: 10px;">🎵</button>
    </div>

    <script>
        function openMiniPlayer(url) {
            window.open(url, '_blank', 'width=400,height=500,top=100,left=100');
        }

        function toggleMessage(id) {
            let elem = document.getElementById(id);
            elem.style.display = (elem.style.display === "none" || elem.style.display === "") ? "block" : "none";
        }

        function generateCompliment() {
            const compliments = [
                "You're a ray of 'sunshine' on the cloudiest days ☀️",
                "The world is a better place with you in it! (Mostly because you haven’t taken over yet. 😈)",
                "You are like a warm hug for the soul 🤗",
                "You make everything better—except my ability to focus, because you’re soooo distracting. 😏",
                "Your smile is so contagious I am afraid it might cause a plague 😊"
            ];
            const randomIndex = Math.floor(Math.random() * compliments.length);
            document.getElementById("compliment").innerText = compliments[randomIndex];
            document.getElementById("compliment").style.display = "block";
        }

        function toggleMusic() {
            var music = document.getElementById("bg-music");
            if (music.paused) {
                music.play();
            } else {
                music.pause();
            }
        }

        function createSparkles() {
            for (let i = 0; i < 50; i++) {
                let sparkle = document.createElement("div");
                sparkle.className = "sparkle";
                document.body.appendChild(sparkle);
                sparkle.style.left = Math.random() * window.innerWidth + "px";
                sparkle.style.top = Math.random() * window.innerHeight + "px";
                sparkle.style.animationDelay = Math.random() * 2 + "s";
            }
        }
        createSparkles();
    </script>
</body>
</html>
