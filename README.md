

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
