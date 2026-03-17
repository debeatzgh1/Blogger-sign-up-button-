
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DeBeatzGH | Firebase Auth</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;600;800&display=swap');

        :root {
            --accent: #00f2ff;
            --bg-glass: rgba(15, 15, 20, 0.9);
            --border: rgba(0, 242, 255, 0.2);
        }

        body { font-family: 'Plus Jakarta Sans', sans-serif; background: #050507; }

        /* --- 1. THE FLOATING TRIGGER --- */
        #auth-trigger {
            position: fixed;
            bottom: 30px;
            right: 30px;
            width: 60px;
            height: 60px;
            background: var(--accent);
            border-radius: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            z-index: 10000;
            box-shadow: 0 10px 30px rgba(0, 242, 255, 0.4);
            transition: 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        #auth-trigger:hover { transform: scale(1.1) rotate(10deg); background: #fff; }

        /* --- 2. AUTH MODAL --- */
        #auth-modal {
            position: fixed;
            inset: 0;
            background: rgba(0,0,0,0.85);
            backdrop-filter: blur(10px);
            display: none;
            align-items: center;
            justify-content: center;
            z-index: 10001;
            padding: 20px;
        }

        .auth-card {
            width: 100%;
            max-width: 400px;
            background: var(--bg-glass);
            border: 1px solid var(--border);
            border-radius: 32px;
            padding: 40px;
            position: relative;
            box-shadow: 0 25px 50px rgba(0,0,0,1);
            animation: slideUp 0.4s ease-out;
        }

        @keyframes slideUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* --- UI COMPONENTS --- */
        .input-group {
            background: rgba(255,255,255,0.03);
            border: 1px solid rgba(255,255,255,0.08);
            border-radius: 16px;
            padding: 12px 16px;
            margin-bottom: 15px;
            transition: 0.3s;
        }

        .input-group:focus-within { border-color: var(--accent); background: rgba(0,242,255,0.03); }

        .input-group input {
            background: transparent;
            border: none;
            color: white;
            width: 100%;
            outline: none;
            font-size: 14px;
        }

        .tab-btn {
            font-size: 12px;
            font-weight: 800;
            text-transform: uppercase;
            letter-spacing: 1px;
            padding-bottom: 8px;
            cursor: pointer;
            color: #64748b;
        }

        .tab-btn.active { color: var(--accent); border-bottom: 2px solid var(--accent); }
    </style>
</head>
<body>

    <div id="auth-trigger" onclick="toggleAuthModal()">
        <i class="fas fa-user-shield text-black text-xl"></i>
    </div>

    <div id="auth-modal">
        <div class="auth-card">
            <button onclick="toggleAuthModal()" class="absolute top-6 right-6 text-gray-500 hover:text-white">
                <i class="fas fa-times"></i>
            </button>

            <div class="flex gap-6 mb-8">
                <span id="tab-login" class="tab-btn active" onclick="switchTab('login')">Login</span>
                <span id="tab-signup" class="tab-btn" onclick="switchTab('signup')">Sign Up</span>
            </div>

            <h2 id="auth-title" class="text-2xl font-black mb-6">Welcome Back.</h2>

            <form id="auth-form" onsubmit="handleAuth(event)">
                <div class="input-group">
                    <label class="text-[9px] uppercase font-bold text-gray-500 block mb-1">Email Address</label>
                    <input type="email" placeholder="name@domain.com" required>
                </div>

                <div class="input-group">
                    <label class="text-[9px] uppercase font-bold text-gray-500 block mb-1">Password</label>
                    <input type="password" placeholder="••••••••" required>
                </div>

                <button type="submit" class="w-full bg-cyan-500 text-black font-black py-4 rounded-2xl mt-4 hover:bg-white transition-all shadow-lg shadow-cyan-500/20">
                    CONTINUE
                </button>
            </form>

            <div class="mt-8 pt-8 border-t border-white/5">
                <button onclick="window.open('https://appdistribution.firebase.dev/i/dc2da2d4d3766b8a', '_blank')" 
                    class="w-full border border-white/10 text-[10px] font-bold py-3 rounded-xl flex items-center justify-center gap-2 hover:bg-white/5 transition">
                    <i class="fab fa-google"></i> FIREBASE APP DISTRIBUTION
                </button>
            </div>
        </div>
    </div>

    <script>
        let currentMode = 'login';

        function toggleAuthModal() {
            const modal = document.getElementById('auth-modal');
            const isVisible = modal.style.display === 'flex';
            modal.style.display = isVisible ? 'none' : 'flex';
        }

        function switchTab(mode) {
            currentMode = mode;
            const title = document.getElementById('auth-title');
            const tabLogin = document.getElementById('tab-login');
            const tabSignup = document.getElementById('tab-signup');

            if (mode === 'login') {
                title.innerText = "Welcome Back.";
                tabLogin.classList.add('active');
                tabSignup.classList.remove('active');
            } else {
                title.innerText = "Create Account.";
                tabSignup.classList.add('active');
                tabLogin.classList.remove('active');
            }
        }

        function handleAuth(e) {
            e.preventDefault();
            // This is where you connect your Firebase SDK logic
            alert(`${currentMode === 'login' ? 'Logging in' : 'Signing up'}... Check Firebase console.`);
        }

        // Close on ESC key
        document.addEventListener('keydown', (e) => {
            if (e.key === "Escape") toggleAuthModal();
        });
    </script>
</body>
</html>
