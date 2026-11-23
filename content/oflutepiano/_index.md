<!DOCTYPE html>
<html lang="fi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>D-Pitkähuilu-piano</title>
</head>
<body style="background: #111; display: flex; justify-content: center; align-items: center; min-height: 100vh; margin: 0;">

    <!-- Pääsovelluksen container -->
    <div id="piano-app-container" style="display: block; font-family: sans-serif; background: #1a1a1a; padding: 25px; border-radius: 15px; text-align: center; max-width: 550px; width: 100%; margin: 0 auto; border: 2px solid #333; box-sizing: border-box;">

        <h3 style="color: white; margin-bottom: 20px; font-size: 22px;">D-Pitkähuilu-piano</h3>
        
        <div id="wp-piano-grid" style="display: grid; grid-template-columns: repeat(auto-fill, minmax(75px, 1fr)); gap: 12px;"></div>

        <p style="color: #888; font-size: 13px; margin-top: 20px;">
            Valkoinen = Avoin (parillinen) <br>
            Tumma = Suljettu (pariton)
        </p>

        <script>
        (function() {
            const fundFrequency = 73.416; 
            const noteLabels = {2:"D3", 3:"A3", 4:"D4", 5:"F#4", 6:"A4", 7:"C5", 8:"D5", 9:"E5", 10:"F#5", 11:"G#5", 12:"A5", 13:"Bb5", 14:"C6", 15:"C#6", 16:"D6", 17:"E6", 18:"F#6"};
            
            let audioContext;
            const grid = document.getElementById('wp-piano-grid');
            for (let i = 2; i <= 18; i++) {
                const btn = document.createElement('button');
                const isOdd = i % 2 !== 0;
                
                Object.assign(btn.style, {
                    aspectRatio: "1/1.4",
                    border: "none",
                    borderRadius: "10px",
                    cursor: "pointer",
                    display: "flex",
                    flexDirection: "column",
                    justifyContent: "center",
                    alignItems: "center",
                    fontWeight: "bold",
                    fontSize: "18px",
                    boxShadow: isOdd ? "0 5px 0 #000" : "0 5px 0 #999",
                    background: isOdd ? "#444" : "#eee",
                    color: isOdd ? "#fff" : "#222",
                    padding: "10px"
                });
                btn.innerHTML = `<span>${i}</span><small style="font-size:10px; opacity:0.7; margin-top:4px; font-weight:normal;">${noteLabels[i] || ""}</small>`;
                
                const playSound = (e) => {
                    e.preventDefault();
                    if (!audioContext) audioContext = new (window.AudioContext || window.webkitAudioContext)();
                    if (audioContext.state === 'suspended') audioContext.resume();
                    const osc = audioContext.createOscillator();
                    const gain = audioContext.createGain();
                    const filter = audioContext.createBiquadFilter();
                    osc.type = 'triangle';
                    osc.frequency.setValueAtTime(fundFrequency * i, audioContext.currentTime);
                    filter.type = "lowpass";
                    filter.frequency.setValueAtTime(isOdd ? (fundFrequency*i)*1.5 : (fundFrequency*i)*4, audioContext.currentTime);
                    gain.gain.setValueAtTime(0, audioContext.currentTime);
                    gain.gain.linearRampToValueAtTime(0.3, audioContext.currentTime + 0.05);
                    gain.gain.exponentialRampToValueAtTime(0.01, audioContext.currentTime + 0.8);
                    osc.connect(filter);
                    filter.connect(gain);
                    gain.connect(audioContext.destination);
                    osc.start();
                    osc.stop(audioContext.currentTime + 0.8);
                    
                    btn.style.transform = "translateY(4px)";
                    btn.style.boxShadow = "none";
                    setTimeout(() => {
                        btn.style.transform = "translateY(0)";
                        btn.style.boxShadow = isOdd ? "0 5px 0 #000" : "0 5px 0 #999";
                    }, 100);
                };
                btn.onmousedown = playSound;
                btn.ontouchstart = playSound;
                grid.appendChild(btn);
            }
        })();
        </script>
    </div>

</body>
</html>
