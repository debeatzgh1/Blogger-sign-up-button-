<div class="space-y-6 reveal" style="transition-delay: 400ms;">
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
