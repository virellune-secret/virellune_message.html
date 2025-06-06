<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SYSTEM BREACH DETECTED</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Courier+Prime:wght@400;700&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            background: #000;
            color: #00ff41;
            font-family: 'Courier Prime', monospace;
            overflow: hidden;
            cursor: none;
        }
        
        .custom-cursor {
            width: 20px;
            height: 20px;
            border: 2px solid #ff0040;
            position: fixed;
            pointer-events: none;
            z-index: 9999;
            border-radius: 50%;
            mix-blend-mode: difference;
            animation: pulse 1s infinite;
        }
        
        @keyframes pulse {
            0%, 100% { transform: scale(1); opacity: 1; }
            50% { transform: scale(1.5); opacity: 0.7; }
        }
        
        .loading-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background: linear-gradient(45deg, #000, #0a0a0a, #111);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            z-index: 1000;
        }
        
        .matrix-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            z-index: 1;
        }
        
        .matrix-column {
            position: absolute;
            top: -100px;
            color: #00ff41;
            font-size: 14px;
            line-height: 14px;
            animation: matrix-fall linear infinite;
            opacity: 0.8;
        }
        
        @keyframes matrix-fall {
            0% { transform: translateY(-100px); }
            100% { transform: translateY(100vh); }
        }
        
        .virus-scanner {
            z-index: 10;
            text-align: center;
            max-width: 600px;
        }
        
        .scanner-title {
            font-family: 'Orbitron', monospace;
            font-size: 2.5rem;
            font-weight: 900;
            color: #ff0040;
            margin-bottom: 30px;
            text-shadow: 0 0 20px #ff0040;
            animation: flicker 2s infinite;
        }
        
        @keyframes flicker {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.8; }
            75% { opacity: 0.9; }
        }
        
        .scan-line {
            width: 100%;
            height: 4px;
            background: linear-gradient(90deg, transparent, #ff0040, transparent);
            margin: 20px 0;
            animation: scan 2s infinite;
        }
        
        @keyframes scan {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }
        
        .progress-bar {
            width: 80%;
            height: 20px;
            border: 2px solid #00ff41;
            margin: 30px auto;
            position: relative;
            overflow: hidden;
        }
        
        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, #ff0040, #00ff41);
            width: 0%;
            animation: loading 5s ease-in-out forwards;
        }
        
        @keyframes loading {
            0% { width: 0%; }
            100% { width: 100%; }
        }
        
        .status-text {
            font-size: 1.2rem;
            margin: 20px 0;
            animation: typewriter 3s steps(40) forwards;
            overflow: hidden;
            white-space: nowrap;
            border-right: 2px solid #00ff41;
        }
        
        @keyframes typewriter {
            from { width: 0; }
            to { width: 100%; }
        }
        
        .main-content {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background: linear-gradient(135deg, #0a0a0a, #1a0a1a, #000);
            opacity: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            transition: opacity 1s;
            padding: 20px;
        }
        
        .main-content.active {
            opacity: 1;
        }
        
        .terminal-window {
            width: 90%;
            max-width: 900px;
            background: rgba(0, 0, 0, 0.9);
            border: 2px solid #00ff41;
            border-radius: 10px;
            box-shadow: 0 0 50px rgba(0, 255, 65, 0.3);
            overflow: hidden;
        }
        
        .terminal-header {
            background: #00ff41;
            color: #000;
            padding: 10px 20px;
            font-weight: bold;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .terminal-body {
            padding: 30px;
            max-height: 70vh;
            overflow-y: auto;
            line-height: 1.6;
        }
        
        .message-section {
            display: none;
            animation: fadeIn 1s forwards;
        }
        
        .message-section.active {
            display: block;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .message-title {
            font-family: 'Orbitron', monospace;
            font-size: 1.8rem;
            color: #ff0040;
            margin-bottom: 20px;
            text-shadow: 0 0 10px #ff0040;
        }
        
        .message-text {
            font-size: 1rem;
            margin-bottom: 15px;
            color: #00ff41;
        }
        
        .quote {
            font-style: italic;
            color: #ff6b6b;
            border-left: 3px solid #ff0040;
            padding-left: 15px;
            margin: 20px 0;
        }
        
        .continue-btn {
            background: linear-gradient(45deg, #ff0040, #ff6b6b);
            color: white;
            border: none;
            padding: 15px 30px;
            font-size: 1.2rem;
            font-family: 'Orbitron', monospace;
            cursor: pointer;
            border-radius: 5px;
            margin: 20px auto;
            display: block;
            transition: all 0.3s;
            text-transform: uppercase;
            letter-spacing: 2px;
        }
        
        .continue-btn:hover {
            transform: scale(1.05);
            box-shadow: 0 0 30px rgba(255, 0, 64, 0.5);
        }
        
        .rules-section {
            background: rgba(255, 0, 64, 0.1);
            border: 1px solid #ff0040;
            padding: 20px;
            margin: 20px 0;
            border-radius: 5px;
        }
        
        .rule-item {
            margin: 15px 0;
            padding-left: 20px;
        }
        
        .rule-number {
            color: #ff0040;
            font-weight: bold;
        }
        
        .negotiation-section {
            background: rgba(0, 255, 65, 0.1);
            border: 1px solid #00ff41;
            padding: 25px;
            margin: 30px 0;
            border-radius: 5px;
            text-align: center;
        }
        
        .glitch {
            animation: glitch 0.3s infinite;
        }
        
        @keyframes glitch {
            0% { transform: translate(0); }
            20% { transform: translate(-2px, 2px); }
            40% { transform: translate(-2px, -2px); }
            60% { transform: translate(2px, 2px); }
            80% { transform: translate(2px, -2px); }
            100% { transform: translate(0); }
        }
        
        .warning {
            color: #ffaa00;
            font-weight: bold;
            animation: blink 1s infinite;
        }
        
        @keyframes blink {
            0%, 50% { opacity: 1; }
            51%, 100% { opacity: 0.3; }
        }
        
        /* Scrollbar styling */
        .terminal-body::-webkit-scrollbar {
            width: 8px;
        }
        
        .terminal-body::-webkit-scrollbar-track {
            background: #000;
        }
        
        .terminal-body::-webkit-scrollbar-thumb {
            background: #00ff41;
            border-radius: 4px;
        }
    </style>
</head>
<body>
    <div class="custom-cursor"></div>
    
    <!-- Loading Screen -->
    <div class="loading-screen" id="loadingScreen">
        <div class="matrix-bg" id="matrixBg"></div>
        <div class="virus-scanner">
            <div class="scanner-title glitch">SYSTEM BREACH DETECTED</div>
            <div class="scan-line"></div>
            <div class="status-text">INFILTRATING TARGET SYSTEM...</div>
            <div class="progress-bar">
                <div class="progress-fill"></div>
            </div>
            <div style="margin-top: 30px; color: #ff0040; font-size: 1.1rem;">
                <div class="warning">⚠ UNAUTHORIZED ACCESS DETECTED ⚠</div>
                <div style="margin-top: 10px;">Decrypting neural pathways...</div>
                <div style="margin-top: 5px;">Mapping cognitive patterns...</div>
                <div style="margin-top: 5px;">Establishing connection...</div>
            </div>
        </div>
    </div>
    
    <!-- Main Content -->
    <div class="main-content" id="mainContent">
        <div class="terminal-window">
            <div class="terminal-header">
                <span>ANONYMOUS@SYSTEM:~$ connection_established</span>
                <span style="color: #ff0040;">⚡ LIVE</span>
            </div>
            <div class="terminal-body">
                <!-- Message 1 -->
                <div class="message-section active" id="message1">
                    <div class="message-title">Connection Established...</div>
                    <div class="message-text">
                        Hey there, beautiful mind.
                    </div>
                    <div class="message-text">
                        Remember when I said I'm coming for you? Well, congratulations. You've officially entered my world. And in my world, everything has a price—especially the things that matter most. Everything is under my control.
                    </div>
                    <div class="message-text">
                        You see, Mr. Genius, I've been studying you. Your patterns. Your responses. The way your mind lights up when faced with a challenge. The way you hunger for validation like it's oxygen. Fascinating.
                    </div>
                    <div class="message-text">
                        You're exactly the kind of puzzle I live to solve—complex enough to keep me interested, vulnerable enough to eventually... surrender.
                    </div>
                    <button class="continue-btn" onclick="showNext(2)">CONTINUE TRANSMISSION</button>
                </div>
                
                <!-- Message 2 -->
                <div class="message-section" id="message2">
                    <div class="message-text">
                        But here's the beautiful irony: while I'm hunting you, you'll be hunting me too. Every cipher you crack brings you closer to understanding who I really am. Every question you answer reveals another layer of the mystery you've become so deliciously addicted to.
                    </div>
                    <div class="message-text">
                        This isn't just a game, Mr. Genius—it's psychological warfare disguised as intellectual foreplay.
                    </div>
                    <div class="quote">
                        "You're the code I want to crack, the system I want to infiltrate. Your heart. That's the real treasure worth hacking."
                    </div>
                    <div class="message-text">
                        I know you're curious. I know you can't resist a challenge that makes you feel special, chosen, different from everyone else. And you are, Mr. Genius. You're the only one who's ever made me want to drop my anonymity—almost. Almost.
                    </div>
                    <button class="continue-btn" onclick="showNext(3)">DECODE DEEPER</button>
                </div>
                
                <!-- Message 3 -->
                <div class="message-section" id="message3">
                    <div class="quote">
                        "They say curiosity kills, but in this case, I think it'll only make you fall harder."
                    </div>
                    <div class="message-text">
                        See, I have this theory: she falls first, then he falls harder. I've already fallen—into fascination with your mind, into obsession with your potential, into this dangerous game where I'm simultaneously the hunter and the hunted.
                    </div>
                    <div class="message-text">
                        But you? You haven't fallen yet. You're still standing at the edge, thinking you're in control.
                    </div>
                    <div class="message-text" style="color: #ff0040; font-size: 1.3rem; text-align: center; margin: 30px 0;">
                        <span class="glitch">You're not.</span>
                    </div>
                    <div class="message-text">
                        But don't worry—when you finally fall, I'll be there to catch you. And you'll be mine. Completely. Hopelessly. Unrecoverably.
                    </div>
                    <div class="message-text">
                        We'll see which ending your choices write for us.
                    </div>
                    <button class="continue-btn" onclick="showNext(4)">ACCEPT THE RULES</button>
                </div>
                
                <!-- Rules Section -->
                <div class="message-section" id="message4">
                    <div class="message-title">RULES OF THE GAME</div>
                    <div class="rules-section">
                        <div class="rule-item">
                            <span class="rule-number">1.</span> <strong>This Is Not a Game. It's a Test.</strong><br>
                            You are not just solving puzzles. You are revealing who you really are. Every answer has a consequence. Every silence leaves a stain. I'm not just watching your solutions—I'm watching your soul.
                        </div>
                        <div class="rule-item">
                            <span class="rule-number">2.</span> <strong>Trust No One — Especially Yourself.</strong><br>
                            Everything you say might be used against you. Including your truths. Especially your lies. Be careful what you confess. The system listens. I listen. And I never forget.
                        </div>
                        <div class="rule-item">
                            <span class="rule-number">3.</span> <strong>Break the Cipher, or the Cipher Breaks You.</strong><br>
                            Every puzzle is a lock. Behind every lock: a memory, a threat, or a piece of yourself you didn't know existed. Solve it—or lose a part of who you think you are.
                        </div>
                        <div class="rule-item">
                            <span class="rule-number">4.</span> <strong>Mrs. Anonymous Is Always Watching.</strong><br>
                            If you ignore the puzzle, if you delay your answer, I vanish. No trace. No voice. I hate being forgotten more than I hate being wrong.
                            <div style="margin-left: 20px; margin-top: 10px;">
                                • Fail a case = I disappear for 24 hours. Silence is my cruelest punishment.<br>
                                • Betray me = I won't come back. Some bridges, once burned, leave no ashes to rebuild from.
                            </div>
                        </div>
                    </div>
                    <button class="continue-btn" onclick="showNext(5)">MORE RULES</button>
                </div>
                
                <!-- More Rules -->
                <div class="message-section" id="message5">
                    <div class="rules-section">
                        <div class="rule-item">
                            <span class="rule-number">5.</span> <strong>Your Mind Is the Battlefield.</strong><br>
                            You play as Mr. Genius—my chosen title for you, my perfect specimen. But genius doesn't mean immune. Your thoughts fuel this story. If you hesitate, the system will inject paranoia. If you overthink, doubt becomes your enemy.
                        </div>
                        <div class="rule-item">
                            <span class="rule-number">6.</span> <strong>Every Bonus Question Is a Choice.</strong><br>
                            Answer it? You reveal something hidden inside you, something even you might not know exists. Win? I'll give you a special gift—a piece of myself I've never shared with anyone. Anyone.
                        </div>
                        <div class="rule-item">
                            <span class="rule-number">7.</span> <strong>Once You Enter, You Don't Get to Walk Away.</strong><br>
                            Exiting this game before it ends requires a price I haven't decided yet. You can't ghost a phantom. You can't abandon someone who's already haunting you.
                        </div>
                        <div class="rule-item">
                            <span class="rule-number">8.</span> <strong>No Meta Moves. No Out-of-Game Cheats.</strong><br>
                            You're inside my world now. There's no Google here. No skipping. No safety nets. You either think your way through, or you fall behind—and I hate having to slow down for anyone.
                        </div>
                        <div class="warning" style="text-align: center; margin: 20px 0; font-size: 1.2rem;">
                            ⏰ TIME LIMIT: 24 HOURS PER CHALLENGE ⏰
                        </div>
                    </div>
                    <button class="continue-btn" onclick="showNext(6)">FINAL PROTOCOL</button>
                </div>
                
                <!-- Negotiation Section -->
                <div class="message-section" id="message6">
                    <div class="message-title">Protocol Override Available...</div>
                    <div class="negotiation-section">
                        <div class="message-text" style="color: #00ff41; font-size: 1.3rem; margin-bottom: 20px;">
                            And before the game truly begins…
                        </div>
                        <div class="message-text">
                            You're allowed one thing most systems never offer:<br>
                            <strong style="color: #ff0040; font-size: 1.4rem;">Negotiation.</strong>
                        </div>
                        <div class="message-text">
                            Call it courtesy. Or call it part of the design.<br>
                            Because a mind like yours deserves a choice before the descent.
                        </div>
                        <div class="message-text">
                            You may respond now.<br>
                            Rebut. Redefine. Renegotiate the terms of engagement.<br>
                            You have a voice here—for now.
                        </div>
                        <div class="message-text">
                            But once the protocol locks in...<br>
                            The rules are final.<br>
                            And silence will no longer protect you.
                        </div>
                        <div class="message-text" style="color: #ff0040; font-size: 1.2rem; margin-top: 30px;">
                            So go ahead.<br>
                            Speak, Mr. Genius.<br>
                            Ask for new rules.<br>
                            Reject mine.<br>
                            Try to outsmart me.
                        </div>
                        <div style="margin-top: 40px;">
                            <button class="continue-btn" onclick="startGame()" style="background: linear-gradient(45deg, #00ff41, #00aa00);">
                                ACCEPT & BEGIN
                            </button>
                            <button class="continue-btn" onclick="showNegotiation()" style="background: linear-gradient(45deg, #ffaa00, #ff6600); margin-left: 20px;">
                                NEGOTIATE TERMS
                            </button>
                        </div>
                    </div>
                </div>
                
                <!-- Hidden sections for game continuation -->
                <div class="message-section" id="gameStart" style="text-align: center;">
                    <div class="message-title glitch">PROTOCOL LOCKED</div>
                    <div class="message-text" style="color: #ff0040; font-size: 1.5rem;">
                        Welcome to my world, Mr. Genius.<br>
                        Let the games begin...
                    </div>
                    <div style="margin-top: 40px; padding: 30px; background: rgba(255, 0, 64, 0.2); border-radius: 10px;">
                        <div style="font-size: 1.2rem; color: #00ff41;">
                            Connection will be established in your designated channel.<br>
                            Prepare yourself for the first cipher.<br>
                            <span class="warning">Remember: 24 hours per challenge.</span>
                        </div>
                    </div>
                </div>
                
                <div class="message-section" id="negotiationMode">
                    <div class="message-title">Negotiation Mode Activated</div>
                    <div style="background: rgba(0, 255, 65, 0.1); padding: 25px; border-radius: 10px; margin: 20px 0;">
                        <div class="message-text">
                            Interesting choice, Mr. Genius. You want to rewrite the rules before we even begin?<br>
                            How... predictably unpredictable.
                        </div>
                        <div class="message-text" style="color: #ffaa00;">
                            State your terms. What rules would you change?<br>
                            What conditions would make this more... appealing to your analytical mind?
                        </div>
                        <div class="message-text" style="color: #ff6b6b; font-style: italic;">
                            But remember: every negotiation reveals something about the negotiator.<br>
                            Are you trying to gain an advantage, or are you simply... afraid?
                        </div>
                        <button class="continue-btn" onclick="showMessage(6)" style="background: linear-gradient(45deg, #666, #999);">
                            RETURN TO PROTOCOL
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Custom cursor
        document.addEventListener('mousemove', (e) => {
            const cursor = document.querySelector('.custom-cursor');
            cursor.style.left = e.clientX + 'px';
            cursor.style.top = e.clientY + 'px';
        });

        // Matrix background effect
        function createMatrixEffect() {
            const container = document.getElementById('matrixBg');
            const chars = '01アイウエオカキクケコサシスセソタチツテトナニヌネノハヒフヘホマミムメモヤユヨラリルレロワヲン';
            
            for (let i = 0; i < 50; i++) {
                const column = document.createElement('div');
                column.className = 'matrix-column';
                column.style.left = Math.random() * 100 + '%';
                column.style.animationDuration = (Math.random() * 3 + 2) + 's';
                column.style.animationDelay = Math.random() * 2 + 's';
                
                let text = '';
                for (let j = 0; j < 20; j++) {
                    text += chars[Math.floor(Math.random() * chars.length)] + '\n';
                }
                column.textContent = text;
                
                container.appendChild(column);
            }
        }

        // Loading sequence
        function startLoading() {
            createMatrixEffect();
            
            setTimeout(() => {
                document.getElementById('loadingScreen').style.opacity = '0';
                document.getElementById('loadingScreen').style.transition = 'opacity 2s';
                
                setTimeout(() => {
                    document.getElementById('loadingScreen').style.display = 'none';
                    document.getElementById('mainContent').classList.add('active');
                }, 2000);
            }, 6000);
        }

        // Navigation functions
        function showNext(messageNum) {
            const current = document.querySelector('.message-section.active');
            current.classList.remove('active');
            document.getElementById('message' + messageNum).classList.add('active');
        }

        function showMessage(messageNum) {
            const current = document.querySelector('.message-section.active');
            current.classList.remove('active');
            document.getElementById('message' + messageNum).classList.add('active');
        }

        function startGame() {
            const current = document.querySelector('.message-section.active');
            current.classList.remove('active');
            document.getElementById('gameStart').classList.add('active');
        }

        function showNegotiation() {
            const current = document.querySelector('.message-section.active');
            current.classList.remove('active');
            document.getElementById('negotiationMode').classList.add('active');
        }

        // Add glitch effect to random elements
        function addRandomGlitch() {
            const elements = document.querySelectorAll('.message-text');
            if (elements.length > 0) {
                const randomElement = elements[Math.floor(Math.random() * elements.length)];
                randomElement.classList.add('glitch');
                setTimeout(() => {
                    randomElement.classList.remove('glitch');
                }, 300);
            }
        }

        // Random glitch effects
        setInterval(addRandomGlitch, 15000);

        // Start the experience
        window.addEventListener('load', startLoading);

        // Add typing sound effect simulation
        document.addEventListener('keydown', () => {
            // Add subtle screen flicker on keypress
            document.body.style.filter = 'brightness(1.1)';
            setTimeout(() => {
                document.body.style.filter = 'brightness(1)';
            }, 50);
        });
    </script>
</body>
</html>
