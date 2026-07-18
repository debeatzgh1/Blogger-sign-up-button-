
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DeBeatzGH - Dynamic Workspace Hub</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Lucide Icons for modern, clean visual cues -->
    <script src="https://unpkg.com/lucide@latest"></script>
    <style>
        /* Glassmorphism utility variables and custom animations */
        .glass-panel {
            background: rgba(255, 255, 255, 0.45);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border: 1px solid rgba(255, 255, 255, 0.25);
        }
        .dark-glass {
            background: rgba(15, 23, 42, 0.3);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.05);
        }
        @keyframes pulse-ring {
            0% { transform: scale(0.95); opacity: 1; }
            50% { transform: scale(1.1); opacity: 0.5; }
            100% { transform: scale(1.3); opacity: 0; }
        }
        .animate-pulse-ring::before {
            content: '';
            position: absolute;
            inset: 0;
            border-radius: 9999px;
            background-color: inherit;
            animation: pulse-ring 2s cubic-bezier(0.4, 0, 0.6, 1) infinite;
            z-index: -1;
        }
        /* Custom scrollbar handling for a clean look */
        ::-webkit-scrollbar { width: 5px; height: 5px; }
        ::-webkit-scrollbar-track { background: transparent; }
        ::-webkit-scrollbar-thumb { background: rgba(156, 163, 175, 0.5); border-radius: 10px; }
    </style>
