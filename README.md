<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>¡Feliz Cumpleaños, Mi Amor! ❤️</title>
    <style>
        /* RESET & BASE STYLES */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Cinzel', 'Georgia', serif;
            background: #030712;
            color: #f1f5f9;
            min-height: 100vh;
            overflow-x: hidden;
            position: relative;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: space-between;
        }

        /* CANVAS BACKGROUND FOR STARS, FIREFLIES, LEAVES, FOG, FLOWERS, BLACK CAT */
        #bg-canvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        /* MOON CONTAINER */
        .moon-container {
            position: fixed;
            top: 40px;
            right: 8%;
            width: 140px;
            height: 140px;
            border-radius: 50%;
            background: radial-gradient(circle at 35% 35%, #fffdf0 0%, #e2e8f0 60%, #cbd5e1 100%);
            box-shadow: 0 0 40px rgba(255, 253, 240, 0.4),
                        0 0 80px rgba(56, 189, 248, 0.25),
                        0 0 120px rgba(168, 85, 247, 0.15);
            z-index: 1;
            animation: moonGlow 6s ease-in-out infinite alternate;
            pointer-events: none;
        }

        /* ENCHANTED SILHOUETTE TREES & FLOWERS AT BOTTOM */
        .forest-silhouette {
            position: fixed;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 160px;
            background: radial-gradient(ellipse at bottom, rgba(15, 23, 42, 0.4) 0%, transparent 80%);
            pointer-events: none;
            z-index: 2;
        }

        /* CONTAINER STRUCTURE */
        .container {
            position: relative;
            z-index: 3;
            width: 100%;
            max-width: 850px;
            padding: 60px 20px 40px 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        /* HERO HEADER */
        header {
            text-align: center;
            margin-bottom: 35px;
            animation: fadeInDown 1.8s ease-out;
        }

        h1 {
            font-size: 2.9rem;
            font-weight: 700;
            background: linear-gradient(135deg, #fef08a 0%, #38bdf8 50%, #e879f9 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 0 35px rgba(56, 189, 248, 0.4);
            margin-bottom: 18px;
            line-height: 1.25;
            letter-spacing: 1px;
        }

        .subtitle-container {
            min-height: 32px;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .typewriter {
            font-size: 1.15rem;
            color: #bae6fd;
            border-right: 2px solid #38bdf8;
            white-space: nowrap;
            overflow: hidden;
            letter-spacing: 1.5px;
            animation: blinkCursor 0.75s step-end infinite;
            font-style: italic;
            font-family: 'Segoe UI', sans-serif;
            text-shadow: 0 0 10px rgba(56, 189, 248, 0.5);
        }

        /* GLASSMORPHISM DARK FANTASY CARD */
        .card {
            background: rgba(11, 19, 43, 0.55);
            backdrop-filter: blur(18px);
            -webkit-backdrop-filter: blur(18px);
            border: 1px solid rgba(212, 175, 55, 0.3);
            border-radius: 24px;
            padding: 45px 40px;
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.7), 
                        0 0 30px rgba(56, 189, 248, 0.1),
                        inset 0 0 25px rgba(212, 175, 55, 0.08);
            margin-bottom: 40px;
            width: 100%;
            animation: fadeInUp 2s ease-out;
            transition: transform 0.4s ease, box-shadow 0.4s ease, border-color 0.4s ease;
            position: relative;
        }

        .card::before {
            content: '✨';
            position: absolute;
            top: 15px;
            left: 20px;
            font-size: 1.2rem;
            opacity: 0.6;
        }

        .card::after {
            content: '✨';
            position: absolute;
            bottom: 15px;
            right: 20px;
            font-size: 1.2rem;
            opacity: 0.6;
        }

        .card:hover {
            transform: translateY(-6px);
            border-color: rgba(212, 175, 55, 0.6);
            box-shadow: 0 25px 65px rgba(0, 0, 0, 0.8), 
                        0 0 45px rgba(56, 189, 248, 0.25),
                        inset 0 0 30px rgba(212, 175, 55, 0.15);
        }

        .card p {
            font-family: 'Segoe UI', 'Georgia', serif;
            font-size: 1.12rem;
            line-height: 1.85;
            color: #e2e8f0;
            margin-bottom: 20px;
            font-weight: 300;
            letter-spacing: 0.4px;
            text-align: justify;
        }

        .card p:last-child {
            margin-bottom: 0;
        }

        /* VIDEO BUTTON SECTION */
        .video-section {
            margin-bottom: 45px;
            text-align: center;
            animation: fadeIn 2.2s ease-out;
        }

        .btn-video {
            display: inline-flex;
            align-items: center;
            gap: 12px;
            padding: 18px 40px;
            font-size: 1.15rem;
            font-weight: 600;
            font-family: 'Segoe UI', sans-serif;
            color: #ffffff;
            background: linear-gradient(135deg, #0284c7 0%, #4c1d95 50%, #7e22ce 100%);
            border: 1px solid rgba(212, 175, 55, 0.5);
            border-radius: 50px;
            text-decoration: none;
            box-shadow: 0 10px 30px rgba(2, 132, 199, 0.4),
                        0 0 20px rgba(212, 175, 55, 0.2);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .btn-video::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.35), transparent);
            transition: left 0.75s;
        }

        .btn-video:hover::before {
            left: 100%;
        }

        .btn-video:hover {
            transform: scale(1.06) translateY(-3px);
            border-color: #fef08a;
            box-shadow: 0 15px 40px rgba(56, 189, 248, 0.6),
                        0 0 30px rgba(254, 240, 138, 0.4);
        }

        /* SPOTIFY CONTAINER */
        .spotify-section {
            width: 100%;
            margin-bottom: 45px;
            display: flex;
            justify-content: center;
            animation: fadeIn 2.4s ease-out;
        }

        .spotify-card {
            width: 100%;
            max-width: 100%;
            border-radius: 22px;
            overflow: hidden;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.7),
                        0 0 25px rgba(76, 29, 149, 0.3);
            background: rgba(15, 23, 42, 0.5);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(212, 175, 55, 0.25);
            padding: 8px;
        }

        .spotify-card iframe {
            border-radius: 14px;
            width: 100%;
            height: 380px;
            border: none;
        }

        /* FOOTER */
        footer {
            position: relative;
            z-index: 3;
            width: 100%;
            padding: 28px 20px;
            text-align: center;
            background: rgba(3, 7, 18, 0.8);
            backdrop-filter: blur(12px);
            border-top: 1px solid rgba(212, 175, 55, 0.15);
        }

        footer p {
            font-size: 1.05rem;
            color: #94a3b8;
            letter-spacing: 0.8px;
            font-weight: 300;
            font-family: 'Segoe UI', sans-serif;
        }

        footer span {
            color: #38bdf8;
            text-shadow: 0 0 10px rgba(56, 189, 248, 0.6);
        }

        /* KEYFRAME ANIMATIONS */
        @keyframes moonGlow {
            0% {
                box-shadow: 0 0 35px rgba(255, 253, 240, 0.35),
                            0 0 70px rgba(56, 189, 248, 0.2);
            }
            100% {
                box-shadow: 0 0 50px rgba(255, 253, 240, 0.55),
                            0 0 100px rgba(168, 85, 247, 0.3);
            }
        }

        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-35px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(45px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes blinkCursor {
            from, to { border-color: transparent; }
            50% { border-color: #38bdf8; }
        }

        /* RESPONSIVE DESIGN */
        @media (max-width: 768px) {
            .moon-container {
                width: 90px;
                height: 90px;
                top: 25px;
                right: 5%;
            }

            h1 {
                font-size: 2.1rem;
            }

            .typewriter {
                font-size: 0.98rem;
            }

            .card {
                padding: 30px 22px;
                border-radius: 20px;
            }

            .card p {
                font-size: 1rem;
                line-height: 1.75;
                text-align: left;
            }

            .btn-video {
                padding: 15px 30px;
                font-size: 1rem;
            }

            .spotify-card iframe {
                height: 350px;
            }
        }

        @media (max-width: 480px) {
            h1 {
                font-size: 1.75rem;
            }

            .typewriter {
                font-size: 0.88rem;
            }

            .card {
                padding: 24px 18px;
            }

            .btn-video {
                width: 100%;
                justify-content: center;
            }
        }
    </style>
</head>
<body>

    <canvas id="bg-canvas"></canvas>
    
    <div class="moon-container"></div>
    <div class="forest-silhouette"></div>

    <div class="container">
        <header>
            <h1>¡Feliz Cumpleaños, Mi Amor! ❤️</h1>
            <div class="subtitle-container">
                <span id="typewriter" class="typewriter"></span>
            </div>
        </header>

        <section class="card">
            <p>Hola, mi amor. ❤️</p>
            <p>Conocerte ha sido la mejor cosa que me ha pasado en la vida. Nunca voy a olvidar la primera vez que te vi. En ese momento pensé para mí mismo: "Algún día quiero estar con ella."</p>
            <p>Con el tiempo, ese día llegó. Nos fuimos acercando poco a poco y, desde entonces, hemos estado juntos compartiendo momentos inolvidables.</p>
            <p>Hoy, en tu cumpleaños, quiero que sepas lo especial que eres para mí. Gracias por tu cariño, por tu compañía y por hacer mi vida mucho más feliz.</p>
            <p>Espero que este nuevo año de vida esté lleno de alegría, salud, sueños cumplidos y mucho amor.</p>
            <p>Siempre estaré a tu lado para apoyarte, cuidarte y seguir construyendo nuestra historia juntos.</p>
            <p>Espero que te guste este pequeño detalle. Lo hice con todo mi cariño para ti.</p>
            <p>También espero que te guste este pequeño ramo de girasoles. 🌻 Sé cuánto te gustan y quise regalártelos como un símbolo de la alegría y la luz que traes a mi vida.</p>
            <p>Y, por cierto... ¿Recuerdas que me dijiste que en tu próximo cumpleaños saldrías conmigo? Bueno... ese día por fin llegó. ❤️ Espero que podamos crear muchos recuerdos bonitos juntos y seguir escribiendo nuestra historia.</p>
        </section>

        <section class="video-section">
            <a href="https://www.instagram.com/reel/DbOpWbKi3Ri/?igsh=MXhlOG81eGs0aWlyMw==" target="_blank" rel="noopener noreferrer" class="btn-video">
                🎥 Mira este video ❤️
            </a>
        </section>

        <section class="spotify-section">
            <div class="spotify-card">
                <iframe src="https://open.spotify.com/embed/playlist/2u7hAgL7NegOZq3F2k0Ehm?utm_source=generator&theme=0" allowfullscreen="" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture" loading="lazy"></iframe>
            </div>
        </section>
    </div>

    <footer>
        <p>Bajo las estrellas y por toda la eternidad... <span>✨ ❤️</span></p>
    </footer>

    <script>
        // TYPEWRITER EFFECT
        const textToType = "En una noche mágica, un regalo directo desde el corazón... ✨";
        const typewriterElement = document.getElementById("typewriter");
        let charIndex = 0;

        function typeEffect() {
            if (charIndex < textToType.length) {
                typewriterElement.textContent += textToType.charAt(charIndex);
                charIndex++;
                setTimeout(typeEffect, 65);
            }
        }

        window.addEventListener("DOMContentLoaded", () => {
            setTimeout(typeEffect, 900);
        });

        // CANVAS ANIMATIONS: STARS, FIREFLIES, LEAVES, FOG, FLOWERS, BLACK CAT
        const canvas = document.getElementById("bg-canvas");
        const ctx = canvas.getContext("2d");

        let width, height;

        function resizeCanvas() {
            width = canvas.width = window.innerWidth;
            height = canvas.height = window.innerHeight;
        }

        window.addEventListener("resize", resizeCanvas);
        resizeCanvas();

        // STAR CLASS
        class Star {
            constructor() { this.reset(); }
            reset() {
                this.x = Math.random() * width;
                this.y = Math.random() * height * 0.8;
                this.size = Math.random() * 1.6 + 0.4;
                this.alpha = Math.random();
                this.speed = Math.random() * 0.012 + 0.004;
                this.increasing = Math.random() > 0.5;
            }
            update() {
                if (this.increasing) {
                    this.alpha += this.speed;
                    if (this.alpha >= 1) this.increasing = false;
                } else {
                    this.alpha -= this.speed;
                    if (this.alpha <= 0.15) this.increasing = true;
                }
            }
            draw() {
                ctx.save();
                ctx.globalAlpha = this.alpha;
                ctx.fillStyle = "#ffffff";
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
                ctx.fill();
                ctx.restore();
            }
        }

        // FIREFLY CLASS (GLOWING MAGICAL PARTICLES)
        class Firefly {
            constructor() { this.reset(); }
            reset() {
                this.x = Math.random() * width;
                this.y = Math.random() * height;
                this.size = Math.random() * 2.5 + 1.2;
                this.alpha = Math.random() * 0.5 + 0.2;
                this.vx = (Math.random() - 0.5) * 0.6;
                this.vy = (Math.random() - 0.5) * 0.6;
                this.pulseSpeed = Math.random() * 0.02 + 0.01;
                this.color = Math.random() > 0.4 ? "#38bdf8" : "#fef08a";
            }
            update() {
                this.x += this.vx;
                this.y += this.vy;
                this.alpha += Math.sin(Date.now() * 0.003) * 0.01;
                
                if (this.x < 0 || this.x > width || this.y < 0 || this.y > height) {
                    this.reset();
                }
            }
            draw() {
                ctx.save();
                ctx.globalAlpha = Math.max(0.1, Math.min(1, this.alpha));
                ctx.fillStyle = this.color;
                ctx.shadowBlur = 12;
                ctx.shadowColor = this.color;
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
                ctx.fill();
                ctx.restore();
            }
        }

        // FLOATING LEAF CLASS
        class FloatingLeaf {
            constructor() { this.reset(true); }
            reset(initial = false) {
                this.x = Math.random() * width;
                this.y = initial ? Math.random() * height : -20;
                this.size = Math.random() * 8 + 8;
                this.speedY = Math.random() * 0.6 + 0.3;
                this.speedX = Math.random() * 0.4 - 0.2;
                this.rotation = Math.random() * Math.PI * 2;
                this.rotSpeed = (Math.random() - 0.5) * 0.03;
                this.oscillation = Math.random() * Math.PI * 2;
                this.alpha = Math.random() * 0.5 + 0.3;
            }
            update() {
                this.y += this.speedY;
                this.oscillation += 0.02;
                this.x += this.speedX + Math.sin(this.oscillation) * 0.6;
                this.rotation += this.rotSpeed;
                if (this.y > height + 30) this.reset(false);
            }
            draw() {
                ctx.save();
                ctx.translate(this.x, this.y);
                ctx.rotate(this.rotation);
                ctx.globalAlpha = this.alpha;
                ctx.fillStyle = "#0f766e";
                ctx.beginPath();
                ctx.ellipse(0, 0, this.size * 0.4, this.size, 0, 0, Math.PI * 2);
                ctx.fill();
                ctx.restore();
            }
        }

        // FOG / MIST CLASS
        class FogParticle {
            constructor() { this.reset(); }
            reset() {
                this.x = Math.random() * width;
                this.y = Math.random() * height * 0.5 + height * 0.5;
                this.radius = Math.random() * 180 + 120;
                this.alpha = Math.random() * 0.08 + 0.02;
                this.vx = Math.random() * 0.2 + 0.05;
            }
            update() {
                this.x += this.vx;
                if (this.x - this.radius > width) this.x = -this.radius;
            }
            draw() {
                ctx.save();
                ctx.globalAlpha = this.alpha;
                const grad = ctx.createRadialGradient(this.x, this.y, 10, this.x, this.y, this.radius);
                grad.addColorStop(0, "rgba(56, 189, 248, 0.2)");
                grad.addColorStop(1, "rgba(3, 7, 18, 0)");
                ctx.fillStyle = grad;
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.radius, 0, Math.PI * 2);
                ctx.fill();
                ctx.restore();
            }
        }

        // SWAYING FLOWERS AT BOTTOM
        class SwayingFlower {
            constructor(x) {
                this.x = x;
                this.height = Math.random() * 30 + 35;
                this.angle = 0;
                this.speed = Math.random() * 0.02 + 0.01;
                this.color = Math.random() > 0.5 ? "#e879f9" : "#38bdf8";
            }
            update() {
                this.angle += this.speed;
            }
            draw() {
                const sway = Math.sin(this.angle) * 8;
                const baseY = height;
                const topY = height - this.height;

                ctx.save();
                ctx.strokeStyle = "#1e293b";
                ctx.lineWidth = 2.5;
                ctx.beginPath();
                ctx.moveTo(this.x, baseY);
                ctx.quadraticCurveTo(this.x + sway * 0.5, baseY - this.height * 0.5, this.x + sway, topY);
                ctx.stroke();

                // Petals
                ctx.fillStyle = this.color;
                ctx.shadowBlur = 8;
                ctx.shadowColor = this.color;
                ctx.beginPath();
                ctx.arc(this.x + sway, topY, 4.5, 0, Math.PI * 2);
                ctx.fill();
                ctx.restore();
            }
        }

        // BLACK CAT WALKING AT BOTTOM
        class BlackCat {
            constructor() {
                this.x = -60;
                this.speed = 0.6;
                this.step = 0;
            }
            update() {
                this.x += this.speed;
                this.step += 0.08;
                if (this.x > width + 80) {
                    this.x = -120;
                }
            }
            draw() {
                const y = height - 12;
                const legOffset = Math.sin(this.step) * 4;

                ctx.save();
                ctx.fillStyle = "#020617";
                ctx.shadowBlur = 4;
                ctx.shadowColor = "rgba(0,0,0,0.8)";

                // Body
                ctx.beginPath();
                ctx.ellipse(this.x, y - 10, 16, 9, 0, 0, Math.PI * 2);
                ctx.fill();

                // Head
                ctx.beginPath();
                ctx.arc(this.x + 14, y - 17, 7, 0, Math.PI * 2);
                ctx.fill();

                // Ears
                ctx.beginPath();
                ctx.moveTo(this.x + 12, y - 22);
                ctx.lineTo(this.x + 15, y - 27);
                ctx.lineTo(this.x + 18, y - 22);
                ctx.fill();

                // Glowing Eyes
                ctx.fillStyle = "#fef08a";
                ctx.shadowBlur = 6;
                ctx.shadowColor = "#fef08a";
                ctx.beginPath();
                ctx.arc(this.x + 17, y - 18, 1.2, 0, Math.PI * 2);
                ctx.fill();

                // Legs
                ctx.fillStyle = "#020617";
                ctx.shadowBlur = 0;
                ctx.fillRect(this.x - 8 + legOffset, y - 3, 2.5, 10);
                ctx.fillRect(this.x - 2 - legOffset, y - 3, 2.5, 10);
                ctx.fillRect(this.x + 6 + legOffset, y - 3, 2.5, 10);
                ctx.fillRect(this.x + 12 - legOffset, y - 3, 2.5, 10);

                // Tail
                ctx.strokeStyle = "#020617";
                ctx.lineWidth = 2.5;
                ctx.beginPath();
                ctx.moveTo(this.x - 15, y - 12);
                ctx.quadraticCurveTo(this.x - 25, y - 20 + Math.sin(this.step) * 3, this.x - 20, y - 28);
                ctx.stroke();

                ctx.restore();
            }
        }

        // INITIALIZE ANIMATION OBJECTS
        const stars = Array.from({ length: 110 }, () => new Star());
        const fireflies = Array.from({ length: 35 }, () => new Firefly());
        const leaves = Array.from({ length: 20 }, () => new FloatingLeaf());
        const fogs = Array.from({ length: 8 }, () => new FogParticle());
        const cat = new BlackCat();

        const flowerCount = Math.floor(window.innerWidth / 35);
        const flowers = [];
        for (let i = 0; i < flowerCount; i++) {
            flowers.push(new SwayingFlower(i * 35 + Math.random() * 15));
        }

        // MAIN ANIMATION LOOP
        function animate() {
            ctx.clearRect(0, 0, width, height);

            // 1. Stars
            stars.forEach(s => { s.update(); s.draw(); });

            // 2. Fog
            fogs.forEach(f => { f.update(); f.draw(); });

            // 3. Swaying Flowers
            flowers.forEach(fl => { fl.update(); fl.draw(); });

            // 4. Black Cat
            cat.update();
            cat.draw();

            // 5. Floating Leaves
            leaves.forEach(l => { l.update(); l.draw(); });

            // 6. Fireflies (Magical Particles)
            fireflies.forEach(ff => { ff.update(); ff.draw(); });

            requestAnimationFrame(animate);
        }

        animate();
    </script>
</body>
</html>
