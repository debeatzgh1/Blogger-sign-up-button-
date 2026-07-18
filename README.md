<!-- Live Workspace Embed Component -->
<div class="dbz-embed-container" style="font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif; margin: 20px auto; max-width: 1000px; border-radius: 16px; overflow: hidden; box-shadow: 0 10px 30px rgba(0,0,0,0.08); border: 1px solid #e2e8f0; background: #ffffff;">
    
    <!-- Control Header -->
    <div style="background: #f8fafc; padding: 12px 20px; border-b: 1px solid #e2e8f0; display: flex; justify-content: space-between; items-center: center; flex-wrap: wrap; gap: 10px;">
        <div style="display: flex; items-center: center; gap: 8px;">
            <span style="width: 10px; height: 10px; border-radius: 50%; background: #ef4444; display: inline-block;"></span>
            <span style="width: 10px; height: 10px; border-radius: 50%; background: #eab308; display: inline-block;"></span>
            <span style="width: 10px; height: 10px; border-radius: 50%; background: #22c55e; display: inline-block;"></span>
            <span style="font-size: 13px; font-weight: 600; color: #475569; margin-left: 10px;">Workspace Viewport |Work and collaborate on Docs </span>
        </div>
        <div>
            <a href="https://appdategh1.blogspot.com/2024/05/tech-business-tools-and-ideas-for.html" target="_blank" style="font-size: 12px; font-weight: 600; color: #2563eb; text-decoration: none; padding: 6px 12px; border-radius: 6px; background: #eff6ff; transition: all 0.2s;" onmouseover="this.style.background='#dbeafe'" onmouseout="this.style.background='#eff6ff'">
                View templates & edit <span style="font-size: 10px; margin-left: 2px;">↗</span>
            </a>
        </div>
    </div>

    <!-- Active Sandbox Viewport -->
    <div style="position: relative; width: 100%; height: 750px; background: #f1f5f9;">
        <!-- CSS-Only Spinner (Hidden automatically once iframe mounts content threads) -->
        <div id="dbz-embed-loader" style="position: absolute; inset: 0; display: flex; flex-direction: column; align-items: center; justify-content: center; background: #ffffff; z-index: 5;">
            <div style="width: 40px; height: 40px; border: 3px solid #cbd5e1; border-top-color: #2563eb; border-radius: 50%; animation: dbz-spin 0.8s linear infinite;"></div>
            <p style="margin-top: 12px; font-size: 13px; color: #64748b; font-weight: 500;">Establishing portal attachment...</p>
        </div>

        <!-- Embedded Frame Target Node -->
        <iframe 
            src="https://docs.google.com/document/d/1jDfbRKcmrtGnWRMPQnp8WqCZ-1y5waoI/edit?usp=drivesdk&ouid=116845182021782803040&rtpof=true&sd=true" 
            style="width: 100%; height: 100%; border: none; opacity: 0; transition: opacity 0.3s ease;" 
            allow="geolocation; microphone; camera; midi; encrypted-media;"
            sandbox="allow-forms allow-modals allow-popups allow-scripts allow-same-origin allow-top-navigation-by-user-activation"
            onload="document.getElementById('dbz-embed-loader').style.display='none'; this.style.opacity='1';">
        </iframe>
    </div>
</div>

<!-- Essential Animation Styles Definition -->
<style>
    @keyframes dbz-spin {
        to { transform: rotate(360deg); }
    }
<style>
:root{
  --dbz-bg:#070b12;
  --dbz-card:rgba(13,17,23,.88);
  --dbz-border:rgba(255,255,255,.08);
  --dbz-text:#f8fafc;
  --dbz-muted:#94a3b8;
  --dbz-accent:#00e0ff;
  --dbz-green:#22c55e;
  --dbz-pink:#d946ef;
  --dbz-shadow:0 15px 40px rgba(0,0,0,.45);
  --dbz-radius:20px;
}

/* ===== GLOBAL ===== */
*{
  box-sizing:border-box;
  margin:0;
  padding:0;
}

body{
  background:#05070d;
  font-family:Inter,Segoe UI,Roboto,sans-serif;
}

/* ===== FLOATING HUB ===== */
.dbz-hustle-widget{
  position:fixed;
  bottom:18px;
  left:50%;
  transform:translateX(-50%);
  width:min(92%,500px);
  z-index:999999;
  animation:dbzEntry .8s cubic-bezier(.175,.885,.32,1.2);
}

