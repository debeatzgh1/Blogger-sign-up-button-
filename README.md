


    <style>
        :root {
            --nav-bg: rgba(13, 17, 23, 0.9);
            --nav-border: #30363d;
            --nav-accent: #58a6ff;
            --nav-hover: #1f6feb;
            --glow-color: rgba(88, 166, 255, 0.5);
        }

        /* Dock Container */
        .nav-dock {
            position: fixed;
            right: 20px;
            top: 50%;
            transform: translateY(-50%);
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 15px;
            z-index: 10000;
        }

        /* Launcher (>) */
        #nav-launcher {
            width: 38px;
            height: 38px;
            background: var(--nav-bg);
            border: 1px solid var(--nav-border);
            color: var(--nav-accent);
            border-radius: 10px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.4rem;
            backdrop-filter: blur(8px);
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(0,0,0,0.4);
        }

        #nav-launcher.open {
            color: white;
            background: var(--nav-hover);
            border-color: var(--nav-accent);
        }

        /* Button Group */
        .nav-group {
            display: flex;
            flex-direction: column;
            gap: 10px;
            pointer-events: none;
        }

        .nav-group.active {
            pointer-events: auto;
        }

        .nav-btn {
            width: 34px;
            height: 34px;
            background: var(--nav-bg);
            border: 1px solid var(--nav-border);
            color: #c9d1d9;
            border-radius: 50%;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            transform: scale(0.5) translateX(30px);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            text-decoration: none;
            position: relative;
        }

        /* Active/Open State for Buttons */
        .nav-group.active .nav-btn {
            opacity: 1;
            transform: scale(1) translateX(0);
        }

        /* Heartbeat Glow Animation */
        @keyframes heartbeatGlow {
            0% { box-shadow: 0 0 0 0 var(--glow-color); transform: scale(1); }
            50% { box-shadow: 0 0 15px 5px var(--glow-color); transform: scale(1.1); }
            100% { box-shadow: 0 0 0 0 var(--glow-color); transform: scale(1); }
        }

        .heartbeat-active {
            animation: heartbeatGlow 1.2s ease-in-out 2; /* Runs twice on open */
        }

        .nav-btn:hover {
            background: var(--nav-hover);
            color: white;
            border-color: var(--nav-accent);
        }

        /* Staggered transition delays for a smooth "pop-in" effect */
        .nav-group.active .nav-btn:nth-child(1) { transition-delay: 0.1s; }
        .nav-group.active .nav-btn:nth-child(2) { transition-delay: 0.2s; }
        .nav-group.active .nav-btn:nth-child(3) { transition-delay: 0.3s; }

        .nav-btn svg { width: 18px; height: 18px; }
    </style>



    <div class="nav-dock">
        <button id="nav-launcher" onclick="toggleNav()">›</button>

        <div class="nav-group" id="navGroup">
            <button class="nav-btn" onclick="window.scrollTo({top: 0, behavior: 'smooth'})">
                <svg viewbox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><polyline points="18 15 12 9 6 15"></polyline></svg>
            </button>

            <a href="https://debeatzgh1.github.io/debeatzgh/" class="nav-btn">
                <svg viewbox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><path d="M3 9l9-7 9 7v11a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2z"></path><polyline points="9 22 9 12 15 12 15 22"></polyline></svg>
            </a>

            <button class="nav-btn" onclick="window.scrollTo({top: document.body.scrollHeight, behavior: 'smooth'})">
                <svg viewbox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><polyline points="6 9 12 15 18 9"></polyline></svg>
            </button>
        </div>
    </div>

    <script>
        function toggleNav() {
            const group = document.getElementById('navGroup');
            const launcher = document.getElementById('nav-launcher');
            const buttons = document.querySelectorAll('.nav-btn');
            
            const isOpen = group.classList.toggle('active');
            launcher.classList.toggle('open');
            launcher.innerText = isOpen ? '‹' : '›';

            if (isOpen) {
                // Trigger heartbeat animation on each button when opened
                buttons.forEach((btn, index) => {
                    // Slight delay before heartbeat starts to match the pop-in
                    setTimeout(() => {
                        btn.classList.add('heartbeat-active');
                    }, (index + 1) * 200);

                    // Remove class after animation ends so it can re-trigger next time
                    setTimeout(() => {
                        btn.classList.remove('heartbeat-active');
                    }, 3000);
                });
            }
        }
    </script>


</!doctype>