</head>
<body class="bg-slate-900 text-slate-100 font-sans h-screen overflow-hidden flex flex-col md:flex-row relative">

    <!-- BACKGROUND EFFECTS -->
    <div class="absolute inset-0 bg-[radial-gradient(circle_at_top_right,rgba(99,102,241,0.15),transparent_45%)] pointer-events-none"></div>
    <div class="absolute inset-0 bg-[radial-gradient(circle_at_bottom_left,rgba(219,39,119,0.1),transparent_50%)] pointer-events-none"></div>

    <!-- SIDEBAR NAVIGATION PANEL -->
    <aside id="sidebar" class="w-full md:w-96 dark-glass h-1/2 md:h-full flex flex-col z-20 transition-all duration-300 border-b md:border-b-0 md:border-r border-slate-800">
        <!-- Brand Profile & Welcome Section -->
        <div class="p-5 border-b border-slate-800 flex items-center justify-between">
            <div class="flex items-center gap-3">
                <div class="h-10 w-10 rounded-xl bg-gradient-to-tr from-indigo-500 to-pink-500 flex items-center justify-center font-bold tracking-wider text-white shadow-lg shadow-indigo-500/20">
                    DB
                </div>
                <div>
                    <h1 class="font-bold tracking-tight text-white text-md">DeBeatzGH Workspace</h1>
                    <span class="text-xs text-indigo-400 flex items-center gap-1 font-medium">
                        <i data-lucide="sparkles" class="w-3 h-3"></i> Premium Ecosystem Active
                    </span>
                </div>
            </div>
            <!-- Quick Info/Status badge -->
            <span class="px-2 py-1 bg-emerald-500/10 text-emerald-400 rounded-full text-[10px] font-semibold uppercase tracking-wider border border-emerald-500/20">
                Online
            </span>
        </div>

        <!-- Scrollable Menu Section -->
        <nav class="flex-1 overflow-y-auto p-4 space-y-3">
            <p class="text-[11px] font-semibold text-slate-400 uppercase tracking-widest px-2 mb-2">Primary Hub</p>
            
            <!-- Item: Default Project Overview -->
            <button onclick="handleNavigation('https://debeatzgh1.github.io/Tech-and-AI-Hub-/', 'Project Overview', false)" 
                    class="menu-btn w-full text-left p-3.5 rounded-xl bg-indigo-600 text-white flex gap-3.5 items-start transition-all duration-200 group active-nav">
                <div class="p-2 rounded-lg bg-white/10 text-white mt-0.5 shadow-sm">
                    <i data-lucide="layout-dashboard" class="w-5 h-5"></i>
                </div>
                <div class="flex-1 min-w-0">
                    <div class="flex items-center justify-between">
                        <span class="font-semibold text-sm truncate">Project Overview</span>
                        <span class="text-[10px] bg-white/20 text-white px-1.5 py-0.5 rounded font-mono">CORE</span>
                    </div>
                    <p class="text-xs text-indigo-100 line-clamp-2 mt-0.5 font-light">Main operational hub covering technical assets, active tools, and foundational setups.</p>
                </div>
            </button>

            <p class="text-[11px] font-semibold text-slate-400 uppercase tracking-widest px-2 pt-4 mb-2">Service Forms</p>

            <!-- Item: Dynamic Order Intake Form -->
            <button onclick="handleNavigation('https://form.jotform.com/241335470278053', 'Service Processing Center', false)"
                    class="menu-btn w-full text-left p-3.5 rounded-xl hover:bg-slate-800/60 text-slate-300 hover:text-white flex gap-3.5 items-start transition-all duration-200 group border border-transparent hover:border-slate-700/50">
                <div class="p-2 rounded-lg bg-slate-800 text-slate-400 group-hover:bg-indigo-500/10 group-hover:text-indigo-400 mt-0.5 transition-colors">
                    <i data-lucide="file-text" class="w-5 h-5"></i>
                </div>
                <div class="flex-1 min-w-0">
                    <div class="flex items-center justify-between">
                        <span class="font-medium text-sm group-hover:font-semibold transition-all">Service Intake Engine</span>
                    </div>
                    <p class="text-xs text-slate-400 group-hover:text-slate-300 mt-0.5 line-clamp-2 font-light">Initiate service parameters, manage incoming requests, and dispatch core orders.</p>
                </div>
            </button>

            <!-- Item: Suggestions & Contact -->
            <button onclick="handleNavigation('https://form.svhrt.com/60f4a0aeedc1993c8c7b3989', 'Customer Suggestion Box', false)"
                    class="menu-btn w-full text-left p-3.5 rounded-xl hover:bg-slate-800/60 text-slate-300 hover:text-white flex gap-3.5 items-start transition-all duration-200 group border border-transparent hover:border-slate-700/50">
                <div class="p-2 rounded-lg bg-slate-800 text-slate-400 group-hover:bg-indigo-500/10 group-hover:text-indigo-400 mt-0.5 transition-colors">
                    <i data-lucide="message-square" class="w-5 h-5"></i>
                </div>
                <div class="flex-1 min-w-0">
                    <span class="font-medium text-sm group-hover:font-semibold block transition-all">Customer Suggestions</span>
                    <p class="text-xs text-slate-400 group-hover:text-slate-300 mt-0.5 line-clamp-2 font-light">Direct feedback channel for ongoing optimization and iterative client proposals.</p>
                </div>
            </button>

            <!-- Item: Google Contact Form -->
            <button onclick="handleNavigation('https://docs.google.com/forms/d/e/1FAIpQLSfBDlR6TcU9sWjbeVOp6dtb4GMKdL6SP_i0KB08IrtbLT9wwA/viewform?usp=header', 'Standard Contact Form', false)"
                    class="menu-btn w-full text-left p-3.5 rounded-xl hover:bg-slate-800/60 text-slate-300 hover:text-white flex gap-3.5 items-start transition-all duration-200 group border border-transparent hover:border-slate-700/50">
                <div class="p-2 rounded-lg bg-slate-800 text-slate-400 group-hover:bg-indigo-500/10 group-hover:text-indigo-400 mt-0.5 transition-colors">
                    <i data-lucide="contact" class="w-5 h-5"></i>
                </div>
                <div class="flex-1 min-w-0">
                    <span class="font-medium text-sm group-hover:font-semibold block transition-all">Direct Contact Portal</span>
                    <p class="text-xs text-slate-400 group-hover:text-slate-300 mt-0.5 line-clamp-2 font-light">General correspondence endpoint configured with secure communication standards.</p>
                </div>
            </button>

            <!-- Item: Project Enquiry -->
            <button onclick="handleNavigation('https://docs.google.com/forms/d/e/1FAIpQLSdipVP7tU1hjTjECfWUdnhzWN-PROdQp19ng25EUDJk5-8JzA/viewform?usp=header', 'Project Enquiry Desk', false)"
                    class="menu-btn w-full text-left p-3.5 rounded-xl hover:bg-slate-800/60 text-slate-300 hover:text-white flex gap-3.5 items-start transition-all duration-200 group border border-transparent hover:border-slate-700/50">
                <div class="p-2 rounded-lg bg-slate-800 text-slate-400 group-hover:bg-indigo-500/10 group-hover:text-indigo-400 mt-0.5 transition-colors">
                    <i data-lucide="briefcase" class="w-5 h-5"></i>
                </div>
                <div class="flex-1 min-w-0">
                    <span class="font-medium text-sm group-hover:font-semibold block transition-all">Project Enquiry Desk</span>
                    <p class="text-xs text-slate-400 group-hover:text-slate-300 mt-0.5 line-clamp-2 font-light">Submit scoping guidelines, development specifications, and feature checklists.</p>
                </div>
            </button>

            <p class="text-[11px] font-semibold text-slate-400 uppercase tracking-widest px-2 pt-4 mb-2">Gateways & Accounts</p>

            <!-- Item: Standard Sign In -->
            <button onclick="handleNavigation('https://docs.google.com/forms/d/e/1FAIpQLSdXCPUz1JBq0W8MHN9VOE0p6cnp5Wtr74Ox2gqLLyzKi0UwKA/viewform?usp=header', 'Secure Sign-In Gateway', false)"
                    class="menu-btn w-full text-left p-3.5 rounded-xl hover:bg-slate-800/60 text-slate-300 hover:text-white flex gap-3.5 items-start transition-all duration-200 group border border-transparent hover:border-slate-700/50">
                <div class="p-2 rounded-lg bg-slate-800 text-slate-400 group-hover:bg-indigo-500/10 group-hover:text-indigo-400 mt-0.5 transition-colors">
                    <i data-lucide="log-in" class="w-5 h-5"></i>
                </div>
                <div class="flex-1 min-w-0">
                    <span class="font-medium text-sm group-hover:font-semibold block transition-all">Account Authentication</span>
                    <p class="text-xs text-slate-400 group-hover:text-slate-300 mt-0.5 line-clamp-2 font-light">Secure single sign-on form verified for general dashboard tier users.</p>
                </div>
            </button>

            <!-- Item: Tally Premium Hub -->
            <button onclick="handleNavigation('https://tally.so/r/3jkE29', 'Premium Suite Hub', false)"
                    class="menu-btn w-full text-left p-3.5 rounded-xl bg-gradient-to-r from-amber-500/5 to-yellow-500/5 hover:from-amber-500/10 hover:to-yellow-500/10 text-slate-300 hover:text-white flex gap-3.5 items-start transition-all duration-200 group border border-amber-500/20 hover:border-amber-500/40 relative overflow-hidden">
                <div class="absolute top-0 right-0 w-16 h-16 bg-amber-500/5 transform rotate-45 translate-x-8 -translate-y-8 pointer-events-none"></div>
                <div class="p-2 rounded-lg bg-amber-500/10 text-amber-400 mt-0.5">
                    <i data-lucide="crown" class="w-5 h-5"></i>
                </div>
                <div class="flex-1 min-w-0">
                    <div class="flex items-center justify-between">
                        <span class="font-medium text-sm text-amber-300 group-hover:font-semibold transition-all">Premium & Admin Suite</span>
                        <span class="text-[9px] bg-amber-500 text-slate-950 px-1.5 py-0.5 rounded-full font-bold tracking-wider uppercase">VIP</span>
                    </div>
                    <p class="text-xs text-slate-400 group-hover:text-slate-300 mt-0.5 line-clamp-2 font-light">Gain template keys, secure architectural files, and register Blog Admin clearance.</p>
                </div>
            </button>
        </nav>

        <!-- Sidebar Footprint Area -->
        <div class="p-4 border-t border-slate-800 dark-glass text-center text-xs text-slate-500 flex items-center justify-between">
            <span>v2.4 Pro Ecosystem</span>
            <span class="flex items-center gap-1"><i data-lucide="shield-check" class="w-3.5 h-3.5 text-indigo-400"></i> Encrypted Session</span>
        </div>
    </aside>

    <!-- CONTENT FIELD / OVERLAY AREA -->
    <main class="flex-1 h-1/2 md:h-full relative flex flex-col bg-slate-950">
        <!-- Interactive Hub Top Navigation Frame -->
        <header class="h-14 border-b border-slate-900 bg-slate-950/80 backdrop-blur-md px-4 flex items-center justify-between z-10 shrink-0">
            <div class="flex items-center gap-2">
                <i data-lucide="panels-top-left" class="w-4 h-4 text-slate-400"></i>
                <h2 id="view-title" class="text-sm font-semibold text-slate-200 tracking-wide truncate">Project Overview</h2>
            </div>
            
            <!-- Context Control Configuration Tools -->
            <div class="flex items-center gap-2">
                <button id="external-link-btn" title="Open in New External Window" class="p-2 hover:bg-slate-800 rounded-lg text-slate-400 hover:text-white transition-colors">
                    <i data-lucide="external-link" class="w-4 h-4"></i>
                </button>
                <div class="w-px h-4 bg-slate-800 mx-1"></div>
                <button id="fullscreen-toggle" title="Maximize View Workspace" class="p-2 hover:bg-slate-800 rounded-lg text-slate-400 hover:text-white transition-colors">
                    <i data-lucide="maximize" class="w-4 h-4"></i>
                </button>
            </div>
        </header>

        <!-- Main Display Frame Pipeline -->
        <div class="flex-1 w-full h-full relative bg-slate-900">
            <!-- Loader Feedback Loop -->
            <div id="frame-loader" class="absolute inset-0 flex flex-col items-center justify-center bg-slate-950/90 z-10 hidden">
                <div class="w-8 h-8 border-2 border-indigo-500 border-t-transparent rounded-full animate-spin mb-3"></div>
                <p class="text-xs text-slate-400 font-mono">Syncing resource interface...</p>
            </div>
            <!-- System Core Iframe -->
            <iframe id="main-frame" 
                    src="https://debeatzgh1.github.io/Tech-and-AI-Hub-/" 
                    class="w-full h-full border-0 bg-transparent transition-opacity duration-300" 
                    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" 
                    allowfullscreen>
            </iframe>
        </div>
    </main>

    <!-- FLOATING FLOOD OVERLAY AREA (SOCIALCREATOR PORTAL) -->
    <div id="social-overlay" class="fixed inset-0 bg-slate-950/80 backdrop-blur-md z-50 flex items-center justify-center p-4 opacity-0 pointer-events-none transition-all duration-300">
        <div class="w-full max-w-4xl h-[85vh] bg-slate-900 rounded-2xl border border-slate-800 shadow-2xl overflow-hidden flex flex-col transform scale-95 transition-transform duration-300">
            <header class="p-4 bg-slate-950/50 border-b border-slate-800 flex items-center justify-between">
                <div class="flex items-center gap-2">
                    <div class="w-2 h-2 bg-pink-500 rounded-full animate-ping"></div>
                    <h3 class="text-sm font-semibold text-white tracking-wide">SocialCreator Platform Hub</h3>
                </div>
                <div class="flex items-center gap-2">
                    <a href="https://www.socialcreator.com/techshop/?s=322742" target="_blank" class="px-3 py-1.5 bg-slate-800 hover:bg-slate-700 text-xs font-medium text-slate-200 rounded-lg transition-colors flex items-center gap-1.5">
                        <i data-lucide="external-link" class="w-3.5 h-3.5"></i> Open External
                    </a>
                    <button onclick="toggleSocialOverlay(false)" class="p-1.5 bg-slate-800 hover:bg-slate-700 text-slate-400 hover:text-white rounded-lg transition-colors">
                        <i data-lucide="x" class="w-4 h-4"></i>
                    </button>
                </div>
            </header>
            <div class="flex-1 bg-slate-950 relative">
                <iframe src="https://www.socialcreator.com/techshop/?s=322742" class="w-full h-full border-0"></iframe>
            </div>
        </div>
    </div>

    <!-- FLOATING ACTION SYSTEM BUTTON (FAB) -->
    <button onclick="toggleSocialOverlay(true)" 
            title="Launch TechShop Ecosystem Overlay"
            class="fixed bottom-6 right-6 z-40 p-4 rounded-full bg-gradient-to-r from-pink-600 to-indigo-600 text-white shadow-xl shadow-indigo-600/20 hover:shadow-pink-600/40 transform hover:scale-110 active:scale-95 transition-all duration-200 animate-pulse-ring group">
        <i data-lucide="shopping-bag" class="w-6 h-6 transform group-hover:rotate-12 transition-transform"></i>
    </button>

    <!-- FUNCTIONAL INTERACTIVE DASHBOARD JAVASCRIPT ARCHITECTURE -->
    <script>
        // Track runtime dashboard elements
        const mainFrame = document.getElementById('main-frame');
        const viewTitle = document.getElementById('view-title');
        const frameLoader = document.getElementById('frame-loader');
        const externalBtn = document.getElementById('external-link-btn');
        const fullscreenBtn = document.getElementById('fullscreen-toggle');
        const sidebar = document.getElementById('sidebar');
        const socialOverlay = document.getElementById('social-overlay');
        
        let currentUrl = 'https://debeatzgh1.github.io/Tech-and-AI-Hub-/';

        // Initialize Icons Engine
        lucide.createIcons();

        // Bind core lifecycle loader animation hook
        mainFrame.addEventListener('load', () => {
            frameLoader.classList.add('hidden');
            mainFrame.classList.remove('opacity-50');
        });

        /**
         * Orchestrates target frame switching, loading mechanics, and button style arrays
         */
        function handleNavigation(url, title, openExternalDirectly = false) {
            currentUrl = url;
            
            if (openExternalDirectly) {
                window.open(url, '_blank');
                return;
            }

            // Trigger visual transitions across frames
            frameLoader.classList.remove('hidden');
            mainFrame.classList.add('opacity-50');
            mainFrame.src = url;
            viewTitle.textContent = title;

            // Dynamically manage operational state profiles within lists
            const buttons = document.querySelectorAll('.menu-btn');
            buttons.forEach(btn => {
                const btnText = btn.querySelector('span').textContent;
                if(title.includes(btnText) || btnText.includes(title)) {
                    // Turn to selected design matrix
                    btn.classList.add('bg-indigo-600', 'text-white');
                    btn.classList.remove('hover:bg-slate-800/60', 'text-slate-300', 'hover:text-white', 'border-transparent');
                    btn.querySelector('.p-2').classList.add('bg-white/10', 'text-white');
                } else {
                    // Turn to unselected base design matrix
                    btn.classList.remove('bg-indigo-600', 'text-white');
                    btn.classList.add('hover:bg-slate-800/60', 'text-slate-300', 'hover:text-white');
                    const iconBox = btn.querySelector('.p-2');
                    iconBox.classList.remove('bg-white/10', 'text-white');
                    if (iconBox.parentElement.parentElement.classList.contains('border-amber-500/20')) {
                        // Protect specific premium styling markers
                        iconBox.classList.add('bg-amber-500/10', 'text-amber-400');
                    }
                }
            });
        }

        // Action routing links
        externalBtn.onclick = () => window.open(currentUrl, '_blank');

        // Toggle full screen canvas workspace mode
        fullscreenBtn.onclick = () => {
            sidebar.classList.toggle('hidden');
            const icon = fullscreenBtn.querySelector('i');
            if(sidebar.classList.contains('hidden')) {
                fullscreenBtn.innerHTML = '<i data-lucide="minimize" class="w-4 h-4"></i>';
            } else {
                fullscreenBtn.innerHTML = '<i data-lucide="maximize" class="w-4 h-4"></i>';
            }
            lucide.createIcons();
        };

        // Handles rendering behavior profiles on the floating ecosystem panel
        function toggleSocialOverlay(displayFlag) {
            const innerPanel = socialOverlay.querySelector('.max-w-4xl');
            if (displayFlag) {
                socialOverlay.classList.remove('opacity-0', 'pointer-events-none');
                innerPanel.classList.remove('scale-95');
                innerPanel.classList.add('scale-100');
            } else {
                socialOverlay.classList.add('opacity-0', 'pointer-events-none');
                innerPanel.classList.remove('scale-100');
                innerPanel.classList.add('scale-95');
            }
        }
    </script>