@keyframes dbzEntry{
  from{
    opacity:0;
    transform:translateX(-50%) translateY(80px);
  }
  to{
    opacity:1;
    transform:translateX(-50%) translateY(0);
  }
}

/* ===== MAIN CARD ===== */
.dbz-mini-card{
  position:relative;
  overflow:hidden;
  border-radius:var(--dbz-radius);
  border:1px solid var(--dbz-border);
  background:var(--dbz-card);
  backdrop-filter:blur(18px);
  -webkit-backdrop-filter:blur(18px);
  box-shadow:var(--dbz-shadow);
  padding:14px;
  display:flex;
  align-items:center;
  gap:14px;
  cursor:pointer;
  transition:.35s ease;
}

.dbz-mini-card:hover{
  transform:translateY(-3px);
  border-color:rgba(0,224,255,.35);
  box-shadow:
    0 0 0 1px rgba(0,224,255,.15),
    0 20px 50px rgba(0,0,0,.5);
}

/* Animated Glow */
.dbz-mini-card::before{
  content:"";
  position:absolute;
  inset:-120%;
  background:conic-gradient(
    transparent,
    rgba(0,224,255,.25),
    transparent,
    rgba(217,70,239,.25),
    transparent
  );
  animation:dbzRotate 8s linear infinite;
}

@keyframes dbzRotate{
  to{
    transform:rotate(360deg);
  }
}

.dbz-mini-card::after{
  content:"";
  position:absolute;
  inset:1px;
  border-radius:inherit;
  background:rgba(8,11,18,.96);
}

/* ===== CONTENT ===== */
.dbz-content{
  position:relative;
  z-index:3;
  display:flex;
  align-items:center;
  width:100%;
  gap:14px;
}

.dbz-icon-wrap{
  width:50px;
  height:50px;
  border-radius:16px;
  background:linear-gradient(135deg,var(--dbz-accent),var(--dbz-pink));
  display:flex;
  align-items:center;
  justify-content:center;
  flex-shrink:0;
  box-shadow:0 10px 25px rgba(0,224,255,.2);
}

.dbz-icon-wrap svg{
  width:24px;
  height:24px;
  fill:#fff;
}

.dbz-text-area{
  flex:1;
  overflow:hidden;
}

.dbz-badge{
  display:inline-flex;
  align-items:center;
  gap:6px;
  background:rgba(34,197,94,.12);
  border:1px solid rgba(34,197,94,.25);
  color:#86efac;
  font-size:.65rem;
  font-weight:800;
  letter-spacing:.08em;
  text-transform:uppercase;
  padding:4px 8px;
  border-radius:999px;
  margin-bottom:7px;
}

.dbz-live-dot{
  width:7px;
  height:7px;
  border-radius:50%;
  background:#22c55e;
  box-shadow:0 0 10px #22c55e;
  animation:dbzPulse 1.5s infinite;
}

@keyframes dbzPulse{
  0%,100%{
    transform:scale(1);
    opacity:1;
  }
  50%{
    transform:scale(1.4);
    opacity:.5;
  }
}

.dbz-slide{
  display:none;
  animation:dbzFade .45s ease;
}

.dbz-slide.active{
  display:block;
}

@keyframes dbzFade{
  from{
    opacity:0;
    transform:translateY(6px);
  }
  to{
    opacity:1;
    transform:translateY(0);
  }
}

.dbz-slide h3{
  color:var(--dbz-text);
  font-size:.92rem;
  font-weight:700;
  margin-bottom:3px;
}

.dbz-slide p{
  color:var(--dbz-muted);
  font-size:.76rem;
  line-height:1.4;
}

.dbz-arrow{
  color:var(--dbz-muted);
  font-size:1.3rem;
  font-weight:900;
  transition:.3s ease;
}

.dbz-mini-card:hover .dbz-arrow{
  color:#fff;
  transform:translateX(4px);
}

/* ===== ACTION BUTTONS ===== */
.dbz-quick-actions{
  margin-top:10px;
  display:flex;
  gap:10px;
}

.dbz-action-btn{
  flex:1;
  border:none;
  border-radius:14px;
  padding:10px 14px;
  font-size:.74rem;
  font-weight:800;
  cursor:pointer;
  transition:.3s ease;
  color:#fff;
}

