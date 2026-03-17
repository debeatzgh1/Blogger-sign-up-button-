
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DeBeatzGH | Clean UI</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;700&family=Plus+Jakarta+Sans:wght@400;800&display=swap');

        :root {
            --accent: #00f2ff;
            --bg-dark: #050507;
            --glass: rgba(255, 255, 255, 0.05);
            --border: rgba(0, 242, 255, 0.2);
        }

        body {
            background-color: var(--bg-dark);
            color: #f0f6fc;
            font-family: 'Plus Jakarta Sans', sans-serif;
            margin: 0; overflow: hidden; height: 100vh;
            display: flex; align-items: center; justify-content: center;
        }

        /* --- AMBIENT BACKGROUND --- */
        .cyber-orb {
            position: fixed; top: 50%; left: 50%;
            width: 600px; height: 600px;
            background: radial-gradient(circle, rgba(0, 242, 255, 0.1) 0%, transparent 70%);
            transform: translate(-50%, -50%);
            z-index: -1;
        }

        /* --- CLEAN GLASS PANEL --- */
        .glass-panel {
            background: var(--glass);
            backdrop-filter: blur(15px);
            -webkit-backdrop-filter: blur(15px);
            border: 1px solid var(--border);
            border-radius: 32px;
            padding: 40px;
            max-width: 420px;
            width: 90%;
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.5);
        }

        /* --- STATIC SMART DOCK --- */
        .smart-dock {
            position: fixed; bottom: 30px; left: 50%;
            transform: translateX(-50%);
            width: 90%; max-width: 480px;
            background: rgba(10, 10, 12, 0.8);
            backdrop-filter: blur(20px);
            border: 1px solid var(--border);
            border-radius: 24px;
            padding: 12px 20px;
            display: flex; align-items: center; justify-content: space-between;
            z-index: 100;
        }

        .ticker-text {
            font-family: 'JetBrains Mono', monospace;
            font-size: 11px;
            color: var(--accent);
            letter-spacing: 0.5px;
        }

        /* --- UI SLIDER STYLING --- */
        input[type="range"] {
            -webkit-appearance: none;
            width: 100%; height: 4px;
            background: rgba(255,255,255,0.1);
            border-radius: 2px;
        }

        input[type="range"]::-webkit-slider-thumb {
            -webkit-appearance: none;
            height: 14px; width: 14px;
            border-radius: 50%;
            background: var(--accent);
            cursor: pointer;
            box-shadow: 0 0 10px var(--accent);
        }
    </style>
</head>
<body>

    <div class="cyber-orb"></div>

    <div class="glass-panel text-center">
        <div class="inline-block p-3 rounded-2xl bg-cyan-500/10 mb-6">
            <i class="fas fa-microchip text-2xl text-cyan-400"></i>
        </div>
        
        <h1 class="text-3xl font-black mb-2 tracking-tighter uppercase">Glass_OS</h1>
        <p class="text-gray-500 text-xs font-bold uppercase tracking-widest mb-8">System Interface v2.0</p>
        
        <div class="space-y-6 text-left">
            <div class="space-y-3">
                <div class="flex justify-between items-center">
                    <label class="text-[10px] uppercase font-black text-gray-400">Transparency</label>
                    <span class="text-[10px] font-mono text-cyan-500">85%</span>
                </div>
                <input type="range" value="85" class="w-full">
            </div>

            <div class="space-y-3">
                <div class="flex justify-between items-center">
                    <label class="text-[10px] uppercase font-black text-gray-400">Blur Intensity</label>
                    <span class="text-[10px] font-mono text-cyan-500">15px</span>
                </div>
                <input type="range" value="40" class="w-full">
            </div>
        </div>

        <button class="w-full mt-10 py-4 bg-cyan-500 text-black font-black rounded-2xl text-xs uppercase tracking-widest hover:bg-white hover:shadow-[0_0_30px_rgba(255,255,255,0.2)] transition-all duration-300">
            Initialize System
        </button>
    </div>

    <div class="smart-dock">
        <div class="flex items-center gap-4">
            <div class="w-8 h-8 rounded-lg bg-white/5 flex items-center justify-center text-cyan-400">
                <i class="fas fa-terminal text-xs"></i>
            </div>
            <span class="ticker-text">>> SYSTEM_READY: ACCESS_GRANTED</span>
        </div>

        <div class="flex gap-2">
            <button class="w-8 h-8 rounded-lg border border-white/10 flex items-center justify-center text-gray-400 hover:text-white hover:bg-white/5 transition">
                <i class="fas fa-cog"></i>
            </button>
            <button class="px-4 py-2 bg-white/5 border border-white/10 rounded-lg text-[10px] font-black uppercase tracking-tighter hover:bg-cyan-500 hover:text-black transition-colors">
                Terminal
            </button>
        </div>
    </div>

</body>
</html>
