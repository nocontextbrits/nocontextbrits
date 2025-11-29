<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NCB Teletext P100</title>
    <link href="https://fonts.googleapis.com/css2?family=VT323&display=swap" rel="stylesheet">
    
    <style>
        /* --- TELETEXT STYLES --- */
        body {
            background-color: #000000;
            color: #ffffff;
            font-family: 'VT323', monospace;
            font-size: 28px; /* Large text like a TV screen */
            line-height: 1.1;
            margin: 0;
            padding: 20px;
            text-transform: uppercase; /* Teletext was almost always uppercase */
            overflow-x: hidden;
        }

        /* The main TV screen container */
        .screen {
            max-width: 800px;
            margin: 0 auto;
        }

        /* Teletext Color Palette Classes */
        .c-yellow { color: #ffff00; }
        .c-cyan { color: #00ffff; }
        .c-green { color: #00ff00; }
        .c-red { color: #ff0000; }
        .c-magenta { color: #ff00ff; }
        .c-blue { color: #0000ff; }
        
        /* Background Highlighting (used for headers) */
        .bg-blue { background-color: #0000ff; color: white; padding: 0 5px; }
        .bg-white { background-color: #ffffff; color: black; }

        /* The Header Row */
        .top-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 20px;
            background-color: #000000;
        }

        /* The Graphic/Logo Area */
        .graphic {
            font-size: 24px;
            white-space: pre; /* Keeps the text alignment for ASCII art */
            color: #ffff00;
            margin-bottom: 20px;
            line-height: 18px;
        }

        /* Lists for news items */
        ul { list-style: none; padding: 0; }
        li { margin-bottom: 10px; }
        
        .page-num { color: white; font-weight: bold; }

        /* The Fastext Buttons (Red, Green, Yellow, Blue links at bottom) */
        .fastext-bar {
            margin-top: 40px;
            display: grid;
            grid-template-columns: 1fr 1fr 1fr 1fr;
            gap: 2px;
            text-align: center;
        }
        .fastext-btn {
            text-decoration: none;
            color: white;
            padding: 5px;
            font-size: 0.9em;
        }
        .ft-red { background-color: #ff0000; }
        .ft-green { background-color: #00ff00; color: black; }
        .ft-yellow { background-color: #ffff00; color: black; }
        .ft-blue { background-color: #00ffff; color: black; } /* Cyan actually readable on black */

        /* Blinking cursor effect */
        .blink { animation: blinker 1s linear infinite; }
        @keyframes blinker { 50% { opacity: 0; } }

    </style>
</head>
<body>

<div class="screen">

    <div class="top-header">
        <span><span class="bg-white">P100</span> <span class="c-cyan">CEEFAX 100</span></span>
        <span class="c-yellow" id="clock">12:00:00</span>
    </div>

    <div class="graphic">
      <span class="c-red">███</span>  <span class="c-white">███</span>  <span class="c-blue">███</span>
      <span class="c-red">███</span>  <span class="c-white">███</span>  <span class="c-blue">███</span>
      <span class="c-red">███</span>  <span class="c-white">███</span>  <span class="c-blue">███</span>
      NO CONTEXT BRITS
    </div>

    <div style="border-top: 2px solid white; border-bottom: 2px solid white; padding: 10px 0; margin-bottom: 20px;">
        <span class="c-cyan">HEADLINES FROM THE PUB</span>
    </div>

    <ul>
        <li>
            <span class="page-num">101</span> <span class="c-yellow">MAN APOLOGISES TO LAMP POST</span>
        </li>
        <li>
            <span class="page-num">102</span> <span class="c-green">BIG BEN BONGING LOUDLY</span>
        </li>
        <li>
            <span class="page-num">103</span> <span class="c-cyan">QUEUE FORMS FOR NO REASON</span>
        </li>
        <li>
            <span class="page-num">104</span> <span class="c-magenta">SOMEONE PUT MILK IN FIRST</span>
        </li>
        <li>
            <span class="page-num">105</span> <span class="c-white">BUS DRIVER NODS AT COLLEAGUE</span>
        </li>
    </ul>

    <div style="margin-top: 30px;">
        <span class="bg-blue">WEATHER</span> <span class="c-yellow">LONDON: GREY</span> <span class="c-cyan">NORTH: WET</span>
    </div>

    <div class="fastext-bar">
        <a href="#" class="fastext-btn ft-red">NEWS</a>
        <a href="#" class="fastext-btn ft-green">SPORT</a>
        <a href="#" class="fastext-btn ft-yellow">WEATHER</a>
        <a href="#" class="fastext-btn ft-blue">TV LIST</a>
    </div>

</div>

<script>
    function updateClock() {
        const now = new Date();
        const timeString = now.toLocaleTimeString('en-GB', { hour12: false });
        const dateString = now.toLocaleDateString('en-GB', { month: 'short', day: 'numeric' });
        document.getElementById('clock').innerText = dateString + " " + timeString;
    }
    setInterval(updateClock, 1000);
    updateClock();
</script>

</body>
</html>
