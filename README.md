# Trending-express01
<!DOCTYPE html>
<html lang="hi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>🎥 मेरी सभी YouTube Videos & Shorts</title>
<meta name="description" content="मेरे सभी YouTube videos और shorts एक जगह">
<link rel="manifest" href="data:application/manifest+json,{
\"name\":\"मेरी Videos\",\"short_name\":\"Videos\",\"start_url\":\".\",
\"display\":\"standalone\",\"background_color\":\"#ff6b6b\",\"theme_color\":\"#4ecdc4\",
\"icons\":[{\"src\":\"https://via.placeholder.com/192/ff6b6b/fff?text=V\",\"sizes\":\"192x192\",\"type\":\"image/png\"}]
}">
<style>*{margin:0;padding:0;box-sizing:border-box;}body{font-family:system-ui;background:linear-gradient(135deg,#ff6b6b 0%,#4ecdc4 50%,#45b7d1 100%);min-height:100vh;padding:15px;color:#333;}.container{max-width:1200px;margin:0 auto;}.header{text-align:center;color:#fff;margin-bottom:30px;}.header h1{font-size:clamp(1.8em,5vw,2.8em);margin-bottom:10px;text-shadow:2px 2px 15px rgba(0,0,0,0.3);}.header p{font-size:1.1em;opacity:0.9;margin-bottom:10px;}.stats{display:flex;justify-content:center;gap:30px;flex-wrap:wrap;margin-bottom:30px;}.stat-card{background:rgba(255,255,255,0.2);backdrop-filter:blur(15px);padding:15px 25px;border-radius:20px;border:1px solid rgba(255,255,255,0.3);color:#fff;text-align:center;min-width:120px;}.video-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(350px,1fr));gap:25px;margin-bottom:30px;}.video-card{background:#fff;border-radius:20px;overflow:hidden;box-shadow:0 15px 40px rgba(0,0,0,0.15);transition:all 0.4s;}.video-card:hover{transform:translateY(-12px) scale(1.02);box-shadow:0 30px 70px rgba(0,0,0,0.25);}.video-container{position:relative;padding-bottom:56.25%;height:0;overflow:hidden;}.video-container iframe{position:absolute;top:0;left:0;width:100%;height:100%;}.video-info{padding:20px;background:linear-gradient(135deg,#f8f9fa 0%,#e9ecef 100%);}.video-title{font-weight:700;font-size:1.2em;color:#2c3e50;margin-bottom:12px;line-height:1.4;display:-webkit-box;-webkit-line-clamp:2;-webkit-box-orient:vertical;overflow:hidden;}.shorts-grid{grid-template-columns:repeat(auto-fit,minmax(280px,1fr));}.shorts-section{background:rgba(255,255,255,0.15);padding:30px;border-radius:25px;margin-top:40px;backdrop-filter:blur(20px);border:1px solid rgba(255,255,255,0.2);}.shorts-title{text-align:center;color:#fff;font-size:1.8em;margin-bottom:25px;text-shadow:1px 1px 10px rgba(0,0,0,0.3);}.footer{text-align:center;color:rgba(255,255,255,0.9);margin-top:40px;padding:25px;background:rgba(0,0,0,0.15);border-radius:20px;font-size:1em;backdrop-filter:blur(15px);}@media(max-width:768px){.video-grid,.shorts-grid{grid-template-columns:1fr;gap:20px;}.stats{gap:15px;}.stat-card{padding:12px 18px;font-size:0.9em;min-width:100px;}}</style>
</head>
<body>
<div class="container">
<div class="header">
<h1>🎥 मेरी सभी YouTube Videos</h1>
<p>9 Videos + Shorts | Fast Loading | Mobile Friendly</p>
<div class="stats">
<div class="stat-card"><strong>9</strong><br>Videos</div>
<div class="stat-card"><strong>100%</strong><br>Mobile</div>
<div class="stat-card"><strong>🚀</strong><br>Fast</div>
</div>
</div>

<div class="video-grid" id="videosSection">
<!-- Videos Auto-Load -->
</div>

<div class="shorts-section">
<h2 class="shorts-title">📱 YouTube Shorts</h2>
<div class="video-grid shorts-grid" id="shortsSection">
<!-- Shorts Auto-Load -->
</div>
</div>

<div class="footer">
💎 सभी videos YouTube से | Views यहाँ भी count होंगे 🔥 | Share करो!
</div>
</div>

<script>
const ALL_VIDEOS = [
    {id:"uloGGqGGmGE",title:"Short 1 🔥",isShort:true},
    {id:"Il0rToQN5Sw",title:"Short 2 💥",isShort:true},
    {id:"Ff1S_aFAb8s",title:"Short 3 🎉",isShort:true},
    {id:"s5nZx2GzXdA",title:"Video 1 🚀",isShort:false},
    {id:"4pvyCxgGu7E",title:"Video 2 💎",isShort:false},
    {id:"T7ttPtzLj2g",title:"Video 3 ⚡",isShort:false},
    {id:"rB7GCb9Wa_0",title:"Video 4 🎵",isShort:false},
    {id:"xvhkL48GjaQ",title:"Video 5 😍",isShort:false},
    {id:"srDFxLz7fb4",title:"Video 6 ⭐",isShort:false}
];

function createEmbedUrl(id){return`https://www.youtube.com/embed/${id}?controls=1&rel=0&modestbranding=1&iv_load_policy=3`;}

// Videos Load
const videos = ALL_VIDEOS.filter(v=>!v.isShort);
const shorts = ALL_VIDEOS.filter(v=>v.isShort);

document.getElementById('videosSection').innerHTML = videos.map((v,i)=>`
<div class="video-card">
<div class="video-container">
<iframe src="${createEmbedUrl(v.id)}" title="${v.title}" frameborder="0" allowfullscreen allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" referrerpolicy="strict-origin-when-cross-origin"></iframe>
</div>
<div class="video-info">
<div class="video-title">${v.title}</div>
</div>
</div>
`).join('');

document.getElementById('shortsSection').innerHTML = shorts.map((s,i)=>`
<div class="video-card">
<div class="video-container">
<iframe src="${createEmbedUrl(s.id)}" title="${s.title}" frameborder="0" allowfullscreen allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" referrerpolicy="strict-origin-when-cross-origin"></iframe>
</div>
<div class="video-info">
<div class="video-title">${s.title}</div>
</div>
</div>
`).join('');

// Smooth animations
document.addEventListener('DOMContentLoaded',()=>{
    document.body.style.opacity='0';
    document.body.style.transition='opacity 0.8s';
    setTimeout(()=>document.body.style.opacity='1',100);
    
    // Lazy load
    const iframes = document.querySelectorAll('iframe');
    const observer = new IntersectionObserver((entries)=>{
        entries.forEach(entry=>{
            if(entry.isIntersecting){
                const iframe = entry.target;
                iframe.src = iframe.dataset.src;
                observer.unobserve(iframe);
            }
        });
    });
    
    iframes.forEach(iframe=>{
        iframe.dataset.src = iframe.src;
        iframe.src = '';
        observer.observe(iframe);
    });
});
</script>
</body>
</html>
