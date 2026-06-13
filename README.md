
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DeBeatzGH - Portal Hub</title>
    <!-- Tailwind CSS for high-performance styling -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- FontAwesome for professional layout icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        .glass-panel {
            background: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.3);
        }
        .custom-scrollbar::-webkit-scrollbar {
            width: 6px;
        }
        .custom-scrollbar::-webkit-scrollbar-thumb {
            background-color: #cbd5e1;
            border-radius: 3px;
        }
    </style>
</head>
<body class="bg-slate-900 text-slate-100 min-h-screen font-sans antialiased selection:bg-teal-500 selection:text-white">

    <!-- HERO BACKGROUND GLOWS -->
    <div class="absolute top-0 left-1/4 w-96 h-96 bg-teal-500/10 rounded-full filter blur-3xl -z-10 animate-pulse"></div>
    <div class="absolute top-1/3 right-1/4 w-96 h-96 bg-blue-500/10 rounded-full filter blur-3xl -z-10 animate-pulse" style="animation-delay: 2s;"></div>

    <!-- HEADER / NAVIGATION -->
    <header class="border-b border-slate-800/80 bg-slate-900/50 backdrop-blur sticky top-0 z-40">
        <div class="max-w-7xl mx-auto px-4 h-16 flex items-center justify-between">
            <div class="flex items-center space-x-3">
                <div class="bg-gradient-to-tr from-teal-500 to-blue-600 p-2.5 rounded-xl shadow-lg shadow-teal-500/20">
                    <i class="fa-solid fa-compact-disc text-white text-xl animate-spin" style="animation-duration: 8s;"></i>
                </div>
                <div>
                    <span class="font-extrabold text-xl tracking-tight bg-gradient-to-r from-teal-400 to-blue-400 bg-clip-text text-transparent">DeBeatzGH</span>
                    <span class="text-xs block text-slate-400 font-medium">Operations & Strategy Hub</span>
                </div>
            </div>
            
            <button onclick="toggleModal('signup-modal', true)" class="bg-gradient-to-r from-teal-500 to-blue-600 hover:from-teal-400 hover:to-blue-500 text-white font-semibold px-5 py-2 rounded-xl shadow-lg shadow-teal-500/25 transition-all duration-300 transform hover:-translate-y-0.5 text-sm">
                <i class="fa-solid fa-user-plus mr-2"></i>Join Portal
            </button>
        </div>
    </header>

    <main class="max-w-7xl mx-auto px-4 py-8 space-y-12">
        
        <!-- AUTO-SLIDING TEXT CAROUSEL SECTION -->
        <section class="bg-slate-800/40 border border-slate-800 rounded-3xl p-6 md:p-8 relative overflow-hidden shadow-inner">
            <div class="absolute top-3 right-4 flex items-center space-x-1.5 bg-slate-900/60 px-3 py-1 rounded-full border border-slate-700/50">
                <span class="w-2 h-2 rounded-full bg-teal-400 animate-ping"></span>
                <span class="text-[11px] font-bold tracking-wider text-slate-400 uppercase">AI System Notice</span>
            </div>
            
            <div class="relative h-24 flex items-center">
                <!-- Slides Container -->
                <div id="carousel-track" class="w-full text-center md:text-left transition-all duration-500 opacity-100 transform translate-y-0">
                    <h3 id="carousel-title" class="text-xs font-bold text-teal-400 uppercase tracking-widest mb-1">Loading System Parameters</h3>
                    <p id="carousel-text" class="text-base md:text-lg text-slate-300 max-w-4xl font-medium leading-relaxed">Initializing pipeline databases and form verification modules...</p>
                </div>
            </div>

            <!-- Slide Indicator Dots -->
            <div class="flex justify-center md:justify-start space-x-2 mt-4" id="carousel-dots"></div>
        </section>

        <!-- PORTAL GRID: OEMBED FORM MANAGER -->
        <section class="grid grid-cols-1 lg:grid-cols-12 gap-8 items-start">
            
            <!-- LEFT COLUMN: INTERACTIVE FORM SELECTOR SLIDER LIST -->
            <div class="lg:col-span-4 space-y-4 max-h-[720px] overflow-y-auto pr-2 custom-scrollbar" id="form-selector-container">
                <div class="p-2">
                    <h2 class="text-lg font-bold text-slate-200">Processing Queues</h2>
                    <p class="text-xs text-slate-400">Select an execution queue to build safe frame embed</p>
                </div>

                <!-- Form Cards will render here dynamically via JavaScript -->
            </div>

            <!-- RIGHT COLUMN: INTERACTIVE EMBED CONTAINER FRAME -->
            <div class="lg:col-span-8 lg:sticky lg:top-24">
                <div class="bg-slate-800/80 border border-slate-700/60 rounded-3xl overflow-hidden shadow-2xl h-[720px] flex flex-col">
                    
                    <!-- Frame Bar Controller -->
                    <div class="bg-slate-900/90 p-4 border-b border-slate-700/50 flex flex-col sm:flex-row justify-between items-start sm:items-center gap-3">
                        <div class="flex items-center space-x-3 max-w-full">
                            <div class="flex space-x-1.5 shrink-0">
                                <span class="w-3 h-3 rounded-full bg-rose-500/80"></span>
                                <span class="w-3 h-3 rounded-full bg-amber-500/80"></span>
                                <span class="w-3 h-3 rounded-full bg-emerald-500/80"></span>
                            </div>
                            <div class="truncate">
                                <span id="current-form-title" class="text-sm font-semibold text-slate-200 block truncate">No Form Selected</span>
                                <span id="current-form-url" class="text-[11px] text-slate-500 font-mono block truncate">Select target workspace below</span>
                            </div>
                        </div>

                        <!-- Action Buttons -->
                        <div class="flex items-center space-x-2 self-stretch sm:self-auto justify-end">
                            <button onclick="reloadActiveFrame()" class="p-2 text-slate-400 hover:text-slate-200 bg-slate-800 hover:bg-slate-700 rounded-lg text-xs border border-slate-700/50 transition">
                                <i class="fa-solid fa-arrows-rotate"></i>
                            </button>
                            <a id="btn-open-tab" href="#" target="_blank" class="bg-slate-800 hover:bg-slate-700 text-slate-200 px-3.5 py-2 rounded-xl text-xs font-semibold border border-slate-700/50 transition flex items-center whitespace-nowrap opacity-50 pointer-events-none">
                                Open New Tab <i class="fa-solid fa-arrow-up-right-from-square ml-2 text-[10px]"></i>
                            </a>
                        </div>
                    </div>

                    <!-- Sandbox Viewport Screen -->
                    <div class="flex-grow w-full h-full bg-slate-950 relative" id="iframe-viewport-wrapper">
                        <!-- Default Blank Setup Overlay -->
                        <div id="viewport-placeholder" class="absolute inset-0 flex flex-col items-center justify-content-center text-center p-8 z-10 my-auto h-fit">
                            <div class="w-16 h-16 rounded-full bg-slate-900 flex items-center justify-center border border-slate-800 text-slate-600 mb-4 shadow-xl">
                                <i class="fa-solid fa-laptop-code text-2xl"></i>
                            </div>
                            <h4 class="text-slate-300 font-bold mb-1">Standby Integration Workspace</h4>
                            <p class="text-xs text-slate-500 max-w-sm">Click any pipeline resource deck on the left. Elements deploy via lazy initialization safely inside this execution pane.</p>
                        </div>
                        
                        <!-- Dynamic iframe will drop here -->
                    </div>
                </div>
            </div>

        </section>
    </main>

    <!-- INTEGRATED POPUP DEBEATZGH SIGN UP MODAL -->
    <div id="signup-modal" class="fixed inset-0 z-50 overflow-y-auto hidden" aria-labelledby="modal-title" role="dialog" aria-modal="true">
        <!-- Backdrop blur -->
        <div class="flex items-center justify-center min-h-screen px-4 pt-4 pb-20 text-center sm:block sm:p-0">
            <div class="fixed inset-0 bg-slate-950/80 backdrop-blur-sm transition-opacity" onclick="toggleModal('signup-modal', false)"></div>

            <!-- Position fix wrapper -->
            <span class="hidden sm:inline-block sm:align-middle sm:h-screen" aria-hidden="true">&#8203;</span>

            <!-- Modal UI Box -->
            <div class="inline-block align-bottom bg-slate-900 border border-slate-800 rounded-3xl text-left overflow-hidden shadow-2xl transform transition-all sm:my-8 sm:align-middle sm:max-w-md sm:w-full relative">
                
                <div class="absolute top-4 right-4">
                    <button onclick="toggleModal('signup-modal', false)" class="text-slate-400 hover:text-slate-200 p-1.5 rounded-lg bg-slate-800/50 hover:bg-slate-800 transition">
                        <i class="fa-solid fa-xmark"></i>
                    </button>
                </div>

                <div class="p-6 md:p-8">
                    <div class="mb-6">
                        <div class="w-10 h-10 rounded-xl bg-teal-500/10 border border-teal-500/20 text-teal-400 flex items-center justify-center mb-3">
                            <i class="fa-solid fa-shield-halved text-lg"></i>
                        </div>
                        <h3 class="text-xl font-bold text-slate-100">DeBeatzGH Onboarding</h3>
                        <p class="text-xs text-slate-400 mt-1">Register your developer profile to claim master workspace keys.</p>
                    </div>

                    <!-- Embedded Form Flow logic -->
                    <form id="debeatz-signup-form" onsubmit="handleSignupSubmit(event)" class="space-y-4">
                        <div>
                            <label class="block text-xs font-bold uppercase tracking-wider text-slate-400 mb-1.5">Legal Identity Name</label>
                            <input type="text" required placeholder="e.g., Kwesi Mensah" class="w-full bg-slate-950 border border-slate-800 focus:border-teal-500/80 rounded-xl px-4 py-2.5 text-sm text-slate-200 placeholder:text-slate-600 outline-none transition">
                        </div>
                        
                        <div>
                            <label class="block text-xs font-bold uppercase tracking-wider text-slate-400 mb-1.5">Network Email Connection</label>
                            <input type="email" required placeholder="kwesi@debeatzgh.com" class="w-full bg-slate-950 border border-slate-800 focus:border-teal-500/80 rounded-xl px-4 py-2.5 text-sm text-slate-200 placeholder:text-slate-600 outline-none transition">
                        </div>

                        <div>
                            <label class="block text-xs font-bold uppercase tracking-wider text-slate-400 mb-1.5">Assigned Architecture Role</label>
                            <select class="w-full bg-slate-950 border border-slate-800 focus:border-teal-500/80 rounded-xl px-4 py-2.5 text-sm text-slate-400 outline-none transition">
                                <option>Independent Content Producer</option>
                                <option>A&R Executive Analyst</option>
                                <option>System Infrastructure Admin</option>
                                <option>Strategic Brand Partner</option>
                            </select>
                        </div>

                        <div class="pt-2">
                            <button type="submit" class="w-full bg-gradient-to-r from-teal-500 to-blue-600 hover:from-teal-400 hover:to-blue-500 text-white font-semibold py-3 rounded-xl shadow-lg shadow-teal-500/10 transition duration-300">
                                Verify & Establish Account
                            </button>
                        </div>
                    </form>

                    <!-- Feedback Alert (Success/Error states hidden by default) -->
                    <div id="form-feedback" class="mt-4 p-3 rounded-xl border hidden text-xs text-center font-medium"></div>
                </div>
            </div>
        </div>
    </div>

    <!-- MAIN CORE LOGIC ARCHITECTURE -->
    <script>
        // TARGET FORMS REPOSITORIES SPECIFICATIONS
        const EMBED_REGISTRY = [
            {
                id: "dbz-f1",
                title: "DeBeatzGH Core Entry Engine",
                type: "JotForm System Container",
                url: "https://form.jotform.com/241325342765051",
                icon: "fa-solid fa-database",
                desc: "Primary node mapping structural workflows and asset logs."
            },
            {
                id: "dbz-f2",
                title: "A&R Quality & Intake Evaluation",
                type: "JotForm Intake Module",
                url: "https://form.jotform.com/241335470278053",
                icon: "fa-solid fa-sliders",
                desc: "Audits master records and production criteria values."
            },
            {
                id: "dbz-f3",
                title: "Strategic Operations Review Matrix",
                type: "JotForm Corporate Deck",
                url: "https://form.jotform.com/241326050865049",
                icon: "fa-solid fa-chart-line",
                desc: "Performance analysis pipeline monitoring corporate parameters."
            },
            {
                id: "dbz-f4",
                title: "Secure Verification Network Portal",
                type: "SVHRT Secure Ledger",
                url: "https://form.svhrt.com/60f4a0aeedc1993c8c7b3989",
                icon: "fa-solid fa-key",
                desc: "High-encryption identity link node handling compliance data authentication."
            }
        ];

        // PROMOTIONAL MARKETING CAROUSEL TRACK STRINGS
        const CAROUSEL_SLIDES = [
            { title: "Network Update Status", text: "Global operations synced across all secure channels. Track responses live directly from your unified terminal panels." },
            { title: "Lazy-Load Protection Enabled", text: "Forms remain dormant until requested. This layout isolates resource thread execution to optimize user experience." },
            { title: "Centralized Onboarding", text: "New team members can run validation protocols natively by hitting 'Join Portal' inside the header navigation structure." }
        ];

        let currentSlideIndex = 0;
        let activeFormUrl = "";

        // CAROUSEL LOGIC ENGINE
        function initCarousel() {
            const trackTitle = document.getElementById('carousel-title');
            const trackText = document.getElementById('carousel-text');
            const dotsContainer = document.getElementById('carousel-dots');

            // Render indicator tracking points
            dotsContainer.innerHTML = '';
            CAROUSEL_SLIDES.forEach((_, idx) => {
                const dot = document.createElement('button');
                dot.className = `w-2 h-2 rounded-full transition-all duration-300 ${idx === 0 ? 'bg-teal-400 w-5' : 'bg-slate-700'}`;
                dot.onclick = () => jumpToSlide(idx);
                dotsContainer.appendChild(dot);
            });

            function executeSlideCycle() {
                currentSlideIndex = (currentSlideIndex + 1) % CAROUSEL_SLIDES.length;
                renderActiveSlide();
            }

            let slideTimer = setInterval(executeSlideCycle, 5000);

            window.jumpToSlide = function(targetIdx) {
                clearInterval(slideTimer);
                currentSlideIndex = targetIdx;
                renderActiveSlide();
                slideTimer = setInterval(executeSlideCycle, 5000);
            }

            function renderActiveSlide() {
                const data = CAROUSEL_SLIDES[currentSlideIndex];
                const track = document.getElementById('carousel-track');
                
                track.classList.add('opacity-0', 'translate-y-1');
                
                setTimeout(() => {
                    trackTitle.innerText = data.title;
                    trackText.innerText = data.text;
                    
                    // Update layout metrics for markers
                    Array.from(dotsContainer.children).forEach((dot, idx) => {
                        if(idx === currentSlideIndex) {
                            dot.className = "w-2 h-2 rounded-full transition-all duration-300 bg-teal-400 w-5";
                        } else {
                            dot.className = "w-2 h-2 rounded-full transition-all duration-300 bg-slate-700";
                        }
                    });
                    
                    track.classList.remove('opacity-0', 'translate-y-1');
                }, 300);
            }
        }

        // OEMBED FRAME INJECTION ARCHITECTURE (LAZY LOAD DESIGN)
        function initFormSelector() {
            const container = document.getElementById('form-selector-container');
            
            EMBED_REGISTRY.forEach(form => {
                const card = document.createElement('div');
                card.id = `card-${form.id}`;
                card.className = "p-4 bg-slate-800/30 border border-slate-800/80 hover:border-slate-700 rounded-2xl cursor-pointer transition-all duration-200 group";
                card.onclick = () => activateFormFrame(form);
                
                card.innerHTML = `
                    <div class="flex items-start space-x-3.5">
                        <div class="w-10 h-10 rounded-xl bg-slate-900 border border-slate-800 group-hover:border-teal-500/30 text-slate-400 group-hover:text-teal-400 flex items-center justify-center shrink-0 shadow-lg transition-all duration-200">
                            <i class="${form.icon} text-base"></i>
                        </div>
                        <div class="space-y-1 min-w-0 flex-grow">
                            <div class="flex justify-between items-center">
                                <span class="text-[10px] font-bold text-slate-500 group-hover:text-teal-400 uppercase tracking-wider transition-colors">${form.type}</span>
                                <i class="fa-solid fa-chevron-right text-[10px] text-slate-600 group-hover:translate-x-0.5 transition-transform"></i>
                            </div>
                            <h3 class="font-bold text-sm text-slate-300 group-hover:text-white transition-colors truncate">${form.title}</h3>
                            <p class="text-xs text-slate-500 line-clamp-2 leading-normal">${form.desc}</p>
                        </div>
                    </div>
                `;
                container.appendChild(card);
            });
        }

        function activateFormFrame(formSpec) {
            // Unset previous selections active styles
            EMBED_REGISTRY.forEach(f => {
                const el = document.getElementById(`card-${f.id}`);
                if(el) el.classList.remove('border-teal-500/50', 'bg-slate-800/60', 'shadow-lg');
            });

            // Tag selected element UI state
            const activeCard = document.getElementById(`card-${formSpec.id}`);
            if(activeCard) activeCard.classList.add('border-teal-500/50', 'bg-slate-800/60', 'shadow-lg');

            // Purge static screen text overlay
            const placeholder = document.getElementById('viewport-placeholder');
            if(placeholder) placeholder.s
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DeBeatzGH | Smart Overlay</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        :root {
            --accent: #00f2ff;
            --glass: rgba(15, 15, 20, 0.8);
            --border: rgba(255, 255, 255, 0.1);
        }

        body { background: #050507; font-family: 'Plus Jakarta Sans', sans-serif; height: 200vh; }

        /* --- 1. TRANSPARENT FLOATING BUTTON --- */
        #home-trigger {
            position: fixed; bottom: 30px; left: 30px;
            width: 55px; height: 55px;
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border: 1px solid var(--border);
            border-radius: 50%;
            display: flex; align-items: center; justify-content: center;
            cursor: pointer; z-index: 10000;
            transition: 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        #home-trigger:hover { border-color: var(--accent); background: rgba(0, 242, 255, 0.1); transform: scale(1.1); }

        /* --- 2. SCROLL INDICATOR ICONS --- */
        .scroll-icon {
            position: fixed; bottom: 95px; left: 47px;
            font-size: 10px; color: var(--accent);
            opacity: 0; transition: 0.3s; pointer-events: none;
        }
        .scroll-icon.active { opacity: 1; transform: translateY(-5px); }

        /* --- 3. OVERLAY CONTAINER --- */
        #home-overlay {
            position: fixed; inset: 0;
            background: rgba(0,0,0,0.9);
            backdrop-filter: blur(15px);
            display: none; z-index: 10001;
            padding: 20px; flex-direction: column;
            animation: fadeIn 0.4s ease;
        }

        .iframe-shell {
            width: 100%; height: 100%;
            border: 1px solid var(--border);
            border-radius: 24px; overflow: hidden;
            background: #fff; box-shadow: 0 0 50px rgba(0,0,0,0.5);
            position: relative;
        }

        /* --- 4. SMART PROMPT --- */
        #stay-prompt {
            position: fixed; top: 50%; left: 50%;
            transform: translate(-50%, -50%);
            width: 320px; background: #111; border: 1px solid var(--accent);
            border-radius: 20px; padding: 25px;
            display: none; z-index: 10005; text-align: center;
            box-shadow: 0 0 40px rgba(0, 242, 255, 0.2);
        }

        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
        @keyframes bounce { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-10px); } }
        .auto-pulse { animation: bounce 1s infinite; border-color: var(--accent) !important; }

    </style>
