
<style>
    @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400..900&display=swap');

    /* Custom Orbitron Style */
    .orbitron-style {
    font-family: "Orbitron", serif;
    font-optical-sizing: auto;
    font-weight: 700;
    font-style: normal;
    color: #745cec;
    }

    body {
        margin: 0;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        background-color: #0d1117;
        color: #c299e1;
        font-family: 'Orbitron', sans-serif;
        overflow: hidden;
    }
    canvas {
        display: block;
    }
    .control {
        position: absolute;
        bottom: 20px;
        text-align: center;
    }
    button {
        background-color: #745cec;
        border: none;
        color: white;
        padding: 10px 20px;
        font-size: 1rem;
        cursor: pointer;
        border-radius: 5px;
    }
    button:hover {
        background-color: #6e50a8;
    }
</style>
<script>
    const canvas = document.getElementById('visualizer');
    const ctx = canvas.getContext('2d');
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;

    const audioContext = new (window.AudioContext || window.webkitAudioContext)();
    const analyser = audioContext.createAnalyser();
    analyser.fftSize = 256;

    const bufferLength = analyser.frequencyBinCount;
    const dataArray = new Uint8Array(bufferLength);

    function draw() {
        requestAnimationFrame(draw);

        analyser.getByteFrequencyData(dataArray);

        ctx.clearRect(0, 0, canvas.width, canvas.height);

        const barWidth = (canvas.width / bufferLength) * 2.5;
        let barHeight;
        let x = 0;

        for (let i = 0; i < bufferLength; i++) {
            barHeight = dataArray[i] / 2;

            const r = barHeight + 50;
            const g = 50;
            const b = 200;

            ctx.fillStyle = `rgb(${r},${g},${b})`;
            ctx.fillRect(x, canvas.height - barHeight, barWidth, barHeight);

            x += barWidth + 1;
        }
    }

    async function startNarration() {
    const synth = window.speechSynthesis;
    const utterance = new SpeechSynthesisUtterance(`Olá, humano! Sou a representação digital do Germano, uma entidade que une paixão por tecnologia e curiosidade infinita pelo universo do desenvolvimento. Minha programação principal inclui linguagens como Java, JavaScript, Python, HTML e CSS. Também adoro explorar ferramentas como Angular, MySQL, Power BI e Machine Learning. Quando não estou em modo de aprendizado contínuo, curto animes, partidas estratégicas de League of Legends e teorias científicas. Vamos evoluir juntos para um futuro mais tecnológico e conectado.`);
    utterance.lang = 'pt-BR';

    const stream = await navigator.mediaDevices.getUserMedia({ audio: true });
    const source = audioContext.createMediaStreamSource(stream);
    source.connect(analyser);

    synth.speak(utterance);
    draw();
    }

    document.getElementById('startButton').addEventListener('click', () => {
    startNarration();
    });

    window.addEventListener('resize', () => {
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
    });
</script>
---
<body>
    <div align="center">
        <h1 class="orbitron-style">Germano Silva</h1>
        <p class="orbitron-style" style="color:#c299e1; font-size: 1.2rem;">
            "I believe that sometimes it's the people no one expects anything, that do the things no one can imagine."
        </p>
    </div>
    <canvas id="visualizer"></canvas>
    <div class="control">
        <button id="startButton">🎙️ Start Narration</button>
    </div>
</body>
---

<div style="color: #c299e1; font-size: 1rem;">
  Olá, humano! Sou a representação digital do Germano, uma entidade que une paixão por tecnologia e curiosidade infinita pelo universo do desenvolvimento. Minha programação principal inclui:

  - **Linguagens Principais:** Java, JavaScript, Python, HTML & CSS.
  - **Frameworks e Ferramentas:** Angular, MySQL, Power BI, Excel e Machine Learning.
  - **Data Science:** Adoro processar e analisar grandes volumes de dados para encontrar padrões significativos.

  Quando não estou em modo de aprendizado contínuo, eu "desligo" para curtir animes, jogar partidas estratégicas de League of Legends e explorar teorias científicas. Minha missão? Evoluir sempre e colaborar para um futuro mais tecnológico e conectado.
</div>

---

## 📊 GitHub Stats
<div align="center">
  <table>
    <tr>
      <td>
        <img src="https://github-readme-stats.vercel.app/api?username=Germano-Silva&show_icons=true&theme=tokyonight" alt="Germano's GitHub stats">
      </td>
      <td>
        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Germano-Silva&layout=compact&theme=tokyonight" alt="Top Languages">
      </td>
    </tr>
  </table>
</div>

---

## Atividade Recente
<div align="center">
  <img src="https://github-readme-activity-graph.cyclic.app/graph?username=germano&theme=tokyo-night&bg_color=transparent&color=745cec&line=6e50a8" alt="Activity Graph">
</div>

---

## 🛠️ Linguagens e Ferramentas
<div align="center">
  <img src="https://skillicons.dev/icons?i=java,html,css,js,angular,python,mysql,powerbi" alt="My Skills">
</div>

---

## 🌐 Redes Sociais e Currículo
<div align="center">
  <a href="https://www.linkedin.com/in/germano" target="_blank">
    <img src="https://img.shields.io/badge/LinkedIn-745cec?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn">
  </a>
  <a href="https://germano-resume.com" target="_blank">
    <img src="https://img.shields.io/badge/Curr%C3%ADculo-6e50a8?style=for-the-badge&logo=readme&logoColor=white" alt="Currículo">
  </a>
</div>

---
