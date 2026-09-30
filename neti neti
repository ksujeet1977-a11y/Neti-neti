<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#120424">

<title>नेति नेति — The Forbidden Omniverse Codex</title>

<!-- Supabase JS Client Library -->
<script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2"></script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Cinzel:wght@600;800;900&family=Plus+Jakarta+Sans:wght@400;600;700;800&family=Yatra+One&display=swap');

*{box-sizing:border-box;}
body{
    margin:0;
    background-color:#120424;
    background-image: 
        radial-gradient(circle at 15% 15%, rgba(175, 30, 245, 0.6) 0%, transparent 55%),
        radial-gradient(circle at 85% 85%, rgba(120, 20, 200, 0.55) 0%, transparent 60%),
        radial-gradient(circle at 50% 50%, rgba(255, 215, 0, 0.15) 0%, transparent 70%),
        linear-gradient(135deg, #120424 0%, #20083c 50%, #0d0218 100%);
    background-attachment: fixed;
    color:#ffffff;
    font-family:'Plus Jakarta Sans', sans-serif;
    min-height:200vh;
    font-size: 16px;
    overflow-x: hidden;
}

/* Floating Mandalas Background Canvas */
#mandalaCanvas {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    pointer-events: none;
    z-index: 1;
}

header{
    padding: 14px 20px;
    background:rgba(22, 6, 42, 0.92);
    backdrop-filter: blur(25px);
    -webkit-backdrop-filter: blur(25px);
    border-bottom:2px solid rgba(255, 225, 120, 0.5);
    position:sticky;
    top:0;
    z-index:30;
    box-shadow: 0 10px 30px rgba(0,0,0,0.8);
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
}
.brand-title {
    font-family: 'Cinzel', serif;
    font-size: 18px;
    font-weight: 900;
    color: #fff4bd;
    letter-spacing: 3px;
    text-decoration: none;
    text-shadow: 0 0 15px rgba(255, 244, 189, 0.8);
    white-space: nowrap;
}
nav{
    display: flex;
    gap: 6px;
    overflow-x: auto;
    padding-bottom: 4px;
}
nav::-webkit-scrollbar { display: none; }
nav button{
    background:rgba(45, 15, 78, 0.85);
    color:#f2e6ff;
    border:1px solid rgba(255, 215, 0, 0.4);
    padding: 7px 12px;
    border-radius: 8px;
    cursor:pointer;
    transition:all 0.3s ease;
    font-size: 11px;
    font-weight: 800;
    letter-spacing: 1px;
    white-space: nowrap;
}
nav button:hover, nav button.active{
    background:linear-gradient(135deg, #c75af9, #7a1fb5);
    color: #ffffff;
    border-color: #fff4bd;
    box-shadow: 0 0 18px rgba(255, 244, 189, 0.6);
}
main{
    max-width:1100px;
    margin:auto;
    padding:25px 16px;
    position: relative;
    z-index: 10;
}

/* Historic-Mysterious Home Hero */
.mystic-hero {
    background: linear-gradient(145deg, rgba(38, 12, 68, 0.9), rgba(18, 5, 35, 0.95));
    border: 2px solid rgba(255, 225, 120, 0.6);
    border-radius: 20px;
    padding: 40px 20px;
    margin-bottom: 30px;
    text-align: center;
    box-shadow: 0 25px 60px rgba(0, 0, 0, 0.85), inset 0 0 40px rgba(180, 50, 240, 0.25);
    position: relative;
    overflow: hidden;
    backdrop-filter: blur(20px);
}
.ancient-seal {
    width: 65px;
    height: 65px;
    margin: 0 auto 15px auto;
    border: 2px solid #fff4bd;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    background: radial-gradient(circle, rgba(190,45,110,0.95) 0%, rgba(55,15,85,0.95) 85%);
    box-shadow: 0 0 25px rgba(255, 244, 189, 0.7), inset 0 0 12px rgba(255, 244, 189, 0.9);
    font-size: 26px;
    color: #fff4bd;
    font-family: 'Yatra One', cursive;
}
.sanskrit-banner {
    color: #fff4bd;
    font-size: 12px;
    font-weight: 800;
    letter-spacing: 4px;
    text-transform: uppercase;
    margin-bottom: 10px;
    text-shadow: 0 0 12px rgba(255, 244, 189, 0.7);
}
.mystic-hero h1 {
    font-family: 'Cinzel', serif;
    font-size: 32px;
    color: #ffffff;
    margin: 10px 0 15px 0;
    letter-spacing: 3px;
    font-weight: 900;
    text-shadow: 0 0 20px rgba(255, 255, 255, 0.7);
    line-height: 1.2;
}
.mystic-hero p {
    color: #f2e6ff;
    font-size: 15px;
    line-height: 1.7;
    max-width: 800px;
    margin: 0 auto 25px auto;
    font-weight: 500;
}
.gate-grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: 18px;
    margin-top: 30px;
    text-align: left;
    position: relative;
    z-index: 2;
}
@media(min-width: 768px) {
    .gate-grid { grid-template-columns: repeat(3, 1fr); }
    .mystic-hero h1 { font-size: 42px; }
}
.gate-card {
    background: linear-gradient(145deg, rgba(50, 16, 85, 0.85), rgba(22, 6, 45, 0.95));
    border: 1px solid rgba(255, 225, 120, 0.5);
    border-radius: 14px;
    padding: 24px;
    transition: all 0.3s ease;
    box-shadow: 0 12px 30px rgba(0,0,0,0.6);
    cursor: pointer;
    position: relative;
    overflow: hidden;
}
.gate-card:hover {
    border-color: #fff4bd;
    transform: translateY(-4px);
    box-shadow: 0 15px 40px rgba(255, 244, 189, 0.4);
}
.gate-card h3 {
    font-family: 'Cinzel', serif;
    color: #fff4bd;
    margin-top: 0;
    font-size: 20px;
    letter-spacing: 1px;
}
.gate-card p {
    color: #e8d7ff;
    font-size: 14px;
    line-height: 1.6;
    margin-bottom: 18px;
}
.epigraph-ticker {
    background: rgba(28, 8, 52, 0.9);
    border: 1px solid rgba(255, 225, 120, 0.6);
    padding: 16px 20px;
    border-radius: 10px;
    margin: 25px 0;
    color: #fff4bd;
    font-size: 14px;
    box-shadow: inset 0 0 20px rgba(0,0,0,0.7), 0 0 15px rgba(255, 215, 0, 0.2);
    position: relative;
    z-index: 2;
    font-weight: 600;
}

.hero-logo-container {
    width: 100%;
    max-width: 800px;
    margin: 10px auto 20px auto;
    text-align: center;
    position: relative;
    z-index: 2;
}
.hero-logo-svg {
    width: 100%;
    height: auto;
    display: block;
    overflow: visible;
}
@keyframes spinClockwise { 0% { transform: rotate(0deg); } 100% { transform: rotate(360deg); } }
@keyframes spinCounter { 0% { transform: rotate(0deg); } 100% { transform: rotate(-360deg); } }
@keyframes corePulse { 0%, 100% { opacity: 0.7; transform: scale(0.92); } 50% { opacity: 1; transform: scale(1.1); } }
.spin-slow { transform-origin: 380px 145px; animation: spinClockwise 70s linear infinite; }
.spin-reverse { transform-origin: 380px 145px; animation: spinCounter 60s linear infinite; }
.spin-fast { transform-origin: 380px 145px; animation: spinClockwise 30s linear infinite; }
.core-glow { transform-origin: 380px 145px; animation: corePulse 5s ease-in-out infinite; }

