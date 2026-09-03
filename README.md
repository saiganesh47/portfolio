<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Sai Ganesh M. — Data Analyst</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Sans:ital,opsz,wght@0,9..40,300;0,9..40,400;0,9..40,500;0,9..40,600;1,9..40,400&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
/* ══ RESET ══ */
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
body{font-family:'DM Sans',system-ui,sans-serif;background:#f4f1eb;color:#1a1a1a;overflow-x:hidden;cursor:none}
body.loaded #pre{opacity:0;pointer-events:none;transition:opacity .5s}
a{color:inherit;text-decoration:none}
::-webkit-scrollbar{width:3px}
::-webkit-scrollbar-track{background:#f4f1eb}
::-webkit-scrollbar-thumb{background:#5b4eff;border-radius:2px}

/* ══ VARS ══ */
:root{
  --bg:#f4f1eb;
  --bg2:#eeebe3;
  --white:#ffffff;
  --ink:#1a1a1a;
  --ink2:#444440;
  --muted:#999990;
  --purple:#5b4eff;
  --purple2:#4535dd;
  --coral:#ff4060;
  --green:#00bc7c;
  --amber:#f59e0b;
  --border:rgba(26,26,26,0.1);
  --border2:rgba(26,26,26,0.06);
  --shadow:0 2px 20px rgba(26,26,26,0.08);
  --shadow2:0 8px 40px rgba(26,26,26,0.12);
  
  --fb:'DM Sans',sans-serif;
  --fm:'JetBrains Mono',monospace;
}

/* ══ CURSOR ══ */
#cur{position:fixed;width:8px;height:8px;background:var(--purple);border-radius:50%;pointer-events:none;z-index:99999;transform:translate(-50%,-50%);transition:width .2s,height .2s,background .2s}
#cur-ring{position:fixed;width:32px;height:32px;border:1.5px solid rgba(91,78,255,0.4);border-radius:50%;pointer-events:none;z-index:99998;transform:translate(-50%,-50%);transition:left .1s,top .1s,width .25s,height .25s}
#cur.hv{width:5px;height:5px;background:var(--coral)}
#cur-ring.hv{width:48px;height:48px;border-color:rgba(255,64,96,0.3)}

/* ══ PROGRESS ══ */
#prog{position:fixed;top:0;left:0;height:3px;background:linear-gradient(90deg,var(--purple),var(--coral));z-index:9999;width:0}

/* ══ PRELOADER ══ */
#pre{position:fixed;inset:0;background:var(--bg);z-index:99997;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:8px}
.pre-logo{font-family:var(--fb);font-size:2.8rem;font-weight:800;color:var(--ink);letter-spacing:-1px;opacity:0;animation:fu .7s .2s forwards}
.pre-tag{font-family:var(--fm);font-size:.62rem;letter-spacing:.26em;color:var(--purple);opacity:0;animation:fu .5s .6s forwards}
.pre-bar-wrap{width:160px;height:2px;background:var(--border);margin-top:24px;border-radius:2px;overflow:hidden;opacity:0;animation:fu .4s .9s forwards}
.pre-bar{height:100%;background:linear-gradient(90deg,var(--purple),var(--coral));width:0;transition:width 1s}
@keyframes fu{from{opacity:0;transform:translateY(10px)}to{opacity:1;transform:none}}

/* ══ NAV ══ */
nav{
  position:fixed;top:0;left:0;right:0;z-index:1000;
  height:68px;
  background:rgba(244,241,235,0.9);backdrop-filter:blur(20px);
  border-bottom:1px solid var(--border2);
  display:flex;align-items:center;padding:0 5%;
  justify-content:space-between;
}
.nav-logo{
  font-family:var(--fb);font-size:.9rem;font-weight:800;
  color:var(--ink);letter-spacing:-.2px;
  display:flex;align-items:center;gap:10px;flex-shrink:0;
}
.nav-mark{
  width:34px;height:34px;background:var(--purple);border-radius:8px;
  display:flex;align-items:center;justify-content:center;
  font-size:.75rem;font-weight:800;color:#fff;letter-spacing:0;flex-shrink:0;
}
/* NAV LINKS — well spaced, clear */
.nav-center{
  display:flex;align-items:center;gap:0;
  background:var(--white);border:1px solid var(--border);
  border-radius:100px;padding:6px 8px;
}
.nav-center a{
  font-size:.7rem;font-weight:600;letter-spacing:.04em;
  color:var(--ink2);padding:7px 16px;border-radius:100px;
  transition:background .2s,color .2s;white-space:nowrap;
}
.nav-center a:hover{color:var(--purple)}
.nav-center a.active{background:var(--purple);color:#fff}
.nav-right{display:flex;align-items:center;gap:12px;flex-shrink:0}
#nav-clk{font-family:var(--fm);font-size:.62rem;color:var(--muted);letter-spacing:.06em}
.nav-hire{
  padding:9px 22px;background:var(--ink);color:#fff;
  font-size:.72rem;font-weight:700;letter-spacing:.06em;
  border-radius:100px;transition:background .2s,transform .2s;cursor:none;
}
.nav-hire:hover{background:var(--purple);transform:translateY(-1px)}
.nav-ham{display:none;background:none;border:none;cursor:none;padding:6px;color:var(--ink)}

/* MOBILE NAV */
#mnav{display:none;position:fixed;inset:0;background:var(--bg);z-index:9996;flex-direction:column;align-items:center;justify-content:center;gap:24px}
#mnav.op{display:flex}
#mnav a{font-family:var(--fb);font-size:2.2rem;font-weight:800;color:var(--ink);transition:color .2s}
#mnav a:hover{color:var(--purple)}
#mnav-x{position:absolute;top:24px;right:5%;background:none;border:none;cursor:none;font-size:1.4rem;color:var(--muted)}

/* ══ RIGHT SCROLL SPY ══ */
#spy{
  position:fixed;right:28px;top:50%;transform:translateY(-50%);
  display:flex;flex-direction:column;gap:12px;z-index:500;
}
.spy-dot{
  width:6px;height:6px;border-radius:50%;
  border:1.5px solid var(--muted);background:transparent;
  transition:background .3s,border-color .3s,transform .3s;
  position:relative;cursor:none;
}
.spy-dot.active{background:var(--purple);border-color:var(--purple);transform:scale(1.5)}
.spy-dot:hover::after{
  content:attr(data-label);position:absolute;right:16px;top:50%;transform:translateY(-50%);
  background:var(--ink);color:#fff;padding:3px 10px;border-radius:4px;
  font-size:.6rem;font-family:var(--fm);white-space:nowrap;letter-spacing:.06em;
}

/* ══ HERO ══ */
#hero{
  min-height:100vh;display:grid;grid-template-rows:1fr auto;
  padding:100px 5% 60px;position:relative;overflow:hidden;
}
.hero-bg-grid{
  position:absolute;inset:0;
  background-image:radial-gradient(circle,rgba(91,78,255,0.04) 1px,transparent 1px);
  background-size:36px 36px;z-index:0;pointer-events:none;
}
.hero-blob{
  position:absolute;top:-20%;right:-10%;width:60vw;height:60vw;
  border-radius:50%;
  background:radial-gradient(circle,rgba(91,78,255,0.08) 0%,transparent 65%);
  pointer-events:none;z-index:0;
}
.hero-content{position:relative;z-index:1;display:grid;grid-template-columns:1fr auto;gap:60px;align-items:end}
.hero-left{}
.hero-badge{
  display:inline-flex;align-items:center;gap:8px;
  background:var(--white);border:1px solid var(--border);
  padding:7px 16px;border-radius:100px;margin-bottom:28px;
  font-size:.65rem;font-weight:600;letter-spacing:.14em;color:var(--green);
  box-shadow:var(--shadow);
}
.hero-badge-dot{width:7px;height:7px;background:var(--green);border-radius:50%;box-shadow:0 0 0 0 rgba(0,188,124,.4);animation:gp 2s infinite}
@keyframes gp{0%{box-shadow:0 0 0 0 rgba(0,188,124,.4)}70%{box-shadow:0 0 0 8px rgba(0,188,124,0)}100%{box-shadow:0 0 0 0 rgba(0,188,124,0)}}
.hero-name{
  font-family:var(--fb);font-size:clamp(3rem,7.5vw,7rem);
  font-weight:800;line-height:.9;letter-spacing:-3px;color:var(--ink);
  margin-bottom:0;overflow:hidden;
}
.hero-name-line{display:block;transform:translateY(110%);opacity:0;animation:nameUp .8s cubic-bezier(.16,1,.3,1) forwards}
.hero-name-line:nth-child(1){animation-delay:.3s}
.hero-name-line:nth-child(2){animation-delay:.45s;color:var(--purple)}
.hero-name-line:nth-child(3){animation-delay:.6s}
@keyframes nameUp{to{transform:none;opacity:1}}
.hero-divider{display:flex;align-items:center;gap:14px;margin:24px 0 20px;opacity:0;animation:fu .6s .9s forwards}
.hero-div-line{height:2px;width:36px;background:var(--purple);flex-shrink:0}
.hero-role{font-family:var(--fm);font-size:.7rem;letter-spacing:.18em;color:var(--muted);text-transform:uppercase;display:flex;flex-direction:column;gap:3px}
.hero-role-type{color:var(--purple);font-size:.72rem;letter-spacing:.16em}
#ht{color:var(--purple)}
#ht::after{content:'|';animation:bl .8s step-end infinite}
@keyframes bl{50%{opacity:0}}
.hero-desc{max-width:460px;font-size:.95rem;line-height:1.8;color:var(--ink2);opacity:0;animation:fu .6s 1s forwards}
.hero-desc strong{color:var(--ink)}
.hero-btns{display:flex;gap:12px;margin-top:32px;flex-wrap:wrap;opacity:0;animation:fu .6s 1.1s forwards}
.btn-filled{
  padding:13px 30px;background:var(--purple);color:#fff;
  font-size:.78rem;font-weight:700;letter-spacing:.06em;border-radius:100px;
  display:inline-flex;align-items:center;gap:8px;cursor:none;
  transition:background .2s,transform .2s,box-shadow .2s;
}
.btn-filled:hover{background:var(--purple2);transform:translateY(-2px);box-shadow:0 8px 24px rgba(91,78,255,0.35)}
.btn-line{
  padding:13px 30px;border:1.5px solid var(--border);color:var(--ink2);
  font-size:.78rem;font-weight:600;letter-spacing:.06em;border-radius:100px;
  display:inline-flex;align-items:center;gap:8px;cursor:none;
  transition:border-color .2s,color .2s;background:var(--white);
}
.btn-line:hover{border-color:var(--purple);color:var(--purple)}
.hero-socials{display:flex;gap:10px;margin-top:24px;opacity:0;animation:fu .6s 1.2s forwards}
.hero-socials a{
  width:38px;height:38px;background:var(--white);border:1px solid var(--border);
  border-radius:10px;display:flex;align-items:center;justify-content:center;
  color:var(--muted);transition:border-color .2s,color .2s,box-shadow .2s;box-shadow:var(--shadow);
}
.hero-socials a:hover{border-color:var(--purple);color:var(--purple);box-shadow:0 4px 16px rgba(91,78,255,0.2)}
/* Hero Right — metric stack */
.hero-right{
  display:grid;grid-template-columns:1fr 1fr;gap:12px;
  opacity:0;animation:fu .8s 1s forwards;
}
.hm{
  background:var(--white);border:1px solid var(--border);
  border-radius:16px;padding:18px 20px;box-shadow:var(--shadow);
  position:relative;overflow:hidden;
}
.hm::after{content:'';position:absolute;bottom:0;left:0;right:0;height:3px}
.hm:nth-child(1)::after{background:var(--purple)}
.hm:nth-child(2)::after{background:var(--green)}
.hm:nth-child(3)::after{background:var(--coral)}
.hm:nth-child(4)::after{background:var(--amber)}
.hm-val{
  font-family:var(--fb);font-size:1.6rem;font-weight:800;
  color:var(--ink);line-height:1;letter-spacing:-.5px;
  display:inline-flex;align-items:baseline;gap:2px;
}
.hm-val sup{font-size:.8rem;font-family:var(--fb);font-weight:700;line-height:1}
.hm:nth-child(1) .hm-val sup{color:var(--purple)}
.hm:nth-child(2) .hm-val sup{color:var(--green)}
.hm:nth-child(3) .hm-val sup{color:var(--coral)}
.hm:nth-child(4) .hm-val sup{color:var(--amber)}
.hm-label{font-size:.58rem;color:var(--muted);letter-spacing:.12em;text-transform:uppercase;margin-top:5px;font-family:var(--fm)}
/* Hero bottom scroll hint */
.hero-bottom{
  position:relative;z-index:1;
  display:flex;align-items:center;justify-content:center;
  padding-top:48px;gap:12px;
  font-size:.6rem;letter-spacing:.24em;color:var(--muted);text-transform:uppercase;
  opacity:0;animation:fu .6s 1.4s forwards;
}
.scroll-arrow{animation:sa 1.5s ease infinite}
@keyframes sa{0%,100%{transform:translateY(0)}50%{transform:translateY(5px)}}

/* ══ SECTION COMMON ══ */
section{padding:96px 5%;width:100%;position:relative}
.sec-label{
  font-family:var(--fm);font-size:.6rem;letter-spacing:.26em;text-transform:uppercase;
  color:var(--purple);display:flex;align-items:center;gap:10px;margin-bottom:12px;
}
.sec-label::before{content:'';width:20px;height:1.5px;background:var(--purple)}
.sec-title{
  font-family:var(--fb);font-size:clamp(1.8rem,3.5vw,3rem);
  font-weight:800;color:var(--ink);line-height:.95;letter-spacing:-1px;margin-bottom:48px;
}
.sec-title span{color:var(--purple)}
.rv{opacity:0;transform:translateY(22px);transition:opacity .65s,transform .65s}
.rv.v{opacity:1;transform:none}
/* Section divider */
.sec-divider{width:100%;height:1px;background:var(--border2)}

/* ══ ABOUT ══ */
#about{background:var(--white)}
.about-wrap{display:grid;grid-template-columns:1fr 1fr;gap:80px;align-items:start}
.about-pull{
  font-family:var(--fb);font-size:1.1rem;font-weight:700;
  color:var(--ink);line-height:1.5;
  border-left:3px solid var(--purple);padding-left:20px;
  margin-bottom:32px;
}
.about-body p{font-size:.9rem;color:var(--ink2);line-height:1.9;margin-bottom:14px}
.about-body strong{color:var(--ink)}
.about-body em{color:var(--purple);font-style:normal;font-weight:600}
.about-info{display:grid;grid-template-columns:1fr 1fr;gap:10px;margin-top:28px}
.info-box{
  padding:14px 16px;background:var(--bg);border:1px solid var(--border2);border-radius:12px;
}
.info-box-label{font-family:var(--fm);font-size:.56rem;letter-spacing:.18em;text-transform:uppercase;color:var(--muted);margin-bottom:4px}
.info-box-val{font-size:.82rem;font-weight:600;color:var(--ink)}
/* About right — stat rows */
.about-stats{display:flex;flex-direction:column}
.about-stats{display:grid;grid-template-columns:1fr 1fr;gap:12px}
.astat{
  background:var(--bg);border:1px solid var(--border2);border-radius:16px;
  padding:20px 22px;display:flex;flex-direction:column;gap:8px;
  border-bottom:3px solid var(--border2);
  transition:box-shadow .25s,transform .25s;
}
.astat:hover{box-shadow:0 6px 24px rgba(26,26,26,0.08);transform:translateY(-2px)}
.astat:nth-child(1){border-bottom-color:var(--purple)}
.astat:nth-child(2){border-bottom-color:var(--green)}
.astat:nth-child(3){border-bottom-color:var(--coral)}
.astat:nth-child(4){border-bottom-color:var(--amber)}
.astat-num{
  font-family:var(--fb);font-size:2rem;font-weight:800;
  color:var(--ink);letter-spacing:-1px;line-height:1;
}
.astat-num span{font-size:1.1rem}
.astat:nth-child(1) .astat-num span{color:var(--purple)}
.astat:nth-child(2) .astat-num span{color:var(--green)}
.astat:nth-child(3) .astat-num span{color:var(--coral)}
.astat:nth-child(4) .astat-num span{color:var(--amber)}
.astat-text strong{display:block;font-size:.82rem;color:var(--ink);margin-bottom:2px;font-weight:600}
.astat-text p{font-size:.7rem;color:var(--muted);line-height:1.55}

/* ══ EXPERIENCE ══ */
#experience{background:var(--bg)}
.exp-wrap{max-width:860px}
.exp-card{
  background:var(--white);border:1px solid var(--border2);
  border-radius:20px;padding:36px;margin-bottom:20px;
  box-shadow:var(--shadow);transition:box-shadow .3s,transform .3s;
}
.exp-card:hover{box-shadow:var(--shadow2);transform:translateY(-2px)}
.exp-card-head{display:flex;align-items:flex-start;justify-content:space-between;gap:20px;margin-bottom:24px;flex-wrap:wrap}
.exp-card-left{}
.exp-role{font-family:var(--fb);font-size:1.15rem;font-weight:800;color:var(--ink);letter-spacing:-.3px;margin-bottom:4px}
.exp-company{font-size:.82rem;color:var(--purple);font-weight:600}
.exp-meta-right{text-align:right;flex-shrink:0}
.exp-date{font-family:var(--fm);font-size:.62rem;color:var(--muted);letter-spacing:.06em;margin-bottom:8px}
.exp-badge{
  display:inline-block;padding:4px 14px;border-radius:100px;
  font-size:.6rem;font-weight:700;letter-spacing:.12em;text-transform:uppercase;
  background:rgba(91,78,255,0.09);border:1px solid rgba(91,78,255,0.2);color:var(--purple);
}
.exp-divider{width:100%;height:1px;background:var(--border2);margin-bottom:22px}
.exp-bullets{list-style:none;display:flex;flex-direction:column;gap:0}
.exp-bullets li{
  display:grid;grid-template-columns:auto 1fr;gap:14px;
  padding:13px 0;border-bottom:1px solid var(--border2);
  font-size:.83rem;color:var(--ink2);line-height:1.75;align-items:start;
}
.exp-bullets li:last-child{border-bottom:none}
.ebadge{
  display:inline-flex;padding:3px 11px;border-radius:100px;
  font-family:var(--fm);font-size:.6rem;font-weight:700;
  letter-spacing:.05em;white-space:nowrap;margin-top:3px;flex-shrink:0;
  background:rgba(91,78,255,0.08);border:1px solid rgba(91,78,255,0.2);color:var(--purple);
}
.ebadge.g{background:rgba(0,188,124,0.08);border-color:rgba(0,188,124,0.2);color:var(--green)}
.ebadge.r{background:rgba(255,64,96,0.08);border-color:rgba(255,64,96,0.2);color:var(--coral)}
.exp-bullets li strong{color:var(--ink)}
.exp-tags{display:flex;flex-wrap:wrap;gap:7px;margin-top:20px}
.etag{
  font-family:var(--fm);font-size:.58rem;padding:4px 12px;
  border-radius:100px;background:var(--bg);border:1px solid var(--border2);color:var(--muted);
}

/* ══ PROJECTS ══ */
#projects{background:var(--white)}
.proj-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(300px,1fr));gap:20px}
.proj-card{
  background:var(--bg);border:1px solid var(--border2);border-radius:20px;
  overflow:hidden;cursor:none;
  transition:transform .35s cubic-bezier(.16,1,.3,1),box-shadow .35s,border-color .35s;
}
.proj-card:hover{transform:translateY(-8px);box-shadow:var(--shadow2);border-color:rgba(91,78,255,0.25)}
.proj-top-bar{height:4px}
.proj-card:nth-child(1) .proj-top-bar{background:linear-gradient(90deg,var(--purple),#a78bfa)}
.proj-card:nth-child(2) .proj-top-bar{background:linear-gradient(90deg,var(--coral),var(--amber))}
.proj-card:nth-child(3) .proj-top-bar{background:linear-gradient(90deg,var(--green),#34d399)}
.proj-card:nth-child(4) .proj-top-bar{background:linear-gradient(90deg,#6366f1,var(--purple))}
.proj-card:nth-child(5) .proj-top-bar{background:linear-gradient(90deg,var(--coral),#f43f5e)}
.proj-card:nth-child(6) .proj-top-bar{background:linear-gradient(90deg,var(--amber),#fb923c)}
.proj-card:nth-child(7) .proj-top-bar{background:linear-gradient(90deg,var(--green),var(--purple))}
.proj-body{padding:24px}
.proj-num{font-family:var(--fm);font-size:.6rem;color:var(--muted);letter-spacing:.14em;margin-bottom:14px}
.proj-name{font-family:var(--fb);font-size:.92rem;font-weight:800;color:var(--ink);margin-bottom:6px;line-height:1.3;letter-spacing:-.2px}
.proj-metric{font-family:var(--fm);font-size:.6rem;color:var(--purple);letter-spacing:.08em;margin-bottom:12px}
.proj-card:nth-child(2) .proj-metric{color:var(--coral)}
.proj-card:nth-child(3) .proj-metric{color:var(--green)}
.proj-desc{font-size:.8rem;color:var(--ink2);line-height:1.7;margin-bottom:18px}
.proj-foot{display:flex;align-items:center;justify-content:space-between}
.proj-tags{display:flex;flex-wrap:wrap;gap:5px}
.ptag{font-family:var(--fm);font-size:.54rem;padding:3px 8px;border-radius:100px;background:var(--white);border:1px solid var(--border);color:var(--muted)}
.proj-btn{
  width:32px;height:32px;background:var(--white);border:1px solid var(--border);
  border-radius:8px;display:flex;align-items:center;justify-content:center;
  color:var(--muted);flex-shrink:0;
  transition:background .2s,border-color .2s,color .2s;
}
.proj-card:hover .proj-btn{background:var(--purple);border-color:var(--purple);color:#fff}

/* ══ SKILLS ══ */
#skills{background:var(--bg)}
.skills-wrap{display:grid;grid-template-columns:1fr 1fr;gap:72px;align-items:start}
.skill-group{margin-bottom:40px}
.skill-group-title{
  font-family:var(--fm);font-size:.6rem;letter-spacing:.22em;
  text-transform:uppercase;color:var(--muted);
  padding-bottom:12px;margin-bottom:18px;
  border-bottom:1.5px solid var(--border2);
  display:flex;align-items:center;justify-content:space-between;
}
.skill-row{display:flex;align-items:center;justify-content:space-between;padding:11px 0;border-bottom:1px solid var(--border2)}
.skill-row:last-child{border-bottom:none}
.skill-name{font-size:.84rem;color:var(--ink);font-weight:500}
.skill-bar-wrap{display:flex;align-items:center;gap:10px}
.skill-bar-bg{width:100px;height:4px;background:var(--border);border-radius:2px;overflow:hidden}
.skill-bar-fill{height:100%;border-radius:2px;width:0;transition:width 1.2s cubic-bezier(.16,1,.3,1)}
.skill-bar-fill.p{background:var(--purple)}
.skill-bar-fill.g{background:var(--green)}
.skill-bar-fill.c{background:var(--coral)}
.skill-bar-fill.a{background:var(--amber)}
.skill-pct{font-family:var(--fm);font-size:.6rem;color:var(--muted);width:28px;text-align:right}
/* Soft skills right */
.soft-grid{display:grid;grid-template-columns:1fr 1fr;gap:10px;margin-bottom:36px}
.soft-card{
  background:var(--white);border:1px solid var(--border2);border-radius:14px;
  padding:16px;transition:border-color .25s,box-shadow .25s;
}
.soft-card:hover{border-color:rgba(91,78,255,0.25);box-shadow:0 4px 16px rgba(91,78,255,0.08)}
.soft-icon{font-size:1.3rem;margin-bottom:7px}
.soft-name{font-size:.8rem;font-weight:600;color:var(--ink);margin-bottom:2px}
.soft-desc{font-size:.68rem;color:var(--muted);line-height:1.5}
.tools-label{font-family:var(--fm);font-size:.6rem;letter-spacing:.22em;text-transform:uppercase;color:var(--muted);margin-bottom:12px;padding-bottom:10px;border-bottom:1.5px solid var(--border2)}
.tools-wrap{display:flex;flex-wrap:wrap;gap:8px}
.tool-pill{
  padding:6px 16px;background:var(--white);border:1px solid var(--border2);
  color:var(--ink2);font-size:.74rem;font-weight:500;border-radius:100px;
  transition:border-color .2s,color .2s,background .2s;
}
.tool-pill:hover{border-color:var(--purple);color:var(--purple);background:rgba(91,78,255,0.04)}

/* ══ EDUCATION ══ */
#education{background:var(--white)}
.edu-wrap{display:grid;grid-template-columns:1fr 1fr;gap:60px;align-items:start}
.edu-card{
  background:var(--bg);border:1px solid var(--border2);border-radius:20px;
  padding:32px;position:relative;overflow:hidden;
}
.edu-card::before{
  content:'';position:absolute;top:0;left:0;width:4px;bottom:0;
  background:linear-gradient(to bottom,var(--purple),var(--coral));
}
.edu-degree{font-family:var(--fb);font-size:1.15rem;font-weight:800;color:var(--ink);letter-spacing:-.3px;margin-bottom:4px}
.edu-field{font-size:.82rem;color:var(--purple);font-weight:600;margin-bottom:4px}
.edu-inst{font-size:.77rem;color:var(--muted);margin-bottom:20px}
.edu-cgpa-badge{
  display:inline-flex;align-items:baseline;gap:6px;
  background:rgba(0,188,124,0.08);border:1px solid rgba(0,188,124,0.2);
  padding:8px 18px;border-radius:100px;margin-bottom:16px;
}
.edu-cgpa-val{font-family:var(--fb);font-size:1.25rem;font-weight:800;color:var(--green);letter-spacing:-.3px}
.edu-cgpa-lbl{font-size:.6rem;letter-spacing:.14em;text-transform:uppercase;color:rgba(0,188,124,0.7);font-family:var(--fm)}
.edu-year{font-family:var(--fm);font-size:.62rem;color:var(--muted);margin-bottom:18px}
.course-head{font-family:var(--fm);font-size:.58rem;letter-spacing:.18em;text-transform:uppercase;color:var(--muted);margin-bottom:10px}
.course-chips{display:flex;flex-wrap:wrap;gap:7px}
.course-chip{font-size:.63rem;padding:4px 12px;border-radius:100px;background:var(--white);border:1px solid var(--border2);color:var(--muted)}
.certs-wrap{display:flex;flex-direction:column;gap:14px}
.cert-card{
  background:var(--bg);border:1px solid var(--border2);border-radius:16px;
  padding:18px 20px;display:grid;grid-template-columns:44px 1fr auto;gap:14px;
  align-items:center;transition:border-color .25s,transform .25s;
}
.cert-card:hover{border-color:rgba(91,78,255,0.25);transform:translateX(4px)}
.cert-icon{
  width:44px;height:44px;border-radius:12px;
  display:flex;align-items:center;justify-content:center;font-size:.95rem;
}
.cert-icon.ib{background:rgba(100,150,255,.1);border:1px solid rgba(100,150,255,.18);color:#6496ff}
.cert-icon.go{background:rgba(91,78,255,.1);border:1px solid rgba(91,78,255,.18);color:var(--purple)}
.cert-name{font-size:.86rem;font-weight:600;color:var(--ink);margin-bottom:2px}
.cert-from{font-size:.72rem;color:var(--muted)}
.cert-link{font-family:var(--fm);font-size:.6rem;color:var(--purple);display:flex;align-items:center;gap:4px;white-space:nowrap}
.cert-link:hover{text-decoration:underline}
.open-card{
  margin-top:6px;padding:18px 20px;
  background:rgba(91,78,255,0.05);border:1px solid rgba(91,78,255,0.14);
  border-radius:16px;
}
.oc-label{font-family:var(--fm);font-size:.58px;letter-spacing:.16em;text-transform:uppercase;color:var(--purple);font-size:.58rem;margin-bottom:7px}
.oc-roles{font-family:var(--fb);font-size:.95rem;font-weight:700;color:var(--ink);margin-bottom:5px}
.oc-note{font-size:.76rem;color:var(--muted);line-height:1.6}

/* ══ CONTACT ══ */
#contact{background:var(--bg);padding:100px 5%}
.contact-wrap{display:grid;grid-template-columns:1fr 1fr;gap:80px;align-items:start}
.contact-left{}
.contact-big{font-family:var(--fb);font-size:clamp(2rem,4vw,3.5rem);font-weight:800;color:var(--ink);line-height:.95;letter-spacing:-1px;margin-bottom:20px}
.contact-big span{color:var(--purple)}
.contact-sub{font-size:.9rem;color:var(--ink2);line-height:1.8;max-width:380px;margin-bottom:36px}
.contact-links{display:flex;flex-direction:column;gap:12px}
.clink{
  display:flex;align-items:center;gap:14px;
  background:var(--white);border:1px solid var(--border2);border-radius:14px;
  padding:14px 18px;transition:border-color .25s,transform .25s;box-shadow:var(--shadow);
}
.clink:hover{border-color:rgba(91,78,255,0.25);transform:translateX(5px)}
.clink-icon{
  width:38px;height:38px;border-radius:10px;flex-shrink:0;
  display:flex;align-items:center;justify-content:center;font-size:.88rem;
}
.clink-icon.ml{background:rgba(91,78,255,.08);border:1px solid rgba(91,78,255,.15);color:var(--purple)}
.clink-icon.li{background:rgba(100,150,255,.08);border:1px solid rgba(100,150,255,.15);color:#6496ff}
.clink-icon.gh{background:rgba(26,26,26,.06);border:1px solid var(--border);color:var(--ink)}
.clink-label{font-family:var(--fm);font-size:.56rem;letter-spacing:.16em;text-transform:uppercase;color:var(--muted);margin-bottom:2px}
.clink-val{font-size:.82rem;font-weight:600;color:var(--ink)}
/* Form */
.contact-form{
  background:var(--white);border:1px solid var(--border2);
  border-radius:24px;padding:36px;box-shadow:var(--shadow2);
}
.form-row{margin-bottom:14px}
.form-2col{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:14px}
label{font-family:var(--fm);font-size:.58rem;letter-spacing:.16em;text-transform:uppercase;color:var(--muted);display:block;margin-bottom:7px}
input.fi,textarea.fi{
  width:100%;background:var(--bg);border:1.5px solid var(--border2);
  border-radius:12px;padding:12px 15px;font-size:.83rem;color:var(--ink);
  font-family:var(--fb);outline:none;transition:border-color .2s,box-shadow .2s;
}
input.fi:focus,textarea.fi:focus{border-color:var(--purple);box-shadow:0 0 0 3px rgba(91,78,255,0.1)}
input.fi::placeholder,textarea.fi::placeholder{color:var(--muted)}
textarea.fi{resize:none;height:110px}
.form-submit{
  width:100%;padding:14px;background:var(--purple);color:#fff;
  font-weight:700;font-size:.78rem;letter-spacing:.1em;
  border:none;border-radius:100px;cursor:none;font-family:var(--fb);
  transition:background .2s,transform .2s,box-shadow .2s;
  display:flex;align-items:center;justify-content:center;gap:9px;
}
.form-submit:hover{background:var(--purple2);transform:translateY(-1px);box-shadow:0 8px 24px rgba(91,78,255,.3)}

/* ══ FOOTER ══ */
footer{
  background:var(--ink);padding:28px 5%;
  display:flex;align-items:center;justify-content:space-between;flex-wrap:wrap;gap:14px;
}
.foot-copy{font-size:.7rem;color:rgba(255,255,255,.4)}
.foot-copy span{color:rgba(91,78,255,.9)}
.foot-nav{display:flex;gap:20px}
.foot-nav a{font-size:.68rem;color:rgba(255,255,255,.4);transition:color .2s}
.foot-nav a:hover{color:#fff}

/* ══ PROJECT MODAL ══ */
#modal{
  position:fixed;inset:0;background:rgba(26,26,26,0.75);backdrop-filter:blur(12px);
  z-index:9990;display:flex;align-items:center;justify-content:center;padding:24px;
  opacity:0;pointer-events:none;transition:opacity .3s;
}
#modal.open{opacity:1;pointer-events:all}
.modal-box{
  background:var(--white);border-radius:24px;padding:40px;
  max-width:600px;width:100%;max-height:90vh;overflow-y:auto;
  box-shadow:0 32px 80px rgba(26,26,26,0.25);
  transform:translateY(16px);transition:transform .3s;
}
#modal.open .modal-box{transform:none}
.modal-ey{font-family:var(--fm);font-size:.6rem;letter-spacing:.2em;color:var(--purple);margin-bottom:7px}
.modal-title{font-family:var(--fb);font-size:1.5rem;font-weight:800;color:var(--ink);letter-spacing:-.3px;margin-bottom:5px}
.modal-metric{font-family:var(--fm);font-size:.66rem;color:var(--green);letter-spacing:.06em;margin-bottom:20px}
.modal-bullets{list-style:none;display:flex;flex-direction:column;gap:11px;margin-bottom:20px}
.modal-bullets li{display:grid;grid-template-columns:18px 1fr;gap:10px;font-size:.84rem;color:var(--ink2);line-height:1.7;align-items:start}
.modal-bullets li::before{content:'→';color:var(--purple);margin-top:2px;font-size:.8rem}
.modal-bullets li strong{color:var(--ink)}
.modal-tags{display:flex;flex-wrap:wrap;gap:7px;margin-bottom:24px}
.modal-actions{display:flex;gap:10px}
.modal-close{background:none;border:1.5px solid var(--border);color:var(--muted);border-radius:100px;padding:8px 22px;font-size:.7rem;letter-spacing:.1em;text-transform:uppercase;cursor:none;transition:border-color .2s,color .2s;font-family:var(--fb);font-weight:600}
.modal-close:hover{border-color:var(--coral);color:var(--coral)}
.modal-gh{display:inline-flex;align-items:center;gap:7px;font-size:.74rem;font-weight:700;padding:8px 22px;background:var(--purple);color:#fff;border-radius:100px;transition:background .2s}
.modal-gh:hover{background:var(--purple2)}

/* ══ RESPONSIVE ══ */
@media(max-width:920px){
  .hero-content{grid-template-columns:1fr}
  .hero-right{flex-direction:row;flex-wrap:wrap}
  .hm{padding:14px 16px}
  .about-wrap,.skills-wrap,.edu-wrap,.contact-wrap{grid-template-columns:1fr;gap:40px}
  .nav-center{display:none}
  .nav-ham{display:block}
  #spy{display:none}
  .form-2col{grid-template-columns:1fr}
}
@media(max-width:600px){
  section{padding:72px 5%}
  nav{padding:0 5%;height:60px}
  .hero-name{font-size:clamp(2.2rem,10vw,4rem)}
  .sec-title{font-size:1.6rem}
  .soft-grid{grid-template-columns:1fr}
  .proj-grid{grid-template-columns:1fr}
  .contact-form{padding:24px}
  footer{padding:22px 5%}
}
</style>
</head>
<body>

<!-- PRELOADER -->
<div id="pre">
  <div class="pre-logo">Sai Ganesh M.</div>
  <div class="pre-tag">Data Analyst Portfolio</div>
  <div class="pre-bar-wrap"><div class="pre-bar" id="pb"></div></div>
</div>

<!-- CURSOR -->
<div id="cur"></div>
<div id="cur-ring"></div>
<div id="prog"></div>

<!-- SCROLL SPY DOTS -->
<div id="spy">
  <div class="spy-dot active" data-sec="hero" data-label="HOME"></div>
  <div class="spy-dot" data-sec="about" data-label="ABOUT"></div>
  <div class="spy-dot" data-sec="experience" data-label="EXPERIENCE"></div>
  <div class="spy-dot" data-sec="projects" data-label="PROJECTS"></div>
  <div class="spy-dot" data-sec="skills" data-label="SKILLS"></div>
  <div class="spy-dot" data-sec="education" data-label="EDUCATION"></div>
  <div class="spy-dot" data-sec="contact" data-label="CONTACT"></div>
</div>

<!-- MOBILE NAV -->
<div id="mnav">
  <button id="mnav-x" onclick="cmn()">✕</button>
  <a href="#hero" onclick="cmn()">Home</a>
  <a href="#about" onclick="cmn()">About</a>
  <a href="#experience" onclick="cmn()">Experience</a>
  <a href="#projects" onclick="cmn()">Projects</a>
  <a href="#skills" onclick="cmn()">Skills</a>
  <a href="#education" onclick="cmn()">Education</a>
  <a href="#contact" onclick="cmn()">Contact</a>
</div>

<!-- NAV -->
<nav>
  <div class="nav-logo">
    <div class="nav-mark">SG</div>
    Sai Ganesh M.
  </div>
  <div class="nav-center">
    <a href="#about" data-nav="about">About</a>
    <a href="#experience" data-nav="experience">Experience</a>
    <a href="#projects" data-nav="projects">Projects</a>
    <a href="#skills" data-nav="skills">Skills</a>
    <a href="#education" data-nav="education">Education</a>
    <a href="#contact" data-nav="contact">Contact</a>
  </div>
  <div class="nav-right">
    <span id="nav-clk"></span>
    <a href="#contact" class="nav-hire">Hire Me</a>
    <button class="nav-ham" onclick="omn()">
      <svg width="20" height="14" viewBox="0 0 20 14" fill="none">
        <rect width="20" height="2" rx="1" fill="currentColor"/>
        <rect y="6" width="14" height="2" rx="1" fill="currentColor"/>
        <rect y="12" width="20" height="2" rx="1" fill="currentColor"/>
      </svg>
    </button>
  </div>
</nav>

<!-- ════════ HERO ════════ -->
<section id="hero">
  <div class="hero-bg-grid"></div>
  <div class="hero-blob"></div>
  <div class="hero-content">
    <div class="hero-left">
      <div class="hero-badge">
        <span class="hero-badge-dot"></span>
        OPEN TO OPPORTUNITIES
      </div>
      <div class="hero-name">
        <span class="hero-name-line">SAI</span>
        <span class="hero-name-line">GANESH</span>
        <span class="hero-name-line">M.</span>
      </div>
      <div class="hero-divider">
        <div class="hero-div-line"></div>
        <div class="hero-role">
            <span class="hero-role-type"><span id="ht">Data Analyst</span></span>
            <span>Hyderabad, Telangana</span>
          </div>
      </div>
      <p class="hero-desc">
        Turning <strong>raw data into powerful decisions</strong> through Python, SQL, Power BI &amp; Machine Learning.
        <strong>2 internships</strong>, <strong>7+ end-to-end projects</strong>, B.Tech in AI &amp; ML — 2025.
      </p>
      <div class="hero-btns">
        <a href="#projects" class="btn-filled">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M5 9.2h3V19H5zM10.6 5h2.8v14h-2.8zm5.6 8H19v6h-2.8z"/></svg>
          View Projects
        </a>
        <a href="#contact" class="btn-line">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M2.01 21L23 12 2.01 3 2 10l15 2-15 2z"/></svg>
          Let's Talk
        </a>
        <a href="#" onclick="dlr();return false" class="btn-line">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M19 9h-4V3H9v6H5l7 7 7-7zM5 18v2h14v-2H5z"/></svg>
          Resume
        </a>
      </div>
      <div class="hero-socials">
        <a href="https://www.linkedin.com/in/saiganeshanalyst/" target="_blank" title="LinkedIn">
          <svg width="15" height="15" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        </a>
        <a href="https://github.com/saiganesh47" target="_blank" title="GitHub">
          <svg width="15" height="15" viewBox="0 0 24 24" fill="currentColor"><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"/></svg>
        </a>
        <a href="mailto:saiganesh.maganti@gmail.com" title="Email">
          <svg width="15" height="15" viewBox="0 0 24 24" fill="currentColor"><path d="M20 4H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/></svg>
        </a>
      </div>
    </div>
    <div class="hero-right">
      <div class="hm">
        <div class="hm-val"><span class="cnt" data-t="7">0</span><sup>+</sup></div>
        <div class="hm-label">Projects</div>
      </div>
      <div class="hm">
        <div class="hm-val"><span class="cnt" data-t="98">0</span><sup>%</sup></div>
        <div class="hm-label">Best Accuracy</div>
      </div>
      <div class="hm">
        <div class="hm-val">8.01</div>
        <div class="hm-label">CGPA</div>
      </div>
      <div class="hm">
        <div class="hm-val"><span class="cnt" data-t="2">0</span></div>
        <div class="hm-label">Internships</div>
      </div>
    </div>
  </div>
  <div class="hero-bottom">
    <svg class="scroll-arrow" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 5v14M5 12l7 7 7-7"/></svg>
    <span>Scroll to explore</span>
  </div>
</section>
<div class="sec-divider"></div>

<!-- ════════ ABOUT ════════ -->
<section id="about">
  <div class="sec-label rv">01 — About Me</div>
  <div class="about-wrap">
    <div class="rv">
      <h2 class="sec-title" style="margin-bottom:28px">The story<br>behind<br><span>the data</span></h2>
      <div class="about-pull">"I don't just analyze data — I make it tell a story that drives real decisions."</div>
      <div class="about-body">
        <p>I'm <strong>Sai Ganesh M.</strong>, a Data Analyst from <em>Hyderabad, Telangana</em> with a B.Tech in Artificial Intelligence &amp; Machine Learning (2025).</p>
        <p>From building ML models at <strong>98% accuracy</strong> to designing Power BI dashboards that improve collection rates by <strong>25%</strong>, I deliver measurable impact at every step.</p>
        <p>My edge: <strong>statistical rigor</strong> + <strong>business intuition</strong> + the ability to communicate insights to any audience.</p>
      </div>
      <div class="about-info">
        <div class="info-box"><div class="info-box-label">Location</div><div class="info-box-val">Hyderabad, Telangana</div></div>
        <div class="info-box"><div class="info-box-label">Degree</div><div class="info-box-val">B.Tech AI &amp; ML, 2025</div></div>
        <div class="info-box"><div class="info-box-label">Email</div><div class="info-box-val" style="font-size:.72rem">saiganesh.maganti@gmail.com</div></div>
        <div class="info-box" style="border-color:rgba(0,188,124,0.25)"><div class="info-box-label">Status</div><div class="info-box-val" style="color:var(--green)">● Open to Work</div></div>
      </div>
    </div>
    <div class="about-stats rv" style="transition-delay:.12s">
      <div class="astat"><div class="astat-num"><span class="cnt" data-t="7">0</span><span>+</span></div><div class="astat-text"><strong>Projects Completed</strong><p>ML models, BI dashboards, NLP classifiers — end-to-end.</p></div></div>
      <div class="astat"><div class="astat-num"><span class="cnt" data-t="98">0</span><span>%</span></div><div class="astat-text"><strong>Best Model Accuracy</strong><p>Oilseeds Yield Prediction using Random Forest Regressor.</p></div></div>
      <div class="astat"><div class="astat-num"><span class="cnt" data-t="50">0</span><span>%</span></div><div class="astat-text"><strong>Efficiency Gain</strong><p>Achieved at Innobyte via Power BI &amp; Excel automation.</p></div></div>
      <div class="astat"><div class="astat-num"><span class="cnt" data-t="29535">0</span></div><div class="astat-text"><strong>Tweets Analyzed</strong><p>Twitter Sentiment NLP — 95% accuracy, 93% F1-score.</p></div></div>
    </div>
  </div>
</section>
<div class="sec-divider"></div>

<!-- ════════ EXPERIENCE ════════ -->
<section id="experience">
  <div class="sec-label rv">02 — Work Experience</div>
  <h2 class="sec-title rv">Professional<br><span>Journey</span></h2>
  <div class="exp-wrap">
    <div class="exp-card rv">
      <div class="exp-card-head">
        <div class="exp-card-left">
          <div class="exp-role">Data Science Intern</div>
          <div class="exp-company">BIST Technologies Pvt Ltd · Virtual</div>
        </div>
        <div class="exp-meta-right">
          <div class="exp-date">Dec 2024 — Jan 2025</div>
          <span class="exp-badge">Internship</span>
        </div>
      </div>
      <div class="exp-divider"></div>
      <ul class="exp-bullets">
        <li><span class="ebadge">92% Accuracy</span><span>Built and deployed ML-based crop recommendation system using Random Forest; improved prediction accuracy by 18% and <strong>reduced error rate by 27%</strong> through feature engineering.</span></li>
        <li><span class="ebadge g">+22% Precision</span><span>Optimized classifiers with hyperparameter tuning — <strong>20% improvement in recall</strong> and 22% higher precision vs baseline models.</span></li>
        <li><span class="ebadge r">40% Faster</span><span>Automated preprocessing pipelines and integrated a Flask dashboard, enhancing <strong>crop-selection efficiency by 33%</strong>.</span></li>
      </ul>
      <div class="exp-tags"><span class="etag">Python</span><span class="etag">Scikit-learn</span><span class="etag">Pandas</span><span class="etag">Flask</span><span class="etag">NumPy</span><span class="etag">Random Forest</span><span class="etag">Matplotlib</span></div>
    </div>
    <div class="exp-card rv" style="transition-delay:.1s">
      <div class="exp-card-head">
        <div class="exp-card-left">
          <div class="exp-role">Data Analyst Intern</div>
          <div class="exp-company">Innobyte Services · Virtual</div>
        </div>
        <div class="exp-meta-right">
          <div class="exp-date">Aug 2024 — Sep 2024</div>
          <span class="exp-badge">Internship</span>
        </div>
      </div>
      <div class="exp-divider"></div>
      <ul class="exp-bullets">
        <li><span class="ebadge g">50% Faster</span><span>Cleaned raw Excel and SharePoint data using Pivot Tables and VLOOKUP, <strong>improving reporting efficiency by 50%</strong>.</span></li>
        <li><span class="ebadge">200+ Accounts</span><span>Designed Power BI dashboard for 200+ account financial portfolio; <strong>25% better collection rates</strong>, 30% fewer claim denials.</span></li>
        <li><span class="ebadge r">+15% CSAT</span><span>Directed cross-functional teams resolving billing issues, achieving <strong>15% improvement in client satisfaction</strong>.</span></li>
      </ul>
      <div class="exp-tags"><span class="etag">Power BI</span><span class="etag">DAX</span><span class="etag">Power Query</span><span class="etag">MS Excel</span><span class="etag">VLOOKUP</span><span class="etag">Pivot Tables</span></div>
    </div>
  </div>
</section>
<div class="sec-divider"></div>

<!-- ════════ PROJECTS ════════ -->
<section id="projects">
  <div class="sec-label rv">03 — Projects</div>
  <h2 class="sec-title rv">Real-world<br><span>Impact</span></h2>
  <div class="proj-grid">
    <div class="proj-card rv" onclick="openM(1)" style="transition-delay:.05s"><div class="proj-top-bar"></div><div class="proj-body"><div class="proj-num">PROJECT 01</div><div class="proj-name">Crop Recommendation System</div><div class="proj-metric">ML · Random Forest · 92% Accuracy</div><div class="proj-desc">End-to-end ML pipeline recommending optimal crops from soil &amp; climate data. Deployed via Flask in real-time.</div><div class="proj-foot"><div class="proj-tags"><span class="ptag">Python</span><span class="ptag">Flask</span><span class="ptag">Scikit-learn</span></div><div class="proj-btn"><svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><line x1="7" y1="17" x2="17" y2="7"/><polyline points="7 7 17 7 17 17"/></svg></div></div></div></div>
    <div class="proj-card rv" onclick="openM(2)" style="transition-delay:.1s"><div class="proj-top-bar"></div><div class="proj-body"><div class="proj-num">PROJECT 02</div><div class="proj-name">House Price Predictor</div><div class="proj-metric">Linear Regression · R² = 0.87</div><div class="proj-desc">Analyzed 5,000+ property listings with EDA and 15+ engineered features for precise valuation.</div><div class="proj-foot"><div class="proj-tags"><span class="ptag">Python</span><span class="ptag">Pandas</span><span class="ptag">Seaborn</span></div><div class="proj-btn"><svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><line x1="7" y1="17" x2="17" y2="7"/><polyline points="7 7 17 7 17 17"/></svg></div></div></div></div>
    <div class="proj-card rv" onclick="openM(3)" style="transition-delay:.15s"><div class="proj-top-bar"></div><div class="proj-body"><div class="proj-num">PROJECT 03</div><div class="proj-name">EV Market Dashboard</div><div class="proj-metric">Power BI · +28% Forecast Accuracy</div><div class="proj-desc">Interactive dashboard exploring Indian EV market growth, battery performance, brand trends.</div><div class="proj-foot"><div class="proj-tags"><span class="ptag">Power BI</span><span class="ptag">DAX</span><span class="ptag">Power Query</span></div><div class="proj-btn"><svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><line x1="7" y1="17" x2="17" y2="7"/><polyline points="7 7 17 7 17 17"/></svg></div></div></div></div>
    <div class="proj-card rv" onclick="openM(4)" style="transition-delay:.2s"><div class="proj-top-bar"></div><div class="proj-body"><div class="proj-num">PROJECT 04</div><div class="proj-name">Customer Segmentation</div><div class="proj-metric">SQL + K-Means · +25% Marketing ROI</div><div class="proj-desc">K-Means clustering on 50K+ SQL records to identify 5 distinct high-value customer segments.</div><div class="proj-foot"><div class="proj-tags"><span class="ptag">SQL</span><span class="ptag">Python</span><span class="ptag">K-Means</span></div><div class="proj-btn"><svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><line x1="7" y1="17" x2="17" y2="7"/><polyline points="7 7 17 7 17 17"/></svg></div></div></div></div>
    <div class="proj-card rv" onclick="openM(5)" style="transition-delay:.25s"><div class="proj-top-bar"></div><div class="proj-body"><div class="proj-num">PROJECT 05</div><div class="proj-name">Twitter Sentiment Analysis</div><div class="proj-metric">NLP · TF-IDF · 95% Accuracy</div><div class="proj-desc">Processed 29,535 tweets. TF-IDF + Logistic Regression: 95% accuracy, 93% F1, AUC=0.97.</div><div class="proj-foot"><div class="proj-tags"><span class="ptag">NLP</span><span class="ptag">TF-IDF</span><span class="ptag">NLTK</span></div><div class="proj-btn"><svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><line x1="7" y1="17" x2="17" y2="7"/><polyline points="7 7 17 7 17 17"/></svg></div></div></div></div>
    <div class="proj-card rv" onclick="openM(6)" style="transition-delay:.3s"><div class="proj-top-bar"></div><div class="proj-body"><div class="proj-num">PROJECT 06</div><div class="proj-name">Amazon Sales Analysis</div><div class="proj-metric">Power BI · 10K+ Transactions</div><div class="proj-desc">KPI dashboards on 10K+ Amazon records. Top 3 categories = 40%+ revenue via Pareto analysis.</div><div class="proj-foot"><div class="proj-tags"><span class="ptag">Power BI</span><span class="ptag">Python</span><span class="ptag">Excel</span></div><div class="proj-btn"><svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><line x1="7" y1="17" x2="17" y2="7"/><polyline points="7 7 17 7 17 17"/></svg></div></div></div></div>
    <div class="proj-card rv" onclick="openM(7)" style="transition-delay:.35s"><div class="proj-top-bar"></div><div class="proj-body"><div class="proj-num">PROJECT 07</div><div class="proj-name">Oilseeds Yield Prediction</div><div class="proj-metric">Random Forest · ~98% R²</div><div class="proj-desc">Highest accuracy model in portfolio. Multi-year yield prediction with feature importance analysis.</div><div class="proj-foot"><div class="proj-tags"><span class="ptag">Random Forest</span><span class="ptag">Scikit-learn</span><span class="ptag">Seaborn</span></div><div class="proj-btn"><svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><line x1="7" y1="17" x2="17" y2="7"/><polyline points="7 7 17 7 17 17"/></svg></div></div></div></div>
  </div>
</section>
<div class="sec-divider"></div>

<!-- ════════ SKILLS ════════ -->
<section id="skills">
  <div class="sec-label rv">04 — Skills</div>
  <h2 class="sec-title rv">Technical<br><span>Arsenal</span></h2>
  <div class="skills-wrap">
    <div class="rv">
      <div class="skill-group">
        <div class="skill-group-title">Programming &amp; Libraries</div>
        <div class="skill-row"><span class="skill-name">Python (Pandas, NumPy, Matplotlib)</span><div class="skill-bar-wrap"><div class="skill-bar-bg"><div class="skill-bar-fill p" data-w="88"></div></div><span class="skill-pct">88%</span></div></div>
        <div class="skill-row"><span class="skill-name">SQL</span><div class="skill-bar-wrap"><div class="skill-bar-bg"><div class="skill-bar-fill p" data-w="82"></div></div><span class="skill-pct">82%</span></div></div>
        <div class="skill-row"><span class="skill-name">Scikit-learn (ML Pipelines)</span><div class="skill-bar-wrap"><div class="skill-bar-bg"><div class="skill-bar-fill p" data-w="84"></div></div><span class="skill-pct">84%</span></div></div>
        <div class="skill-row"><span class="skill-name">NLP (TF-IDF, NLTK)</span><div class="skill-bar-wrap"><div class="skill-bar-bg"><div class="skill-bar-fill p" data-w="75"></div></div><span class="skill-pct">75%</span></div></div>
        <div class="skill-row"><span class="skill-name">R</span><div class="skill-bar-wrap"><div class="skill-bar-bg"><div class="skill-bar-fill p" data-w="60"></div></div><span class="skill-pct">60%</span></div></div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">BI &amp; Visualization</div>
        <div class="skill-row"><span class="skill-name">Power BI (DAX, Power Query)</span><div class="skill-bar-wrap"><div class="skill-bar-bg"><div class="skill-bar-fill a" data-w="85"></div></div><span class="skill-pct">85%</span></div></div>
        <div class="skill-row"><span class="skill-name">Excel (Pivot Tables, VLOOKUP)</span><div class="skill-bar-wrap"><div class="skill-bar-bg"><div class="skill-bar-fill a" data-w="80"></div></div><span class="skill-pct">80%</span></div></div>
        <div class="skill-row"><span class="skill-name">Tableau</span><div class="skill-bar-wrap"><div class="skill-bar-bg"><div class="skill-bar-fill a" data-w="65"></div></div><span class="skill-pct">65%</span></div></div>
        <div class="skill-row"><span class="skill-name">Matplotlib &amp; Seaborn</span><div class="skill-bar-wrap"><div class="skill-bar-bg"><div class="skill-bar-fill a" data-w="82"></div></div><span class="skill-pct">82%</span></div></div>
      </div>
    </div>
    <div class="rv" style="transition-delay:.12s">
      <div class="skill-group-title" style="font-family:var(--fm);font-size:.6rem;letter-spacing:.22em;text-transform:uppercase;color:var(--muted);padding-bottom:12px;margin-bottom:18px;border-bottom:1.5px solid var(--border2)">Soft Skills</div>
      <div class="soft-grid">
        <div class="soft-card"><div class="soft-icon">🔍</div><div class="soft-name">Analytical Thinking</div><div class="soft-desc">Structured decomposition of complex data problems</div></div>
        <div class="soft-card"><div class="soft-icon">💬</div><div class="soft-name">Stakeholder Comms</div><div class="soft-desc">Translating insights into business language</div></div>
        <div class="soft-card"><div class="soft-icon">🎯</div><div class="soft-name">Attention to Detail</div><div class="soft-desc">Zero tolerance for data quality issues</div></div>
        <div class="soft-card"><div class="soft-icon">🧩</div><div class="soft-name">Problem Solving</div><div class="soft-desc">Creative solutions from messy data</div></div>
        <div class="soft-card"><div class="soft-icon">⏱️</div><div class="soft-name">Time Management</div><div class="soft-desc">Consistent delivery under deadlines</div></div>
        <div class="soft-card"><div class="soft-icon">📈</div><div class="soft-name">Strategic Thinking</div><div class="soft-desc">Connecting data to business outcomes</div></div>
      </div>
      <div class="tools-label">Tools &amp; Cloud</div>
      <div class="tools-wrap">
        <span class="tool-pill">Git &amp; GitHub</span><span class="tool-pill">Snowflake</span>
        <span class="tool-pill">Flask</span><span class="tool-pill">Jupyter</span>
        <span class="tool-pill">VS Code</span><span class="tool-pill">SharePoint</span>
        <span class="tool-pill">Feature Engineering</span><span class="tool-pill">ETL Pipelines</span>
      </div>
    </div>
  </div>
</section>
<div class="sec-divider"></div>

<!-- ════════ EDUCATION ════════ -->
<section id="education">
  <div class="sec-label rv">05 — Education &amp; Credentials</div>
  <h2 class="sec-title rv">Foundation &amp;<br><span>Certifications</span></h2>
  <div class="edu-wrap">
    <div class="edu-card rv">
      <div class="edu-degree">Bachelor of Technology</div>
      <div class="edu-field">Artificial Intelligence &amp; Machine Learning</div>
      <div class="edu-inst">Sri Vasavi Institute of Engineering &amp; Technology · Pedana, AP</div>
      <div class="edu-cgpa-badge"><div class="edu-cgpa-val">8.01</div><div class="edu-cgpa-lbl">CGPA</div></div>
      <div class="edu-year">Graduated 2025</div>
      <div class="course-head">Relevant Coursework</div>
      <div class="course-chips">
        <span class="course-chip">Data Structures</span><span class="course-chip">Statistics</span>
        <span class="course-chip">Machine Learning</span><span class="course-chip">Database Management</span>
        <span class="course-chip">Python Programming</span><span class="course-chip">Deep Learning</span>
        <span class="course-chip">Computer Vision</span>
      </div>
    </div>
    <div class="certs-wrap rv" style="transition-delay:.1s">
      <div class="skill-group-title" style="font-family:var(--fm);font-size:.6rem;letter-spacing:.22em;text-transform:uppercase;color:var(--muted);padding-bottom:12px;margin-bottom:6px;border-bottom:1.5px solid var(--border2)">Certifications</div>
      <div class="cert-card">
        <div class="cert-icon ib"><svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C9.24 2 7 4.24 7 7c0 1.9 1 3.56 2.5 4.5L8 22l4-2 4 2-1.5-10.5C15.99 10.56 17 8.9 17 7c0-2.76-2.24-5-5-5zm0 2c1.66 0 3 1.34 3 3s-1.34 3-3 3-3-1.34-3-3 1.34-3 3-3z"/></svg></div>
        <div><div class="cert-name">IBM Data Analyst</div><div class="cert-from">Coursera · Oct 2023</div></div>
        <a href="https://coursera.org/verify/professional-cert/IBM-DATA-ANALYST" target="_blank" class="cert-link">Verify <svg width="10" height="10" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M18 13v6a2 2 0 01-2 2H5a2 2 0 01-2-2V8a2 2 0 012-2h6"/><polyline points="15 3 21 3 21 9"/><line x1="10" y1="14" x2="21" y2="3"/></svg></a>
      </div>
      <div class="cert-card">
        <div class="cert-icon go"><svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C9.24 2 7 4.24 7 7c0 1.9 1 3.56 2.5 4.5L8 22l4-2 4 2-1.5-10.5C15.99 10.56 17 8.9 17 7c0-2.76-2.24-5-5-5zm0 2c1.66 0 3 1.34 3 3s-1.34 3-3 3-3-1.34-3-3 1.34-3 3-3z"/></svg></div>
        <div><div class="cert-name">Google Advanced Data Analytics</div><div class="cert-from">Coursera · Oct 2023</div></div>
        <a href="https://coursera.org/verify/professional-cert/GOOGLE-ADVANCED-DA" target="_blank" class="cert-link">Verify <svg width="10" height="10" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M18 13v6a2 2 0 01-2 2H5a2 2 0 01-2-2V8a2 2 0 012-2h6"/><polyline points="15 3 21 3 21 9"/><line x1="10" y1="14" x2="21" y2="3"/></svg></a>
      </div>
      <div class="open-card">
        <div class="oc-label">Looking For</div>
        <div class="oc-roles">Data Analyst · ML Engineer · BI Developer</div>
        <div class="oc-note">Open to full-time roles, internships &amp; freelance. Immediate joiner.</div>
        <a href="#contact" style="display:inline-flex;align-items:center;gap:6px;margin-top:12px;font-size:.74rem;color:var(--purple);font-weight:700">Get in touch <svg width="10" height="10" viewBox="0 0 24 24" fill="currentColor"><path d="M12 4l-1.41 1.41L16.17 11H4v2h12.17l-5.58 5.59L12 20l8-8z"/></svg></a>
      </div>
    </div>
  </div>
</section>
<div class="sec-divider"></div>

<!-- ════════ CONTACT ════════ -->
<section id="contact">
  <div class="sec-label rv">06 — Contact</div>
  <div class="contact-wrap">
    <div class="rv">
      <h2 class="contact-big">Let's build<br><span>something</span><br>great.</h2>
      <p class="contact-sub">Open for Data Analyst roles, internships, and collaborations. If you have data and a problem — I'm your person.</p>
      <div class="contact-links">
        <a href="mailto:saiganesh.maganti@gmail.com" class="clink">
          <div class="clink-icon ml"><svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M20 4H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/></svg></div>
          <div><div class="clink-label">Email</div><div class="clink-val">saiganesh.maganti@gmail.com</div></div>
        </a>
        <a href="https://www.linkedin.com/in/saiganeshanalyst/" target="_blank" class="clink">
          <div class="clink-icon li"><svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg></div>
          <div><div class="clink-label">LinkedIn</div><div class="clink-val">linkedin.com/in/saiganeshanalyst</div></div>
        </a>
        <a href="https://github.com/saiganesh47" target="_blank" class="clink">
          <div class="clink-icon gh"><svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"/></svg></div>
          <div><div class="clink-label">GitHub</div><div class="clink-val">github.com/saiganesh47</div></div>
        </a>
      </div>
    </div>
    <form class="contact-form rv" style="transition-delay:.12s" onsubmit="hf(event)">
      <div class="form-2col">
        <div class="form-row"><label>Your Name</label><input class="fi" type="text" id="cf-n" placeholder="John Smith" required></div>
        <div class="form-row"><label>Email</label><input class="fi" type="email" id="cf-e" placeholder="john@company.com" required></div>
      </div>
      <div class="form-row"><label>Subject</label><input class="fi" type="text" id="cf-s" placeholder="Data Analyst Role — Company Name"></div>
      <div class="form-row" style="margin-bottom:20px"><label>Message</label><textarea class="fi" id="cf-m" placeholder="Tell me about the opportunity or project..." required></textarea></div>
      <button type="submit" class="form-submit">Send Message &nbsp;→</button>
    </form>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="foot-copy">© 2026 <span>Sai Ganesh M.</span> · Data Analyst Portfolio</div>
  <div class="foot-nav">
    <a href="#hero">Top</a><a href="#projects">Projects</a>
    <a href="#skills">Skills</a><a href="#contact">Contact</a>
  </div>
</footer>

<!-- PROJECT MODAL -->
<div id="modal" onclick="if(event.target.id==='modal')closeM()">
  <div class="modal-box">
    <div id="modal-in"></div>
    <div class="modal-actions">
      <button class="modal-close" onclick="closeM()">Close ✕</button>
      <span id="modal-gh"></span>
    </div>
  </div>
</div>

<script>
// ── PRELOADER
(function(){
  var b=document.getElementById('pb');
  if(b)b.style.width='100%';
  setTimeout(function(){document.body.classList.add('loaded');},1500);
})();

// ── CURSOR
var cur=document.getElementById('cur'),ring=document.getElementById('cur-ring');
var mx=0,my=0,rx=0,ry=0;
document.addEventListener('mousemove',function(e){mx=e.clientX;my=e.clientY;cur.style.left=mx+'px';cur.style.top=my+'px';});
(function lp(){rx+=(mx-rx)*.13;ry+=(my-ry)*.13;ring.style.left=rx+'px';ring.style.top=ry+'px';requestAnimationFrame(lp);})();
document.querySelectorAll('a,button,input,textarea,.proj-card,.cert-card,.astat,.soft-card,.tool-pill,.clink').forEach(function(el){
  el.addEventListener('mouseenter',function(){cur.classList.add('hv');ring.classList.add('hv');});
  el.addEventListener('mouseleave',function(){cur.classList.remove('hv');ring.classList.remove('hv');});
});

// ── SCROLL PROGRESS
window.addEventListener('scroll',function(){
  document.getElementById('prog').style.width=(scrollY/(document.body.scrollHeight-innerHeight)*100)+'%';
  updateSpy();
});

// ── CLOCK
function tick(){var n=new Date(),z=function(v){return String(v).padStart(2,'0');};var e=document.getElementById('nav-clk');if(e)e.textContent=z(n.getHours())+':'+z(n.getMinutes())+':'+z(n.getSeconds());}
setInterval(tick,1000);tick();

// ── MOBILE NAV
function omn(){document.getElementById('mnav').classList.add('op');}
function cmn(){document.getElementById('mnav').classList.remove('op');}

// ── SCROLL SPY (dots + nav active)
var secs=['hero','about','experience','projects','skills','education','contact'];
function updateSpy(){
  var mid=window.innerHeight/2;
  var cur2='hero';
  secs.forEach(function(id){
    var el=document.getElementById(id);
    if(!el)return;
    var r=el.getBoundingClientRect();
    if(r.top<=mid&&r.bottom>=mid)cur2=id;
  });
  document.querySelectorAll('.spy-dot').forEach(function(d){d.classList.toggle('active',d.dataset.sec===cur2);});
  document.querySelectorAll('.nav-center a').forEach(function(a){a.classList.toggle('active',a.dataset.nav===cur2);});
}

// ── SCROLL REVEAL
var ro=new IntersectionObserver(function(e){e.forEach(function(en){if(en.isIntersecting){en.target.classList.add('v');ro.unobserve(en.target);}});},{threshold:.1});
document.querySelectorAll('.rv').forEach(function(el){ro.observe(el);});

// ── COUNTERS
function ac(el,t,dur){var s=performance.now();(function step(n){var p=Math.min((n-s)/dur,1),e=1-Math.pow(1-p,3);el.textContent=Math.round(t*e).toLocaleString();if(p<1)requestAnimationFrame(step);else el.textContent=t.toLocaleString();})(performance.now());}
var co=new IntersectionObserver(function(e){e.forEach(function(en){if(en.isIntersecting){en.target.querySelectorAll('.cnt').forEach(function(c){ac(c,+c.dataset.t,1500);});co.unobserve(en.target);}});},{threshold:.25});
document.querySelectorAll('.hero-right,.about-stats').forEach(function(el){co.observe(el);});

// ── SKILL BARS
var bo=new IntersectionObserver(function(e){e.forEach(function(en){if(en.isIntersecting){en.target.querySelectorAll('.skill-bar-fill').forEach(function(b){setTimeout(function(){b.style.width=b.dataset.w+'%';},150);});bo.unobserve(en.target);}});},{threshold:.15});
document.querySelectorAll('#skills').forEach(function(el){bo.observe(el);});

// ── PROJECT DATA
var PD={
  1:{title:'Crop Recommendation System',ey:'Agriculture & ML · 2025',m:'92% accuracy · Flask deployed · Error ↓27%',b:['Built end-to-end ML pipeline from soil nutrients (N,P,K) and climate data to crop recommendation.','Achieved <strong>92% accuracy</strong> with Random Forest after hyperparameter tuning — 18% over baseline.','Deployed real-time Flask web app; decision efficiency improved by <strong>33%</strong>.','Automated preprocessing pipelines, cutting data prep time by <strong>40%</strong>.'],t:['Python','Scikit-learn','Pandas','Flask','NumPy','Random Forest'],lk:'https://github.com/saiganesh47/crop-recommendation'},
  2:{title:'House Price Predictor',ey:'Real Estate · Regression',m:'R² = 0.87 · 5,000+ listings',b:['Analyzed 5,000+ property listings with comprehensive EDA.','Engineered <strong>15+ new features</strong> from raw listing data (proximity, age, size ratios).','Linear Regression achieving <strong>R² = 0.87</strong> on held-out test set.','Visualized price drivers for clear stakeholder communication.'],t:['Python','Scikit-learn','Pandas','Matplotlib','Seaborn'],lk:'#'},
  3:{title:'EV Market Dashboard',ey:'Power BI · Forecasting',m:'+28% forecast accuracy · 6 report pages',b:['Interactive Power BI dashboard on Indian EV market growth, battery efficiency, brand trends.','Time-series forecasting with <strong>+28%</strong> accuracy vs moving-average baseline.','Created <strong>12+ DAX measures</strong>: range efficiency, adoption rate, regional share.','Drill-through across state, brand, and time periods.'],t:['Power BI','DAX','Power Query','Excel','Time Series'],lk:'#'},
  4:{title:'Customer Segmentation',ey:'SQL + Unsupervised Learning',m:'+25% marketing ROI · 5 segments',b:['SQL queries extracting <strong>50K+</strong> customer transaction records.','K-Means clustering (k=5) validated with elbow method and silhouette score.','High-value segment identified — <strong>25% marketing ROI improvement</strong>.','Delivered segment profiles and channel-specific recommendations.'],t:['SQL','Python','K-Means','Pandas','Seaborn'],lk:'#'},
  5:{title:'Twitter Sentiment Analysis',ey:'NLP · 2025',m:'95% accuracy · 93% F1 · AUC 0.97',b:['Processed <strong>29,535 tweets</strong>: noise removal, stemming, stopword filtering.','TF-IDF + Logistic Regression: <strong>95% accuracy</strong> and <strong>93% F1-score</strong>.','Reduced error by 20% via Bayesian hyperparameter search.','Generated ROC curve, confusion matrix, and annotated word clouds.'],t:['Python','Scikit-learn','NLTK','TF-IDF','Logistic Regression'],lk:'https://github.com/saiganesh47/twitter-sentiment-nlp'},
  6:{title:'Amazon Sales Analysis',ey:'E-commerce · BI · 2025',m:'10K+ transactions · 40% revenue = top 3 categories',b:['Cleaned <strong>10K+</strong> Amazon records, resolving 15% missing/inconsistent data.','Built Power BI KPI dashboards: revenue, top SKUs, regional trends.','Pareto analysis: top 3 categories contribute <strong>40%+ of total revenue</strong>.','Seasonal demand patterns and fulfillment impact insights delivered.'],t:['Python','Pandas','Power BI','Excel','DAX'],lk:'https://github.com/saiganesh47/amazon-sales-analysis'},
  7:{title:'Oilseeds Yield Prediction',ey:'Agriculture · Forecasting · 2025',m:'~98% R² · Best model in portfolio',b:['Multi-year yield data analysis across Indian states (rainfall, soil, area).','Feature selection removed <strong>30% irrelevant variables</strong>.','Random Forest Regressor achieving <strong>~98% R²</strong> — portfolio best.','Feature importance and regional trend visualizations for ag. planning.'],t:['Python','Pandas','Scikit-learn','Random Forest','Matplotlib','Seaborn'],lk:'https://github.com/saiganesh47/oilseeds-yield-prediction'},
};
function openM(id){
  var d=PD[id];if(!d)return;
  document.getElementById('modal-in').innerHTML='<div class="modal-ey">'+d.ey+'</div><div class="modal-title">'+d.title+'</div><div class="modal-metric">'+d.m+'</div><ul class="modal-bullets">'+d.b.map(function(b){return'<li><span>'+b+'</span></li>';}).join('')+'</ul><div class="modal-tags">'+d.t.map(function(t){return'<span class="ptag">'+t+'</span>';}).join('')+'</div>';
  document.getElementById('modal-gh').innerHTML=d.lk&&d.lk!='#'?'<a href="'+d.lk+'" target="_blank" class="modal-gh"><svg width="13" height="13" viewBox="0 0 24 24" fill="currentColor"><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"/></svg> View on GitHub</a>':'';
  document.getElementById('modal').classList.add('open');
  document.body.style.overflow='hidden';
}
function closeM(){document.getElementById('modal').classList.remove('open');document.body.style.overflow='';}
document.addEventListener('keydown',function(e){if(e.key==='Escape')closeM();});

// ── TYPEWRITER
(function(){
  var phrases=['Data Analyst','ML Engineer','Power BI Developer','Problem Solver'];
  var pi=0,ci=0,del=false;
  var el=document.getElementById('ht');
  if(!el)return;
  el.textContent='Data Analyst';
  function tick(){
    var ph=phrases[pi];
    if(del){
      el.textContent=ph.substring(0,--ci);
      if(ci===0){del=false;pi=(pi+1)%phrases.length;setTimeout(tick,400);return;}
    }else{
      el.textContent=ph.substring(0,++ci);
      if(ci===ph.length){del=true;setTimeout(tick,2000);return;}
    }
    setTimeout(tick,del?45:90);
  }
  setTimeout(tick,1800);
})();

// ── FORM
function hf(e){
  e.preventDefault();
  var n=document.getElementById('cf-n').value,em=document.getElementById('cf-e').value;
  var s=document.getElementById('cf-s').value||'Portfolio Inquiry',m=document.getElementById('cf-m').value;
  window.location.href='mailto:saiganesh.maganti@gmail.com?subject='+encodeURIComponent(s)+'&body='+encodeURIComponent('Hi Sai Ganesh,\n\nName: '+n+'\nEmail: '+em+'\n\n'+m);
  e.target.innerHTML='<div style="text-align:center;padding:36px 0"><div style="font-family:var(--fb);font-size:1.8rem;font-weight:800;color:var(--ink);margin-bottom:8px">Message Sent ✓</div><div style="color:var(--muted);font-size:.84rem">Thank you, '+n+'. I\'ll reply within 24 hours.</div></div>';
}

// ── RESUME
function dlr(){
  var url='#';// ← Replace with your PDF URL
  if(url==='#'){alert('📄 Replace "#" in dlr() with your PDF URL.');return;}
  var a=document.createElement('a');a.href=url;a.download='Sai_Ganesh_M_Resume.pdf';a.click();
}
</script>
</body>
</html>
