<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SECURITY BREACH DETECTED</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Courier New', monospace;
        }
        
        body {
            background-color: #000;
            color: #0f0;
            overflow: hidden;
            height: 100vh;
            position: relative;
            cursor: none;
        }
        
        .scan-line {
            position: absolute;
            height: 2px;
            width: 100%;
            background: linear-gradient(to right, rgba(0, 255, 0, 0), rgba(0, 255, 0, 0.8), rgba(0, 255, 0, 0));
            top: 0;
            animation: scan 3s linear infinite;
            z-index: 100;
            box-shadow: 0 0 15px rgba(0, 255, 0, 0.7);
        }
        
        .noise {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 250 250' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noiseFilter'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.65' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noiseFilter)'/%3E%3C/svg%3E");
            opacity: 0.05;
            pointer-events: none;
            z-index: 10;
        }
        
        .container {
            padding: 20px;
            max-width: 900px;
            margin: 0 auto;
            height: 100vh;
            display: flex;
            flex-direction: column;
        }
        
        .header {
            text-align: center;
            margin-bottom: 20px;
            padding: 10px;
            border-bottom: 1px solid #0f0;
            position: relative;
            overflow: hidden;
        }
        
        .glitch {
            font-size: 28px;
            font-weight: bold;
            text-transform: uppercase;
            position: relative;
            text-shadow: 0.05em 0 0 rgba(255, 0, 0, 0.75), -0.025em -0.05em 0 rgba(0, 255, 0, 0.75), 0.025em 0.05em 0 rgba(0, 0, 255, 0.75);
            animation: glitch 2s infinite;
            color: #ff0000;
        }
        
        .terminal {
            background-color: rgba(0, 20, 0, 0.8);
            border: 1px solid #0f0;
            border-radius: 5px;
            padding: 15px;
            flex-grow: 1;
            overflow-y: auto;
            box-shadow: 0 0 15px rgba(0, 255, 0, 0.3);
            position: relative;
        }
        
        .terminal-line {
            margin-bottom: 5px;
            line-height: 1.4;
            opacity: 0;
            animation: fadeIn 0.1s forwards;
        }
        
        .prompt {
            color: #0f0;
            font-weight: bold;
        }
        
        .command {
            color: #0af;
        }
        
        .output {
            color: #0f0;
        }
        
        .warning {
            color: #ff0;
            font-weight: bold;
        }
        
        .danger {
            color: #f00;
            font-weight: bold;
            text-shadow: 0 0 5px rgba(255, 0, 0, 0.7);
        }
        
        .progress-container {
            margin-top: 20px;
            background-color: rgba(0, 30, 0, 0.5);
            border-radius: 3px;
            overflow: hidden;
            height: 20px;
            border: 1px solid #0f0;
        }
        
        .progress-bar {
            height: 100%;
            width: 0%;
            background: linear-gradient(90deg, #0f0, #0c0);
            transition: width 0.5s ease;
        }
        
        .blink {
            animation: blink 0.7s infinite;
        }
        
        .access-granted {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: #000;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            z-index: 1000;
            opacity: 0;
            pointer-events: none;
            transition: opacity 1s;
        }
        
        .access-text {
            font-size: 48px;
            color: #0f0;
            text-shadow: 0 0 10px #0f0;
            margin-bottom: 20px;
            animation: pulse 2s infinite;
        }
        
        .flashing {
            animation: flash 0.3s infinite;
        }
        
        .fake-popup {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: linear-gradient(to bottom, #2a2a2a, #1a1a1a);
            border: 2px solid #f00;
            border-radius: 10px;
            padding: 20px;
            width: 300px;
            z-index: 2000;
            box-shadow: 0 0 30px rgba(255, 0, 0, 0.5);
            display: none;
        }
        
        .popup-title {
            color: #f00;
            font-weight: bold;
            margin-bottom: 15px;
            text-align: center;
        }
        
        .popup-content {
            color: #fff;
            margin-bottom: 20px;
            text-align: center;
        }
        
        .popup-buttons {
            display: flex;
            justify-content: space-around;
        }
        
        .popup-btn {
            padding: 8px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-weight: bold;
        }
        
        .popup-deny {
            background: #444;
            color: #fff;
        }
        
        .popup-allow {
            background: linear-gradient(to bottom, #f00, #900);
            color: #fff;
        }
        
        .fake-cursor {
            position: absolute;
            width: 12px;
            height: 20px;
            background: #0f0;
            z-index: 3000;
            animation: blink 1s infinite;
            pointer-events: none;
        }
        
        .exit-message {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: rgba(0, 0, 0, 0.8);
            border: 1px solid #f00;
            padding: 10px;
            border-radius: 5px;
            color: #f00;
            font-size: 14px;
            display: none;
            z-index: 1500;
        }
        
        .remove-hack {
            position: fixed;
            bottom: 10px;
            left: 10px;
            background: rgba(0, 0, 0, 0.8);
            border: 1px solid #0f0;
            padding: 10px;
            border-radius: 5px;
            color: #0f0;
            font-size: 12px;
            z-index: 1500;
            text-align: center;
        }
        
        .remove-hack a {
            color: #0ff;
            text-decoration: none;
        }
        
        @keyframes scan {
            0% { top: 0; }
            100% { top: 100%; }
        }
        
        @keyframes glitch {
            0% { text-shadow: 0.05em 0 0 rgba(255, 0, 0, 0.75), -0.05em -0.025em 0 rgba(0, 255, 0, 0.75), -0.025em 0.05em 0 rgba(0, 0, 255, 0.75); }
            14% { text-shadow: 0.05em 0 0 rgba(255, 0, 0, 0.75), -0.05em -0.025em 0 rgba(0, 255, 0, 0.75), -0.025em 0.05em 0 rgba(0, 0, 255, 0.75); }
            15% { text-shadow: -0.05em -0.025em 0 rgba(255, 0, 0, 0.75), 0.025em 0.025em 0 rgba(0, 255, 0, 0.75), -0.05em -0.05em 0 rgba(0, 0, 255, 0.75); }
            49% { text-shadow: -0.05em -0.025em 0 rgba(255, 0, 0, 0.75), 0.025em 0.025em 0 rgba(0, 255, 0, 0.75), -0.05em -0.05em 0 rgba(0, 0, 255, 0.75); }
            50% { text-shadow: 0.025em 0.05em 0 rgba(255, 0, 0, 0.75), 0.05em 0 0 rgba(0, 255, 0, 0.75), 0 -0.05em 0 rgba(0, 0, 255, 0.75); }
            99% { text-shadow: 0.025em 0.05em 0 rgba(255, 0, 0, 0.75), 0.05em 0 0 rgba(0, 255, 0, 0.75), 0 -0.05em 0 rgba(0, 0, 255, 0.75); }
            100% { text-shadow: -0.025em 0 0 rgba(255, 0, 0, 0.75), -0.025em -0.025em 0 rgba(0, 255, 0, 0.75), -0.025em -0.05em 0 rgba(0, 0, 255, 0.75); }
        }
        
        @keyframes fadeIn {
            to { opacity: 1; }
        }
        
        @keyframes blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0; }
        }
        
        @keyframes pulse {
            0%, 100% { transform: scale(1); opacity: 1; }
            50% { transform: scale(1.05); opacity: 0.8; }
        }
        
        @keyframes flash {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.3; }
        }
        
        .vibration {
            animation: vibrate 0.3s linear infinite;
        }
        
        @keyframes vibrate {
            0% { transform: translate(0); }
            20% { transform: translate(-2px, 2px); }
            40% { transform: translate(-2px, -2px); }
            60% { transform: translate(2px, 2px); }
            80% { transform: translate(2px, -2px); }
            100% { transform: translate(0); }
        }
    </style>