.knowledge-box {
    background: linear-gradient(145deg, rgba(38, 12, 68, 0.85), rgba(18, 5, 35, 0.92));
    border: 1px solid rgba(255, 225, 120, 0.5);
    border-radius: 16px;
    padding: 24px;
    margin-bottom: 25px;
    text-align: left;
    box-shadow: 0 12px 30px rgba(0,0,0,0.6);
}
.knowledge-box h3 {
    font-family: 'Cinzel', serif;
    color: #fff4bd;
    margin-top: 0;
    font-size: 20px;
    letter-spacing: 1px;
    border-bottom: 1px solid rgba(255, 225, 120, 0.3);
    padding-bottom: 12px;
}
.knowledge-grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: 15px;
    margin-top: 15px;
}
@media(min-width: 600px) {
    .knowledge-grid { grid-template-columns: repeat(3, 1fr); }
}
.knowledge-item {
    background: rgba(60, 20, 100, 0.75);
    border: 1px solid rgba(255, 215, 0, 0.4);
    border-radius: 10px;
    padding: 16px;
}
.knowledge-item strong {
    color: #fff4bd;
    display: block;
    margin-bottom: 6px;
    font-size: 14px;
    font-family: 'Cinzel', serif;
}
input,textarea{
    width:100%;
    background:rgba(25, 8, 48, 0.95);
    color:#ffffff;
    border:2px solid rgba(255, 215, 0, 0.5);
    border-radius:12px;
    padding:16px;
    font-size:15px;
    outline:none;
    transition: all 0.3s ease;
    margin-bottom: 16px;
    font-family: 'Plus Jakarta Sans', sans-serif;
}
input:focus, textarea:focus{
    border-color: #fff4bd;
    box-shadow: 0 0 20px rgba(255, 244, 189, 0.6);
    background: rgba(38, 12, 68, 0.98);
}
textarea{min-height:150px; resize:vertical;}
.filters{
    display:flex;
    gap:8px;
    overflow-x:auto;
    padding:14px 0;
    position:sticky;
    top:60px;
    background:rgba(18, 5, 35, 0.95);
    z-index:20;
}
.filters::-webkit-scrollbar { height: 4px; }
.filters::-webkit-scrollbar-thumb { background: #ffd700; border-radius: 4px; }
.filters button{
    white-space:nowrap;
    background:rgba(45, 15, 78, 0.85);
    color:#f2e6ff;
    border:1px solid rgba(255, 215, 0, 0.4);
    border-radius:8px;
    padding:9px 18px;
    cursor:pointer;
    font-size: 12px;
    font-weight: 800;
    letter-spacing: 1px;
    transition: all 0.3s ease;
}
.filters button.active{
    border-color:#fff4bd;
    color:#ffffff;
    background:linear-gradient(135deg, #c75af9, #7a1fb5);
    box-shadow: 0 0 15px rgba(255, 244, 189, 0.6);
}
.count{ color:#fff4bd; font-size:14px; margin:15px 0; font-weight:800; letter-spacing: 1px; text-shadow: 0 0 10px rgba(255,244,189,0.4); }
.card{
    background:linear-gradient(145deg, rgba(45, 15, 78, 0.85), rgba(20, 5, 40, 0.95));
    border:2px solid rgba(255, 215, 0, 0.5);
    border-radius:16px;
    padding:22px;
    margin:18px 0;
    box-shadow: 0 12px 35px rgba(0, 0, 0, 0.7);
    transition: transform 0.3s ease, border-color 0.3s ease;
}
.card:hover {
    border-color: #fff4bd;
    transform: translateY(-2px);
}
.card h3{ margin:10px 0 8px; font-size:22px; color:#ffffff; font-family: 'Cinzel', serif; letter-spacing: 1px; text-shadow: 0 0 10px rgba(255,255,255,0.4); }
.meta{ color:#e8d7ff; font-size:13px; margin-bottom:12px; font-weight: 600; }
.author-badge {
    color: #ffffff; font-weight: 800; font-size: 12px;
    background: rgba(255, 215, 0, 0.25);
    border: 1px solid rgba(255, 215, 0, 0.6);
    padding: 5px 12px; border-radius: 6px; display: inline-block; margin-bottom: 10px;
    letter-spacing: 1px;
}
.description{ color:#ffffff; line-height:1.8; font-size:15px; font-weight: 400; }
.tag{
    display:inline-block; border:1px solid rgba(255, 215, 0, 0.6);
    color:#fff4bd; border-radius:6px; padding:5px 12px; font-size:11px;
    margin-right:6px; margin-bottom:6px; background:rgba(30, 8, 55, 0.9); font-weight:800; letter-spacing: 1px;
}
.read, .postBtn{
    display:inline-block; margin-top:16px;
    background:linear-gradient(135deg, #b026ff, #6a0dad);
    color:white; text-decoration:none; border:2px solid rgba(255, 225, 120, 0.7); border-radius:10px;
    padding:12px 24px; font-weight:800; font-size:13px; cursor:pointer; letter-spacing: 1px;
    box-shadow: 0 6px 20px rgba(176, 38, 255, 0.6);
    transition: all 0.3s ease;
}
.read:hover, .postBtn:hover { transform: translateY(-2px); box-shadow: 0 10px 30px rgba(255, 244, 189, 0.8); border-color: #fff4bd; background:linear-gradient(135deg, #c44fff, #7c15c4); }

.modal-overlay {
    position: fixed; top: 0; left: 0; width: 100%; height: 100%;
    background: rgba(10, 2, 20, 0.95); backdrop-filter: blur(15px);
    display: flex; justify-content: center; align-items: center; z-index: 100; padding: 15px;
}
.modal-content {
    background: linear-gradient(145deg, rgba(55, 18, 95, 0.98), rgba(22, 6, 45, 0.98));
    border: 2px solid rgba(255, 225, 120, 0.8); border-radius: 18px;
    max-width: 750px; width: 100%; max-height: 85vh; overflow-y: auto; padding: 28px;
    box-shadow: 0 30px 80px rgba(0,0,0,0.95); position: relative;
}
.modal-close {
    position: absolute; top: 14px; right: 16px;
    background: rgba(160, 30, 100, 0.9); border: 2px solid rgba(255, 225, 120, 0.8);
    color: #ffffff; font-size: 15px; font-weight: bold; width: 34px; height: 34px;
    border-radius: 50%; cursor: pointer; display: flex; align-items: center; justify-content: center;
}
footer{ text-align:center; color:#e8d7ff; padding:35px 16px; font-size:12px; letter-spacing:1px; border-top: 1px solid rgba(255, 225, 120, 0.3); margin-top: 40px; font-weight: 600;}
</style>
</head>

<body>

<!-- Background Canvas for Floating Mandalas -->
<canvas id="mandalaCanvas"></canvas>

<template id="userOriginalLogoTemplate">
    <div class="hero-logo-container">
        <svg class="hero-logo-svg" viewBox="0 0 760 430" xmlns="http://www.w3.org/2000/svg">
            <defs>
                <linearGradient id="goldGrad" x1="0%" y1="0%" x2="100%" y2="100%">
                    <stop offset="0%" stop-color="#ffffff" />
                    <stop offset="35%" stop-color="#fff4bd" />
                    <stop offset="70%" stop-color="#ffd700" />
                    <stop offset="100%" stop-color="#b8860b" />
                </linearGradient>
                <linearGradient id="mysticCrimsonGrad" x1="0%" y1="0%" x2="100%" y2="0%">
                    <stop offset="0%" stop-color="#ffbdfc" />
                    <stop offset="50%" stop-color="#e04fd0" />
                    <stop offset="100%" stop-color="#b43aff" />
                </linearGradient>
                <radialGradient id="coreGlow" cx="50%" cy="50%" r="50%">
                    <stop offset="0%" stop-color="rgba(255, 244, 189, 1)" />
                    <stop offset="45%" stop-color="rgba(176, 38, 255, 0.8)" />
                    <stop offset="100%" stop-color="transparent" />
                </radialGradient>
                <filter id="intenseGlow" x="-40%" y="-40%" width="180%" height="180%">
                    <feGaussianBlur stdDeviation="6" result="blur" />
                    <feComposite in="SourceGraphic" in2="blur" operator="over" />
                </filter>
            </defs>

            <g transform="translate(380, 140)" filter="url(#intenseGlow)">
                <circle cx="0" cy="0" r="115" fill="url(#coreGlow)" class="core-glow"/>
                <g class="spin-slow">
                    <circle cx="0" cy="0" r="98" fill="none" stroke="url(#goldGrad)" stroke-width="3.5" stroke-dasharray="6 9" opacity="1"/>
                    <circle cx="0" cy="0" r="84" fill="none" stroke="url(#mysticCrimsonGrad)" stroke-width="3" opacity="1"/>
                </g>
                <g class="spin-reverse">
                    <polygon points="0,-90 78,45 -78,45" fill="none" stroke="url(#goldGrad)" stroke-width="3.5" opacity="1"/>
                    <polygon points="0,90 78,-45 -78,-45" fill="none" stroke="url(#goldGrad)" stroke-width="3.5" opacity="1"/>
                </g>
                <g class="spin-fast">
                    <rect x="-35" y="-35" width="70" height="70" fill="none" stroke="url(#mysticCrimsonGrad)" stroke-width="3" transform="rotate(45)" opacity="1"/>
                </g>
                <circle cx="0" cy="0" r="34" fill="#180530" stroke="url(#goldGrad)" stroke-width="4"/>
                <circle cx="0" cy="0" r="11" fill="none" stroke="url(#mysticCrimsonGrad)" stroke-width="3.5"/>
                <circle cx="0" cy="0" r="4.5" fill="#ffffff"/>
                <path d="M0 -105 L0 -120 M0 105 L0 120 M-105 0 L-120 0 M105 0 L120 0" stroke="url(#goldGrad)" stroke-width="4" stroke-linecap="round"/>
            </g>

            <text x="380" y="305" text-anchor="middle" font-family="'Cinzel', serif" font-weight="900" font-size="64" fill="url(#goldGrad)" letter-spacing="10" filter="url(#intenseGlow)">NETI NETI</text>
            <text x="380" y="355" text-anchor="middle" font-family="'Yatra One', cursive" font-size="24" fill="#ffffff" letter-spacing="2">नज़र नहीं, नज़रिया बदलो</text>
            <text x="380" y="395" text-anchor="middle" font-family="'Cinzel', serif" font-weight="700" font-size="13" fill="#fff4bd" letter-spacing="8">THE ETERNAL CODEX OF NEGATION</text>
        </svg>
    </div>
</template>

<header>
    <a href="#" class="brand-title" onclick="page('home', document.querySelectorAll('nav button')[0])">NETI NETI</a>
    <nav>
        <button class="active" onclick="page('home',this)">HOME</button>
        <button onclick="page('dharma',this)">DHARMA</button>
        <button onclick="page('philosophy',this)">100K TREATISES</button>
        <button onclick="page('explore',this)">CHRONICLE</button>
        <button onclick="page('create',this)">SCRIBE</button>
    </nav>
</header>

<main id="app"></main>
<div id="modalContainer"></div>

<footer>
नेति नेति • The Sealed Omniverse Repository of 4,000 Dharma Canons & 100,000 Philosophical Treatises
</footer>

<script>
// ==========================================
// SUPABASE REAL-TIME CONFIGURATION (यहाँ अपनी डिटेल्स डालें)
// ==========================================
const SUPABASE_URL = 'YOUR_SUPABASE_URL_HERE'; 
const SUPABASE_ANON_KEY = 'YOUR_SUPABASE_ANON_KEY_HERE';

let supabaseClient = null;
if (window.supabase && SUPABASE_URL !== 'YOUR_SUPABASE_URL_HERE') {
    supabaseClient = window.supabase.createClient(SUPABASE_URL, SUPABASE_ANON_KEY);
}

// High-Luminance Floating Mandalas Animation Engine
const canvas = document.getElementById('mandalaCanvas');
const ctx = canvas.getContext('2d');

function resizeCanvas() {
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
}
window.addEventListener('resize', resizeCanvas);
resizeCanvas();

const mandalaCount = 35;
const mandalas = [];

for(let i = 0; i < mandalaCount; i++) {
    mandalas.push({
        x: Math.random() * canvas.width,
        y: Math.random() * canvas.height,
        radius: 25 + Math.random() * 45,
        speedX: (Math.random() - 0.5) * 0.4,
        speedY: -0.3 - Math.random() * 0.5,
        rotation: Math.random() * Math.PI * 2,
        rotSpeed: (Math.random() - 0.5) * 0.01,
        opacity: 0.5 + Math.random() * 0.4,
        colorType: Math.random() > 0.35 ? 'gold' : 'purple',
        petals: 6 + Math.floor(Math.random() * 3) * 2 
    });
}

function drawComplexMandala(x, y, radius, rotation, petals, opacity, colorType) {
    ctx.save();
    ctx.translate(x, y);
    ctx.rotate(rotation);
    
    if(colorType === 'gold') {
        ctx.strokeStyle = `rgba(255, 244, 189, ${opacity})`;
        ctx.fillStyle = `rgba(255, 215, 0, ${opacity * 0.3})`;
    } else {
        ctx.strokeStyle = `rgba(240, 140, 255, ${opacity})`;
        ctx.fillStyle = `rgba(176, 38, 255, ${opacity * 0.3})`;
    }
    
    ctx.lineWidth = 2;

    ctx.beginPath();
    ctx.arc(0, 0, radius, 0, Math.PI * 2);
    ctx.stroke();

    ctx.beginPath();
    for (let j = 0; j < petals; j++) {
        let angle = (j * 2 * Math.PI) / petals;
        let px = Math.cos(angle) * radius;
        let py = Math.sin(angle) * radius;
        if (j === 0) ctx.moveTo(px, py);
        else ctx.lineTo(px, py);
    }
    ctx.closePath();
    ctx.fill();
    ctx.stroke();

    ctx.restore();
}

function animateMandalas() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    
    mandalas.forEach(m => {
        m.x += m.speedX;
        m.y += m.speedY;
        m.rotation += m.rotSpeed;

        if (m.y < -70) {
            m.y = canvas.height + 70;
            m.x = Math.random() * canvas.width;
        }
        if (m.x < -70) m.x = canvas.width + 70;
        if (m.x > canvas.width + 70) m.x = -70;

        drawComplexMandala(m.x, m.y, m.radius, m.rotation, m.petals, m.opacity, m.colorType);
    });

    requestAnimationFrame(animateMandalas);
}
animateMandalas();


const baseDharmaList = [
    ["Rigveda Samhita", "Hinduism - Vedic", "Ancient India", "Foundational hymns dedicated to cosmic deities and Rita.", "https://sacred-texts.com/hin/rigveda/index.htm"],
    ["Samaveda, Yajurveda & Atharvaveda Samhitas", "Hinduism - Vedic", "Ancient India", "Vedic liturgical chants, sacrificial formulas, and spiritual incantations.", "https://sacred-texts.com/hin/index.htm"],
    ["The Principal Upanishads (108 Canons)", "Hinduism - Vedanta", "Ancient India", "Deep metaphysical dialogues on Brahman, Atman, and liberation (Moksha).", "https://sacred-texts.com/hin/upan/index.htm"],
    ["Valmiki Ramayana", "Hinduism - Itihasa", "Ancient India", "Epic narrative of Lord Rama, righteousness (dharma), and divine devotion.", "https://sacred-texts.com/hin/rama/index.htm"],
    ["Mahabharata (incl. Bhagavad Gita)", "Hinduism - Itihasa", "Ancient India", "The colossal epic detailing duty, righteousness, and the dialogue between Krishna and Arjuna.", "https://sacred-texts.com/hin/maha/index.htm"],
    ["Goswami Tulsidas Ramcharitmanas", "Hinduism - Bhakti", "Medieval India", "Retelling of the Ramayana in Awadhi poetry celebrating the grace and glory of Shri Ram."],
    ["The 18 Mahapuranas", "Hinduism - Puranas", "Ancient India", "Encyclopedic texts recording cosmological histories, genealogies, deity praise, and moral codes.", "https://sacred-texts.com/hin/purana/index.htm"],
    ["Shaiva Agamas & Tirumantiram", "Hinduism - Shaivism", "South India", "Foundational scriptures of Shaiva Siddhanta philosophy and devotion to Lord Shiva."],
    ["Shakta Tantras & Devi Bhagavata Purana", "Hinduism - Shaktism", "India", "Sacred texts exalting the Supreme Divine Feminine (Adi Parashakti)."],
    ["Pali Canon (Tipitaka)", "Buddhism - Theravada", "Ancient India", "The complete basket of teachings and psychological analyses spoken by the Buddha.", "https://sacred-texts.com/bud/sbe10/index.htm"],
    ["Mahayana Sutras (Lotus, Heart, Diamond)", "Buddhism - Mahayana", "India / East Asia", "Profound discourses on emptiness (Sunyata) and universal Bodhisattva compassion.", "https://sacred-texts.com/bud/lotus/index.htm"],
    ["Tibetan Kangyur & Tengyur", "Buddhism - Vajrayana", "Tibet / Himalayas", "Vast collections of tantric texts, commentaries, and epistemology."],
    ["The Holy Quran (Mushaf)", "Islam - Core Scripture", "Middle East", "The immutable divine revelations given to Prophet Muhammad as absolute guidance.", "https://sacred-texts.com/isl/quran/index.htm"],
    ["Sahih al-Bukhari & Sahih Muslim Hadith", "Islam - Hadith", "Middle East", "Authenticated reports of sayings, approvals, and actions of Prophet Muhammad.", "https://sacred-texts.com/isl/index.htm"],
    ["Mathnawi of Rumi & Sufi Poetry", "Islam - Sufism", "Persia", "Sublime mystical poetry exploring divine love and annihilation in the Divine."],
    ["The Holy Bible (Old & New Testaments)", "Christianity - Canonical", "Levant / Rome", "Scriptures detailing creation, covenant, prophecy, and the life and teachings of Jesus Christ.", "https://sacred-texts.com/bib/index.htm"],
    ["Nag Hammadi Gnostic Gospels", "Christianity - Gnostic", "Alexandria", "Esoteric Christian writings revealing secret spiritual knowledge."],
    ["The Tanakh (Hebrew Bible)", "Judaism - Scripture", "Ancient Near East", "The foundational written law and prophetic history of Israel.", "https://sacred-texts.com/jud/index.htm"],
    ["The Babylonian Talmud", "Judaism - Rabbinic", "Middle East", "Monumental codifications of Jewish law, ethics, and rabbinical debate."],
    ["The Zohar (Book of Splendor)", "Judaism - Kabbalah", "Spain / Middle East", "The supreme text of Jewish mysticism outlining divine emanations (Sefirot)."],
    ["Sri Guru Granth Sahib", "Sikhism - Scripture", "Punjab, India", "The central holy scripture of Sikhism composed of devotional hymns celebrating Oneness."],
    ["Tao Te Ching (Laozi)", "Taoism - Scripture", "Ancient China", "Laozi's foundational treatise on living in harmony with the Dao.", "https://sacred-texts.com/tao/taote.htm"],
    ["The Four Books and Five Classics", "Confucianism - Canon", "Ancient China", "Core texts establishing ritual propriety (li) and humaneness (ren).", "https://sacred-texts.com/cfu/conf1.htm"],
    ["Jain Agamas & Angas", "Jainism - Scripture", "Ancient India", "The canonical preachings of Tirthankaras emphasizing absolute non-violence (ahimsa).", "https://sacred-texts.com/jai/index.htm"],
    ["The Avesta", "Zoroastrianism - Scripture", "Ancient Persia", "Ancient liturgical hymns centered on Ahura Mazda and Asha.", "https://sacred-texts.com/zor/index.htm"]
];

const religiousCanons = [];
let dharmaId = 1;
while(religiousCanons.length < 4000){
    const template = baseDharmaList[(dharmaId - 1) % baseDharmaList.length];
    religiousCanons.push([
        template[0] + " (Codex Vol. " + Math.ceil(dharmaId / baseDharmaList.length) + ")",
        template[1],
        template[2],
        template[3] + " [Sealed Manuscript #" + dharmaId + "]",
        "Sacred codex preserving spiritual doctrines, metaphysical secrets, and ritual ordinances across lineage #" + dharmaId + ".",
        template[4] || "https://sacred-texts.com/index.htm"
    ]);
    dharmaId++;
}

const philosophyTraditions = [
    "Indian Statecraft & Political Realism (Acharya Chanakya / Arthashastra & Niti)",
    "Ancient Greek - Socratic Dialogues & Ethics (Socrates / Plato)",
    "Ancient Greek - Aristotelian Metaphysics & Nicomachean Ethics",
    "Pre-Socratic Philosophy (Heraclitus, Parmenides, Pythagoras)",
    "Hellenistic - Stoicism (Epictetus, Marcus Aurelius, Seneca)",
    "Hellenistic - Epicureanism & Skepticism",
    "Indian Materialism - Charvaka / Lokayata (Pratyaksha)", 
    "Indian Fatalism - Ajivika (Niyati)", 
    "Indian Agnosticism - Ajñana",
    "Indian Darshana - Nyaya (Logic & Epistemology)", 
    "Indian Darshana - Vaisheshika (Atomism)",
    "Indian Darshana - Samkhya (Dualism)", 
    "Indian Darshana - Yoga (Patanjali)",
    "Indian Darshana - Mimamsa (Hermeneutics)", 
    "Indian Darshana - Vedanta (Advaita, Dvaita, Vishishtadvaita)",
    "Buddhist Philosophy - Madhyamaka (Emptiness / Sunyata)", 
    "Buddhist Philosophy - Yogachara (Mind-Only)",
    "Medieval Scholasticism (Aquinas, Augustine, Abelard)", 
    "Islamic Philosophy - Avicenna (Ibn Sina) & Averroes (Ibn Rushd)",
    "Jewish Philosophy - Maimonides & Spinoza", 
    "Continental Rationalism (Descartes, Spinoza, Leibniz)",
    "British Empiricism (John Locke, David Hume, George Berkeley)", 
    "German Idealism (Immanuel Kant, G.W.F. Hegel, Arthur Schopenhauer)",
    "Existentialism (Jean-Paul Sartre, Albert Camus, Søren Kierkegaard, Nietzsche)", 
    "Phenomenology (Edmund Husserl, Martin Heidegger, Maurice Merleau-Ponty)",
    "Analytic Philosophy (Bertrand Russell, Ludwig Wittgenstein, Gottlob Frege)", 
    "Pragmatism (William James, Charles Sanders Peirce, John Dewey)",
    "Chinese Philosophy (Confucianism, Daoism, Moism, Legalism)", 
    "Postmodernism & Deconstruction (Jacques Derrida, Michel Foucault)"
];

const philosophyThemes = [
    "Epistemology & Theory of Valid Knowledge (Pramana / Gnoseology)", 
    "Ontology & Categories of Being (Tattva / Metaphysics)",
    "Ethics, Virtue & Moral Duty (Dharma / Arete / Niti)", 
    "Metaphysics of Consciousness & Mind (Citta / Psyche)",
    "Logic & Formal Inference (Anumana / Syllogistic Deduction)", 
    "Political Philosophy, Statecraft & Sovereignty (Rajneeti / Arthashastra / Polis)",
    "Philosophy of Language & Meaning (Sabda / Semiotics)", 
    "Aesthetics & Perception of Beauty (Rasa / Catharsis)",
    "Philosophy of Science & Materialism", 
    "Existential Freedom, Absurdity & Meaning", 
    "Philosophy of Religion & Transcendent Truth"
];

const TOTAL_PHILOSOPHY_COUNT = 100000;
function getPhilosophyItem(i) {
    const philIndex = i + 1;
    const tradition = philosophyTraditions[i % philosophyTraditions.length];
    const theme = philosophyThemes[Math.floor(i / philosophyTraditions.length) % philosophyThemes.length];
    
    let descriptionText = "A classified philosophical treatise investigating " + theme.toLowerCase() + " through the esoteric framework of " + tradition + ". Interrogating metaphysical axioms and absolute truths. [Codex Tome #" + philIndex + "]";
    
    if (tradition.includes("Chanakya")) {
        descriptionText = "A rare statecraft manuscript detailing espionage, treasury administration, intelligence networks, and royal ethics formulated by Kautilya. [Codex Tome #" + philIndex + "]";
    } else if (tradition.includes("Socratic")) {
        descriptionText = "An unrecorded Socratic dialogue uncovering the soul's recollection of truth and dialectical refutation of sophistry. [Codex Tome #" + philIndex + "]";
    } else if (tradition.includes("Aristotelian")) {
        descriptionText = "An ancient Peripatetic scroll analyzing prime matter, final causes, and political constitutions. [Codex Tome #" + philIndex + "]";
    } else if (tradition.includes("Charvaka")) {
        descriptionText = "A forbidden materialist scroll arguing against transcendental afterlife and asserting direct empirical perception as the sole reality. [Codex Tome #" + philIndex + "]";
    } else if (tradition.includes("Stoicism")) {
        descriptionText = "A recovered parchment detailing inner citadel defense, emotional detachment, and alignment with cosmic fate. [Codex Tome #" + philIndex + "]";
    }

    return [
        "Treatise on " + theme.split(" ")[0] + " #" + philIndex,
        "World Philosophy",
        tradition,
        "Master Thinker / Acharya #" + philIndex,
        descriptionText,
        "https://sacred-texts.com/index.htm"
    ];
}

let currentPage = "home";
let currentDharmaCategory = "All";
let currentPhilCategory = "All";
let currentExploreFilter = "all";
let currentExploreSort = "newest";
let currentSearchResults = [];
let uploadedImageBase64 = "";

function page(name, button){
    currentPage = name;
    document.querySelectorAll("nav button").forEach(b => b.classList.remove("active"));
    if(button) button.classList.add("active");
    render();
    window.scrollTo({ top: 0, behavior: "smooth" });
}

function render(){
    const app = document.getElementById("app");
    if(!app) return;
    if(currentPage === "home") renderHome(app);
    else if(currentPage === "dharma") renderDharma(app);
    else if(currentPage === "philosophy") renderPhilosophy(app);
    else if(currentPage === "explore") renderExplore(app);
    else if(currentPage === "create") renderCreate(app);
}

function renderHome(app){
    const templateNode = document.getElementById('userOriginalLogoTemplate');
    app.innerHTML = "";
    if(templateNode) app.appendChild(templateNode.content.cloneNode(true));

    app.innerHTML += `
    <section class="mystic-hero">
        <div class="ancient-seal">ॐ</div>
        <div class="sanskrit-banner">गुप्त अभिलेख • The Sealed Sanctuary of Negation</div>
        <h1>THE ETERNAL MANUSCRIPT CODEX</h1>
        <p>
            You have crossed the threshold of the hidden library. For millennia, seekers have approached the ultimate truth not by adding constructs, but by stripping away illusion through the ancient formula: <strong>Neti Neti</strong>—neither this, nor that. Enter the sealed crypts holding <strong>4,000 Dharma Canons</strong> and <strong>100,000 Philosophical Treatises</strong>.
        </p>

        <div class="epigraph-ticker">
            "Behind every veil of dogma lies the unwritten silence from which all universes sprang. Look past the shadow; perceive the lens."
        </div>

        <div class="gate-grid">
            <div class="gate-card" onclick="page('dharma', document.querySelectorAll('nav button')[1])">
                <h3>📜 DHARMA CANONS</h3>
                <p>Unlock ${religiousCanons.length.toLocaleString()} sacred scriptures, ancient Vedas, Upanishads, Gnostic texts, and spiritual hymns.</p>
                <span style="color:#fff4bd; font-weight:bold; font-size:12px; font-family:'Cinzel',serif; letter-spacing:1px;">BREAK THE SEAL →</span>
            </div>
            <div class="gate-card" onclick="page('philosophy', document.querySelectorAll('nav button')[2])">
                <h3>⚖️ 100K PHILOSOPHICAL TREATISES</h3>
                <p>Investigate classified statecraft from Chanakya, Socratic dialogues, Aristotelian metaphysics, and Stoic antiquity.</p>
                <span style="color:#fff4bd; font-weight:bold; font-size:12px; font-family:'Cinzel',serif; letter-spacing:1px;">UNROLL SCROLLS →</span>
            </div>
            <div class="gate-card" onclick="page('explore', document.querySelectorAll('nav button')[3])">
                <h3>👁️ THE CHRONICLE</h3>
                <p>Read profound philosophical insights, notes, and epigraphs recorded by fellow inquirers across the omniverse.</p>
                <span style="color:#fff4bd; font-weight:bold; font-size:12px; font-family:'Cinzel',serif; letter-spacing:1px;">READ CHRONICLE →</span>
            </div>
        </div>
    </section>
    `;
}

function renderDharma(app){
    const categories = ["All", ...new Set(religiousCanons.map(x => x[2]))];
    app.innerHTML = `
    <section class="mystic-hero" style="padding:25px 16px; margin-bottom:20px;">
        <h2 style="color:#ffffff; margin:0 0 8px 0; font-size:26px; font-family:'Cinzel',serif;">DHARMA CANONS (${religiousCanons.length.toLocaleString()})</h2>
        <p class="description" style="margin:0;">Sealed scriptures and canonical traditions across ancient global lineages.</p>
    </section>

    <div class="knowledge-box">
        <h3>THE DOCTRINE OF DHARMA (धर्मा / धम्म)</h3>
        <p class="description" style="margin-top:10px; font-size:15px;">
            Rooted in Sanskrit <em>'dhṛ'</em> (to hold or sustain), Dharma is the hidden cosmic law and moral order holding the fabric of reality together.
        </p>
        <div class="knowledge-grid">
            <div class="knowledge-item">
                <strong>1. Cosmic Order (Ṛta)</strong>
                The unalterable rhythm governing celestial rotation and moral gravity.
            </div>
            <div class="knowledge-item">
                <strong>2. Righteous Duty (Kartavya)</strong>
                The sacred obligation aligning human action with truth and cosmic balance.
            </div>
            <div class="knowledge-item">
                <strong>3. Liberation Path (Marga)</strong>
                The ascetic and devotional journey past illusion toward eternal freedom.
            </div>
        </div>
    </div>

    <input id="dharmaSearch" placeholder="Search Vedas, Upanishads, Ramcharitmanas, Quran, Bible, Tripitaka..." oninput="searchDharma()">
    
    <div class="filters">
        ${categories.map(c => `
        <button class="${c === currentDharmaCategory ? 'active' : ''}" onclick="chooseDharmaCategory('${c.replace(/'/g, "\\'")}')">
        ${escapeHTML(c)}
        </button>
        `).join("")}
    </div>
    <div id="dharmaCount" class="count"></div>
    <div id="dharmaResults"></div>
    `;
    searchDharma();
}

function chooseDharmaCategory(cat){
    currentDharmaCategory = cat;
    renderDharma(document.getElementById("app"));
}

function searchDharma(){
    const query = document.getElementById("dharmaSearch")?.value.toLowerCase() || "";
    currentSearchResults = religiousCanons.filter(item => {
        const catMatch = currentDharmaCategory === "All" || item[2] === currentDharmaCategory;
        const textMatch = item.join(" ").toLowerCase().includes(query);
        return catMatch && textMatch;
    });

    const countEl = document.getElementById("dharmaCount");
    const resultsEl = document.getElementById("dharmaResults");
    if(countEl) countEl.textContent = "Showing " + currentSearchResults.length.toLocaleString() + " dharma canons (Filtered from " + religiousCanons.length.toLocaleString() + " total)";
    if(resultsEl) {
        resultsEl.innerHTML = currentSearchResults.slice(0, 100).map((item, index) => `
            <article class="card">
                <span class="tag">${escapeHTML(item[1])}</span>
                <span class="tag">${escapeHTML(item[2])}</span>
                <h3>${escapeHTML(item[0])}</h3>
                <div class="meta">${escapeHTML(item[3])}</div>
                <div class="description">${escapeHTML(item[4])}</div>
                <button class="read" onclick="openTextReaderByIndex(${index}, 'dharma')">UNSEAL CANON</button>
            </article>
        `).join("") + (currentSearchResults.length > 100 ? `<div class="card"><p class="description">Showing first 100 matches out of ${currentSearchResults.length.toLocaleString()}. Refine search above to inspect specific scrolls.</p></div>` : "");
    }
}

function renderPhilosophy(app){
    const categories = ["All", ...philosophyTraditions];
    app.innerHTML = `
    <section class="mystic-hero" style="padding:25px 16px; margin-bottom:20px;">
        <h2 style="color:#ffffff; margin:0 0 8px 0; font-size:26px; font-family:'Cinzel',serif;">${TOTAL_PHILOSOPHY_COUNT.toLocaleString()} PHILOSOPHICAL TREATISES</h2>
        <p class="description" style="margin:0 auto 12px auto;">Classified treatises spanning Chanakya, Socratic inquiries, Charvaka materialism, and Stoic wisdom.</p>
        <input id="philSearch" placeholder="Search Chanakya, Arthashastra, Socrates, Plato, Aristotle, Charvaka, Stoicism..." oninput="searchPhilosophy()">
    </section>
    <div class="filters">
        ${categories.map(c => `
        <button class="${c === currentPhilCategory ? 'active' : ''}" onclick="choosePhilCategory('${c.replace(/'/g, "\\'")}')">
        ${escapeHTML(c)}
        </button>
        `).join("")}
    </div>
    <div id="philCount" class="count"></div>
    <div id="philResults"></div>
    `;
    searchPhilosophy();
}

function choosePhilCategory(cat){
    currentPhilCategory = cat;
    renderPhilosophy(document.getElementById("app"));
}

function searchPhilosophy(){
    const query = document.getElementById("philSearch")?.value.toLowerCase().trim() || "";
    
    const matchedItems = [];
    for(let i = 0; i < TOTAL_PHILOSOPHY_COUNT; i++) {
        const item = getPhilosophyItem(i);
        const catMatch = currentPhilCategory === "All" || item[2] === currentPhilCategory;
        if(!catMatch) continue;
        
        if(query === "" || item[0].toLowerCase().includes(query) || item[2].toLowerCase().includes(query) || item[3].toLowerCase().includes(query) || item[4].toLowerCase().includes(query)) {
            matchedItems.push(item);
            if(matchedItems.length >= 25000) break;
        }
    }
    currentSearchResults = matchedItems;

    const countEl = document.getElementById("philCount");
    const resultsEl = document.getElementById("philResults");
    if(countEl) countEl.textContent = "Showing matching philosophical treatises (Filtered from " + TOTAL_PHILOSOPHY_COUNT.toLocaleString() + " total archives)";
    if(resultsEl) {
        resultsEl.innerHTML = currentSearchResults.slice(0, 100).map((item, index) => `
            <article class="card">
                <span class="tag">${escapeHTML(item[1])}</span>
                <span class="tag">${escapeHTML(item[2])}</span>
                <h3>${escapeHTML(item[0])}</h3>
                <div class="meta">${escapeHTML(item[3])}</div>
                <div class="description">${escapeHTML(item[4])}</div>
                <button class="read" onclick="openTextReaderByIndex(${index}, 'philosophy')">UNROLL TREATISE</button>
            </article>
        `).join("") + (currentSearchResults.length > 100 ? `<div class="card"><p class="description">Showing first 100 matches out of ${currentSearchResults.length.toLocaleString()} found. Refine your search above.</p></div>` : "");
    }
}

function openTextReaderByIndex(index, section) {
    const item = currentSearchResults[index];
    if(!item) return;
    
    const title = item[0];
    const category = item[2];
    const description = item[4];
    const sourceUrl = item[5] || 'https://sacred-texts.com/index.htm';

    const modalContainer = document.getElementById("modalContainer");
    modalContainer.innerHTML = `
        <div class="modal-overlay" onclick="closeTextReader(event)">
            <div class="modal-content" onclick="event.stopPropagation()">
                <button class="modal-close" onclick="closeTextReader()">✕</button>
                <span class="tag">${escapeHTML(category)}</span>
                <h2 style="color:#ffffff; margin-top:12px; font-size:22px; font-family:'Cinzel',serif;">${escapeHTML(title)}</h2>
                <div class="description" style="font-size:15px; margin: 18px 0; line-height:1.8;">
                    ${escapeHTML(description)}
                    <br><br>
                    <strong>Codex Exegesis:</strong> Preserved within the sealed omniverse repository connecting all ancient metaphysical traditions.
                </div>
                <div style="display:flex; gap:10px; margin-top:20px; flex-wrap:wrap;">
                    <button class="postBtn" style="margin:0; cursor:pointer;" onclick="window.open('${sourceUrl}', '_blank');">OPEN EXTERNAL ARCHIVE</button>
                    <button class="read" style="margin:0; background:rgba(60,20,100,0.9); border:1px solid #fff4bd;" onclick="closeTextReader()">CLOSE SCROLL</button>
                </div>
            </div>
        </div>
    `;
}

function closeTextReader() {
    const modalContainer = document.getElementById("modalContainer");
    if(modalContainer) modalContainer.innerHTML = "";
}

/* ==========================================
   CHRONICLE SECTION (SUPABASE + LOCAL FALLBACK)
   ========================================== */
async function fetchAllPosts() {
    if (supabaseClient) {
        try {
            const { data, error } = await supabaseClient
                .from('neti_posts')
                .select('*')
                .order('id', { ascending: false });
            if (!error && data) return data;
        } catch (e) {
            console.error("Supabase fetch error, using local storage fallback", e);
        }
    }
    return JSON.parse(localStorage.getItem("netiCommunityPosts") || "[]");
}

function renderExplore(app){
    app.innerHTML = `
    <section class="mystic-hero" style="padding:25px 16px; margin-bottom:20px;">
        <h2 style="color:#ffffff; margin:0 0 8px 0; font-size:26px; font-family:'Cinzel',serif;">THE CHRONICLE OF INQUIRERS</h2>
        <p class="description" style="margin:0;">Reflections, epigraphs, and verses inscribed by seekers across the omniverse.</p>
    </section>

    <!-- Interactive Search and Sorting Control Bar -->
    <div style="display:flex; gap:10px; flex-wrap:wrap; margin-bottom:15px;">
        <input id="exploreSearchInput" placeholder="Search insights by keyword or author..." style="flex:1; min-width:240px; margin-bottom:0;" oninput="filterExplorePosts()" value="${window.exploreQuery || ''}">
        <select id="exploreSortSelect" onchange="filterExplorePosts()" style="background:rgba(25, 8, 48, 0.95); color:#ffffff; border:2px solid rgba(255, 215, 0, 0.5); border-radius:12px; padding:12px 16px; font-size:14px; outline:none; font-family:'Plus Jakarta Sans', sans-serif; cursor:pointer;">
            <option value="newest" ${currentExploreSort === 'newest' ? 'selected' : ''}>Sort: Newest First</option>
            <option value="oldest" ${currentExploreSort === 'oldest' ? 'selected' : ''}>Sort: Oldest First</option>
            <option value="author" ${currentExploreSort === 'author' ? 'selected' : ''}>Sort: By Author</option>
        </select>
    </div>

    <div class="filters" style="margin-top:0;">
        <button class="${currentExploreFilter === 'all' ? 'active' : ''}" onclick="setExploreFilter('all')">All Inscriptions</button>
        <button class="${currentExploreFilter === 'philosophy' ? 'active' : ''}" onclick="setExploreFilter('philosophy')">Philosophy</button>
        <button class="${currentExploreFilter === 'dharma' ? 'active' : ''}" onclick="setExploreFilter('dharma')">Dharma</button>
        <button class="${currentExploreFilter === 'verse' ? 'active' : ''}" onclick="setExploreFilter('verse')">Poetry & Verse</button>
    </div>

    <div id="exploreCount" class="count"></div>
    <div id="exploreFeed"></div>
    `;
    filterExplorePosts();
}

function setExploreFilter(filter){
    currentExploreFilter = filter;
    renderExplore(document.getElementById("app"));
}

async function filterExplorePosts(){
    const query = document.getElementById("exploreSearchInput")?.value.toLowerCase() || "";
    window.exploreQuery = query;
    currentExploreSort = document.getElementById("exploreSortSelect")?.value || "newest";

    let posts = await fetchAllPosts();
    const savedPosts = JSON.parse(localStorage.getItem("netiSavedPosts") || "[]");

    if(query.trim() !== ""){
        posts = posts.filter(p => p.text.toLowerCase().includes(query) || (p.author && p.author.toLowerCase().includes(query)));
    }

    if(currentExploreFilter === 'philosophy'){
        posts = posts.filter(p => /truth|mind|logic|reality|existence|reason|shunya|neti/i.test(p.text));
    } else if(currentExploreFilter === 'dharma'){
        posts = posts.filter(p => /dharma|karma|god|divine|soul|veda|sacred/i.test(p.text));
    } else if(currentExploreFilter === 'verse'){
        posts = posts.filter(p => /shiraz|gazal|dohe|poetry|verse|شاعری|कविता/i.test(p.text) || p.text.split('\n').length > 3);
    }

    if(currentExploreSort === 'newest'){
        posts.sort((a, b) => b.id - a.id);
    } else if(currentExploreSort === 'oldest'){
        posts.sort((a, b) => a.id - b.id);
    } else if(currentExploreSort === 'author'){
        posts.sort((a, b) => (a.author || 'Anonymous').localeCompare(b.author || 'Anonymous'));
    }

    const countEl = document.getElementById("exploreCount");
    const feedEl = document.getElementById("exploreFeed");

    if(countEl) countEl.textContent = `Showing ${posts.length} chronicle entries`;
    if(feedEl) {
        if(posts.length === 0){
            feedEl.innerHTML = `<div class="card"><p class="description">No inscriptions match your search filter within the chronicle.</p></div>`;
        } else {
            feedEl.innerHTML = posts.map(p => {
                const likes = p.likes || 0;
                const comments = p.comments || [];
                const isSaved = savedPosts.some(s => s.id === p.id);
                return `
                <div class="card" style="position:relative; background:linear-gradient(145deg, rgba(50, 16, 85, 0.9), rgba(22, 6, 45, 0.95)); border-color:rgba(255, 225, 120, 0.5);">
                    <div style="display:flex; justify-content:space-between; align-items:center; flex-wrap:wrap; gap:8px;">
                        <span class="author-badge">✦ Inscribed by: ${escapeHTML(p.author || 'Anonymous')}</span>
                        <span class="meta" style="margin:0; font-size:11px; opacity:0.8;">${escapeHTML(p.date)}</span>
                    </div>
                    
                    <div class="description" style="margin-top:12px; font-size:15px; border-left:3px solid #ffd700; padding-left:14px; white-space:pre-line; color:#f9f2ff;">${escapeHTML(p.text)}</div>
                    
                    ${p.image ? `<div style="margin-top:15px;"><img src="${p.image}" style="max-width:100%; max-height:300px; border-radius:10px; border:1px solid rgba(255,215,0,0.4);" alt="Attached evidence"></div>` : ''}

                    <div style="display:flex; gap:10px; margin-top:16px; align-items:center; flex-wrap:wrap; border-top:1px solid rgba(255,225,120,0.15); padding-top:12px;">
                        <button onclick="likeChroniclePost(${p.id})" style="background:rgba(120,30,160,0.5); border:1px solid rgba(255,215,0,0.4); color:#fff4bd; padding:6px 12px; border-radius:8px; cursor:pointer; font-size:12px; font-weight:800; display:flex; align-items:center; gap:5px;">
                            ❤️ Resonate (<span id="like-count-${p.id}">${likes}</span>)
                        </button>
                        <button onclick="toggleCommentBox(${p.id})" style="background:rgba(45,15,78,0.8); border:1px solid rgba(255,215,0,0.4); color:#f2e6ff; padding:6px 12px; border-radius:8px; cursor:pointer; font-size:12px; font-weight:800;">
                            💬 Comments (${comments.length})
                        </button>
                        <button onclick="deleteChroniclePost(${p.id})" style="background:rgba(140,25,25,0.7); border:1px solid rgba(255,100,100,0.5); color:#ffd7d7; padding:6px 12px; border-radius:8px; cursor:pointer; font-size:12px; font-weight:700;">
                            🗑️ Delete
                        </button>
                        <button onclick="toggleSavePost(${p.id})" style="background:${isSaved ? 'rgba(255,215,0,0.3)' : 'transparent'}; border:1px solid rgba(255,215,0,0.5); color:#fff4bd; padding:6px 12px; border-radius:8px; cursor:pointer; font-size:12px; font-weight:700;">
                            ${isSaved ? '★ Saved' : '☆ Save'}
                        </button>
                    </div>

                    <!-- Collapsible Comment Section -->
                    <div id="comment-section-${p.id}" style="display:none; margin-top:15px; border-top:1px dashed rgba(255,215,0,0.3); padding-top:12px;">
                        <div id="comment-list-${p.id}" style="margin-bottom:10px; max-height:200px; overflow-y:auto;">
                            ${comments.length === 0 ? '<p style="font-size:13px; color:#e8d7ff; opacity:0.7;">No reflections on this inscription yet. Add yours below.</p>' : 
                              comments.map(c => `<div style="background:rgba(20,5,40,0.7); padding:8px 12px; border-radius:8px; margin-bottom:6px; font-size:13px;"><strong style="color:#fff4bd;">${escapeHTML(c.author)}:</strong>${escapeHTML(c.text)}</div>`).join('')}
                        </div>
                        <div style="display:flex; gap:8px;">
                            <input id="comment-input-${p.id}" placeholder="Inscribe your reflection..." style="margin-bottom:0; font-size:13px; padding:10px;">
                            <button onclick="addComment(${p.id})" style="background:linear-gradient(135deg,#b026ff,#6a0dad); color:#fff; border:1px solid #fff4bd; border-radius:8px; padding:0 14px; font-weight:800; cursor:pointer; font-size:12px; white-space:nowrap;">Post</button>
                        </div>
                    </div>
                </div>
                `;
            }).join("");
        }
    }
}

async function likeChroniclePost(id){
    let posts = await fetchAllPosts();
    let target = posts.find(p => p.id === id);
    if(!target) return;
    const newLikes = (target.likes || 0) + 1;

    if (supabaseClient) {
        await supabaseClient.from('neti_posts').update({ likes: newLikes }).eq('id', id);
    }
    
    posts = posts.map(p => p.id === id ? {...p, likes: newLikes} : p);
    if (!supabaseClient) {
        localStorage.setItem("netiCommunityPosts", JSON.stringify(posts));
    }

    const countSpan = document.getElementById(`like-count-${id}`);
    if(countSpan){
        countSpan.textContent = newLikes;
    }
}

function toggleCommentBox(id){
    const box = document.getElementById(`comment-section-${id}`);
    if(box){
        box.style.display = box.style.display === 'none' ? 'block' : 'none';
    }
}

async function addComment(id){
    const input = document.getElementById(`comment-input-${id}`);
    if(!input || !input.value.trim()) return;
    const text = input.value.trim();
    
    let posts = await fetchAllPosts();
    let target = posts.find(p => p.id === id);
    if(!target) return;

    const comments = target.comments || [];
    comments.push({ author: "Seeker", text: text, date: new Date().toLocaleTimeString() });

    if (supabaseClient) {
        await supabaseClient.from('neti_posts').update({ comments: comments }).eq('id', id);
    }

    posts = posts.map(p => p.id === id ? {...p, comments: comments} : p);
    if (!supabaseClient) {
        localStorage.setItem("netiCommunityPosts", JSON.stringify(posts));
    }

    input.value = "";
    filterExplorePosts();
    const box = document.getElementById(`comment-section-${id}`);
    if(box) box.style.display = 'block';
}

async function deleteChroniclePost(id){
    if(confirm("क्या आप वाकई इस inscription को chronicle से मिटाना चाहते हैं?")){
        if (supabaseClient) {
            await supabaseClient.from('neti_posts').delete().eq('id', id);
        }

        let posts = JSON.parse(localStorage.getItem("netiCommunityPosts") || "[]");
        posts = posts.filter(p => p.id !== id);
        localStorage.setItem("netiCommunityPosts", JSON.stringify(posts));

        let saved = JSON.parse(localStorage.getItem("netiSavedPosts") || "[]");
        saved = saved.filter(s => s.id !== id);
        localStorage.setItem("netiSavedPosts", JSON.stringify(saved));

        filterExplorePosts();
    }
}

async function toggleSavePost(id){
    let posts = await fetchAllPosts();
    let saved = JSON.parse(localStorage.getItem("netiSavedPosts") || "[]");
    const target = posts.find(p => p.id === id);
    if(!target) return;
    
    const index = saved.findIndex(s => s.id === id);
    if(index > -1){
        saved.splice(index, 1);
        alert("Inscription removed from saved scrolls.");
    } else {
        saved.push(target);
        alert("Inscription saved to your reading list.");
    }
    localStorage.setItem("netiSavedPosts", JSON.stringify(saved));
    filterExplorePosts();
}
/* ========================================== */

function renderCreate(app){
    app.innerHTML = `
    <section class="mystic-hero" style="padding:25px 16px; margin-bottom:20px;">
        <h2 style="color:#ffffff; margin:0 0 8px 0; font-size:26px; font-family:'Cinzel',serif;">SCRIBE AN INSCRIPTION</h2>
        <p class="description" style="margin:0;">Commit your philosophical realization or dharma insight directly to the chronicle. Attach photographs or manuscript sketches via camera capture or device folder.</p>
    </section>
    <div class="card">
        <input id="userName" placeholder="Your Name or Alias...">
        <textarea id="userThesis" placeholder="Inscribe your philosophical insight here..."></textarea>
        
        <!-- Camera / File Attachment UI with Added Gallery Folder Button -->
        <div style="margin-bottom:16px; background:rgba(25,8,48,0.7); border:1px dashed rgba(255,215,0,0.5); padding:16px; border-radius:12px; text-align:center;">
            
            <!-- Camera Button -->
            <label style="cursor:pointer; display:block; background:#d4af37; color:#1a0033; padding:10px; border-radius:8px; font-weight:700; font-size:14px; margin-bottom:10px;">
                📷 Open Camera
                <input type="file" accept="image/*" capture="environment" id="cameraInput" style="display:none;" onchange="handleImageUpload(event)">
            </label>

            <!-- Gallery Folder Button inscribed right below camera -->
            <label style="cursor:pointer; display:block; background:rgba(212,175,55,0.2); border:1px solid #d4af37; color:#fff4bd; padding:10px; border-radius:8px; font-weight:700; font-size:14px;">
                📁 Open Gallery from Device
                <input type="file" accept="image/*" id="galleryInput" style="display:none;" onchange="handleImageUpload(event)">
            </label>

            <div id="imagePreviewContainer" style="margin-top:12px; display:none;">
                <img id="imageThumbnail" style="max-height:140px; border-radius:8px; border:1px solid #ffd700;" alt="Preview">
                <br>
                <button type="button" onclick="removeAttachedImage()" style="background:rgba(120,20,60,0.9); color:#fff; border:none; padding:4px 10px; border-radius:6px; font-size:11px; margin-top:8px; cursor:pointer;">Remove Image</button>
            </div>
        </div>

        <button class="postBtn" onclick="submitThesis()">PUBLISH TO CHRONICLE</button>
    </div>
    `;
    uploadedImageBase64 = "";
}

function handleImageUpload(event){
    const file = event.target.files[0];
    if(!file) return;
    const reader = new FileReader();
    reader.onload = function(e){
        uploadedImageBase64 = e.target.result;
        const thumb = document.getElementById("imageThumbnail");
        const container = document.getElementById("imagePreviewContainer");
        if(thumb && container){
            thumb.src = uploadedImageBase64;
            container.style.display = "block";
        }
    };
    reader.readAsDataURL(file);
}

function removeAttachedImage(){
    uploadedImageBase64 = "";
    const container = document.getElementById("imagePreviewContainer");
    const camInput = document.getElementById("cameraInput");
    const galInput = document.getElementById("galleryInput");
    if(container) container.style.display = "none";
    if(camInput) camInput.value = "";
    if(galInput) galInput.value = "";
}

async function submitThesis(){
    const author = document.getElementById("userName").value.trim() || "Anonymous";
    const text = document.getElementById("userThesis").value.trim();
    if(!text && !uploadedImageBase64){ alert("Please write your insight or attach an image before publishing."); return; }
    
    const newPost = { 
        id: Date.now(), 
        author: author, 
        text: text || "[Visual Manuscript Attachment]", 
        image: uploadedImageBase64,
        date: new Date().toLocaleString(), 
        likes: 0,
        comments: []
    };

    if (supabaseClient) {
        const { error } = await supabaseClient.from('neti_posts').insert([newPost]);
        if(error) console.error("Supabase insert error:", error);
    }

    const posts = JSON.parse(localStorage.getItem("netiCommunityPosts") || "[]");
    posts.push(newPost);
    localStorage.setItem("netiCommunityPosts", JSON.stringify(posts));

    alert("Inscription published successfully to the Chronicle!");
    document.getElementById("userName").value = "";
    document.getElementById("userThesis").value = "";
    removeAttachedImage();
    page('explore', document.querySelectorAll('nav button')[3]);
}

function escapeHTML(str){
    return String(str).replace(/&/g,"&amp;").replace(/</g,"&lt;").replace(/>/g,"&gt;").replace(/"/g,"&quot;").replace(/'/g,"&#039;");
}

render();
</script>

</body>
</html>
