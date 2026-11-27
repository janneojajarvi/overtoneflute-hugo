---
layout: post
title: "See Your Sound: Exploring Harmonics with our Real-Time Visualizer"
date: 2024-11-27
aliases:
  - "/2026/03/24/visualizing-the-invisible-a-real-time-guide-to-harmonics/"
---

#### See Your Sound: Exploring Harmonics with our Real-Time Visualizer

Have you ever wondered what makes the sound of an overtone flute so hauntingly beautiful, or why a harmonica has its characteristic "grit"? The answer lies in the harmonic series—a hidden stack of frequencies that exists within every note we play.

While our ears perceive these frequencies as a single rich tone, our new Harmonic Visualizer allows you to see them with scientific precision. By using your device's microphone, this tool transforms sound waves into a live spectral graph, revealing the "DNA" of your instrument’s voice.

**What to Look For:**
* **The Fundamental**: The first and strongest peak on the left represents the basic pitch of the note[span_3](start_span)[span_3](end_span)[span_4](start_span)[span_4](end_span).
* **Overtones**: The smaller peaks to the right are the harmonics. On an overtone flute, you can watch these peaks shift as you change your blowing pressure[span_5](start_span)[span_5](end_span)[span_6](start_span)[span_6](end_span).
* **Sound Color** (Timbre): A "pure" sound like a whistle will show fewer peaks, while a rich, buzzy sound will create a dense forest of harmonics[span_7](start_span)[span_7](end_span)[span_8](start_span)[span_8](end_span).

**How to Use the Tool:**
1. Click "Start Microphone" and grant your browser permission to access audio[span_9](start_span)[span_9](end_span)[span_10](start_span)[span_10](end_span).
2. Play a steady note on your flute, harmonica, or even sing into the mic[span_11](start_span)[span_11](end_span)[span_12](start_span)[span_12](end_span).
3. Observe how the peaks react to different playing techniques[span_13](start_span)[span_13](end_span)[span_14](start_span)[span_14](end_span).
4. To get the most accurate reading, try practicing in a quiet room to minimize background noise[span_15](start_span)[span_15](end_span)[span_16](start_span)[span_16](end_span).

Ready to visualize your music? Kokeile työkalua suoraan alta[span_17](start_span)[span_17](end_span)!

<style>
.analyzer-container {
  background: #fdfdfd;
  border: 1px solid #7a8c5a;
  border-radius: 15px;
  padding: 25px;
  max-width: 600px;
  margin: 20px auto;
  font-family: 'Segoe UI', sans-serif;
  text-align: center;
}
.analyzer-info { font-size: 0.85rem; color: #666; margin-bottom: 15px; }

.canvas-wrapper {
  position: relative;
  background: #1a1a1a;
  border-radius: 8px;
  padding: 10px;
  margin-bottom: 20px;
  border: 2px solid #333;
}
#visualizerCanvas { width: 100%; height: 200px; display: block; }

.freq-labels {
  display: flex;
  justify-content: space-between;
  font-size: 0.7rem;
  color: #888;
  margin-top: 5px;
}

.mic-btn {
  padding: 12px 24px;
  background: #7a8c5a;
  color: white;
  border: none;
  border-radius: 6px;
  font-weight: bold;
  cursor: pointer;
  transition: 0.2s;
}
.mic-btn.active { background: #e74c3c; }
</style>

<div class="analyzer-container">
  <h3>Overtone Visualizer</h3>
  <p class="analyzer-info">Grant microphone access and play your flute to see its frequency structure (spectrum).</p>
  
  <div class="canvas-wrapper">
    <canvas id="visualizerCanvas"></canvas>
    <div class="freq-labels">
      <span>0 Hz</span>
      <span>5 kHz</span>
      <span>10 kHz</span>
    </div>
  </div>

  <div class="controls">
    <button id="micBtn" class="mic-btn" onclick="toggleMic()">START MICROPHONE</button>
  </div>
</div>

<script>
let audioContext = null;
let analyser = null;
let microphone = null;
let isAnalyzing = false;
let animationId = null;

function getCanvasContext() {
  const canvas = document.getElementById('visualizerCanvas');
  return canvas ? canvas.getContext('2d') : null;
}

async function toggleMic() {
  const btn = document.getElementById('micBtn');
  
  if (isAnalyzing) {
    stopAnalysis();
    btn.innerText = "START MICROPHONE";
    btn.classList.remove('active');
    return;
  }

  try {
    const stream = await navigator.mediaDevices.getUserMedia({ audio: true });
    audioContext = new (window.AudioContext || window.webkitAudioContext)();
    analyser = audioContext.createAnalyser();
    microphone = audioContext.createMediaStreamSource(stream);
    
    analyser.fftSize = 4096;
    microphone.connect(analyser);
    
    isAnalyzing = true;
    btn.innerText = "STOP MICROPHONE";
    btn.classList.add('active');
    
    draw();
  } catch (err) {
    console.error("Microphone access denied or error:", err);
    alert("Could not access microphone. Please ensure you have granted permission.");
  }
}

function stopAnalysis() {
  isAnalyzing = false;
  if (animationId) cancelAnimationFrame(animationId);
  if (audioContext) {
    audioContext.close();
    audioContext = null;
  }
}

function draw() {
  if (!isAnalyzing) return;
  
  animationId = requestAnimationFrame(draw);
  
  const canvas = document.getElementById('visualizerCanvas');
  const canvasCtx = getCanvasContext();
  if (!canvas || !canvasCtx) return;

  if (canvas.width !== canvas.clientWidth || canvas.height !== canvas.clientHeight) {
    canvas.width = canvas.clientWidth;
    canvas.height = canvas.clientHeight;
  }
  
  const bufferLength = analyser.frequencyBinCount;
  const dataArray = new Uint8Array(bufferLength);
  analyser.getByteFrequencyData(dataArray);

  canvasCtx.fillStyle = '#1a1a1a';
  canvasCtx.fillRect(0, 0, canvas.width, canvas.height);

  const barWidth = (canvas.width / bufferLength) * 2.5;
  let x = 0;

  for (let i = 0; i < bufferLength; i++) {
    const barHeight = (dataArray[i] / 1.5) * (canvas.height / 200);

    canvasCtx.fillStyle = `rgb(122, 140, 90)`;
    canvasCtx.fillRect(x, canvas.height - barHeight, barWidth, barHeight);

    x += barWidth + 1;
  }
}
</script>