<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Debeatzgh Ecosystem Hub</title>
    <style>
        :root {
            --bg: #0d1117;
            --card: #161b22;
            --border: #30363d;
            --accent: #58a6ff;
            --success: #238636;
            --premium: #d29922;
            --danger: #f85149;
            --text: #c9d1d9;
            --shadow: rgba(0,0,0,0.5);
        }

        [data-theme="light"] {
            --bg: #f6f8fa;
            --card: #ffffff;
            --border: #d0d7de;
            --accent: #0969da;
            --success: #1a7f37;
            --premium: #9a6700;
            --danger: #cf222e;
            --text: #1f2328;
            --shadow: rgba(0,0,0,0.1);
        }

        * { box-sizing: border-box; transition: background 0.3s, color 0.3s, border-color 0.3s; }
        
        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
            background-color: var(--bg);
            color: var(--text);
            margin: 0;
            overflow: hidden;
        }

        /* --- AUTHENTICATION --- */
        #auth-gate, #welcome-modal {
            position: fixed;
            inset: 0;
            background: var(--bg);
            z-index: 9999;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 20px;
        }

        .auth-card {
            background: var(--card);
            border: 1px solid var(--border);
            padding: 40px;
            border-radius: 16px;
            text-align: center;
            max-width: 450px;
            box-shadow: 0 10px 50px var(--shadow);
        }

        .shake-box { animation: box-shake 8s infinite; }

        /* --- LOADER --- */
        #loader-overlay {
            position: absolute;
            inset: 0;
            background: var(--bg);
            opacity: 0.9;
            display: none;
            align-items: center;
            justify-content: center;
            z-index: 50;
            backdrop-filter: blur(4px);
        }

        .spinner {
            width: 45px;
            height: 45px;
            border: 4px solid var(--border);
            border-left-color: var(--accent);
            border-radius: 50%;
            animation: spin 0.8s linear infinite;
        }

        /* --- TOP BANNER --- */
        .banner-carousel {
            height: 50px;
            background: var(--card);
            border-bottom: 1px solid var(--border);
            display: flex;
            align-items: center;
            overflow: hidden;
        }

        .carousel-track {
            display: flex;
            white-space: nowrap;
            animation: scrollText 40s linear infinite;
        }

        .carousel-item {
            padding: 0 60px;
            color: var(--text);
            font-size: 0.85rem;
            text-decoration: none;
            font-weight: 500;
        }

        /* --- MAIN LAYOUT --- */
        .main-container {
            display: grid;
            grid-template-columns: 260px 1fr 300px;
            height: calc(100vh - 50px);
            opacity: 0.05;
            filter: blur(20px);
            transition: all 1.2s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .main-container.unlocked { opacity: 1; filter: blur(0); }

        .sidebar {
            background: var(--card);
            padding: 20px;
            display: flex;
            flex-direction: column;
            border-right: 1px solid var(--border);
        }

        .tab-btn {
            width: 100%;
            padding: 12px;
            margin-bottom: 10px;
            background: var(--bg);
            border: 1px solid var(--border);
            color: var(--text);
            border-radius: 8px;
            cursor: pointer;
            text-align: left;
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 0.9rem;
        }

        .tab-btn:hover { border-color: var(--accent); }
        .tab-btn.active { border-color: var(--accent); background: rgba(88,166,255,0.05); font-weight: bold; }

        /* --- STATUS & SUPPORT --- */
        .status-container {
            margin-top: auto;
            padding: 10px;
            background: rgba(0,0,0,0.1);
            border-radius: 10px;
            border: 1px solid var(--border);
        }

        .status-line {
            display: flex;
            align-items: center;
            gap: 8px;
            font-size: 0.75rem;
            margin-bottom: 10px;
            color: var(--text);
        }

        .status-dot {
            width: 8px;
            height: 8px;
            background: #3fb950;
            border-radius: 50%;
            box-shadow: 0 0 8px #3fb950;
            animation: status-pulse 2s infinite;
        }

        .support-btn {
            background: rgba(248, 81, 73, 0.1);
            border: 1px solid var(--danger);
            color: var(--danger);
            padding: 10px;
            border-radius: 6px;
            text-decoration: none;
            text-align: center;
            font-size: 0.8rem;
            font-weight: bold;
            display: block;
            transition: 0.3s;
        }

        .support-btn:hover { background: var(--danger); color: white; }

        /* --- THEME TOGGLE --- */
        .theme-switch {
            margin-top: 15px;
            padding-top: 10px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            font-size: 0.75rem;
        }

        .toggle-box {
            width: 36px; height: 18px;
            background: var(--border);
            border-radius: 20px;
            position: relative;
            cursor: pointer;
        }

        .toggle-circle {
            width: 14px; height: 14px;
            background: var(--accent);
            border-radius: 50%;
            position: absolute;
            top: 2px; left: 2px;
            transition: 0.3s;
        }

        [data-theme="light"] .toggle-circle { left: 20px; }

        /* --- VIEWER & FEED --- */
        .viewer-area { position: relative; background: #000; }
        iframe { width: 100%; height: 100%; border: none; background: #fff; }

        .sidebar-right { border-left: 1px solid var(--border); background: var(--card); overflow-y: auto; }
        .chat-msg {
            background: var(--bg);
            padding: 15px;
            border-radius: 12px;
            margin: 15px;
            font-size: 0.8rem;
            border: 1px solid var(--border);
            border-left: 4px solid var(--accent);
            animation: slideIn 0.5s ease;
        }

        /* --- ANIMATIONS --- */
        @keyframes spin { to { transform: rotate(360deg); } }
        @keyframes scrollText { from { transform: translateX(0); } to { transform: translateX(-50%); } }
        @keyframes box-shake { 0%, 90%, 100% { transform: rotate(0); } 92% { transform: rotate(1deg); } 95% { transform: rotate(-1deg); } }
        @keyframes status-pulse { 0% { opacity: 1; transform: scale(1); } 50% { opacity: 0.5; transform: scale(1.2); } 100% { opacity: 1; transform: scale(1); } }
        @keyframes slideIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }

        .btn-primary {
            background: var(--success);
            color: white;
            padding: 14px 25px;
            border: none;
            border-radius: 8px;
            font-weight: bold;
            cursor: pointer;
            width: 100%;
        }

        .tag { background: var(--premium); color: white; font-size: 0.6rem; padding: 1px 5px; border-radius: 3px; margin-left: auto; }
    </style>
</head>
<body data-theme="dark">

    <div id="auth-gate">
        <div class="auth-card shake-box">
            <h2 style="color:var(--text)">Secure Hub Access</h2>
            <p style="color:var(--text)">Authentication is required via the Collaborators Form.</p>
            <a href="https://docs.google.com/forms/d/e/1FAIpQLSdXCPUz1JBq0W8MHN9VOE0p6cnp5Wtr74Ox2gqLLyzKi0UwKA/viewform" target="_blank" style="text-decoration:none">
                <button class="btn-primary" onclick="showWelcome()">Authenticate / Sign Up</button>
            </a>
            <p style="margin-top:15px; font-size:0.8rem">Already verified? <span onclick="showWelcome()" style="color:var(--accent); cursor:pointer">Enter Workspace</span></p>
        </div>
    </div>

    <div id="welcome-modal" style="display:none">
        <div class="auth-card">
            <h2 style="color:var(--success)">Welcome Aboard! 🚀</h2>
            <p>Your session is ready. Launch the <strong>Integrated Productivity Suite</strong> below.</p>
            <button class="btn-primary" style="background:var(--accent)" onclick="initHub()">Launch Dashboard</button>
        </div>
    </div>

    <div class="banner-carousel">
        <div class="carousel-track">
            <a href="#" class="carousel-item">Access your lifestyle productivity tools and ideas All in one place.</a>
            <a href="#" class="carousel-item">Powered by Debeatzgh Ecosystem — Version 2.4 Live.</a>
            <a href="#" class="carousel-item">Access your lifestyle productivity tools and ideas All in one place.</a>
        </div>
    </div>

    <div class="main-container" id="mainHub">
        <div class="sidebar">
            <h4 style="margin:0 0 15px 0; color:var(--accent); font-size: 0.7rem; letter-spacing: 1.5px;">SYSTEM ASSETS</h4>
            
            <button class="tab-btn active" onclick="nav('https://debeatzgh1.github.io/1/', this)">
                <span>📂</span> Master Hub <span class="tag">ACTIVE</span>
            </button>
            <button class="tab-btn" onclick="nav('https://debeatzgh1.github.io/ai-chat/', this)">
                <span>🤖</span> AI Assistant
            </button>
            <button class="tab-btn" onclick="nav('https://debeatzgh1.github.io/The-Ultimate-Guide-to-Side-Hustle/', this)">
                <span>💰</span> Side Hustles
            </button>
            <button class="tab-btn" onclick="nav('https://debeatzgh1.github.io/posts/', this)">
                <span>📝</span> Global Feed
            </button>

            <div class="status-container">
                <div class="status-line">
                    <div class="status-dot"></div>
                    <span>System Online</span>
                </div>
                <a href="https://docs.google.com/forms/d/e/1FAIpQLSfBDlR6TcU9sWjbeVOp6dtb4GMKdL6SP_i0KB08IrtbLT9wwA/viewform?usp=header" target="_blank" class="support-btn">
                    Get Support
                </a>
            </div>
            
            <div class="theme-switch">
                <span>Interface Theme</span>
                <div class="toggle-box" onclick="theme()">
                    <div class="toggle-circle"></div>
                </div>
            </div>
        </div>

        <div class="viewer-area">
            <div id="loader-overlay"><div class="spinner"></div></div>
            <iframe id="viewport" src="https://debeatzgh1.github.io/1/"></iframe>
        </div>

        <div class="sidebar-right">
            <div id="msg-feed">
                <div class="chat-msg"><strong>System Log:</strong> Syncing ecosystem resources...</div>
            </div>
        </div>
    </div>

    <script>
        const vp = document.getElementById('viewport');
        const ld = document.getElementById('loader-overlay');

        function showWelcome() {
            document.getElementById('auth-gate').style.display = 'none';
            document.getElementById('welcome-modal').style.display = 'flex';
        }

        function initHub() {
            document.getElementById('welcome-modal').style.display = 'none';
            document.getElementById('mainHub').classList.add('unlocked');
            startFeed();
        }

        function nav(url, btn) {
            ld.style.display = 'flex';
            vp.src = url;
            document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
            btn.classList.add('active');
            vp.onload = () => { ld.style.display = 'none'; };
        }

        function theme() {
            const b = document.body;
            b.setAttribute('data-theme', b.getAttribute('data-theme') === 'light' ? 'dark' : 'light');
        }

        function startFeed() {
            const items = [
                { n: "Portfolio Suite", l: "https://debeatzgh1.github.io/Personal-Portfolio-site-/" },
                { n: "AI Starter Kit", l: "https://debeatzgh1.github.io/Decode-AI-starter-kit-/" },
                { n: "Business Kit", l: "https://debeatzgh1.github.io/Online-business-kit/" }
            ];
            let idx = 0;
            setInterval(() => {
                const f = document.getElementById('msg-feed');
                const m = document.createElement('div');
                m.className = 'chat-msg';
                m.innerHTML = `<strong>Hub Activity:</strong><br>${items[idx].n}<br><a href="${items[idx].l}" target="_blank" style="color:var(--accent); font-weight:bold; text-decoration:none;">Preview Tool &rarr;</a>`;
                f.prepend(m);
                idx = (idx + 1) % items.length;
            }, 7000);
        }
    </script>
</body>
</html>


# 📨 Blogger Floating Subscribe Popup (with Firebase or EmailJS)

This project provides a **floating subscribe button** for Blogger that triggers a **pop-up email signup form**. Designed to be fully compatible with Blogger and easily pasteable into any post or page in HTML view.

> 📌 Perfect for bloggers, creators, and marketers who want to grow their email list using a sleek, mobile-friendly form.

---

## ✨ Features

- 💬 Floating “Subscribe” button
- 💌 Pop-up email form with Name & Email fields
- ✅ Email auto-responder via [EmailJS](https://www.emailjs.com)
- ✅ Firebase-ready if needed
- 📱 Responsive design (mobile-friendly)
- 🧩 Fully works in Blogger (no external hosting required)

---

## 📦 Installation

### Option 1: Use in Blogger

1. Go to your Blogger dashboard.
2. Create a **new Page** or **Post**.
3. Click **HTML** view.
4. Paste the contents of `index.html`.
5. Replace the following placeholders:

```js
emailjs.init("YOUR_USER_ID");
emailjs.send("YOUR_SERVICE_ID", "YOUR_TEMPLATE_ID", { name, email });


# 🚀 DeBeatzGH – AI Tools & Side Hustle Hub  

![DeBeatzGH Thumbnail](https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/designamodernminimalisticdesignfeaturinganai-themedicon28likeabraincircuitorrobot29overlaidwithdebeatzghoraitoolshustles6089986211026037047.jpg)  

## 🌟 About  
Welcome to **[DeBeatzGH](https://debeatzgh.wordpress.com/)** — your go-to hub for **AI tools, side hustle strategies, blogging resources, and digital growth guides**.  

Our platform is built to help **students, creators, startups, and professionals** unlock the power of AI, monetize their skills, and thrive in today’s digital economy.  

### ✨ What You’ll Find  
- 💡 Explore **AI prompts, tools, and hacks**  
- 📈 Discover **side hustle strategies & online income ideas**  
- ✍️ Access **blogging & digital business guides**  
- 🚀 Stay ahead with **regular updates and fresh insights**  

---

## 👉 Get Started  
🔥 **Start your journey today → [Visit DeBeatzGH](https://debeatzgh.wordpress.com/)**  

---

