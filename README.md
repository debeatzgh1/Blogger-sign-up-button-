
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>G-Dev Portfolio | Hiring Portal</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Google+Sans:wght@400;500;700&display=swap');

        :root {
            --g-blue: #8ab4f8;
            --g-green: #34A853;
            --dark-bg: #1a1c1e;
            --dark-card: #2d2f31;
            --glass-border: rgba(255, 255, 255, 0.08);
        }

        body { font-family: 'Google Sans', sans-serif; background: #121212; margin: 0; }

        /* 1. LAUNCHER */
        #gdev-launcher {
            position: fixed; left: 20px; top: 50%; transform: translateY(-50%);
            display: flex; align-items: center; gap: 12px;
            background: var(--dark-card); padding: 8px 18px 8px 8px;
            border-radius: 40px; cursor: pointer; z-index: 9999;
            box-shadow: 0 10px 40px rgba(0,0,0,0.5);
            transition: 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            border: 1px solid var(--glass-border);
        }

        #gdev-launcher:hover { transform: translateY(-50%) scale(1.08) translateX(5px); border-color: var(--g-blue); }

        .dev-avatar {
            width: 42px; height: 42px; background: #121212; border-radius: 50%;
            display: flex; align-items: center; justify-content: center;
            border: 2px solid var(--g-blue); color: var(--g-blue); position: relative;
        }

        .status-dot {
            position: absolute; bottom: 2px; right: 2px; width: 10px; height: 10px;
            background: var(--g-green); border-radius: 50%; border: 2px solid var(--dark-card);
        }

        .status-glow {
            position: absolute; inset: 0; background: var(--g-green);
            border-radius: 50%; animation: status-pulse 2s infinite;
        }

        @keyframes status-pulse { 0% { transform: scale(1); opacity: 0.8; } 100% { transform: scale(2.5); opacity: 0; } }

        /* 2. OVERLAY MODAL */
        #gdev-overlay {
            position: fixed; inset: 0; background: rgba(0,0,0,0.85);
            backdrop-filter: blur(12px); display: none; z-index: 10000;
            justify-content: center; align-items: center; padding: 20px;
            opacity: 0; transition: opacity 0.4s ease;
        }

        #gdev-overlay.active { display: flex; opacity: 1; }

        .gdev-modal {
            width: 100%; max-width: 950px; height: 92vh;
            background: var(--dark-bg); border-radius: 28px;
            display: flex; flex-direction: column; overflow: hidden;
            border: 1px solid var(--glass-border); position: relative;
        }

        /* 3. IFRAME & FOOTER */
        #gdev-frame { flex-grow: 1; width: 100%; border: none; background: #fff; }

        .close-gdev {
            position: absolute; top: 20px; right: 25px; width: 40px; height: 30px;
            background: var(--dark-card); border-radius: 50%;
            display: flex; align-items: center; justify-content: center;
            cursor: pointer; color: #fff; z-index: 20;
        }

        /* CONTACT ME BUTTON STYLE */
        .hire-btn {
            background: var(--g-green);
            color: white;
            padding: 8px 18px;
            border-radius: 20px;
            font-size: 11px;
            font-weight: 800;
            text-transform: uppercase;
            letter-spacing: 1px;
            display: flex;
            align-items: center;
            gap: 8px;
            transition: 0.3s;
            box-shadow: 0 4px 15px rgba(52, 168, 83, 0.3);
        }
        .hire-btn:hover { transform: translateY(-2px); box-shadow: 0 6px 20px rgba(52, 168, 83, 0.4); background: #2e964a; }

        @media (max-width: 768px) {
            .gdev-modal { height: 100vh; border-radius: 0; }
            .footer-controls { flex-direction: column; gap: 10px; padding: 15px; }
        }
    </style>
</head>
<body>

    <div id="gdev-launcher" onclick="toggleGDev()">
        <div class="dev-avatar">
            <i class="fab fa-google"></i>
            <div class="status-dot"><div class="status-glow"></div></div>
        </div>
        <div class="hidden sm:block">
            <div class="flex items-center gap-2">
                <span class="text-[9px] text-[#34A853] font-bold uppercase tracking-widest">Active</span>
            </div>
            <p class="text-[14px] font-medium text-gray-200">@debeatzgh</p>
        </div>
    </div>

    <div id="gdev-overlay">
        <div class="gdev-modal">
            <div class="close-gdev" onclick="toggleGDev()"><i class="fas fa-times"></i></div>
            
            <iframe id="gdev-frame" src=""></iframe>

            <div class="footer-controls p-4 bg-[#1a1c1e] border-t border-white/5 flex justify-between items-center px-8">
                <span class="text-[9px] text-gray-600 font-bold uppercase tracking-[2px]">G-Dev Protocol v4.0</span>
                
                <div class="flex items-center gap-3">
                    <button id="copy-btn" class="text-[11px] text-[#8ab4f8] font-bold px-4 py-2 hover:text-white transition" onclick="copyProfileLink()">
                        Copy Profile
                    </button>
                    <a href="https://wa.me/233549757544?text=Hi%20DeBeatz,%20I%20saw%20your%20Google%20Dev%20profile%20and%20would%20like%20to%20discuss%20a%20project." 
                       target="_blank" class="hire-btn">
                        <i class="fas fa-briefcase"></i> Contact Me
                    </a>
                </div>
            </div>
        </div>
    </div>

    <script>
        const overlay = document.getElementById('gdev-overlay');
        const frame = document.getElementById('gdev-frame');
        const profileUrl = "https://share.google/ISgPfTLdVk98YZ6UM";

        function toggleGDev() {
            if (overlay.style.display === 'flex') {
                overlay.classList.remove('active');
                setTimeout(() => { overlay.style.display = 'none'; frame.src = ""; }, 400);
                document.body.style.overflow = 'auto';
            } else {
                overlay.style.display = 'flex';
                setTimeout(() => overlay.classList.add('active'), 10);
                frame.src = profileUrl;
                document.body.style.overflow = 'hidden';
            }
        }

        async function copyProfileLink() {
            await navigator.clipboard.writeText(profileUrl);
            const btn = document.getElementById('copy-btn');
            btn.innerText = "Copied!";
            setTimeout(() => { btn.innerText = "Copy Profile"; }, 2000);
        }

        overlay.onclick = (e) => { if (e.target === overlay) toggleGDev(); };
    </script>
</body>
</html>




<div id="firebase-mini-banner" class="firebase-node-mini">
    <div class="mini-content">
        <div class="status-indicator">
            <span class="pulse-dot"></span>
        </div>
        <div class="mini-text">
            <span class="label">Internal Build</span>
            <span class="version">v2.4-stable</span>
        </div>
    </div>
    <button onclick="openFirebaseNode()" class="mini-action-btn">
        <i class="fas fa-download"></i>
    </button>
</div>

<style>
    .firebase-node-mini {
        position: fixed;
        bottom: 25px;
        left: 25px; /* Positioned left to avoid clashing with the 'Suggest' button */
        width: 180px;
        height: 42px;
        background: rgba(10, 10, 12, 0.85);
        backdrop-filter: blur(12px);
        -webkit-backdrop-filter: blur(12px);
        border: 1px solid rgba(0, 242, 255, 0.2);
        border-radius: 10px;
        display: flex;
        align-items: center;
        justify-content: space-between;
        padding: 0 6px 0 12px;
        z-index: 9999;
        box-shadow: 0 8px 24px rgba(0, 0, 0, 0.5);
        transition: all 0.3s ease;
    }

    .firebase-node-mini:hover {
        border-color: #00f2ff;
        transform: translateY(-3px);
    }

    .mini-content {
        display: flex;
        align-items: center;
        gap: 10px;
    }

    .status-indicator {
        position: relative;
        display: flex;
        align-items: center;
    }

    .pulse-dot {
        width: 6px;
        height: 6px;
        background: #00f2ff;
        border-radius: 50%;
        box-shadow: 0 0 8px #00f2ff;
        animation: miniPulse 2s infinite;
    }

    @keyframes miniPulse {
        0% { transform: scale(1); opacity: 1; }
        50% { transform: scale(1.5); opacity: 0.5; }
        100% { transform: scale(1); opacity: 1; }
    }

    .mini-text {
        display: flex;
        flex-direction: column;
    }

    .mini-text .label {
        font-size: 8px;
        font-weight: 900;
        text-transform: uppercase;
        color: #475569;
        letter-spacing: 1px;
    }

    .mini-text .version {
        font-size: 10px;
        font-family: monospace;
        color: #f1f5f9;
        font-weight: bold;
    }

    .mini-action-btn {
        background: #00f2ff;
        color: #000;
        border: none;
        width: 30px;
        height: 30px;
        border-radius: 8px;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 12px;
        cursor: pointer;
        transition: 0.2s;
    }

    .mini-action-btn:hover {
        background: #fff;
        transform: scale(1.1);
    }

    /* Integration with your Master Overlay System */
</style>

<script>
    function openFirebaseNode() {
        // Using the same openLink/openFrame logic we built for your Hub
        if (typeof openLink === "function") {
            openLink('https://appdistribution.firebase.dev/i/dc2da2d4d3766b8a');
        } else if (typeof openFrame === "function") {
            openFrame('https://appdistribution.firebase.dev/i/dc2da2d4d3766b8a');
        } else {
            // Fallback for standalone use
            window.open('https://appdistribution.firebase.dev/i/dc2da2d4d3766b8a', '_blank');
        }
    }
</script>





<section class="mt-20 reveal">
    <div class="mb-10 p-[1px] rounded-2xl bg-gradient-to-r from-blue-600 via-cyan-400 to-blue-600 animate-gradient-x">
        <div class="bg-black/90 backdrop-filter blur-md rounded-[15px] p-6 flex flex-col md:flex-row items-center justify-between gap-6">
            <div class="flex items-center gap-5">
                <div class="w-12 h-12 rounded-full bg-cyan-500/10 flex items-center justify-center text-cyan-400 shadow-[0_0_20px_rgba(6,182,212,0.3)]">
                    <i class="fas fa-globe text-xl"></i>
                </div>
                <div>
                    <h3 class="font-black text-lg tracking-tight">Claim Your Digital Identity</h3>
                    <p class="text-gray-400 text-xs uppercase tracking-widest font-bold">Create <span class="text-white">name.debeatzgh.wordpress.com</span> for FREE</p>
                </div>
            </div>
            <a href="https://debeatzgh.wordpress.com/wp-login.php?action=register" class="bg-white text-black px-8 py-3 rounded-xl font-black text-xs uppercase hover:bg-cyan-400 transition-all duration-300">Register Now</a>
        </div>
    </div>

    <div class="max-w-md mx-auto">
        <div class="glass-card p-8 border-white/10 relative overflow-hidden">
            <div class="absolute -top-10 -right-10 w-32 h-32 bg-blue-500/10 blur-[50px] rounded-full"></div>
            
            <div class="text-center mb-8">
                <div class="inline-flex items-center justify-center w-14 h-14 rounded-2xl bg-white/5 border border-white/10 mb-4">
                    <img src="https://www.gstatic.com/mobilesdk/160503_mobilesdk/logo/2x/firebase_28dp.png" class="w-8 h-8 object-contain" alt="Firebase">
                </div>
                <h2 class="text-2xl font-black tracking-tighter">APP ACCESS</h2>
                <p class="text-gray-500 text-[10px] uppercase tracking-[0.2em] font-bold">Firebase Distribution Node</p>
            </div>

            <form class="space-y-4">
                <div class="space-y-1">
                    <label class="text-[10px] font-bold text-gray-500 uppercase ml-2">Secure Email</label>
                    <input type="email" placeholder="dev@debeatzgh.com" class="w-full bg-black/50 border border-white/10 rounded-xl px-4 py-3 text-sm focus:border-cyan-400 focus:outline-none transition-all">
                </div>
                <div class="space-y-1">
                    <label class="text-[10px] font-bold text-gray-500 uppercase ml-2">Access Key</label>
                    <input type="password" placeholder="••••••••" class="w-full bg-black/50 border border-white/10 rounded-xl px-4 py-3 text-sm focus:border-cyan-400 focus:outline-none transition-all">
                </div>

                <div class="pt-4 space-y-3">
                    <button type="button" onclick="window.location.href='https://appdistribution.firebase.dev/i/dc2da2d4d3766b8a'" class="w-full bg-cyan-500 text-black py-4 rounded-xl font-black text-xs uppercase tracking-widest hover:shadow-[0_0_25px_rgba(6,182,212,0.4)] transition-all">
                        Initialize Session
                    </button>
                    
                    <div class="flex items-center justify-between px-2">
                        <button type="button" class="text-[10px] font-bold text-gray-500 hover:text-white uppercase transition">Forgot Key?</button>
                        <button type="button" class="text-[10px] font-black text-cyan-500 hover:text-white uppercase transition">Request Invite</button>
                    </div>
                </div>
            </form>

            <div class="flex items-center gap-4 my-6">
                <div class="h-[1px] flex-grow bg-white/5"></div>
                <span class="text-[9px] font-bold text-gray-600 uppercase">External Auth</span>
                <div class="h-[1px] flex-grow bg-white/5"></div>
            </div>

            <div class="grid grid-cols-2 gap-3">
                <button class="flex items-center justify-center gap-2 bg-white/5 border border-white/10 py-3 rounded-xl hover:bg-white/10 transition">
                    <i class="fab fa-google text-xs"></i>
                    <span class="text-[10px] font-bold">Google</span>
                </button>
                <button class="flex items-center justify-center gap-2 bg-white/5 border border-white/10 py-3 rounded-xl hover:bg-white/10 transition">
                    <i class="fab fa-github text-xs"></i>
                    <span class="text-[10px] font-bold">GitHub</span>
                </button>
            </div>
        </div>
    </div>
</section>

<style>
    @keyframes gradient-x {
        0%, 100% { background-position: 0% 50%; }
        50% { background-position: 100% 50%; }
    }
    .animate-gradient-x {
        background-size: 200% 200%;
        animation: gradient-x 5s ease infinite;
    }
</style><div class="space-y-6 reveal" style="transition-delay: 400ms;">
    <div class="flex items-center justify-between px-2">
        <h4 class="text-xs font-black uppercase tracking-widest text-gray-500">Live_Network_Feed</h4>
        <div class="flex items-center gap-2">
            <span class="relative flex h-2 w-2">
                <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-cyan-400 opacity-75"></span>
                <span class="relative inline-flex rounded-full h-2 w-2 bg-cyan-500"></span>
            </span>
            <span class="text-[9px] font-mono text-cyan-500 animate-pulse">LIVE</span>
        </div>
    </div>

    <div id="activity-stream" class="space-y-4 max-h-[300px] overflow-hidden relative">
        <div class="absolute bottom-0 left-0 right-0 h-20 bg-gradient-to-t from-[#0a0a0c] to-transparent z-10 pointer-events-none"></div>
        
        <div id="activity-items" class="space-y-3 transition-all duration-500">
            <div class="flex gap-3 p-3 rounded-xl bg-white/5 border border-white/5 opacity-80 scale-95 transition-all">
                <div class="w-8 h-8 rounded-lg bg-blue-500/10 flex items-center justify-center text-blue-400">
                    <i class="fas fa-plus-circle text-[10px]"></i>
                </div>
                <div>
                    <p class="text-[10px] text-white font-bold leading-none">kofi.debeatzgh...</p>
                    <p class="text-[8px] text-gray-500 uppercase mt-1">Domain Claimed 2m ago</p>
                </div>
            </div>

            <div class="flex gap-3 p-3 rounded-xl bg-white/5 border border-white/5 opacity-60 scale-90 transition-all">
                <div class="w-8 h-8 rounded-lg bg-orange-500/10 flex items-center justify-center text-orange-400">
                    <i class="fas fa-download text-[10px]"></i>
                </div>
                <div>
                    <p class="text-[10px] text-white font-bold leading-none">User_8291</p>
                    <p class="text-[8px] text-gray-500 uppercase mt-1">Accessing Build v2.4</p>
                </div>
            </div>
        </div>
    </div>
</div>

<script>
    // NETWORK ACTIVITY SIMULATOR
    const activityContainer = document.getElementById('activity-items');
    const activities = [
        { user: "ama.debeatzgh...", action: "Domain Registered", icon: "fa-plus-circle", color: "text-blue-400", bg: "bg-blue-500/10" },
        { user: "dev_zero", action: "Build v2.4 Sync", icon: "fa-sync", color: "text-cyan-400", bg: "bg-cyan-500/10" },
        { user: "kwame_tech", action: "Claimed 500 XP", icon: "fa-bolt", color: "text-yellow-400", bg: "bg-yellow-500/10" },
        { user: "josh.debeatzgh...", action: "Portfilio Live", icon: "fa-globe", color: "text-green-400", bg: "bg-green-500/10" },
        { user: "beta_tester_9", action: "App Distributed", icon: "fa-download", color: "text-orange-400", bg: "bg-orange-500/10" }
    ];

    function addActivity() {
        const item = activities[Math.floor(Math.random() * activities.length)];
        const html = `
            <div class="flex gap-3 p-3 rounded-xl bg-white/5 border border-cyan-500/10 animate-fade-in-down">
                <div class="w-8 h-8 rounded-lg ${item.bg} flex items-center justify-center ${item.color}">
                    <i class="fas ${item.icon} text-[10px]"></i>
                </div>
                <div>
                    <p class="text-[10px] text-white font-bold leading-none">${item.user}</p>
                    <p class="text-[8px] text-gray-500 uppercase mt-1">${item.action} • Just now</p>
                </div>
            </div>
        `;

        activityContainer.insertAdjacentHTML('afterbegin', html);

        // Remove oldest if more than 5 items
        if (activityContainer.children.length > 5) {
            activityContainer.lastElementChild.classList.add('opacity-0');
            setTimeout(() => {
                activityContainer.removeChild(activityContainer.lastElementChild);
            }, 500);
        }
    }

    // New activity every 4-8 seconds
    setInterval(addActivity, Math.random() * 4000 + 4000);

    // Initial first burst
    setTimeout(addActivity, 1500);
</script>

<style>
    @keyframes fade-in-down {
        0% { opacity: 0; transform: translateY(-10px) scale(0.95); }
        100% { opacity: 1; transform: translateY(0) scale(1); }
    }
    .animate-fade-in-down {
        animation: fade-in-down 0.5s ease-out forwards;
    }
</style>