</head>
<body>

    <i id="scroll-up" class="fas fa-chevron-up scroll-icon"></i>
    <i id="scroll-down" class="fas fa-chevron-down scroll-icon"></i>

    <div id="home-trigger" onclick="toggleHome()">
        <i class="fas fa-home text-white/50 text-sm" id="main-icon"></i>
    </div>

    <div id="home-overlay">
        <div class="flex justify-between items-center mb-4 px-4">
            <span class="text-[10px] font-black tracking-widest text-cyan-400">DEBEATZGH_HOME // LIVE_VIEW</span>
            <button onclick="toggleHome()" class="text-gray-500 hover:text-white text-xs font-bold uppercase">
               <i class="fas fa-times mr-1"></i> Close
            </button>
        </div>
        <div class="iframe-shell">
            <iframe id="home-frame" src="" class="w-full h-full border-none"></iframe>
        </div>
    </div>

    <div id="stay-prompt">
        <h3 class="text-white font-bold mb-2">Session Sync</h3>
        <p class="text-gray-500 text-[11px] mb-6">You've been active for 1 minute. How would you like to continue?</p>
        <div class="flex flex-col gap-2">
            <button onclick="handlePrompt('stay')" class="bg-cyan-500 text-black py-3 rounded-xl text-[10px] font-black uppercase">Stay on Page</button>
            <button onclick="handlePrompt('new')" class="border border-white/10 text-white py-3 rounded-xl text-[10px] font-bold uppercase hover:bg-white/5">Open New Tab</button>
        </div>
    </div>

    <script>
        const homeUrl = "https://debeatzgh1.github.io/Home-/";
        let lastScrollTop = 0;

        // --- 1. AUTO-POPUP LOGIC (Every 6s) ---
        setInterval(() => {
            const btn = document.getElementById('home-trigger');
            btn.classList.add('auto-pulse');
            setTimeout(() => btn.classList.remove('auto-pulse'), 2000);
        }, 6000);

        // --- 2. SCROLL DIRECTION LOGIC ---
        window.addEventListener("scroll", () => {
            let st = window.pageYOffset || document.documentElement.scrollTop;
            const up = document.getElementById('scroll-up');
            const down = document.getElementById('scroll-down');

            if (st > lastScrollTop) {
                down.classList.add('active');
                up.classList.remove('active');
            } else {
                up.classList.add('active');
                down.classList.remove('active');
            }
            lastScrollTop = st <= 0 ? 0 : st;
            
            // Auto hide after 1.5s stillness
            clearTimeout(window.scrollTimer);
            window.scrollTimer = setTimeout(() => {
                up.classList.remove('active');
                down.classList.remove('active');
            }, 1500);
        });

        // --- 3. OVERLAY TOGGLE ---
        function toggleHome() {
            const overlay = document.getElementById('home-overlay');
            const frame = document.getElementById('home-frame');
            const isVisible = overlay.style.display === 'flex';

            if (!isVisible) {
                frame.src = homeUrl;
                overlay.style.display = 'flex';
                document.body.style.overflow = 'hidden';
            } else {
                overlay.style.display = 'none';
                frame.src = "";
                document.body.style.overflow = 'auto';
            }
        }

        // --- 4. ONE MINUTE PROMPT LOGIC ---
        setTimeout(() => {
            document.getElementById('stay-prompt').style.display = 'block';
        }, 60000);

        function handlePrompt(choice) {
            const prompt = document.getElementById('stay-prompt');
            prompt.style.display = 'none';

            if (choice === 'stay') {
                // If on same page, ensure UI is minimized/closed if open
                console.log("User chose to stay.");
            } else {
                // Open in new tab without leaving current
                window.open(homeUrl, '_blank');
            }
        }
    </script>
</body>
</html>




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
