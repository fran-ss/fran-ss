<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<title>Franciane | Portfólio</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Arial, sans-serif;
}
a {
  text-decoration: none;
}
body {
  background: #0a0a0f;
  color: white;
  text-align: center;
  overflow-x: hidden;
}

/* CANVAS */
canvas {
  position: fixed;
  top: 0;
  left: 0;
  z-index: -1;
}

/* HEADER */
header {
  padding: 40px 20px;
  animation: fadeDown 1s ease;
}

@keyframes fadeDown {
  from { opacity: 0; transform: translateY(-30px); }
  to { opacity: 1; transform: translateY(0); }
}

img {
  border-radius: 20px;
  transition: 0.4s;
}

img:hover {
  transform: scale(1.05);
  box-shadow: 0 0 20px #8A2BE2;
}

h1 {
  color: #8A2BE2;
  font-size: 2.5em;
  margin-top: 10px;
}

.subtitle {
  color: #ccc;
  margin-top: 10px;
}

.container {
  max-width: 900px;
  margin: auto;
  padding: 20px;
}

/* CARDS */
.card {
  background: rgba(255,255,255,0.05);
  border-radius: 15px;
  padding: 20px;
  margin: 20px 0;
  backdrop-filter: blur(10px);
  transition: 0.4s;
  animation: fadeUp 1s ease;
  text-align: left; /* Melhor legibilidade para listas */
}

.card h2 {
  color: #8A2BE2;
  margin-bottom: 15px;
  text-align: center;
}

.card:hover {
  transform: translateY(-5px) scale(1.01);
  box-shadow: 0 0 20px #8A2BE2;
}

@keyframes fadeUp {
  from { opacity: 0; transform: translateY(40px); }
  to { opacity: 1; transform: translateY(0); }
}

/* ESTILO PARA OS CURSOS */
.course-item {
  border-left: 3px solid #8A2BE2;
  padding-left: 15px;
  margin-bottom: 20px;
}

.course-item h3 {
  font-size: 1.1em;
  color: #fff;
}

.course-item span {
  font-size: 0.85em;
  color: #8A2BE2;
  display: block;
  margin-bottom: 5px;
}

.course-item p {
  font-size: 0.9em;
  color: #ccc;
}

/* BOTÕES */
.btn {
  display: block;
  padding: 15px;
  margin: 10px 0;
  background: linear-gradient(45deg, #8A2BE2, #6a1cb0);
  border-radius: 10px;
  font-weight: bold;
  text-align: center;
  color: #1a0033;
  transition: 0.3s;
}

.btn:hover {
  transform: scale(1.05);
  box-shadow: 0 0 15px #8A2BE2;
}

footer {
  padding: 30px 0;
  color: #aaa;
}
</style>
</head>

<body>

<canvas id="matrix"></canvas>

<header>
<img src="https://raw.githubusercontent.com/fran-ss/fran-ss.github.io/main/WhatsApp%20Image%202026-04-28%20at%2021.35.59.jpeg" width="250"/>
<h1>💜 Franciane</h1>
<p class="subtitle">Backend • Data • Embedded Systems</p>
</header>

<div class="container">

<div class="card">
<h2>👩‍💻 Sobre mim</h2>
<p style="text-align: center;">
Desenvolvedora formada em Sistemas para Internet pelo IFMA e residente em Sistemas Embarcados.
Atuo com backend, dados e hardware criando soluções reais.
</p>
</div>

<div class="card">
<h2>🎓 Residências Tecnológicas (EmbarcaTech)</h2>

<div class="course-item">
  <span>IFMA / SOFTEX • 240h • 2025</span>
  <h3>Residência em FPGA</h3>
  <p>Foco em descrição de hardware (Verilog/VHDL), arquitetura de plataformas adaptativas e circuitos digitais complexos.</p>
</div>

<div class="course-item">
  <span>IFMA / SOFTEX • 240h • 2025</span>
  <h3>Residência em Software Embarcado</h3>
  <p>Desenvolvimento para microcontroladores, RTOS (Sistemas Operacionais de Tempo Real) e projetos aplicados de IoT.</p>
</div>
</div>

<div class="card">
<h2>🚀 Projetos em Destaque</h2>
<p style="margin-bottom: 15px;"><strong>GASMAR:</strong> Plataforma digital com análise de consumo e gestão de usuários (BFF, JWT, Dashboards).</p>
<a class="btn" href="https://drive.google.com" target="_blank">▶️ Ver detalhes do projeto</a>
</div>

<div class="card">
<h2>💻 Tecnologias</h2>
<p style="text-align: center; line-height: 1.6;">
<strong>Linguagens:</strong> C • C++ • Python • C# • Java • Verilog • VHDL<br>
<strong>Frameworks/DB:</strong> .NET • Django • Node • PostgreSQL • BigQuery<br>
<strong>Hardware/Cloud:</strong> FPGA • RTOS • Raspberry Pi • Docker • GCP
</p>
</div>

<div class="card">
<h2>🔗 Links</h2>
<a class="btn" href="https://github.com/fran-ss" target="_blank">🚀 GitHub</a>
<a class="btn" href="https://www.linkedin.com/in/franciane-santos-da-hora-757939289" target="_blank">💼 LinkedIn</a>
<a class="btn" href="mailto:francianesachos@gmail.com">📩 Email</a>
<a class="btn" href="https://www.instagram.com/franciane_ss" target="_blank">📸 Instagram</a>
</div>

</div>

<footer>
✨ Construindo soluções com código, dados e hardware
</footer>

<script>
const canvas = document.getElementById("matrix");
const ctx = canvas.getContext("2d");

canvas.height = window.innerHeight;
canvas.width = window.innerWidth;

const letters = "01{}<>/\\[]+=-";
const fontSize = 14;
const columns = canvas.width / fontSize;

const drops = [];

for (let x = 0; x < columns; x++) {
  drops[x] = 1;
}

function draw() {
  ctx.fillStyle = "rgba(10,10,15,0.05)";
  ctx.fillRect(0, 0, canvas.width, canvas.height);

  ctx.fillStyle = "#8A2BE2";
  ctx.font = fontSize + "px monospace";

  for (let i = 0; i < drops.length; i++) {
    const text = letters[Math.floor(Math.random() * letters.length)];
    ctx.fillText(text, i * fontSize, drops[i] * fontSize);

    if (drops[i] * fontSize > canvas.height && Math.random() > 0.975) {
      drops[i] = 0;
    }
    drops[i]++;
  }
}

setInterval(draw, 33);

window.addEventListener('resize', () => {
  canvas.width = window.innerWidth;
  canvas.height = window.innerHeight;
});
</script>

</body>
</html>
