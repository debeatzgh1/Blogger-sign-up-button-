


Creators Hub– AI Tools, Side Hustles & Digital Growth

<!-- Fonts -->
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@500;600;700&amp;family=Inter:wght@400;500;600&amp;display=swap" rel="stylesheet" />

<!-- Tailwind -->
<script src="https://cdn.tailwindcss.com"></script>

<script>
tailwind.config = {
  theme: {
    extend: {
      colors: {
        primary: '#0F2A44',
        secondary: '#1E88E5',
        accent: '#00C2A8',
        highlight: '#6C63FF',
        bg: '#F8FAFC'
      },
      fontFamily: {
        heading: ['Poppins','sans-serif'],
        body: ['Inter','sans-serif']
      }
    }
  }
}
</script>

<style>
@keyframes pulseSoft {
  0%,100% { transform: scale(1); }
  50% { transform: scale(1.08); }
}
.floating-btn { animation: pulseSoft 1.8s infinite; }
</style>




<!-- NAVBAR -->
<header class="sticky top-0 z-40 bg-white shadow-sm">
  <div class="max-w-7xl mx-auto px-4 py-4 flex justify-between items-center">
    <button onclick="openFrame('https://form.jotform.com/241325342765051')" class="text-2xl font-heading font-bold text-primary">
      Debeatzgh
    </button>
    <nav class="hidden md:flex gap-8 font-medium">
      <button onclick="openFrame('https://form.jotform.com/241325342765051')" class="hover:text-secondary">Home</button>
      <button onclick="openFrame('https://form.jotform.com/241335470278053')" class="hover:text-secondary">Products</button>
      <button onclick="openFrame('https://debeatzgh1.github.io/blogs/')" class="hover:text-secondary">Blogs</button>
      <button onclick="openFrame('https://msha.ke/debeatzgh')" class="hover:text-secondary">Milkshake</button>
    </nav>
    <button onclick="openFrame('https://msha.ke/debeatzgh')" class="bg-secondary text-white px-5 py-2 rounded-xl shadow hover:scale-105 transition">
      Open Hub
    </button>
  </div>
</header>

<!-- HERO -->
<section class="max-w-7xl mx-auto px-4 py-20 grid md:grid-cols-2 gap-12 items-center">
  <div>
    <h2 class="text-4xl md:text-5xl font-heading font-bold text-primary">
      Build Income with <span class="text-secondary">AI Tools</span> & Smart Side Hustles
    </h2>
    <p class="mt-6 text-lg text-gray-600">
      AI tools, blogging guides, and digital products — all curated to help you earn online.
    </p>
    <div class="mt-8 flex gap-4">
      <button onclick="openFrame('https://debeatzgh1.github.io/-My-Brand-Online-Digital-Products-Affiliate-Shop/')" class="bg-secondary text-white px-6 py-3 rounded-xl shadow hover:scale-105 transition">
        View Products
      </button>
      <button onclick="openFrame('https://debeatzgh1.github.io/blogs/')" class="border border-secondary text-secondary px-6 py-3 rounded-xl hover:bg-secondary hover:text-white transition">
        Read Blogs 
      </button>
    </div>
  </div>

  <div class="bg-white rounded-xl shadow-lg p-6">
    <img src="https://images.unsplash.com/photo-1674027444485-cec3da58eef4" class="rounded-xl" />
  </div>
</section>

<!-- FEATURES -->
<section class="bg-white py-16">
  <div class="max-w-7xl mx-auto px-4">
    <h3 class="text-3xl font-heading font-semibold text-center text-primary">
      What You’ll Find
    </h3>

    <div class="grid md:grid-cols-3 gap-8 mt-12">
      <button onclick="openFrame('https://debeatzgh.wordpress.com/')" class="p-6 rounded-xl shadow hover:shadow-lg transition text-left">
        <span class="bg-accent text-white px-3 py-1 rounded-full text-sm">HUB</span>
        <h4 class="mt-4 font-heading text-xl font-semibold">Central Link Hub</h4>
        <p class="mt-2 text-gray-600">Access all Debeatzgh tools, products & platforms.</p>
      </button>

      <button onclick="openFrame('https://form.jotform.com/241335470278053')" class="p-6 rounded-xl shadow hover:shadow-lg transition text-left">
        <span class="bg-highlight text-white px-3 py-1 rounded-full text-sm">TOOLS</span>
        <h4 class="mt-4 font-heading text-xl font-semibold">Digital Tools</h4>
        <p class="mt-2 text-gray-600">AI prompts, resources & affiliate tools.</p>
      </button>

      <button onclick="openFrame('https://tally.so/r/3jkE29')" class="p-6 rounded-xl shadow hover:shadow-lg transition text-left">
        <span class="bg-secondary text-white px-3 py-1 rounded-full text-sm">GUIDE</span>
        <h4 class="mt-4 font-heading text-xl font-semibold">Side Hustle Playbook</h4>
        <p class="mt-2 text-gray-600">Proven ways to start earning online.</p>
      </button>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer class="bg-primary text-gray-300 py-10 text-center">
  <h4 class="font-heading text-xl text-white">Debeatzgh</h4>
  <p class="mt-2 text-sm">AI • Blogging • Side Hustles • Digital Growth</p>
  <p class="mt-4 text-xs opacity-70">© 2025 Debeatzgh</p>
</footer>

<!-- FLOATING BUTTON -->
<button onclick="openFrame('https://a4b45e9212e142d58780cdadee65af5b.elf.site')" class="fixed bottom-6 right-6 bg-accent text-white w-14 h-14 rounded-full shadow-lg floating-btn text-2xl">
  ☰
</button>