</head>
<body>
    <div class="noise"></div>
    <div class="scan-line"></div>
    <div class="fake-cursor" id="fake-cursor"></div>
    
    <div class="container">
        <div class="header">
            <div class="glitch">SECURITY BREACH DETECTED</div>
            <div class="warning">UNAUTHORIZED ACCESS IN PROGRESS</div>
        </div>
        
        <div class="terminal" id="terminal">
            <div class="terminal-line"><span class="prompt">root@darknet:~#</span> <span class="command">initiate system_breach.exe</span></div>
            <div class="terminal-line output">Initializing attack vector...</div>
            <div class="terminal-line output">Bypassing firewall protections...</div>
            <div class="terminal-line output">Firewall compromised. Access granted.</div>
            <div class="terminal-line"><span class="prompt">root@darknet:~#</span> <span class="command">scan_network --target=local</span></div>
            <div class="terminal-line output">Scanning network for connected devices...</div>
            <div class="terminal-line output">Device identified: Samsung Galaxy S23</div>
            <div class="terminal-line output">Owner: Abhay</div>
            <div class="terminal-line output">IP: 192.168.1.107</div>
            <div class="terminal-line"><span class="prompt">root@darknet:~#</span> <span class="command">exploit android --cve-2023-4863</span></div>
            <div class="terminal-line output">Exploiting vulnerability CVE-2023-4863...</div>
            <div class="terminal-line output">Vulnerability successfully exploited!</div>
            <div class="terminal-line output">Establishing persistent connection...</div>
            <div class="terminal-line"><span class="prompt">root@darknet:~#</span> <span class="command">access_storage --full</span></div>
            <div class="terminal-line output">Accessing device storage...</div>
            <div class="terminal-line warning">WARNING: This device has protected content</div>
            <div class="terminal-line"><span class="prompt">root@darknet:~#</span> <span class="command">override_protection --force</span></div>
            <div class="terminal-line output">Bypassing protection mechanisms...</div>
            <div class="terminal-line output">Protection override successful!</div>
            <div class="terminal-line"><span class="prompt">root@darknet:~#</span> <span class="command">download --all --destination=remote_server/abhay_phone</span></div>
            <div class="terminal-line output">Downloading all accessible data...</div>
            <div class="terminal-line output">Downloading photos (487 files)...</div>
            <div class="terminal-line output">Downloading messages (1243 conversations)...</div>
            <div class="terminal-line output">Downloading contacts (187 entries)...</div>
            <div class="terminal-line output">Downloading browsing history...</div>
            <div class="terminal-line output">Downloading app data...</div>
            <div class="terminal-line danger">ALERT: Security application detected!</div>
            <div class="terminal-line"><span class="prompt">root@darknet:~#</span> <span class="command">kill_process com.antivirus.android</span></div>
            <div class="terminal-line output">Terminating security processes...</div>
            <div class="terminal-line output">Security processes terminated successfully.</div>
            <div class="terminal-line"><span class="prompt">root@darknet:~#</span> <span class="command">enable_backdoor --persistent</span></div>
            <div class="terminal-line output">Installing persistent backdoor...</div>
            <div class="terminal-line output">Backdoor installed successfully.</div>
            <div class="terminal-line"><span class="prompt">root@darknet:~#</span> <span class="command">encrypt_storage --key=0x7F3A9C</span></div>
            <div class="terminal-line output">Encrypting device storage...</div>
            <div class="terminal-line blink">ENCRYPTION IN PROGRESS... DO NOT TURN OFF DEVICE</div>
        </div>
        
        <div class="progress-container">
            <div class="progress-bar" id="progress-bar"></div>
        </div>
    </div>
    
    <div class="access-granted" id="access-granted">
        <div class="access-text">ACCESS GRANTED</div>
        <div class="output">System fully compromised. All data extracted.</div>
        <div class="output">Backdoor installed. Persistent access established.</div>
    </div>
    
    <div class="fake-popup" id="fake-popup">
        <div class="popup-title">SECURITY ALERT</div>
        <div class="popup-content">System protection needs access to storage to verify security threats. Allow access?</div>
        <div class="popup-buttons">
            <button class="popup-btn popup-deny" id="popup-deny">DENY</button>
            <button class="popup-btn popup-allow" id="popup-allow">ALLOW</button>
        </div>
    </div>
    
    <div class="exit-message" id="exit-message">
        Exit blocked: System security compromised. Cannot exit during encryption process.
    </div>
    
    <div class="remove-hack">
      Remove hack - 91116621220@axl (Send 500₹)<br>
