
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#030604">
<meta name="description" content="00:00 ANY :)">
<title>00:00 ANY</title>

<style>
:root {
  --green: #39ff78;
  --muted: #63836c;
  --bg: #030604;
}

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html, body {
  width: 100%;
  min-height: 100%;
}

body {
  min-height: 100vh;
  overflow: hidden;
  background: var(--bg);
  color: #f0f5f1;
  font-family: "Courier New", monospace;
}

#matrix {
  position: fixed;
  inset: 0;
  width: 100%;
  height: 100%;
  opacity: .23;
  pointer-events: none;
}

body::after {
  content: "";
  position: fixed;
  inset: 0;
  pointer-events: none;
  background:
    radial-gradient(ellipse at center,
      #030604 0%,
      rgba(3, 6, 4, .96) 25%,
      rgba(3, 6, 4, .55) 65%,
      rgba(3, 6, 4, .2) 100%);
}

.page {
  position: relative;
  z-index: 1;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 30px 20px;
}

.status {
  position: absolute;
  top: 32px;
  left: 36px;
  display: flex;
  align-items: center;
  gap: 9px;
  color: #779681;
  font-size: 10px;
  letter-spacing: 2px;
}

.dot {
  width: 6px;
  height: 6px;
  background: var(--green);
  border-radius: 50%;
  box-shadow: 0 0 10px rgba(57, 255, 120, .7);
  animation: pulse 2s infinite;
}

.top-right {
  position: absolute;
  top: 32px;
  right: 36px;
  color: #456b4e;
  font-size: 10px;
  letter-spacing: 2px;
}

.content {
  width: 100%;
  max-width: 680px;
  text-align: center;
  animation: appear 1.5s ease both;
}

.signature {
  color: var(--green);
  font-size: 11px;
  letter-spacing: 5px;
  margin-bottom: 26px;
}

h1 {
  font-family: Arial, Helvetica, sans-serif;
  font-size: clamp(46px, 9vw, 82px);
  font-weight: 500;
  letter-spacing: -3px;
  line-height: 1.1;
}

h1 span {
  color: var(--green);
  font-weight: 700;
}

.subtitle {
  margin-top: 18px;
  color: #84978a;
  font-size: 11px;
  letter-spacing: 3px;
}

.divider {
  width: 46px;
  height: 1px;
  margin: 42px auto;
  background: var(--green);
  opacity: .65;
}

.countdown {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 24px;
}

.unit {
  min-width: 0;
}

.number {
  display: block;
  color: #f4f7f4;
  font-family: Arial, Helvetica, sans-serif;
  font-size: clamp(34px, 7vw, 58px);
  font-weight: 400;
  font-variant-numeric: tabular-nums;
  letter-spacing: -2px;
}

.label {
  display: block;
  margin-top: 13px;
  color: var(--muted);
  font-size: 9px;
  letter-spacing: 2px;
}

.date {
  margin-top: 34px;
  color: var(--green);
  font-size: 11px;
  letter-spacing: 3px;
}

.message {
  margin-top: 22px;
  color: #718478;
  font-size: 11px;
  letter-spacing: 1px;
  line-height: 2;
}

.bottom {
  position: absolute;
  bottom: 28px;
  left: 36px;
  right: 36px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  color: #526958;
  font-size: 10px;
  letter-spacing: 1px;
}

.smile {
  color: var(--green);
  font-size: 15px;
  letter-spacing: 0;
}

@keyframes pulse {
  50% {
    opacity: .35;
    box-shadow: 0 0 2px var(--green);
  }
}

