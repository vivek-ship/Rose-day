<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Will You Be My Rose Day Date?</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            text-align: center;
            background-color: #ffe6e6;
            overflow: hidden;
        }
        .container {
            margin-top: 100px;
        }
        h1 {
            color: #d63384;
        }
        p {
            font-size: 18px;
            color: #333;
        }
        .rose {
            width: 150px;
            margin: 20px;
        }
        .btn {
            display: inline-block;
            padding: 15px 30px;
            font-size: 18px;
            color: white;
            background-color: #ff4d4d;
            border: none;
            cursor: pointer;
            border-radius: 10px;
            text-decoration: none;
            transition: 0.3s;
        }
        .btn:hover {
            background-color: #cc0000;
        }
        .no-btn {
            background-color: grey;
            position: absolute;
        }
        .confetti {
            position: fixed;
            width: 10px;
            height: 10px;
            background-color: red;
            top: -10px;
            left: 50%;
            opacity: 0.8;
            border-radius: 50%;
            animation: fall 2s linear infinite;
        }
        @keyframes fall {
            0% { transform: translateY(0px) rotate(0deg); }
            100% { transform: translateY(100vh) rotate(360deg); }
        }
    </style>
</head>
<body>

    <div class="container">
        <h1>🌹 Happy Rose Day! 🌹</h1>
        <p>Dear [NIDHI],</p>
        <p>Roses are red, violets are blue,  
        This Rose Day, I’d love to go on a date with you! ❤️</p>
        <img src="https://upload.wikimedia.org/wikipedia/commons/b/bb/Rose_Red_Flower_Bloom_600.jpg" class="rose" alt="Rose">
        <br>
        <button class="btn" id="yesButton">Yes, I'd Love To!</button>
        <button class="btn no-btn" id="noButton">Maybe Next Time</button>
    </div>

    <script>
        const noButton = document.getElementById("noButton");
        let moveCount = 0;

        noButton.addEventListener("mouseover", function() {
            if (moveCount < 10) {
                const x = Math.random() * (window.innerWidth - 200);
                const y = Math.random() * (window.innerHeight - 100);
                noButton.style.left = `${x}px`;
                noButton.style.top = `${y}px`;
                moveCount++;
            }
        });

        document.getElementById("yesButton").addEventListener("click", function() {
            for (let i = 0; i < 50; i++) {
                let confetti = document.createElement("div");
                confetti.classList.add("confetti");
                confetti.style.backgroundColor = `hsl(${Math.random() * 360}, 100%, 50%)`;
                confetti.style.left = `${Math.random() * window.innerWidth}px`;
                confetti.style.animationDuration = `${Math.random() * 3 + 1}s`;
                document.body.appendChild(confetti);

                setTimeout(() => {
                    confetti.remove();
                }, 3000);
            }
        });
    </script>

</body>
</html>