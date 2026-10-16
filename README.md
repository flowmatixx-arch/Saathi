<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1,viewport-fit=cover">
<meta name="theme-color" content="#08060f">
<meta name="description" content="Saathi - a companion who texts back and paints every scene.">
<title>Saathi - she texts back</title>
<style>html,body{margin:0;padding:0;background:#08060f;overscroll-behavior:none;-webkit-text-size-adjust:100%}@media(max-width:700px){.app{height:100dvh!important;border-radius:0!important}.wrap{max-width:none!important}}</style>
</head>
<body>

<div class="wrap">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;500;600;700&amp;display=swap" rel="stylesheet">
<style>
:root{
  --pink:#ff3d8b; --violet:#a855f7; --cyan:#22d3ee; --gold:#ffc46b;
  --bg:#08060f; --bg2:#0f0a1c; --card:rgba(255,255,255,.045); --line:rgba(255,255,255,.09);
  --txt:#f6f1ff; --mut:#a094bd; --dim:#6f6689;
}
*{box-sizing:border-box;-webkit-tap-highlight-color:transparent}
.wrap{width:100%;max-width:700px;margin:0 auto;font-family:'Outfit',Inter,system-ui,sans-serif}
.app{
  position:relative;width:100%;height:900px;border-radius:26px;overflow:hidden;display:flex;
  background:
    radial-gradient(900px 500px at 100% -10%, rgba(168,85,247,.28), transparent 60%),
    radial-gradient(700px 500px at -10% 110%, rgba(255,61,139,.22), transparent 60%),
    linear-gradient(160deg,#0c0817,#07050d 60%);
  border:1px solid var(--line); box-shadow:0 30px 80px rgba(0,0,0,.55);
  color:var(--txt);
}
.app *{scrollbar-width:thin;scrollbar-color:rgba(255,255,255,.16) transparent}
.app ::-webkit-scrollbar{width:6px;height:6px}
.app ::-webkit-scrollbar-thumb{background:rgba(255,255,255,.14);border-radius:9px}
.app ::-webkit-scrollbar-track{background:transparent}
button{font-family:inherit;cursor:pointer;border:0;background:none;color:inherit}
input,textarea{font-family:inherit}

/* ---------- rail ---------- */
.rail{width:78px;flex:0 0 78px;border-right:1px solid var(--line);display:flex;flex-direction:column;align-items:center;gap:10px;padding:14px 0;background:rgba(255,255,255,.02);backdrop-filter:blur(6px)}
.brand-dot{width:40px;height:40px;border-radius:14px;display:grid;place-items:center;font-weight:700;font-size:17px;letter-spacing:-.5px;
  background:linear-gradient(140deg,var(--pink),var(--violet));color:#fff;box-shadow:0 8px 24px rgba(255,61,139,.35);margin-bottom:4px}
.rail-avatars{flex:1;width:100%;overflow-y:auto;display:flex;flex-direction:column;align-items:center;gap:10px;padding:2px 0}
.rav{width:50px;height:50px;border-radius:16px;overflow:hidden;border:1.5px solid transparent;position:relative;flex:0 0 auto;background:#1a1330}
.rav img{width:100%;height:100%;object-fit:cover;display:block}
.rav.on{border-color:var(--pink);box-shadow:0 0 0 3px rgba(255,61,139,.18)}
.rav .ph{position:absolute;inset:0;display:grid;place-items:center;font-size:16px;font-weight:600}
.icon-btn{width:44px;height:44px;border-radius:14px;display:grid;place-items:center;border:1px solid var(--line);background:var(--card);transition:.18s;flex:0 0 auto}
.icon-btn:hover{background:rgba(255,255,255,.09);border-color:rgba(255,255,255,.2)}
.icon-btn svg{width:19px;height:19px;stroke:var(--txt);fill:none;stroke-width:1.7;stroke-linecap:round;stroke-linejoin:round}

/* ---------- stage ---------- */
.stage{flex:1;position:relative;display:flex;flex-direction:column;min-width:0}
.view{position:absolute;inset:0;display:none;flex-direction:column;min-height:0}
.view.on{display:flex}

/* discover */
.disc{overflow-y:auto;padding:22px 20px 40px}
.hero h1{font-size:34px;line-height:1.03;margin:0 0 8px;font-weight:600;letter-spacing:-1.2px}
.hero h1 span{background:linear-gradient(100deg,var(--pink),var(--violet) 55%,var(--cyan));-webkit-background-clip:text;background-clip:text;color:transparent}
.hero p{margin:0 0 16px;color:var(--mut);font-size:14.5px;max-width:430px;line-height:1.5}
.badges{display:flex;gap:7px;flex-wrap:wrap;margin-bottom:20px}
.badge{font-size:11px;padding:5px 11px;border-radius:99px;border:1px solid var(--line);background:var(--card);color:var(--mut);letter-spacing:.2px}
.badge b{color:var(--txt);font-weight:500}
.badge.hot{border-color:rgba(255,61,139,.4);background:rgba(255,61,139,.12);color:#ffc0da}

.sec-title{display:flex;align-items:baseline;justify-content:space-between;margin:22px 0 12px}
.sec-title h2{font-size:13px;text-transform:uppercase;letter-spacing:1.6px;color:var(--dim);margin:0;font-weight:500}
.sec-title em{font-size:12px;color:var(--dim);font-style:normal}

.grid{display:grid;grid-template-columns:repeat(3,1fr);gap:12px}
.ccard{border-radius:18px;overflow:hidden;border:1px solid var(--line);background:var(--card);position:relative;transition:.22s;text-align:left}
.ccard:hover{transform:translateY(-3px);border-color:rgba(255,61,139,.45);box-shadow:0 14px 34px rgba(0,0,0,.45)}
.ccard .shot{aspect-ratio:3/4;position:relative;overflow:hidden;background:#170f28}
.ccard .shot img{width:100%;height:100%;object-fit:cover;display:block;transition:.5s}
.ccard:hover .shot img{transform:scale(1.05)}
.ccard .shot .ph{position:absolute;inset:0;display:grid;place-items:center;font-size:30px;font-weight:600;color:rgba(255,255,255,.85)}
.ccard .shot .veil{position:absolute;inset:0;background:linear-gradient(to top,rgba(8,6,15,.94) 6%,rgba(8,6,15,.15) 55%,transparent)}
.ccard .meta{position:absolute;left:0;right:0;bottom:0;padding:10px 11px}
.ccard .meta h3{margin:0;font-size:14px;font-weight:600;display:flex;align-items:center;gap:6px}
.ccard .meta h3 i{font-style:normal;font-size:11px;font-weight:400;color:var(--mut)}
.ccard .meta p{margin:2px 0 0;font-size:11.5px;color:var(--mut);line-height:1.35;display:-webkit-box;-webkit-line-clamp:2;-webkit-box-orient:vertical;overflow:hidden}
.ccard .live{position:absolute;top:8px;left:8px;font-size:9.5px;padding:3px 7px;border-radius:99px;background:rgba(8,6,15,.7);border:1px solid rgba(34,197,94,.5);color:#8ef0b0;display:flex;align-items:center;gap:4px;backdrop-filter:blur(4px)}
.ccard .live i{width:5px;height:5px;border-radius:99px;background:#3ddc7f;box-shadow:0 0 8px #3ddc7f;font-style:normal}

.strip{display:flex;gap:9px;overflow-x:auto;padding:4px 2px 8px}
.scene{border:1px solid var(--line);background:var(--card);border-radius:14px;padding:9px 13px;white-space:nowrap;font-size:12.5px;color:var(--mut);transition:.18s;display:flex;align-items:center;gap:7px}
.scene:hover{color:var(--txt);border-color:rgba(168,85,247,.5);background:rgba(168,85,247,.1)}
.scene b{font-weight:500;color:var(--txt)}
.note{font-size:11.5px;color:var(--dim);line-height:1.6;border-top:1px solid var(--line);margin-top:22px;padding-top:14px}
.note code{background:rgba(255,255,255,.07);padding:1px 5px;border-radius:5px;font-size:11px;color:#dcc8ff}

/* chat */
.chead{display:flex;align-items:center;gap:11px;padding:13px 15px;border-bottom:1px solid var(--line);background:rgba(10,7,18,.55);backdrop-filter:blur(14px);z-index:5}
.chead .av{width:42px;height:42px;border-radius:14px;overflow:hidden;position:relative;flex:0 0 auto;background:#1a1330;border:1px solid var(--line)}
.chead .av img{width:100%;height:100%;object-fit:cover}
.chead .av .ph{position:absolute;inset:0;display:grid;place-items:center;font-weight:600}
.chead h3{margin:0;font-size:15px;font-weight:600;display:flex;align-items:center;gap:7px}
.chead h3 i{font-style:normal;font-size:11px;color:var(--mut);font-weight:400}
.chead .st{font-size:11.5px;color:var(--mut);display:flex;align-items:center;gap:5px;margin-top:1px}
.chead .st i{width:6px;height:6px;border-radius:99px;background:#3ddc7f;font-style:normal;box-shadow:0 0 7px #3ddc7f}
.chead .st.typing{color:#ffb8d6}
.chead .st.typing i{background:var(--pink);box-shadow:0 0 7px var(--pink);animation:pulse 1s infinite}
@keyframes pulse{50%{opacity:.35}}
.grow{flex:1}
.back{display:none}

.msgs{flex:1;overflow-y:auto;padding:18px 16px 10px;display:flex;flex-direction:column;gap:14px;scroll-behavior:smooth}
.scenecard{align-self:center;font-size:11.5px;color:#e2c9ff;border:1px solid rgba(168,85,247,.35);background:rgba(168,85,247,.11);padding:6px 14px;border-radius:99px}
.row{display:flex;gap:9px;max-width:88%}
.row.u{align-self:flex-end;flex-direction:row-reverse}
.row .pav{width:30px;height:30px;border-radius:11px;overflow:hidden;flex:0 0 auto;background:#1a1330;align-self:flex-end}
.row .pav img{width:100%;height:100%;object-fit:cover}
.bub{border-radius:17px;padding:11px 14px;font-size:14.3px;line-height:1.55;position:relative}
.row.a .bub{background:linear-gradient(150deg,rgba(255,255,255,.075),rgba(255,255,255,.04));border:1px solid var(--line);border-bottom-left-radius:6px}
.row.u .bub{background:linear-gradient(140deg,var(--pink),#c1359f 90%);color:#fff;border-bottom-right-radius:6px;box-shadow:0 8px 22px rgba(255,61,139,.22)}
.bub em{color:#ffc9e2;font-style:italic;opacity:.92}
.row.u .bub em{color:#ffe3f0}
.caret{display:inline-block;width:6px;height:14px;background:var(--pink);border-radius:2px;margin-left:2px;vertical-align:-2px;animation:blink .9s steps(1) infinite}
@keyframes blink{50%{opacity:0}}
.tools{display:flex;gap:6px;margin-top:7px;opacity:.55;transition:.2s}
.bub:hover .tools{opacity:1}
.tools button{font-size:10.5px;color:var(--mut);border:1px solid var(--line);padding:3px 8px;border-radius:99px;background:rgba(255,255,255,.03)}
.tools button:hover{color:var(--txt);border-color:rgba(255,255,255,.25)}

.dots{display:flex;gap:4px;padding:4px 2px}
.dots i{width:6px;height:6px;border-radius:99px;background:var(--mut);animation:bo 1.1s infinite}
.dots i:nth-child(2){animation-delay:.15s}.dots i:nth-child(3){animation-delay:.3s}
@keyframes bo{0%,60%,100%{transform:translateY(0);opacity:.4}30%{transform:translateY(-4px);opacity:1}}

/* generated image card */
.gen{margin-top:9px;border-radius:16px;overflow:hidden;border:1px solid var(--line);background:#100b1d;width:236px;max-width:100%}
.gen .cap{font-size:10.5px;color:var(--mut);padding:7px 10px;border-bottom:1px solid var(--line);display:flex;gap:6px;align-items:center;line-height:1.3}
.gen .cap svg{width:12px;height:12px;stroke:var(--pink);fill:none;stroke-width:1.7;flex:0 0 auto}
.gen .frame{position:relative;aspect-ratio:3/4;background:linear-gradient(140deg,#1a1230,#0e0a1a)}
.gen .frame img{width:100%;height:100%;object-fit:cover;display:block;opacity:0;transition:opacity .6s}
.gen .frame img.in{opacity:1}
.shim{position:absolute;inset:0;background:linear-gradient(100deg,transparent 20%,rgba(255,255,255,.09) 50%,transparent 80%);background-size:220% 100%;animation:sweep 1.4s infinite}
@keyframes sweep{to{background-position:-220% 0}}
.gen .frame .ph{position:absolute;inset:0;display:grid;place-items:center;text-align:center;padding:14px;font-size:11px;color:rgba(255,255,255,.72);line-height:1.4}
.gen .acts{display:flex;border-top:1px solid var(--line)}
.gen .acts button{flex:1;font-size:11px;color:var(--mut);padding:8px 4px;transition:.15s}
.gen .acts button:hover{background:rgba(255,255,255,.05);color:var(--txt)}
.gen .acts button+button{border-left:1px solid var(--line)}

/* composer */
.comp{border-top:1px solid var(--line);padding:10px 12px 13px;background:rgba(10,7,18,.6);backdrop-filter:blur(14px)}
.chips{display:flex;gap:7px;overflow-x:auto;padding:0 2px 9px}
.chip{white-space:nowrap;font-size:11.5px;color:var(--mut);border:1px solid var(--line);background:var(--card);padding:5px 11px;border-radius:99px;transition:.16s}
.chip:hover{color:#fff;background:rgba(255,61,139,.16);border-color:rgba(255,61,139,.45)}
.inbar{display:flex;gap:9px;align-items:flex-end}
.inbar textarea{flex:1;resize:none;max-height:110px;min-height:46px;border-radius:15px;border:1px solid var(--line);background:rgba(255,255,255,.05);color:var(--txt);padding:13px 14px;font-size:14.3px;line-height:1.4;outline:none;transition:.2s}
.inbar textarea:focus{border-color:rgba(255,61,139,.55);background:rgba(255,61,139,.06)}
.inbar textarea::placeholder{color:var(--dim)}
.send{width:46px;height:46px;border-radius:15px;background:linear-gradient(140deg,var(--pink),var(--violet));display:grid;place-items:center;flex:0 0 auto;box-shadow:0 8px 22px rgba(255,61,139,.3);transition:.18s}
.send:hover{transform:translateY(-1px)}
.send svg{width:19px;height:19px;stroke:#fff;fill:none;stroke-width:1.9;stroke-linecap:round;stroke-linejoin:round}
.comp .fine{display:flex;justify-content:space-between;font-size:10.5px;color:var(--dim);margin-top:8px;padding:0 3px}

/* heat */
.heat{display:flex;gap:4px;border:1px solid var(--line);background:rgba(255,255,255,.04);border-radius:99px;padding:3px}
.heat button{font-size:11px;padding:4px 10px;border-radius:99px;color:var(--mut);transition:.16s}
.heat button.on{background:linear-gradient(140deg,var(--pink),var(--violet));color:#fff;font-weight:500}

/* overlays */
.ov{position:absolute;inset:0;z-index:40;display:none}
.ov.on{display:block}
.panel{position:absolute;top:0;right:0;bottom:0;width:330px;max-width:88%;background:linear-gradient(180deg,#120c22,#0a0714);border-left:1px solid var(--line);padding:20px 18px;overflow-y:auto;box-shadow:-24px 0 60px rgba(0,0,0,.5)}
.panel h2{margin:0 0 3px;font-size:17px;font-weight:600}
.panel .sub{font-size:11.5px;color:var(--dim);margin-bottom:18px}
.fld{margin-bottom:15px}
.fld label{display:block;font-size:11px;text-transform:uppercase;letter-spacing:1.2px;color:var(--dim);margin-bottom:6px}
.fld input,.fld select,.fld textarea{width:100%;border-radius:11px;border:1px solid var(--line);background:rgba(255,255,255,.05);color:var(--txt);padding:9px 11px;font-size:13px;outline:none}
.fld input:focus,.fld select:focus{border-color:rgba(168,85,247,.6)}
.fld select option{background:#150f26;color:var(--txt)}
.fld .hint{font-size:10.5px;color:var(--dim);margin-top:5px;line-height:1.45}
.tog{display:flex;align-items:center;justify-content:space-between;padding:9px 0;border-bottom:1px solid rgba(255,255,255,.055)}
.tog span{font-size:13px}
.tog small{display:block;font-size:10.5px;color:var(--dim);margin-top:2px}
.sw{width:40px;height:23px;border-radius:99px;background:rgba(255,255,255,.12);position:relative;flex:0 0 auto;transition:.2s}
.sw::after{content:'';position:absolute;top:3px;left:3px;width:17px;height:17px;border-radius:99px;background:#fff;transition:.2s}
.sw.on{background:linear-gradient(140deg,var(--pink),var(--violet))}
.sw.on::after{left:20px}
.pbtn{width:100%;border-radius:12px;padding:11px;font-size:13px;font-weight:500;background:linear-gradient(140deg,var(--pink),var(--violet));color:#fff;margin-top:6px}
.pbtn.ghost{background:rgba(255,255,255,.06);border:1px solid var(--line);color:var(--txt);margin-top:9px}
.close-x{position:absolute;top:16px;right:16px;width:32px;height:32px;border-radius:10px;border:1px solid var(--line);display:grid;place-items:center;font-size:15px;color:var(--mut)}
.close-x:hover{color:#fff}

/* lightbox */
.lb{background:rgba(5,3,10,.93);backdrop-filter:blur(10px);display:none;place-items:center;padding:22px;z-index:60}
.lb.on{display:grid}
.lb img{max-width:100%;max-height:74%;border-radius:18px;border:1px solid var(--line);box-shadow:0 30px 80px rgba(0,0,0,.7)}
.lb .lbcap{color:var(--mut);font-size:12px;text-align:center;margin-top:14px;max-width:80%}
.lb .lbbtns{display:flex;gap:9px;margin-top:14px}
.lb .lbbtns button{font-size:12px;border:1px solid var(--line);background:rgba(255,255,255,.06);color:var(--txt);padding:8px 15px;border-radius:11px}
.lb .lbbtns button:hover{background:rgba(255,61,139,.18)}

/* gate */
.gate{background:rgba(6,4,12,.96);backdrop-filter:blur(8px);display:none;place-items:center;text-align:center;padding:30px;z-index:80}
.gate.on{display:grid}
.gate .g{max-width:360px}
.gate h2{font-size:26px;margin:0 0 8px;font-weight:600}
.gate p{color:var(--mut);font-size:13.5px;line-height:1.6;margin:0 0 20px}
.gate .btns{display:flex;gap:10px;justify-content:center;flex-wrap:wrap}
.gate button{padding:11px 22px;border-radius:13px;font-size:13.5px;font-weight:500;border:1px solid var(--line);background:rgba(255,255,255,.06)}
.gate button.pri{background:linear-gradient(140deg,var(--pink),var(--violet));border-color:transparent;color:#fff}

@media (max-width:620px){
  .app{height:100dvh;border-radius:0;border-left:0;border-right:0}
  .wrap{max-width:none}
  .grid{grid-template-columns:repeat(2,1fr)}
  .rail{display:none}
  .back{display:grid}
}
</style>

<div class="app" id="app">

  <!-- RAIL -->
  <div class="rail">
    <div class="brand-dot">S</div>
    <div class="rail-avatars" id="railAv"></div>
    <button class="icon-btn" id="railNew" title="Discover">
      <svg viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"></path></svg>
    </button>
    <button class="icon-btn" id="railSet" title="Settings">
      <svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="3.2"></circle><path d="M19.4 15a1.7 1.7 0 0 0 .34 1.87l.06.06a2 2 0 1 1-2.83 2.83l-.06-.06A1.7 1.7 0 0 0 15 19.4a1.7 1.7 0 0 0-1 1.55V21a2 2 0 1 1-4 0v-.05A1.7 1.7 0 0 0 9 19.4a1.7 1.7 0 0 0-1.87.34l-.06.06a2 2 0 1 1-2.83-2.83l.06-.06A1.7 1.7 0 0 0 4.6 15a1.7 1.7 0 0 0-1.55-1H3a2 2 0 1 1 0-4h.05A1.7 1.7 0 0 0 4.6 9a1.7 1.7 0 0 0-.34-1.87l-.06-.06a2 2 0 1 1 2.83-2.83l.06.06A1.7 1.7 0 0 0 9 4.6 1.7 1.7 0 0 0 10 3.05V3a2 2 0 1 1 4 0v.05A1.7 1.7 0 0 0 15 4.6a1.7 1.7 0 0 0 1.87-.34l.06-.06a2 2 0 1 1 2.83 2.83l-.06.06A1.7 1.7 0 0 0 19.4 9v.05a1.7 1.7 0 0 0 1.55 1H21a2 2 0 1 1 0 4h-.05a1.7 1.7 0 0 0-1.55 1z"></path></svg>
    </button>
  </div>

  <!-- STAGE -->
  <div class="stage">

    <!-- DISCOVER -->
    <div class="view on" id="vDisc">
      <div class="disc">
        <div class="hero">
          <h1>Someone is<br>waiting for <span>you</span>.</h1>
          <p id="subLine">She texts back like a real person, remembers what you like, and paints the picture of whatever you two are doing — right there in the chat.</p>
          <div class="badges">
            <div class="badge"><b>∞</b> messages</div>
            <div class="badge"><b>live</b> scene images</div>
            <div class="badge hot">no filters on her mouth</div>
            <div class="badge">remembers you</div>
          </div>
        </div>

        <div class="sec-title"><h2>pick someone</h2><em id="charCount"></em></div>
        <div class="grid" id="grid"></div>

        <div class="sec-title"><h2>fantasies</h2><em>tap one, then go talk</em></div>
        <div class="strip" id="sceneStrip"></div>

        <div class="note">
          <b style="color:#cbb6ff">Want it live?</b> The companions run offline by default — unlimited and instant. Open <code>settings</code> → <code>backend</code> to plug in a free online brain or your own API for even more unpredictable replies. Everything else (characters, fantasies, the whole look) lives in the <code>CONFIG</code> and <code>CHARACTERS</code> blocks at the very top of this file.
        </div>
      </div>
    </div>

    <!-- CHAT -->
    <div class="view" id="vChat">
      <div class="chead">
        <button class="icon-btn back" id="backBtn" style="width:36px;height:36px">
          <svg viewBox="0 0 24 24"><path d="M15 19l-7-7 7-7"></path></svg>
        </button>
        <div class="av" id="cAv"></div>
        <div>
          <h3 id="cName"></h3>
          <div class="st" id="cStat"><i></i><span>online now</span></div>
        </div>
        <div class="grow"></div>
        <div class="heat" id="heatCtl">
          <button data-h="1">sweet</button>
          <button data-h="2">flirty</button>
          <button data-h="3">filthy</button>
        </div>
        <button class="icon-btn" id="chatMenu" style="width:36px;height:36px">
          <svg viewBox="0 0 24 24"><circle cx="12" cy="5" r="1.4"></circle><circle cx="12" cy="12" r="1.4"></circle><circle cx="12" cy="19" r="1.4"></circle></svg>
        </button>
      </div>

      <div class="msgs" id="msgs"></div>

      <div class="comp">
        <div class="chips" id="chips"></div>
        <div class="inbar">
          <textarea id="inp" rows=
          