@keyframes appear {
  from {
    opacity: 0;
    transform: translateY(8px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@media (max-width: 500px) {
  .status {
    top: 22px;
    left: 18px;
    font-size: 8px;
    letter-spacing: 1px;
  }

  .top-right {
    top: 22px;
    right: 18px;
    font-size: 8px;
    letter-spacing: 1px;
  }

  .countdown {
    gap: 8px;
  }

  .number {
    font-size: clamp(29px, 8vw, 42px);
  }

  .label {
    font-size: 7px;
    letter-spacing: 1px;
  }

  .date {
    font-size: 9px;
    letter-spacing: 2px;
  }

  .bottom {
    left: 18px;
    right: 18px;
    bottom: 20px;
    font-size: 8px;
  }

  .subtitle {
    font-size: 9px;
    letter-spacing: 2px;
  }

  .divider {
    margin: 32px auto;
  }
}

@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation: none !important;
  }
}
</style>
</head>

<body>
<canvas id="matrix" aria-hidden="true"></canvas>

<div class="page">
  <div class="status">
    <span class="dot"></span>
    <span>SYSTEM ONLINE</span>
  </div>

  <div class="top-right">UNKNOWN / 001</div>

  <main class="content">
    <p class="signature">[ NO IDENTITY ]</p>

    <h1>00:00 <span>ANY</span></h1>

    <p class="subtitle">YOU FOUND YOUR WAY HERE.</p>

    <div class="divider"></div>

    <section class="countdown">
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

    <p class="date">01.11.2026 — 00:00 BRT</p>

    <p class="message" id="message">
      NO EXPLANATIONS.<br>
      JUST WAIT.
    </p>
  </main>

  <footer class="bottom">
    <span>00:00 ANY — 2026</span>
    <span class="smile">:)</span>
    <span>SEE YOU AT ZERO.</span>
  </footer>
</div>

<script>
const canvas = document.getElementById("matrix");
const ctx = canvas.getContext("2d");
const chars = "0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZアイウエオカキクケコ#$%";
const fontSize = 15;

let columns = 0;
let drops = [];

function resize() {
  const dpr = Math.min(window.devicePixelRatio || 1, 2);

  canvas.width = innerWidth * dpr;
  canvas.height = innerHeight * dpr;
  canvas.style.width = innerWidth + "px";
  canvas.style.height = innerHeight + "px";

  ctx.setTransform(dpr, 0, 0, dpr, 0, 0);

  columns = Math.ceil(innerWidth / fontSize);
  drops = Array.from(
    { length: columns },
    () => Math.random() * -100
  );
}

function draw() {
  ctx.fillStyle = "rgba(3, 6, 4, 0.12)";
  ctx.fillRect(0, 0, innerWidth, innerHeight);
  ctx.font = fontSize + "px monospace";

  for (let i = 0; i < columns; i++) {
    const char = chars[Math.floor(Math.random() * chars.length)];
    const x = i * fontSize;
    const y = drops[i] * fontSize;

    ctx.fillStyle = Math.random() > 0.96
      ? "#baffca"
      : "#00d94b";

    ctx.fillText(char, x, y);

    if (y > innerHeight && Math.random() > 0.975) {
      drops[i] = Math.random() * -20;
    } else {
      drops[i] += 0.45;
    }
  }
}

let lastFrame = 0;

function animate(time) {
  if (time - lastFrame > 55) {
    draw();
    lastFrame = time;
  }

  requestAnimationFrame(animate);
}

resize();
window.addEventListener("resize", resize);
requestAnimationFrame(animate);

const target = Date.parse("2026-11-01T03:00:00Z");

function updateTimer() {
  let remaining = Math.max(0, target - Date.now());

  const days = Math.floor(remaining / 86400000);
  remaining %= 86400000;

  const hours = Math.floor(remaining / 3600000);
  remaining %= 3600000;

  const minutes = Math.floor(remaining / 60000);
  const seconds = Math.floor((remaining % 60000) / 1000);

  document.getElementById("days").textContent =
    String(days).padStart(2, "0");

  document.getElementById("hours").textContent =
    String(hours).padStart(2, "0");

  document.getElementById("minutes").textContent =
    String(minutes).padStart(2, "0");

  document.getElementById("seconds").textContent =
    String(seconds).padStart(2, "0");

  if (Date.now() >= target) {
    document.getElementById("message").innerHTML =
      "YOU MADE IT.<br>:)";
  }
}

updateTimer();
setInterval(updateTimer, 250);
</script>
</body>
</html>
