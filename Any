
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#020502">
<meta name="description" content="00:00 ANY — The signal is approaching.">
<title>00:00 ANY</title>

<style>
:root {
  --green: #00ff41;
  --dark-green: #008f11;
  --black: #020502;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background: var(--black);
  color: white;
  font-family: Consolas, "Courier New", monospace;
  min-height: 100vh;
  overflow: hidden;
}

#matrix {
  position: fixed;
  inset: 0;
  width: 100%;
  height: 100%;
  opacity: .65;
  z-index: 0;
}

body::after {
  content: "";
  position: fixed;
  inset: 0;
  z-index: 1;
  pointer-events: none;
  background: repeating-linear-gradient(
    transparent 0px,
    rgba(0, 0, 0, .12) 1px,
    transparent 2px,
    transparent 4px
  );
}

.screen {
  position: relative;
  z-index: 2;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 28px;
}

.top, .bottom {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 12px;
  color: var(--green);
  font-size: 11px;
  letter-spacing: 2px;
}

.status {
  display: flex;
  align-items: center;
  gap: 8px;
}

.dot {
  width: 7px;
  height: 7px;
  background: var(--green);
  border-radius: 50%;
  box-shadow: 0 0 12px var(--green);
  animation: blink 1.5s infinite;
}

main {
  width: 100%;
  max-width: 760px;
  margin: auto;
  text-align: center;
  padding: 60px 0;
}

.eyebrow {
  color: var(--dark-green);
  font-size: 11px;
  letter-spacing: 5px;
  margin-bottom: 20px;
}

h1 {
  font-size: clamp(48px, 11vw, 100px);
  letter-spacing: 5px;
  font-weight: 900;
  color: white;
  text-shadow: 0 0 24px rgba(0,255,65,.22);
  animation: flicker 7s infinite;
}

h1 span {
  color: var(--green);
}

.subtitle {
  color: #7a9c80;
  font-size: 11px;
  letter-spacing: 4px;
  margin-top: 16px;
}

.line {
  height: 1px;
  width: 100%;
  margin: 42px 0 28px;
  background: linear-gradient(
    90deg, transparent, var(--dark-green), transparent
  );
}

.countdown {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 12px;
}

.unit {
  border: 1px solid rgba(0,255,65,.18);
  background: rgba(0,10,2,.72);
  padding: 22px 4px;
}

.number {
  display: block;
  font-size: clamp(27px, 6vw, 48px);
  color: white;
  font-weight: bold;
  font-variant-numeric: tabular-nums;
}

.label {
  display: block;
  margin-top: 10px;
  color: var(--dark-green);
  font-size: 9px;
  letter-spacing: 2px;
}

.date {
  color: var(--green);
  font-size: 12px;
  letter-spacing: 3px;
  margin-top: 28px;
}

.message {
  margin-top: 22px;
  color: #6b8870;
  font-size: 11px;
  letter-spacing: 2px;
  line-height: 1.8;
}

.terminal {
  margin: 30px auto 0;
  color: #16782c;
  font-size: 10px;
  line-height: 2;
  text-align: left;
  max-width: 420px;
  overflow-wrap: anywhere;
}

.cursor {
  display: inline-block;
  width: 7px;
  height: 12px;
  background: var(--green);
  vertical-align: middle;
  animation: blink .8s infinite;
}

.bottom {
  color: #267538;
  font-size: 9px;
  letter-spacing: 1px;
}

@keyframes blink {
  50% { opacity: 0; }
}

@keyframes flicker {
  0%, 94%, 96%, 100% { opacity: 1; }
  95% { opacity: .72; }
}

@media (max-width: 480px) {
  .screen { padding: 20px 15px; }
  .top, .bottom { font-size: 8px; letter-spacing: 1px; }
  .countdown { gap: 5px; }
  .unit { padding: 17px 2px; }
  .label { font-size: 7px; letter-spacing: 1px; }
  .subtitle { font-size: 9px; letter-spacing: 2px; }
  .terminal { font-size: 9px; }
}

@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after { animation-duration: 0.01ms !important; }
}
</style>
</head>

<body>
<canvas id="matrix" aria-hidden="true"></canvas>