<!-- IFRAME OVERLAY -->
<div id="iframeOverlay" class="fixed inset-0 bg-black/70 hidden z-50">
  <div class="absolute inset-4 bg-white rounded-xl overflow-hidden flex flex-col">
    
    <!-- CONTROLS -->
    <div class="flex items-center justify-between bg-primary text-white px-4 py-2">
      <div class="flex gap-4 text-lg">
        <button onclick="frameBack()">⟵</button>
        <button onclick="frameForward()">⟶</button>
      </div>
      <div class="flex gap-4 text-lg">
        <button onclick="toggleFullscreen()">⛶</button>
        <button onclick="closeFrame()">✕</button>
      </div>
    </div>

    <!-- IFRAME -->
    <iframe id="contentFrame" class="flex-1 w-full border-none"></iframe>
  </div>
</div>

<script>
const frame = document.getElementById('contentFrame');
const overlay = document.getElementById('iframeOverlay');

function openFrame(url){
  frame.src = url;
  overlay.classList.remove('hidden');
}

function closeFrame(){
  frame.src = '';
  overlay.classList.add('hidden');
}

function frameBack(){
  frame.contentWindow.history.back();
}

function frameForward(){
  frame.contentWindow.history.forward();
}

function toggleFullscreen(){
  const box = overlay.querySelector('div');
  if(!document.fullscreenElement){
    box.requestFullscreen();
  } else {
    document.exitFullscreen();
  }
}
</script>






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
   <style>
    /* --- PROFILE CARD STYLING --- */
    #user-profile-card {
        position: fixed;
        bottom: 100px;
        right: 30px;
        width: 280px;
        background: rgba(10, 10, 15, 0.95);
        backdrop-filter: blur(20px);
        border: 1px solid rgba(0, 242, 255, 0.2);
        border-radius: 24px;
        padding: 24px;
        display: none; /* Controlled by Auth State */
        flex-direction: column;
        z-index: 10002;
        box-shadow: 0 20px 50px rgba(0,0,0,0.8);
        animation: popIn 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
    }

    @keyframes popIn {
        from { opacity: 0; transform: scale(0.9) translateY(20px); }
        to { opacity: 1; transform: scale(1) translateY(0); }
    }

    .profile-avatar {
        width: 50px; height: 50px;
        background: linear-gradient(135deg, #00f2ff, #0066ff);
        border-radius: 15px;
        display: flex; align-items: center; justify-content: center;
        font-weight: 900; color: #000; font-size: 20px;
        margin-bottom: 15px;
    }

    .status-badge {
        font-size: 8px; font-weight: 900; text-transform: uppercase;
        padding: 2px 8px; border-radius: 99px;
        background: rgba(34, 197, 94, 0.2); color: #22c55e;
        border: 1px solid rgba(34, 197, 94, 0.3);
    }

    .profile-link {
        display: flex; align-items: center; gap: 10px;
        padding: 12px; border-radius: 12px;
        color: #94a3b8; font-size: 11px; font-weight: 600;
        transition: 0.3s; margin-top: 5px;
    }
    .profile-link:hover { background: rgba(255,255,255,0.05); color: #fff; }
</style>

<div id="user-profile-card">
    <div class="flex justify-between items-start">
        <div class="profile-avatar" id="user-initial">U</div>
        <span class="status-badge">Secure Session</span>
    </div>
    
    <div class="mt-2">
        <h4 class="text-white font-black text-sm tracking-tight" id="display-email">user@dkonsult.com</h4>
        <p class="text-gray-500 text-[9px] uppercase font-bold mt-1">Dkonsult Verified Member</p>
    </div>

    <div class="mt-6 space-y-1">
        <a href="https://appdistribution.firebase.dev/i/dc2da2d4d3766b8a" target="_blank" class="profile-link">
            <i class="fas fa-layer-group text-cyan-400"></i> My App Builds
        </a>
        <a href="https://debeatzgh.wordpress.com/" class="profile-link">
            <i class="fas fa-external-link-alt text-gray-500"></i> Main Hub
        </a>
    </div>

    <button onclick="handleLogout()" class="w-full mt-6 py-3 bg-red-500/10 hover:bg-red-500 text-red-500 hover:text-white rounded-xl text-[10px] font-black uppercase tracking-widest transition-all">
        Terminate Session
    </button>
</div>

<script type="module">
    import { getAuth, signOut, onAuthStateChanged } from "https://www.gstatic.com/firebasejs/10.8.0/firebase-auth.js";

    const auth = getAuth();
    const profileCard = document.getElementById('user-profile-card');
    const trigger = document.getElementById('auth-trigger');

    // Toggle logic for the floating button
    window.toggleAuthModal = () => {
        const user = auth.currentUser;
        if (user) {
            // If logged in, toggle the Profile Card instead of Login Modal
            profileCard.style.display = (profileCard.style.display === 'flex') ? 'none' : 'flex';
        } else {
            // If logged out, open the existing Login Modal
            document.getElementById('auth-modal').style.display = 'flex';
        }
    };

    // Logout logic
    window.handleLogout = () => {
        signOut(auth).then(() => {
            profileCard.style.display = 'none';
            alert("Session Ended.");
        });
    };

    // UI Observer update
    onAuthStateChanged(auth, (user) => {
        if (user) {
            document.getElementById('display-email').innerText = user.email;
            document.getElementById('user-initial').innerText = user.email.charAt(0).toUpperCase();
            trigger.style.background = "#22c55e"; 
            trigger.innerHTML = '<i class="fas fa-check text-white"></i>';
        } else {
            profileCard.style.display = 'none';
            trigger.style.background = "#00f2ff";
            trigger.innerHTML = '<i class="fas fa-user-shield text-black"></i>';
        }
    });
</script>
