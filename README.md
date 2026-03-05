<h1 align="center">🚧 Página de Manutenção Premium</h1>

<p align="center">
  <strong>Nome do Repositório:</strong> <code>pagina-de-manutencao</code><br>
  <strong>Descrição para o GitHub:</strong> Template premium e responsivo para página de "Em Construção". Conta com efeito Glassmorphism, fundo interativo de partículas, SVG animado e contagem regressiva em Vanilla JS.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5">
  <img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS3">
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="JavaScript">
</p>

---

## 📸 Preview

[![Preview do Projeto](https://prnt.sc/tJOQ3EShUvPL)](https://prnt.sc/tJOQ3EShUvPL)
*Clique na imagem para ampliar caso não carregue automaticamente.*

---

## ✨ Funcionalidades

Este não é só mais um aviso de "Voltamos logo". A página foi desenhada para reter a atenção e passar credibilidade:

- **🌌 Fundo de Partículas Interativas:** Efeito em Vanilla JS simulando uma rede de conexões.
- **🧊 Glassmorphism:** Painel principal com efeito de vidro fosco (tendência de design).
- **⏱️ Contagem Regressiva:** Timer dinâmico e animado.
- **🎨 Animações SVG:** Um dev trabalhando, engrenagens girando e código subindo, tudo super leve.
- **⌨️ Typing Effect:** O título simula alguém digitando em tempo real.
- **📱 100% Responsivo:** Fica perfeito no celular, tablet ou PC.
- **🚀 Zero Dependências:** Não usa bibliotecas externas pesadas. Tudo em um único arquivo!

---

## 💻 O Código Completo (index.html)

Copie o código abaixo, salve como `index.html` e suba para a sua hospedagem:

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Quase lá...</title>
    <link href="[https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&display=swap](https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&display=swap)" rel="stylesheet">
    <style>
        :root {
            --primary: #00ff88;
            --secondary: #00b8ff;
            --bg-dark: #0a0a0a;
            --glass-bg: rgba(20, 20, 20, 0.7);
            --glass-border: rgba(255, 255, 255, 0.1);
            --text-light: #ffffff;
            --text-muted: #a0a0a0;
        }

        * { box-sizing: border-box; margin: 0; padding: 0; }

        body {
            font-family: 'Poppins', sans-serif;
            background-color: var(--bg-dark);
            color: var(--text-light);
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
        }

        #particles-canvas {
            position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: 0;
        }

        .glass-card {
            position: relative; z-index: 10;
            background: var(--glass-bg);
            backdrop-filter: blur(15px); -webkit-backdrop-filter: blur(15px);
            border: 1px solid var(--glass-border); border-radius: 20px;
            padding: 40px; max-width: 600px; width: 90%; text-align: center;
            box-shadow: 0 25px 50px rgba(0,0,0,0.5);
        }

        .typing-container { display: inline-block; margin-bottom: 15px; }
        .typing-text {
            font-size: 2rem; font-weight: 700;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            -webkit-background-clip: text; -webkit-text-fill-color: transparent;
            overflow: hidden; white-space: nowrap; border-right: 3px solid var(--primary);
            width: 0; animation: typing 3s steps(30, end) forwards, blink-caret .75s step-end infinite;
        }

        @keyframes typing { from { width: 0 } to { width: 100% } }
        @keyframes blink-caret { from, to { border-color: transparent } 50% { border-color: var(--primary); } }

        p.message { font-size: 1.1rem; color: var(--text-muted); line-height: 1.6; margin-bottom: 30px; }
        .author-name { color: var(--text-light); font-weight: 700; font-size: 1.2rem; }

        .countdown { display: flex; justify-content: center; gap: 15px; margin-bottom: 30px; }
        .time-box {
            background: rgba(0, 0, 0, 0.5); border: 1px solid var(--glass-border);
            border-radius: 10px; padding: 15px; min-width: 80px;
        }
        .time-box span { display: block; font-size: 2rem; font-weight: 700; color: var(--primary); }
        .time-box small { font-size: 0.75rem; text-transform: uppercase; letter-spacing: 1px; color: var(--text-muted); }

        .loader-container {
            width: 100%; background: rgba(255,255,255,0.1); border-radius: 10px;
            height: 8px; overflow: hidden; position: relative;
        }
        .loader-bar {
            height: 100%; width: 0%;
            background: linear-gradient(90deg, var(--secondary), var(--primary));
            border-radius: 10px; animation: loadProgress 2s ease-in-out forwards;
            box-shadow: 0 0 10px var(--primary);
        }
        @keyframes loadProgress { from { width: 0%; } to { width: 85%; } }

        .illustration { width: 180px; margin-bottom: 20px; }
        .gear-spin { animation: spin 4s linear infinite; transform-origin: center; }
        .arm-type { animation: typeFast 0.2s infinite alternate; }
        .code-float { animation: codeUp 2s linear infinite; }

        @keyframes spin { 100% { transform: rotate(360deg); } }
        @keyframes typeFast { 0% { transform: translateY(0); } 100% { transform: translateY(3px); } }
        @keyframes codeUp { 0% { transform: translateY(10px); opacity: 0; } 50% { opacity: 1; } 100% { transform: translateY(-15px); opacity: 0; } }

        @media (max-width: 500px) {
            .countdown { gap: 8px; }
            .time-box { min-width: 60px; padding: 10px; }
            .time-box span { font-size: 1.5rem; }
            .typing-text { font-size: 1.5rem; }
        }
    </style>
</head>
<body>
    <canvas id="particles-canvas"></canvas>
    <div class="glass-card">
        <svg class="illustration" viewBox="0 0 200 200" xmlns="[http://www.w3.org/2000/svg](http://www.w3.org/2000/svg)">
            <g class="gear-spin" style="transform-origin: 100px 100px;">
                <path d="M140,95 l5,-5 a1,1 0 0,1 1.4,0 l10,10 a1,1 0 0,1 0,1.4 l-5,5 a1,1 0 0,1 -1.4,0 l-10,-10 a1,1 0 0,1 0,-1.4 M135,90 a20,20 0 1,0 24,24" stroke="#00ff88" fill="none" stroke-width="2" opacity="0.3"/>
            </g>
            <rect x="20" y="160" width="160" height="5" rx="2" fill="#333"/>
            <rect x="50" y="90" width="100" height="70" rx="5" fill="#111" stroke="#444" stroke-width="3"/>
            <rect x="55" y="95" width="90" height="55" rx="2" fill="#051525"/>
            <rect x="90" y="160" width="20" height="15" fill="#444"/>
            <g class="code-float">
                <line x1="65" y1="110" x2="100" y2="110" stroke="#00ff88" stroke-width="2" stroke-linecap="round"/>
                <line x1="65" y1="120" x2="130" y2="120" stroke="#00b8ff" stroke-width="2" stroke-linecap="round"/>
                <line x1="65" y1="130" x2="90" y2="130" stroke="#ff0055" stroke-width="2" stroke-linecap="round"/>
            </g>
            <circle cx="100" cy="70" r="25" fill="#1e293b"/>
            <rect x="70" y="100" width="60" height="60" rx="20" fill="#1e293b"/>
            <path d="M 75 70 A 25 25 0 0 1 125 70" fill="none" stroke="#fff" stroke-width="3"/>
            <rect x="70" y="65" width="10" height="15" rx="5" fill="#00ff88"/>
            <rect x="120" y="65" width="10" height="15" rx="5" fill="#00ff88"/>
            <g class="arm-type">
                <rect x="40" y="145" width="30" height="8" rx="4" fill="#334155" transform="rotate(20 40 145)"/>
                <rect x="130" y="145" width="30" height="8" rx="4" fill="#334155" transform="rotate(-20 130 145)"/>
            </g>
        </svg>

        <div class="typing-container">
            <div class="typing-text">Sistema em Obras...</div>
        </div>
        <p class="message">
            Olha, meu programador está trabalhando a todo vapor e <strong>quase terminando</strong> tudo por aqui!<br><br>
            Prepare-se para algo incrível. <br>
            <span class="author-name">— Felipe de Godoi</span>
        </p>

        <div class="countdown">
            <div class="time-box"><span id="days">00</span><small>Dias</small></div>
            <div class="time-box"><span id="hours">00</span><small>Horas</small></div>
            <div class="time-box"><span id="minutes">00</span><small>Minutos</small></div>
            <div class="time-box"><span id="seconds">00</span><small>Segundos</small></div>
        </div>

        <div class="loader-container"><div class="loader-bar"></div></div>
        <small style="color: var(--primary); display: block; margin-top: 10px; font-weight: bold;">Progresso: 85%</small>
    </div>

    <script>
        const targetDate = new Date();
        targetDate.setDate(targetDate.getDate() + 7); 
        const countDownDate = targetDate.getTime();

        const x = setInterval(function() {
            const now = new Date().getTime();
            const distance = countDownDate - now;

            const days = Math.floor(distance / (1000 * 60 * 60 * 24));
            const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((distance % (1000 * 60)) / 1000);

            document.getElementById("days").innerText = days < 10 ? "0" + days : days;
            document.getElementById("hours").innerText = hours < 10 ? "0" + hours : hours;
            document.getElementById("minutes").innerText = minutes < 10 ? "0" + minutes : minutes;
            document.getElementById("seconds").innerText = seconds < 10 ? "0" + seconds : seconds;

            if (distance < 0) {
                clearInterval(x);
                document.getElementById("days").innerText = "00";
                document.getElementById("hours").innerText = "00";
                document.getElementById("minutes").innerText = "00";
                document.getElementById("seconds").innerText = "00";
            }
        }, 1000);

        const canvas = document.getElementById('particles-canvas');
        const ctx = canvas.getContext('2d');
        let particlesArray;

        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;

        class Particle {
            constructor(x, y, directionX, directionY, size, color) {
                this.x = x; this.y = y; this.directionX = directionX; this.directionY = directionY;
                this.size = size; this.color = color;
            }
            draw() {
                ctx.beginPath(); ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2, false);
                ctx.fillStyle = '#00ff88'; ctx.fill();
            }
            update() {
                if (this.x > canvas.width || this.x < 0) this.directionX = -this.directionX;
                if (this.y > canvas.height || this.y < 0) this.directionY = -this.directionY;
                this.x += this.directionX; this.y += this.directionY;
                this.draw();
            }
        }

        function initParticles() {
            particlesArray = [];
            let numberOfParticles = (canvas.height * canvas.width) / 9000;
            for (let i = 0; i < numberOfParticles; i++) {
                let size = (Math.random() * 2) + 1;
                let x = (Math.random() * ((innerWidth - size * 2) - (size * 2)) + size * 2);
                let y = (Math.random() * ((innerHeight - size * 2) - (size * 2)) + size * 2);
                let directionX = (Math.random() * 1) - 0.5;
                let directionY = (Math.random() * 1) - 0.5;
                particlesArray.push(new Particle(x, y, directionX, directionY, size, '#00ff88'));
            }
        }

        function animateParticles() {
            requestAnimationFrame(animateParticles);
            ctx.clearRect(0, 0, innerWidth, innerHeight);
            for (let i = 0; i < particlesArray.length; i++) { particlesArray[i].update(); }
        }

        window.addEventListener('resize', function() { canvas.width = innerWidth; canvas.height = innerHeight; initParticles(); });
        initParticles(); animateParticles();
    </script>
</body>
</html>

🛠️ Como personalizar
Você pode deixar a página com a sua cara alterando algumas linhas simples no código:

1. Alterar as Cores (Tema Neon)
O esquema de cores está configurado no topo do CSS, nas variáveis :root. Troque o Verde e Azul por outras cores se preferir:

CSS
:root {
    --primary: #00ff88; /* Mude o HEX aqui */
    --secondary: #00b8ff; /* Mude o HEX aqui */
}
2. Configurar a Data Final da Contagem Regressiva
Se você quiser uma data fixa para o lançamento (exemplo: final do ano), mude a lógica do script JavaScript:

De:

JavaScript
const targetDate = new Date();
targetDate.setDate(targetDate.getDate() + 7); 
const countDownDate = targetDate.getTime();
Para:

JavaScript
// Coloque o Mês (em inglês), Dia, Ano e a Hora
const countDownDate = new Date("Dec 31, 2026 23:59:59").getTime();
👨‍💻 Autor
Criado e idealizado por Felipe de Godoi (e seu dev trabalhando a todo vapor!).

Conecte-se comigo:

https://www.instagram.com/degodoi.felipe

https://www.linkedin.com/in/degodoi/
