
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Debeatzgh Hub</title>
    <!-- Google Fonts & FontAwesome Icons -->
    <link href="https://googleapis.com" rel="stylesheet">
    <link rel="stylesheet" href="https://cloudflare.com">
    
    <style>
        :root {
            --bg-primary: #0f172a;
            --bg-secondary: #1e293b;
            --accent-color: #6366f1;
            --accent-premium: #f59e0b;
            --text-main: #f8fafc;
            --text-muted: #94a3b8;
            --sidebar-width: 320px;
            --glass-bg: rgba(30, 41, 59, 0.7);
            --glass-border: rgba(255, 255, 255, 0.1);
        }

        [data-theme="premium"] {
            --bg-primary: #0a051b;
            --bg-secondary: #130b2e;
            --accent-color: #d946ef;
            --text-main: #ffffff;
            --text-muted: #a78bfa;
            --glass-bg: rgba(19, 11, 46, 0.6);
            --glass-border: rgba(217, 70, 239, 0.2);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Inter', sans-serif;
            transition: background 0.3s ease, border 0.3s ease;
        }

        body {
            background-color: var(--bg-primary);
            color: var(--text-main);
            display: flex;
            height: 100vh;
            overflow: hidden;
        }

        /* --- SIDEBAR --- */
        .sidebar {
            width: var(--sidebar-width);
            background-color: var(--bg-secondary);
            border-right: 1px solid var(--glass-border);
            display: flex;
            flex-direction: column;
            height: 100%;
            z-index: 10;
        }

        .sidebar-header {
            padding: 24px;
            border-bottom: 1px solid var(--glass-border);
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .brand-title {
            font-size: 1.25rem;
            font-weight: 700;
            letter-spacing: -0.5px;
            background: linear-gradient(to right, #fff, var(--accent-color));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .premium-badge {
            background: linear-gradient(45deg, var(--accent-premium), #ef4444);
            font-size: 0.7rem;
            padding: 4px 8px;
            border-radius: 20px;
            font-weight: bold;
            color: #fff;
            cursor: pointer;
            box-shadow: 0 0 10px rgba(245, 158, 11, 0.3);
        }

        .menu-sections {
            flex: 1;
            overflow-y: auto;
            padding: 16px;
        }

        .menu-section-heading {
            font-size: 0.75rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            color: var(--text-muted);
            margin: 20px 0 10px 8px;
            font-weight: 700;
        }

        .menu-item {
            background: transparent;
            border: 1px solid transparent;
            border-radius: 12px;
            padding: 12px;
            margin-bottom: 8px;
            cursor: pointer;
            display: flex;
            align-items: flex-start;
            gap: 12px;
            position: relative;
        }

        .menu-item:hover, .menu-item.active {
            background-color: rgba(255, 255, 255, 0.03);
            border-color: var(--glass-border);
        }

        .menu-item.active {
            border-left: 4px solid var(--accent-color);
        }

        .menu-icon-box {
            background-color: rgba(255, 255, 255, 0.05);
            padding: 10px;
            border-radius: 10px;
            color: var(--accent-color);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.1rem;
        }

        .menu-item.premium-feature .menu-icon-box {
            color: var(--accent-premium);
        }

        .menu-text {
            flex: 1;
        }

        .menu-title {
            font-size: 0.9rem;
            font-weight: 600;
            margin-bottom: 2px;
            display: flex;
            align-items: center;
            gap: 6px;
        }

        .menu-desc {
            font-size: 0.75rem;
            color: var(--text-muted);
            line-height: 1.3;
        }

        /* Item Quick Launch Actions */
        .menu-actions {
            display: flex;
            flex-direction: column;
            gap: 6px;
            opacity: 0;
            transition: opacity 0.2s ease;
        }

        .menu-item:hover .menu-actions {
            opacity: 1;
        }

        .action-btn {
            background: rgba(255, 255, 255, 0.08);
            border: none;
            color: var(--text-main);
            padding: 4px 6px;
            border-radius: 4px;
            font-size: 0.7rem;
            cursor: pointer;
        }

        .action-btn:hover {
            background: var(--accent-color);
            color: white;
        }

        /* --- MAIN CONTENT & OVERLAY SYSTEM --- */
        .main-content {
            flex: 1;
            position: relative;
            background-color: var(--bg-primary);
        }

        .content-frame {
            width: 100%;
            height: 100%;
            border: none;
            background: #fff;
        }

        /* Overlay Pane */
        .overlay-pane {
            position: absolute;
            top: 0;
            right: -100%;
            width: 100%;
            height: 100%;
            background: var(--bg-primary);
            transition: right 0.4s cubic-bezier(0.16, 1, 0.3, 1);
            z-index: 5;
            display: flex;
            flex-direction: column;
        }

        .overlay-pane.open {
            right: 0;
        }

        .overlay-header {
            background: var(--glass-bg);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            padding: 14px 24px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            border-bottom: 1px solid var(--glass-border);
        }

        .overlay-title {
            font-size: 1rem;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .overlay-controls {
            display: flex;
            gap: 12px;
        }

        .ctrl-btn {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid var(--glass-border);
            color: var(--text-main);
            padding: 8px 14px;
            border-radius: 8px;
            cursor: pointer;
            font-size: 0.85rem;
            display: flex;
            align-items: center;
            gap: 6px;
        }

        .ctrl-btn:hover {
            background: rgba(255, 255, 255, 0.1);
        }

        .ctrl-btn.close-btn {
            background: rgba(239, 68, 68, 0.2);
            border-color: rgba(239, 68, 68, 0.4);
        }

        .ctrl-btn.close-btn:hover {
            background: rgba(239, 68, 68, 0.4);
        }

        .overlay-body {
            flex: 1;
            background: #fff;
        }

        /* --- FLOATING ACTION BUTTON (FAB) --- */
        .fab-container {
            position: fixed;
            bottom: 30px;
            right: 30px;
            z-index: 100;
        }

        .fab-trigger {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: linear-gradient(135deg, #3b82f6, #06b6d4);
            border: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
            box-shadow: 0 10px 25px rgba(59, 130, 246, 0.5);
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
        }

        .fab-trigger::after {
            content: 'Social';
            position: absolute;
            left: -65px;
            background: rgba(15, 23, 42, 0.8);
            backdrop-filter: blur(4px);
            padding: 4px 8px;
            border-radius: 6px;
            font-size: 0.75rem;
            font-weight: 600;
            letter-spacing: 0.5px;
            opacity: 0;
            pointer-events: none;
            transition: opacity 0.2s ease;
        }

        .fab-trigger:hover::after {
            opacity: 1;
        }

        /* Responsive changes */
        @media(max-width: 768px) {
            body { flex-direction: column; }
            .sidebar { width: 100%; height: auto; }
            .main-content { height: 100%; }
        }
    </style>
</head>
<body>

    <!-- SIDEBAR NAVIGATION -->
    <aside class="sidebar">
        <div class="sidebar-header">
            <div class="brand-title">Debeatzgh Hub</div>
            <div class="premium-badge" id="themeToggle" title="Switch style ecosystem"><i class="fa-solid fa-crown"></i> PRO</div>
        </div>

        <div class="menu-sections">
            <!-- Section 1 -->
            <div class="menu-section-heading">Primary Space</div>
            
            <div class="menu-item active" onclick="loadMainFrame('https://debeatzgh1.github.io/Tech-and-AI-Hub-/', this)">
                <div class="menu-icon-box"><i class="fa-solid fa-layer-group"></i></div>
                <div class="menu-text">
                    <div class="menu-title">Project Overview</div>
                    <div class="menu-desc">Core tech and artificial intelligence hub dashboard layout.</div>
                </div>
            </div>

            <!-- Section 2 -->
            <div class="menu-section-heading">Intake & Verification</div>
            