Click Here: <a href="https://wa.me/919329800917?text=Please%20hata%20do%20%F0%9F%98%AB%F0%9F%99%8F%F0%9F%99%8F%F0%9F%92%93" target="_blank"><button>Send 500₹</button></a>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const terminal = document.getElementById('terminal');
            const progressBar = document.getElementById('progress-bar');
            const accessGranted = document.getElementById('access-granted');
            const fakePopup = document.getElementById('fake-popup');
            const popupAllow = document.getElementById('popup-allow');
            const popupDeny = document.getElementById('popup-deny');
            const exitMessage = document.getElementById('exit-message');
            const fakeCursor = document.getElementById('fake-cursor');
            const lines = document.querySelectorAll('.terminal-line');
            
            // Disable right-click
            document.addEventListener('contextmenu', function(e) {
                e.preventDefault();
                showExitBlocked();
                return false;
            });
            
            // Disable back button
            history.pushState(null, null, document.URL);
            window.addEventListener('popstate', function() {
                history.pushState(null, null, document.URL);
                showExitBlocked();
            });
            
            // Move fake cursor
            document.addEventListener('mousemove', function(e) {
                fakeCursor.style.left = (e.pageX - 6) + 'px';
                fakeCursor.style.top = (e.pageY - 10) + 'px';
            });
            
            // Function to show exit blocked message
            function showExitBlocked() {
                exitMessage.style.display = 'block';
                setTimeout(function() {
                    exitMessage.style.display = 'none';
                }, 3000);
                playSound('error');
            }
            
            // Function to simulate vibration
            function vibrate() {
                document.body.classList.add('vibration');
                setTimeout(() => {
                    document.body.classList.remove('vibration');
                }, 300);
            }
            
            // Function to simulate device shaking
            function shake() {
                const intensity = 10;
                let startTime = null;
                
                function animate(timestamp) {
                    if (!startTime) startTime = timestamp;
                    const elapsed = timestamp - startTime;
                    
                    const x = Math.sin(elapsed / 50) * intensity;
                    const y = Math.cos(elapsed / 70) * intensity;
                    
                    terminal.style.transform = `translate(${x}px, ${y}px)`;
                    
                    if (elapsed < 1000) {
                        requestAnimationFrame(animate);
                    } else {
                        terminal.style.transform = 'translate(0, 0)';
                    }
                }
                
                requestAnimationFrame(animate);
            }
            
            // Function to flash the screen
            function flashScreen() {
                document.body.style.backgroundColor = '#ff0000';
                setTimeout(() => {
                    document.body.style.backgroundColor = '#000';
                }, 100);
            }
            
            // Function to add glitch effect
            function glitchEffect() {
                terminal.style.filter = 'blur(1px)';
                setTimeout(() => {
                    terminal.style.filter = 'none';
                }, 100);
            }
            
            // Function to play sound
            function playSound(type) {
                try {
                    if (type === 'access') {
                        // Create scary access granted sound
                        const context = new (window.AudioContext || window.webkitAudioContext)();
                        const oscillator = context.createOscillator();
                        const gain = context.createGain();
                        
                        oscillator.type = 'sawtooth';
                        oscillator.frequency.setValueAtTime(100, context.currentTime);
                        oscillator.frequency.exponentialRampToValueAtTime(800, context.currentTime + 0.5);
                        
                        gain.gain.setValueAtTime(0.5, context.currentTime);
                        gain.gain.exponentialRampToValueAtTime(0.01, context.currentTime + 0.8);
                        
                        oscillator.connect(gain);
                        gain.connect(context.destination);
                        
                        oscillator.start();
                        oscillator.stop(context.currentTime + 0.8);
                    } else if (type === 'error') {
                        // Create error sound
                        const context = new (window.AudioContext || window.webkitAudioContext)();
                        const oscillator = context.createOscillator();
                        const gain = context.createGain();
                        
                        oscillator.type = 'square';
                        oscillator.frequency.setValueAtTime(300, context.currentTime);
                        oscillator.frequency.exponentialRampToValueAtTime(100, context.currentTime + 0.2);
                        
                        gain.gain.setValueAtTime(0.5, context.currentTime);
                        gain.gain.exponentialRampToValueAtTime(0.01, context.currentTime + 0.3);
                        
                        oscillator.connect(gain);
                        gain.connect(context.destination);
                        
                        oscillator.start();
                        oscillator.stop(context.currentTime + 0.3);
                    }
                } catch (e) {
                    console.log('Audio context not supported');
                }
            }
            
            // Show fake permission popup
            function showPopup() {
                fakePopup.style.display = 'block';
                vibrate();
                playSound('error');
            }
            
            // Handle popup buttons
            popupAllow.addEventListener('click', function() {
                fakePopup.style.display = 'none';
                playSound('access');
                // Continue with the hack process
                continueHack();
            });
            
            popupDeny.addEventListener('click', function() {
                fakePopup.style.display = 'none';
                // Show popup again after a delay to annoy the user
                setTimeout(showPopup, 2000);
                playSound('error');
                vibrate();
            });
            
            // Continue hack after permission granted
            function continueHack() {
                const additionalLines = [
                    '<span class="prompt">root@darknet:~#</span> <span class="command">access_camera --front</span>',
                    '<span class="output">Accessing front camera...</span>',
                    '<span class="output">Camera feed captured.</span>',
                    '<span class="prompt">root@darknet:~#</span> <span class="command">access_microphone</span>',
                    '<span class="output">Accessing microphone...</span>',
                    '<span class="output">Microphone activated. Recording audio.</span>',
                    '<span class="prompt">root@darknet:~#</span> <span class="command">exfiltrate_data --server=darkweb://data.drop</span>',
                    '<span class="output">Exfiltrating all collected data...</span>',
                    '<span class="output">Transfer complete. 2.7GB uploaded.</span>',
                    '<span class="prompt">root@darknet:~#</span> <span class="command">clean_traces --deep</span>',
                    '<span class="output">Removing all traces of intrusion...</span>',
                    '<span class="output">Forensic countermeasures deployed.</span>',
                    '<span class="danger">MISSION COMPLETE. SYSTEM OWNED.</span>'
                ];
                
                let delay = 0;
                additionalLines.forEach((line, index) => {
                    setTimeout(() => {
                        const newLine = document.createElement('div');
                        newLine.className = 'terminal-line';
                        newLine.innerHTML = line;
                        terminal.appendChild(newLine);
                        newLine.style.animation = `fadeIn 0.1s forwards`;
                        
                        // Random effects during the "hack"
                        if (Math.random() > 0.7) vibrate();
                        if (index % 5 === 0) shake();
                        
                        // Scroll to bottom of terminal
                        terminal.scrollTop = terminal.scrollHeight;
                        
                        // Update progress bar
                        progressBar.style.width = `${((lines.length + index) / (lines.length + additionalLines.length)) * 100}%`;
                        
                        // Show access granted at the end
                        if (index === additionalLines.length - 1) {
                            setTimeout(() => {
                                accessGranted.style.opacity = '1';
                                accessGranted.style.pointerEvents = 'all';
                                playSound('access');
                                vibrate();
                                flashScreen();
                            }, 1000);
                        }
                    }, delay);
                    
                    delay += 500 + Math.random() * 500;
                });
            }
            
            // Animate terminal lines with progressive display
            let delay = 0;
            lines.forEach((line, index) => {
                setTimeout(() => {
                    line.style.animation = `fadeIn 0.1s forwards`;
                    
                    // Random effects during the "hack"
                    if (Math.random() > 0.7) vibrate();
                    if (Math.random() > 0.8) glitchEffect();
                    if (index % 7 === 0) shake();
                    if (index === 15 || index === 25) flashScreen();
                    
                    // Show popup at specific points
                    if (index === 8) {
                        setTimeout(showPopup, 1000);
                    }
                    
                    // Scroll to bottom of terminal
                    terminal.scrollTop = terminal.scrollHeight;
                    
                    // Update progress bar
                    progressBar.style.width = `${(index / lines.length) * 100}%`;
                }, delay);
                
                delay += 500 + Math.random() * 500;
            });
        });
    </script>
</body>
</html>
