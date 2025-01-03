<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0"> 
    <title>To 🦋 </title>
    <style>
        @keyframes heartbeat {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes float {
            0% { transform: translateY(0) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(10deg); }
            100% { transform: translateY(0) rotate(0deg); }
        }

        @keyframes twinkle {
            0% { opacity: 0.3; }
            50% { opacity: 1; }
            100% { opacity: 0.3; }
        }

        body {
            margin: 0;
            padding: 0;
            min-height: 100vh;
            font-family: 'Arial', sans-serif;
            color: #fff;
            position: relative;
            overflow: hidden;
            background: linear-gradient(to bottom, #0a0a2a, #1a1a3a);
        }

        .stars {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
        }

        .star {
            position: absolute;
            background: white;
            border-radius: 50%;
            animation: twinkle 2s infinite;
        }

        /* Music Controls */
        .music-controls {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: rgba(255, 255, 255, 0.1);
            padding: 10px;
            border-radius: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
            backdrop-filter: blur(5px);
            z-index: 1000;
        }

        .music-controls button {
            background: transparent;
            border: 1px solid white;
            color: white;
            padding: 8px;
            border-radius: 50%;
            cursor: pointer;
            transition: all 0.3s ease;
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .music-controls button:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: scale(1.1);
        }

        .volume-slider {
            width: 100px;
            height: 4px;
            -webkit-appearance: none;
            background: rgba(255, 255, 255, 0.3);
            border-radius: 2px;
            outline: none;
        }

        .volume-slider::-webkit-slider-thumb {
            -webkit-appearance: none;
            width: 15px;
            height: 15px;
            background: white;
            border-radius: 50%;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .volume-slider::-webkit-slider-thumb:hover {
            transform: scale(1.2);
        }

        /* Entrance Page Styles */
        .entrance-page {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 1000;
            transition: opacity 1s ease-out;
            background: linear-gradient(to bottom, #0a0a2a, #1a1a3a);
        }

        .entrance-title {
            font-size: 2.5em;
            color: white;
            text-align: center;
            margin-bottom: 30px;
            animation: fadeIn 2s ease-in;
            text-shadow: 0 0 10px rgba(255, 255, 255, 0.5);
        }

        .enter-button {
            padding: 15px 40px;
            font-size: 1.2em;
            background: transparent;
            border: 2px solid white;
            color: white;
            border-radius: 30px;
            cursor: pointer;
            transition: all 0.3s ease;
            animation: fadeIn 2s ease-in;
            position: relative;
            overflow: hidden;
        }

        .enter-button:hover {
            background: rgba(255, 255, 255, 0.1);
            transform: scale(1.05);
            box-shadow: 0 0 20px rgba(255, 255, 255, 0.3);
        }

        /* Main Content Styles */
        .main-content {
            display: none;
            opacity: 0;
            transition: opacity 1s ease-in;
        }

        .love-symbols {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        .symbol {
            position: absolute;
            font-size: 24px;
            opacity: 0.7;
            animation: float 6s infinite;
            text-shadow: 0 0 10px rgba(255, 255, 255, 0.5);
        }

        .container {
            max-width: 800px;
            padding: 40px;
            background: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            box-shadow: 0 0 30px rgba(255, 255, 255, 0.1);
            margin: 20px auto;
            color: #444;
            position: relative;
            z-index: 2;
        }
    </style>
</head>
<body>
    <!-- Audio Background -->
    <audio id="backgroundMusic" loop>
        <source src="tmusic.mp3" type="audio/mp3">
        Your browser does not support the audio element.
    </audio>

    <!-- Music Controls -->
    <div class="music-controls">
        <button id="playPauseBtn" title="Play/Pause">▶️</button>
        <input type="range" id="volumeSlider" class="volume-slider" min="0" max="1" step="0.1" value="0.5" title="Volume">
    </div>

    <div class="stars" id="stars"></div>
    
    <!-- Entrance Page -->
    <div class="entrance-page" id="entrancePage">
        <h1 class="entrance-title">❤️<br> Note To T <br></h1>
        <button class="enter-button" id="enterButton">come in </button>
    </div>

    <!-- Main Content -->
    <div class="main-content" id="mainContent">
        <div class="love-symbols" id="loveSymbols"></div>
        <div class="container">
            I don't know how to start because words feel so small when it comes to you. You're like this perfect blend of innocence and mischief, laughter and depth.   As I said to you before you have  this way of lighting up a room with your smile, and your laugh—ohhhh, it's like music that stayed in my head from long I don't know if you've noticed, but when I see you, the world just stops for a moment for me. Time gets slows, and everything else feels blurry because, you're the only thing in focus. The  moment I met you, I've carried a piece of you with me, deep within. You've become a part of me, and I find traces of you in everything I do, in every thought I have. You are always with me, even when we're apart I don't know if you feel the same way about me, and honestly, I'm not here to put pressure on you. If your answer is no, I'll accept it with all my heart, and I'll still think you're the most incredible beautiful person i have ever  met in this 25 years of my life, From the moment I met you, something inside me knew that you were someone special. As I've gotten to know you, my heart has only grown more certain that I want to share my life with you. I want to be by your side through all of life's moments, to support you, and to create a future together. So, today I'm asking you—will you marry me? I promise to cherish you, respect you, and love you with everything I am I promise you this: First- I will be the luckiest man in the world. But I will also be the most concerned, because treating you like the princess you are and ensuring that your 'yes' was the best decision you've ever made. No matter what you choose, just know you'll always have a place in my heart. Yours, Always Thinking of You,
        </div>
    </div>

    <script>
        // Music Controls
        const audio = document.getElementById('backgroundMusic');
        const playPauseBtn = document.getElementById('playPauseBtn');
        const volumeSlider = document.getElementById('volumeSlider');

        // Set initial volume
        audio.volume = volumeSlider.value;

        playPauseBtn.addEventListener('click', () => {
            if (audio.paused) {
                audio.play();
                playPauseBtn.textContent = '⏸️';
            } else {
                audio.pause();
                playPauseBtn.textContent = '▶️';
            }
        });

        volumeSlider.addEventListener('input', (e) => {
            audio.volume = e.target.value;
        });

        // Create stars
        const starsContainer = document.getElementById('stars');
        for (let i = 0; i < 200; i++) {
            const star = document.createElement('div');
            star.className = 'star';
            star.style.width = Math.random() * 3 + 'px';
            star.style.height = star.style.width;
            star.style.left = Math.random() * 100 + 'vw';
            star.style.top = Math.random() * 100 + 'vh';
            star.style.animationDelay = Math.random() * 2 + 's';
            starsContainer.appendChild(star);
        }

        // Enter button functionality
        document.getElementById('enterButton').addEventListener('click', function() {
            const entrancePage = document.getElementById('entrancePage');
            const mainContent = document.getElementById('mainContent');
            
            // Start playing music when entering
            audio.play().catch(e => console.log('Auto-play prevented:', e));
            playPauseBtn.textContent = '⏸️';
            
            // Fade out entrance page
            entrancePage.style.opacity = '0';
            
            // After entrance fade out, show main content
            setTimeout(() => {
                entrancePage.style.display = 'none';
                mainContent.style.display = 'block';
                
                // Small delay before fading in main content
                setTimeout(() => {
                    mainContent.style.opacity = '1';
                    
                    // Start creating love symbols after main content is visible
                    createInitialSymbols();
                    setInterval(createSymbol, 1000);
                }, 100);
            }, 1000);
        });

        // Love symbols functionality
        const symbols = ['❤️', '💕', '💝', '💖', '💗', '💓', '💘', '🌹', '✨', '💫'];
        const container = document.getElementById('loveSymbols');

        function createSymbol() {
            const symbol = document.createElement('div');
            symbol.className = 'symbol';
            symbol.style.left = Math.random() * 100 + 'vw';
            symbol.style.top = Math.random() * 100 + 'vh';
            symbol.style.animationDelay = Math.random() * 5 + 's';
            symbol.textContent = symbols[Math.floor(Math.random() * symbols.length)];
            container.appendChild(symbol);

            setTimeout(() => {
                symbol.remove();
            }, 6000);
        }

        function createInitialSymbols() {
            for (let i = 0; i < 15; i++) {
                createSymbol();
            }
        }
    </script>
</body>
</html>