.dbz-open{
  background:linear-gradient(135deg,var(--dbz-accent),#0ea5e9);
}

.dbz-visit{
  background:linear-gradient(135deg,var(--dbz-pink),#8b5cf6);
}

.dbz-action-btn:hover{
  transform:translateY(-2px);
  filter:brightness(1.08);
}

/* ===== IFRAME OVERLAY ===== */
#dbzOverlay{
  position:fixed;
  inset:0;
  display:none;
  align-items:center;
  justify-content:center;
  background:rgba(0,0,0,.78);
  backdrop-filter:blur(10px);
  z-index:9999999;
  padding:18px;
}

#dbzOverlay.active{
  display:flex;
  animation:dbzFade .35s ease;
}

.dbz-frame-shell{
  width:min(1300px,100%);
  height:min(92vh,860px);
  background:#0d1117;
  border-radius:24px;
  overflow:hidden;
  position:relative;
  border:1px solid rgba(255,255,255,.08);
  box-shadow:0 25px 80px rgba(0,0,0,.6);
  display:flex;
  flex-direction:column;
}

/* ===== TOP BAR ===== */
.dbz-topbar{
  height:62px;
  background:#090d16;
  border-bottom:1px solid rgba(255,255,255,.06);
  display:flex;
  align-items:center;
  justify-content:space-between;
  padding:0 16px;
  flex-shrink:0;
}

.dbz-brand{
  display:flex;
  align-items:center;
  gap:12px;
}

.dbz-brand-icon{
  width:28px;
  height:28px;
  border-radius:12px;
  background:linear-gradient(135deg,var(--dbz-accent),var(--dbz-pink));
  display:flex;
  align-items:center;
  justify-content:center;
  color:#fff;
  font-weight:900;
}

.dbz-brand h2{
  font-size:.95rem;
  color:#fff;
  font-weight:800;
}

.dbz-brand p{
  font-size:.7rem;
  color:var(--dbz-muted);
}

.dbz-controls{
  display:flex;
  gap:10px;
}

.dbz-control-btn{
  border:none;
  padding:10px 14px;
  border-radius:12px;
  cursor:pointer;
  font-size:.72rem;
  font-weight:800;
  transition:.25s ease;
}

.dbz-fullscreen{
  background:#0ea5e9;
  color:#fff;
}

.dbz-external{
  background:#22c55e;
  color:#fff;
}

.dbz-close{
  background:#ef4444;
  color:#fff;
}

.dbz-control-btn:hover{
  transform:translateY(-1px);
}

/* ===== FRAME AREA ===== */
.dbz-frame-wrap{
  position:relative;
  flex:1;
  background:#000;
}

.dbz-loader{
  position:absolute;
  inset:0;
  display:flex;
  flex-direction:column;
  align-items:center;
  justify-content:center;
  gap:16px;
  background:#06080f;
  z-index:2;
}

.dbz-loader-ring{
  width:60px;
  height:60px;
  border-radius:50%;
  border:4px solid rgba(255,255,255,.08);
  border-top-color:var(--dbz-accent);
  animation:dbzSpin 1s linear infinite;
}

@keyframes dbzSpin{
  to{
    transform:rotate(360deg);
  }
}

.dbz-loader p{
  color:var(--dbz-muted);
  font-size:.82rem;
}

#dbzIframe{
  width:100%;
  height:100%;
  border:none;
  opacity:0;
  transition:opacity .45s ease;
}

/* ===== MINI POPUP ===== */
.dbz-toast{
  position:fixed;
  top:24px;
  right:24px;
  background:rgba(15,23,42,.92);
  border:1px solid rgba(255,255,255,.08);
  color:#fff;
  padding:14px 18px;
  border-radius:16px;
  z-index:99999999;
  display:flex;
  align-items:center;
  gap:12px;
  backdrop-filter:blur(12px);
  box-shadow:0 10px 35px rgba(0,0,0,.45);
  animation:dbzToast .6s ease;
}

@keyframes dbzToast{
  from{
    opacity:0;
    transform:translateY(-20px);
  }
  to{
    opacity:1;
    transform:translateY(0);
  }
}

.dbz-toast strong{
  display:block;
  font-size:.82rem;
}

.dbz-toast span{
  color:var(--dbz-muted);
  font-size:.72rem;
}

/* ===== MOBILE ===== */
@media(max-width:768px){

  .dbz-mini-card{
    padding:12px;
  }

  .dbz-frame-shell{
    height:95vh;
    border-radius:18px;
  }

  .dbz-topbar{
    padding:0 10px;
    height:58px;
  }

  .dbz-controls{
    gap:6px;
  }

  .dbz-control-btn{
    padding:8px 10px;
    font-size:.64rem;
  }

  .dbz-brand p{
    display:none;
  }

  .dbz-toast{
    right:12px;
    left:12px;
    top:16px;
  }
}
</style>