<div class="screen">
  <header class="top">
    <div class="status">
      <span class="dot"></span>
      <span>SYSTEM ONLINE</span>
    </div>
    <span>ANONYMOUS / 001</span>
  </header>

  <main>
    <p class="eyebrow">[ INCOMING TRANSMISSION ]</p>

    <h1>00:00 <span>ANY</span></h1>

    <p class="subtitle">SOMETHING WILL HAPPEN.</p>

    <div class="line"></div>

    <section class="countdown" aria-label="Contagem regressiva">
      <div class="unit">
        <span class="number" id="days">00</span>
        <span class="label">DAYS</span>
      </div>
      <div class="unit">
        <span class="number" id="hours">00</span>
        <span class="label">HOURS</span>
      </div>
      <div class="unit">
        <span class="number" id="minutes">00</span>
        <span class="label">MINUTES</span>
      </div>
      <div class="unit">
        <span class="number" id="seconds">00</span>
        <span class="label">SECONDS</span>
      </div>
    </section>

    <p class="date">01 / 11 / 2026 — 00:00 BRT</p>

    <p class="message" id="message">
      THE SIGNAL IS APPROACHING.<br>
      YOUR TIME IS RUNNING OUT.
    </p>

    <div class="terminal">
      <p>&gt; initializing connection...</p>
      <p>&gt; source: <span id="source">UNKNOWN</span></p>
      <p>&gt; encryption: ACTIVE</p>
      <p>&gt; awaiting signal<span class="cursor"></span></p>
    </div>
  </main>

  <footer class="bottom">
    <span>© 2026 — 00:00 ANY</span>
    <span>IDENTITY UNKNOWN</span>
  </footer>
</div>

<script>
/* MATRIX BACKGROUND */
const canvas = document.getElementById("matrix");
const ctx = canvas.getContext("2d");

const alphabet = "アカサタナハマヤラワ0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ#$%&<>/";
const fontSize = 15;
let columns = 0;
let drops = [];

function resizeMatrix() {
  const dpr = Math.min(window.devicePixelRatio || 1, 2);
  canvas.width = Math.floor(innerWidth * dpr);
  canvas.height = Math.floor(innerHeight * dpr);
  canvas.style.width = innerWidth + "px";
  canvas.style.height = innerHeight + "px";
  ctx.setTransform(dpr, 0, 0, dpr, 0, 0);

  columns = Math.ceil(innerWidth / fontSize);
  drops = Array.from(
    { length: columns },
    () => Math.random() * -innerHeight / fontSize
  );
}

function drawMatrix() {
  ctx.fillStyle = "rgba(2, 5, 2, 0.09)";
  ctx.fillRect(0, 0, innerWidth, innerHeight);
  ctx.font = fontSize + "px monospace";

  for (let i = 0; i < columns; i++) {
    const char = alphabet[Math.floor(Math.random() * alphabet.length)];
    const x = i * fontSize;
    const y = drops[i] * fontSize;

    ctx.fillStyle = Math.random() > 0.975 ? "#d7ffe0" : "#00ff41";
    ctx.fillText(char, x, y);

    if (y > innerHeight && Math.random() > 0.975) {
      drops[i] = 0;
    } else {
      drops[i] += 0.55;
    }
  }
}

let matrixFrame;
let lastDraw = 0;

function animateMatrix(timestamp) {
  if (timestamp - lastDraw > 45) {
    drawMatrix();
    lastDraw = timestamp;
  }
  matrixFrame = requestAnimationFrame(animateMatrix);
}

resizeMatrix();
window.addEventListener("resize", resizeMatrix);
matrixFrame = requestAnimationFrame(animateMatrix);

/* COUNTDOWN: BRASILIA TIME, UTC-3 */
const target = Date.parse("2026-11-01T03:00:00Z");

const ids = {
  days: document.getElementById("days"),
  hours: document.getElementById("hours"),
  minutes: document.getElementById("minutes"),
  seconds: document.getElementById("seconds")
};

function updateCountdown() {
  let remaining = Math.max(0, target - Date.now());

  const days = Math.floor(remaining / 86400000);
  remaining %= 86400000;

  const hours = Math.floor(remaining / 3600000);
  remaining %= 3600000;

  const minutes = Math.floor(remaining / 60000);
  const seconds = Math.floor((remaining % 60000) / 1000);

  ids.days.textContent = String(days).padStart(2, "0");
  ids.hours.textContent = String(hours).padStart(2, "0");
  ids.minutes.textContent = String(minutes).padStart(2, "0");
  ids.seconds.textContent = String(seconds).padStart(2, "0");

  if (Date.now() >= target) {
    document.getElementById("message").innerHTML =
      "THE TIME HAS COME.<br>TRANSMISSION COMPLETE.";
    document.querySelector(".subtitle").textContent =
      "SIGNAL RECEIVED.";
  }
}

updateCountdown();
setInterval(updateCountdown, 250);
</script>
</body>
</html>
