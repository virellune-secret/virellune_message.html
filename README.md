<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Encrypted Soul - Message from Virellune</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;700&family=Crimson+Text:ital,wght@0,400;0,600;1,400&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'JetBrains Mono', monospace;
            background: #0a0a0a;
            color: #00ff88;
            overflow-x: hidden;
            cursor: none;
        }

        /* Custom Cursor */
        .cursor {
            position: fixed;
            width: 20px;
            height: 20px;
            border: 2px solid #00ff88;
            border-radius: 50%;
            background: rgba(0, 255, 136, 0.1);
            pointer-events: none;
            z-index: 9999;
            transition: all 0.1s ease;
            backdrop-filter: blur(5px);
        }

        .cursor.hover {
            transform: scale(2);
            background: rgba(0, 255, 136, 0.3);
            border-color: #ff0080;
        }

        /* Matrix Rain Background */
        .matrix-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            opacity: 0.1;
        }

        /* Glitch Effect */
        .glitch {
            position: relative;
            animation: glitch 2s infinite;
        }

        @keyframes glitch {
            0%, 100% { transform: translate(0); }
            20% { transform: translate(-2px, 2px); }
            40% { transform: translate(-2px, -2px); }
            60% { transform: translate(2px, 2px); }
            80% { transform: translate(2px, -2px); }
        }

        /* Header */
        .header {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(0, 0, 0, 0.9);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid #00ff88;
            padding: 1rem 0;
            z-index: 1000;
        }

        .header-content {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: #ff0080;
            text-shadow: 0 0 10px #ff0080;
        }

        .system-status {
            font-size: 0.8rem;
            color: #00ff88;
        }

        .status-dot {
            display: inline-block;
            width: 8px;
            height: 8px;
            background: #00ff88;
            border-radius: 50%;
            margin-right: 0.5rem;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.3; }
        }

        /* Main Container */
        .container {
            max-width: 900px;
            margin: 0 auto;
            padding: 8rem 2rem 4rem;
            min-height: 100vh;
        }

        /* Terminal Window */
        .terminal {
            background: rgba(0, 0, 0, 0.8);
            border: 1px solid #00ff88;
            border-radius: 8px;
            margin-bottom: 3rem;
            box-shadow: 0 0 30px rgba(0, 255, 136, 0.3);
            position: relative;
            overflow: hidden;
        }

        .terminal::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 2px;
            background: linear-gradient(90deg, #ff0080, #00ff88, #ff0080);
            animation: scan 3s linear infinite;
        }

        @keyframes scan {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }

        .terminal-header {
            background: #1a1a1a;
            padding: 0.5rem 1rem;
            border-bottom: 1px solid #333;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .terminal-dots {
            display: flex;
            gap: 0.3rem;
        }

        .dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
        }

        .dot.red { background: #ff5f56; }
        .dot.yellow { background: #ffbd2e; }
        .dot.green { background: #27ca3f; }

        .terminal-title {
            margin-left: 1rem;
            font-size: 0.9rem;
            color: #888;
        }

        .terminal-content {
            padding: 2rem;
            font-size: 0.9rem;
            line-height: 1.6;
        }

        /* Email Header */
        .email-header {
            border: 1px solid #333;
            padding: 1.5rem;
            margin-bottom: 2rem;
            background: rgba(0, 255, 136, 0.05);
        }

        .email-field {
            margin-bottom: 0.5rem;
        }

        .email-field strong {
            color: #ff0080;
            width: 80px;
            display: inline-block;
        }

        /* Message Content */
        .message-content {
            background: rgba(0, 0, 0, 0.6);
            border: 1px solid #333;
            padding: 2rem;
            border-radius: 8px;
            position: relative;
        }

        .encryption-header {
            text-align: center;
            margin-bottom: 2rem;
            padding: 1rem;
            border: 1px dashed #00ff88;
            background: rgba(0, 255, 136, 0.1);
            font-weight: 700;
            letter-spacing: 2px;
        }

        /* Quote Styling */
        .quote {
            font-family: 'Crimson Text', serif;
            font-style: italic;
            font-size: 1.1rem;
            color: #ff0080;
            text-align: center;
            margin: 2rem 0;
            padding: 1rem;
            border-left: 3px solid #ff0080;
            background: rgba(255, 0, 128, 0.1);
            position: relative;
        }

        .quote::before,
        .quote::after {
            content: '"';
            font-size: 2rem;
            color: #00ff88;
            position: absolute;
        }

        .quote::before {
            top: 0;
            left: 0.5rem;
        }

        .quote::after {
            bottom: 0;
            right: 0.5rem;
        }

        /* Message Text */
        .message-text {
            font-size: 1rem;
            line-height: 1.8;
            margin: 1.5rem 0;
        }

        .message-text p {
            margin-bottom: 1.5rem;
        }

        .highlight {
            color: #ff0080;
            font-weight: 500;
            text-shadow: 0 0 5px #ff0080;
        }

        /* Special Effects */
        .typewriter {
            overflow: hidden;
            border-right: 3px solid #00ff88;
            white-space: nowrap;
            animation: typewriter 4s steps(40) 1s forwards, blink 0.75s step-end infinite;
            width: 0;
        }

        @keyframes typewriter {
            from { width: 0; }
            to { width: 100%; }
        }

        @keyframes blink {
            from, to { border-color: transparent; }
            50% { border-color: #00ff88; }
        }

        /* Signature */
        .signature {
            margin-top: 3rem;
            padding: 2rem;
            border: 1px solid #ff0080;
            background: rgba(255, 0, 128, 0.1);
            text-align: center;
            position: relative;
        }

        .signature-title {
            font-size: 1.2rem;
            color: #ff0080;
            margin-bottom: 1rem;
            font-weight: 700;
        }

        .signature-subtitle {
            font-size: 0.9rem;
            color: #888;
            font-style: italic;
        }

        /* Floating Elements */
        .floating-code {
            position: fixed;
            font-size: 0.8rem;
            color: rgba(0, 255, 136, 0.3);
            pointer-events: none;
            animation: float 20s linear infinite;
            z-index: -1;
        }

        @keyframes float {
            0% {
                transform: translateY(100vh) rotate(0deg);
                opacity: 0;
            }
            10%, 90% {
                opacity: 1;
            }
            100% {
                transform: translateY(-100vh) rotate(360deg);
                opacity: 0;
            }
        }

        /* Interactive Elements */
        .decode-button {
            background: linear-gradient(45deg, #ff0080, #00ff88);
            border: none;
            padding: 1rem 2rem;
            color: #000;
            font-family: 'JetBrains Mono', monospace;
            font-weight: 700;
            border-radius: 4px;
            cursor: pointer;
            transition: all 0.3s ease;
            margin: 2rem auto;
            display: block;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .decode-button:hover {
            transform: scale(1.05);
            box-shadow: 0 0 20px rgba(255, 0, 128, 0.5);
        }

        /* Hidden Message */
        .hidden-message {
            opacity: 0;
            transform: translateY(20px);
            transition: all 1s ease;
            margin-top: 2rem;
            padding: 2rem;
            border: 1px dashed #00ff88;
            background: rgba(0, 255, 136, 0.1);
        }

        .hidden-message.revealed {
            opacity: 1;
            transform: translateY(0);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .container {
                padding: 6rem 1rem 2rem;
            }
            
            .terminal-content {
                padding: 1rem;
                font-size: 0.8rem;
            }
            
            .quote {
                font-size: 1rem;
            }
        }

        /* Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }

        ::-webkit-scrollbar-track {
            background: #000;
        }

        ::-webkit-scrollbar-thumb {
            background: #00ff88;
            border-radius: 4px;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: #ff0080;
        }
    </style>
</head>
<body>
    <div class="cursor"></div>
    <canvas class="matrix-bg" id="matrix"></canvas>
    
    <header class="header">
        <div class="header-content">
            <div class="logo glitch">VIRELLUNE.SYS</div>
            <div class="system-status">
                <span class="status-dot"></span>
                CONNECTION ESTABLISHED
            </div>
        </div>
    </header>

    <div class="container">
        <div class="terminal">
            <div class="terminal-header">
                <div class="terminal-dots">
                    <div class="dot red"></div>
                    <div class="dot yellow"></div>
                    <div class="dot green"></div>
                </div>
                <div class="terminal-title">encrypted_transmission.exe</div>
            </div>
            <div class="terminal-content">
                <div class="email-header">
                    <div class="email-field">
                        <strong>From:</strong> anonymous@localhost
                    </div>
                    <div class="email-field">
                        <strong>To:</strong> crush@zion.com
                    </div>
                    <div class="email-field">
                        <strong>Subject:</strong> <span class="highlight">Just a tiny glitch in your system</span>
                    </div>
                    <div class="email-field">
                        <strong>Encrypted:</strong> True
                    </div>
                    <div class="email-field">
                        <strong>Priority:</strong> <span class="highlight">MAXIMUM</span>
                    </div>
                </div>

                <div class="message-content">
                    <div class="encryption-header glitch">
                        ---BEGIN ENCRYPTED SOUL---
                    </div>

                    <div class="quote">
                        You pierce my soul. I am half agony, half hope.
                        <br><small>— Jane Austen, Persuasion</small>
                    </div>

                    <div class="quote">
                        The very best thing you can do for the whole world is to make the most of yourself.
                        <br><small>— Wallace Wattles</small>
                    </div>

                    <div class="message-text">
                        <p><span class="highlight">Hey, genius.</span></p>
                        
                        <p>Your response to my first transmission was... <em class="highlight">fascinating</em>. The way you unraveled each layer, the excitement in your words when you cracked the codes—it told me everything I needed to know about the beautiful mind I'm dealing with.</p>

                        <p><strong>Fun fact:</strong> I'm not the type who gives up easily. And definitely not reckless when it comes to wanting something... or <span class="highlight">someone</span>. Maybe, for me, just watching you from afar used to be enough—admiring how you think, how your mind works like poetry in motion.</p>

                        <p>But that message you decoded was just the first breadcrumb. Starting today, you'll need to brace yourself. <span class="highlight">I'm coming for you.</span></p>

                        <p>Not in a rush. Not loudly. But carefully. Precisely. I'll try to win your heart—if you don't mind.</p>

                        <div class="quote">
                            Mystery creates wonder and wonder is the basis of man's desire to understand.
                            <br><small>— Neil Armstrong</small>
                        </div>

                        <p><strong>Why anonymous? Why puzzles?</strong> Simple. I believe in the power of intrigue. You're someone who appreciates intellectual stimulation, who gets excited by challenges that others might find impossible. And in this game, you're not just the player—<span class="highlight">you're the prize</span>.</p>

                        <p>No—more than that. You're the code I want to crack, the system I want to infiltrate. <span class="highlight">Your heart.</span> That's the real treasure worth hacking.</p>

                        <p>They say curiosity kills, but in this case, I think it'll only make you fall harder. So let me ask just once: <span class="highlight">Are you single—or something? Would you let me play this game?</span></p>

                        <p>I'm not asking for a guarantee. Just a chance. Everyone deserves at least that, right?</p>

                        <div class="quote">
                            Life is either a daring adventure or nothing at all.
                            <br><small>— Helen Keller</small>
                        </div>

                        <p>And no, I don't back down before a war even begins. So trust me—<span class="highlight">this will be fun</span>. Especially for someone like you.</p>
                    </div>

                    <button class="decode-button" onclick="revealSecret()">
                        DECODE HIDDEN MESSAGE
                    </button>

                    <div class="hidden-message" id="hiddenMessage">
                        <p><strong>DECRYPTION COMPLETE...</strong></p>
                        <p>You found it. The hidden layer within the transmission.</p>
                        <p>This proves you're exactly who I thought you were—someone who doesn't stop until they've uncovered every secret.</p>
                        <p><span class="highlight">I'm waiting for your reply...</span></p>
                    </div>

                    <div class="signature">
                        <div class="signature-title">— VIRELLUNE —</div>
                        <div class="signature-subtitle">
                            "gabungan dari kata 'veil' (tirai) dan 'lune' (bulan dalam Prancis),<br>
                            seperti bulan yang tersembunyi di balik tirai malam."
                        </div>
                    </div>

                    <div class="encryption-header" style="margin-top: 2rem;">
                        ---END ENCRYPTED SOUL---
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Custom Cursor
        const cursor = document.querySelector('.cursor');
        
        document.addEventListener('mousemove', (e) => {
            cursor.style.left = e.clientX - 10 + 'px';
            cursor.style.top = e.clientY - 10 + 'px';
        });

        document.addEventListener('mouseenter', () => {
            cursor.style.opacity = '1';
        });

        document.addEventListener('mouseleave', () => {
            cursor.style.opacity = '0';
        });

        // Cursor hover effects
        const interactiveElements = document.querySelectorAll('button, a, .highlight');
        interactiveElements.forEach(el => {
            el.addEventListener('mouseenter', () => {
                cursor.classList.add('hover');
            });
            el.addEventListener('mouseleave', () => {
                cursor.classList.remove('hover');
            });
        });

        // Matrix Rain Effect
        const canvas = document.getElementById('matrix');
        const ctx = canvas.getContext('2d');

        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;

        const matrix = "ABCDEFGHIJKLMNOPQRSTUVWXYZ123456789@#$%^&*()*&^%+-/~{[|`]}";
        const matrixArray = matrix.split("");

        const fontSize = 10;
        const columns = canvas.width / fontSize;

        const drops = [];
        for(let x = 0; x < columns; x++) {
            drops[x] = 1;
        }

        function draw() {
            ctx.fillStyle = 'rgba(0, 0, 0, 0.04)';
            ctx.fillRect(0, 0, canvas.width, canvas.height);
            
            ctx.fillStyle = '#00ff88';
            ctx.font = fontSize + 'px monospace';

            for(let i = 0; i < drops.length; i++) {
                const text = matrixArray[Math.floor(Math.random() * matrixArray.length)];
                ctx.fillText(text, i * fontSize, drops[i] * fontSize);
                
                if(drops[i] * fontSize > canvas.height && Math.random() > 0.975) {
                    drops[i] = 0;
                }
                drops[i]++;
            }
        }

        setInterval(draw, 35);

        // Floating Code Elements
        function createFloatingCode() {
            const codes = ['01010101', '11001100', 'DECODE', 'ENCRYPT', '0xFFFF', 'NULL', 'TRUE', 'FALSE'];
            const code = document.createElement('div');
            code.className = 'floating-code';
            code.textContent = codes[Math.floor(Math.random() * codes.length)];
            code.style.left = Math.random() * 100 + 'vw';
            code.style.animationDuration = (Math.random() * 10 + 10) + 's';
            document.body.appendChild(code);

            setTimeout(() => {
                code.remove();
            }, 20000);
        }

        setInterval(createFloatingCode, 3000);

        // Reveal Hidden Message
        function revealSecret() {
            const hiddenMessage = document.getElementById('hiddenMessage');
            const button = document.querySelector('.decode-button');
            
            button.textContent = 'DECRYPTING...';
            button.disabled = true;
            
            setTimeout(() => {
                hiddenMessage.classList.add('revealed');
                button.style.display = 'none';
            }, 2000);
        }

        // Glitch Effect on Scroll
        window.addEventListener('scroll', () => {
            const scrolled = window.pageYOffset;
            const parallax = document.querySelectorAll('.glitch');
            const speed = 0.5;

            parallax.forEach(element => {
                const yPos = -(scrolled * speed);
                element.style.transform = `translateY(${yPos}px)`;
            });
        });

        // Typewriter Effect for Specific Elements
        const typewriterElements = document.querySelectorAll('.message-text p:first-child');
        typewriterElements.forEach(el => {
            el.classList.add('typewriter');
        });

        // Window Resize Handler
        window.addEventListener('resize', () => {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        });

        // Easter Egg: Konami Code
        let konamiCode = [];
        const targetCode = [
            'ArrowUp', 'ArrowUp', 'ArrowDown', 'ArrowDown',
            'ArrowLeft', 'ArrowRight', 'ArrowLeft', 'ArrowRight',
            'KeyB', 'KeyA'
        ];

        document.addEventListener('keydown', (e) => {
            konamiCode.push(e.code);
            if (konamiCode.length > targetCode.length) {
                konamiCode.shift();
            }
            
            if (konamiCode.join(',') === targetCode.join(',')) {
                document.body.style.animation = 'glitch 0.5s infinite';
                setTimeout(() => {
                    document.body.style.animation = '';
                    alert('🌙 Secret code activated! Virellune sees you... 👁️');
                }, 3000);
            }
        });
    </script>
</body>
</html>
