
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Debeatzgh App Experience</title>
    <style>
        :root {
            --primary-color: #ff6b6b;
            --secondary-color: #4ecdc4;
            --dark-color: #2f3640;
            --light-color: #f7f9fa;
            --premium-gold: #f1c40f;
        }

        body, html {
            margin: 0;
            padding: 0;
            width: 100%;
            height: 100%;
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
            background-color: var(--light-color);
            overflow: hidden;
        }

        /* 1. FULL PAGE OVERLAY SPLASH SCREEN */
        #splash-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #2f3640 0%, #111 100%);
            color: white;
            z-index: 9999;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            transition: opacity 0.5s ease, transform 0.5s ease;
        }

        #splash-overlay.hidden {
            opacity: 0;
            pointer-events: none;
            transform: scale(1.05);
        }

        .splash-content {
            max-width: 500px;
            padding: 20px;
        }

        .splash-logo {
            font-size: 3rem;
            font-weight: bold;
            margin-bottom: 10px;
            letter-spacing: 2px;
            background: linear-gradient(45deg, var(--primary-color), var(--premium-gold));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .splash-btn {
            background-color: var(--primary-color);
            color: white;
            border: none;
            padding: 15px 40px;
            font-size: 1.1rem;
            font-weight: bold;
            border-radius: 30px;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(255, 107, 107, 0.4);
            transition: transform 0.2s, background 0.2s;
            margin-top: 25px;
        }

        .splash-btn:hover {
            transform: translateY(-2px);
            background-color: #ff5252;
        }

        /* 2. TOP FLOATING INSTRUCTION BAR */
        #top-instruction-bar {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            background-color: var(--dark-color);
            color: #fff;
            text-align: center;
            padding: 12px 10px;
            font-size: 0.9rem;
            font-weight: 500;
            z-index: 999;
            box-shadow: 0 2px 10px rgba(0,0,0,0.2);
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 10px;
        }

        .badge {
            background-color: var(--secondary-color);
            color: var(--dark-color);
            padding: 2px 8px;
            border-radius: 4px;
            font-weight: bold;
            font-size: 0.75rem;
            text-transform: uppercase;
        }

        /* MAIN APP CONTAINER INTERFACE */
        #app-wrapper {
            margin-top: 45px; /* Offset for top bar */
            height: calc(100vh - 45px);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            box-sizing: border-box;
            padding: 20px;
        }

        .iframe-container {
            position: relative;
            box-shadow: 0 10px 30px rgba(0,0,0,0.15);
            border-radius: 16px;
            overflow: hidden;
            background: #fff;
            transition: transform 0.3s ease;
            transform-origin: center center;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        iframe {
            border: none;
            display: block;
        }

        /* 3. FLOATING BUTTON: DEBEATZGH SEARCH AD */
        #debeatzgh-ad-btn {
            position: fixed;
            bottom: 30px;
            right: 30px;
            background: linear-gradient(135deg, #6c5ce7, #a29bfe);
            color: white;
            border: none;
            padding: 14px 22px;
            border-radius: 50px;
            font-weight: bold;
            box-shadow: 0 5px 20px rgba(108, 92, 231, 0.4);
            cursor: pointer;
            z-index: 998;
            display: flex;
            align-items: center;
            gap: 8px;
            transition: all 0.3s ease;
            text-decoration: none;
        }

        #debeatzgh-ad-btn:hover {
            transform: scale(1.05) translateY(-3px);
            box-shadow: 0 8px 25px rgba(108, 92, 231, 0.6);
        }

        .pulse-ring {
            position: absolute;
            width: 100%;
            height: 100%;
            background: rgba(108, 92, 231, 0.4);
            border-radius: 50px;
            left: 0;
            top: 0;
            animation: pulse 2s infinite;
            z-index: -1;
        }

        @keyframes pulse {
            0% { transform: scale(0.95); opacity: 1; }
            100% { transform: scale(1.2); opacity: 0; }
        }

        /* 4. INTERFACE ZOOM CONTROLS */
        #zoom-controls {
            position: fixed;
            top: 30px;
            left: 30px;
            background: white;
            padding: 8px;
            border-radius: 30px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            display: flex;
            gap: 5px;
            z-index: 998;
        }

        .zoom-btn {
            background: #f1f2f6;
            border: none;
            width: 36px;
            height: 36px;
            border-radius: 50%;
            font-weight: bold;
            font-size: 1.1rem;
            cursor: pointer;
            color: var(--dark-color);
            transition: background 0.2s;
        }

        .zoom-btn:hover {
            background: #dfe4ea;
        }

        /* 5. PREMIUM FEATURES SIDEBAR PANEL */
        #premium-sidebar {
            position: fixed;
            right: -320px;
            top: 45px;
            width: 280px;
            height: calc(100vh - 45px);
            background: white;
            box-shadow: -5px 0 25px rgba(0,0,0,0.1);
            z-index: 997;
            padding: 20px;
            transition: right 0.3s ease;
            overflow-y: auto;
        }

        #premium-sidebar.open {
            right: 0;
        }

        #premium-toggle {
            position: fixed;
            right: 0;
            top: 50%;
            transform: translateY(-50%);
            background: var(--premium-gold);
            color: var(--dark-color);
            padding: 12px 8px;
            border-radius: 8px 0 0 8px;
            cursor: pointer;
            font-weight: bold;
            writing-mode: vertical-rl;
            text-transform: uppercase;
            letter-spacing: 1px;
            font-size: 0.75rem;
            z-index: 997;
            box-shadow: -2px 2px 10px rgba(0,0,0,0.1);
        }

        .premium-card {
            background: linear-gradient(135deg, #fff9db, #fff);
            border: 1px solid #ffe066;
            border-radius: 8px;
            padding: 15px;
            margin-bottom: 15px;
        }

        .premium-card h4 {
            margin: 0 0 8px 0;
            color: #f08c00;
        }

        .premium-card p {
            margin: 0;
            font-size: 0.85rem;
            color: #495057;
            line-height: 1.4;
        }
    </style>
</head>
<body>

    <!-- 1. FULL PAGE OVERLAY -->
    <div id="splash-overlay">
        <div class="splash-content">
            <div class="splash-logo">DE-I APP</div>
            <p style="color: #a4b0be; font-size: 1.1rem;">Welcome to the Next-Gen Portal experience built on GitHub Pages.</p>
            <button class="splash-btn" onclick="closeSplash()">Launch App Experience</button>
        </div>
    </div>

    <!-- 2. FLOATING TOP INSTRUCTION BAR -->
    <div id="top-instruction-bar">
        <span class="badge">New Update</span> 
        !
    </div>

    <!-- MAIN APP CONTAINER -->
    <div id="app-wrapper">
        <div class="iframe-container" id="iframe-holder">
            <!-- Provided Jotform App Embed -->
            <iframe 
                id="JotFormIFrame-232295354707561" 
                title="De-I" 
                allow="geolocation; microphone; camera; clipboard-write" 
                src="https://www.jotform.com/app/232295354707561?appEmbedded=1" 
                style="height:600px; width:375px;">
            </iframe>
        </div>
    </div>

    <!-- 3. FLOATING BUTTON: DEBEATZGH SEARCH -->
    <a href="https://www.google.com/search?q=Debeatzgh" target="_blank" id="debeatzgh-ad-btn">
        <div class="pulse-ring"></div>
        🔍 Discover Debeatzgh Search
    </a>

    <!-- 4. INTERFACE ZOOM CONTROLS -->
    <div id="zoom-controls">
        <button class="zoom-btn" onclick="adjustZoom(0.1)" title="Zoom In">+</button>
        <button class="zoom-btn" onclick="adjustZoom(-0.1)" title="Zoom Out">-</button>
        <button class="zoom-btn" onclick="resetZoom()" title="Reset Zoom">⟲</button>
    </div>

    <!-- 5. PREMIUM FEATURES SIDEBAR & IDEAS -->
    <div id="premium-toggle" onclick="togglePremiumSidebar()">⭐ Premium Options</div>
    <div id="premium-sidebar">
        <h3 style="margin-top:0; border-bottom: 2px solid var(--premium-gold); padding-bottom: 8px;">Premium Hub</h3>
        
        <div class="premium-card">
            <h4>✨ Dynamic Layout Resizer</h4>
            <p>Unlock landscape full-width viewing angles beyond standard mobile bounds for heavy desktop data management.</p>
        </div>

        <div class="premium-card">
            <h4>🚀 Ultra-Fast Fast-Pass Loading</h4>
            <p>Bypasses UI caching structures natively using dedicated global mirrors on Premium GitHub Actions builds.</p>
        </div>

        <div class="premium-card">
            <h4>🎨 Custom CSS Theme Injector</h4>
            <p>Premium allows overriding the default Jotform structure wrappers with customized brand colors and dark mode variants.</p>
        </div>

        <div class="premium-card">
            <h4>📊 Analytics Companion</h4>
            <p>Access background analytics mapping interaction performance data directly from your embedded forms layout.</p>
        </div>
    </div>

    <script>
        // Splash overlay close logic
        function closeSplash() {
            document.getElementById('splash-overlay').classList.add('hidden');
        }

        // Zoom state configuration
        let currentScale = 1.0;
        const iframeHolder = document.getElementById('iframe-holder');

        function adjustZoom(amount) {
            currentScale += amount;
            // Clamping the zoom levels safely between 0.5x and 2.0x
            currentScale = Math.min(Math.max(currentScale, 0.5), 2.0);
            applyZoom();
        }

        function resetZoom() {
            currentScale = 1.0;
            applyZoom();
        }

        function applyZoom() {
            iframeHolder.style.transform = `scale(${currentScale})`;
        }

        // Premium Sidebar Toggle Logic
        function togglePremiumSidebar() {
            document.getElementById('premium-sidebar').classList.toggle('open');
        }
    </script>
