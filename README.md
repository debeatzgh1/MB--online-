<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Debeatzgh Ultimate Ecosystem</title>
    <style>
        :root {
            --yt-red: #FF0000;
            --spotify-green: #1DB954;
            --cyber-cyan: #00f2ff;
            --deep-pink: #FF1493;
            --bg-dark: #0d1117;
            --glass: rgba(15, 15, 15, 0.9);
        }

        body { 
            margin: 0; 
            font-family: 'Inter', system-ui, -apple-system, sans-serif; 
            background: var(--bg-dark); 
            color: white;
            overflow-x: hidden;
        }

        /* --- GLOBAL TOP BANNER SYSTEM --- */
        .master-banner-container {
            position: fixed;
            top: 15px;
            left: 50%;
            transform: translateX(-50%);
            z-index: 10000;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 10px;
        }

        .floating-banner {
            width: 350px;
            height: 52px;
            background: var(--glass);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 50px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0 6px 0 15px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
            transition: 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        /* --- THEMES --- */
        .banner-productivity { border-color: var(--deep-pink); box-shadow: 0 0 15px rgba(255, 20, 147, 0.3); }
        .banner-entertainment { border-color: var(--yt-red); box-shadow: 0 0 15px rgba(255, 0, 0, 0.3); }
        .banner-ui { border-color: var(--cyber-cyan); box-shadow: 0 0 15px rgba(0, 242, 255, 0.3); }

        .banner-text-slider {
            flex: 1;
            height: 20px;
            overflow: hidden;
            margin-right: 10px;
        }

        .slide-inner {
            display: flex;
            flex-direction: column;
            animation: verticalSlide 6s infinite;
        }

        .slide-inner span {
            height: 20px;
            font-size: 0.75rem;
            font-weight: 700;
            display: flex;
            align-items: center;
            gap: 8px;
            white-space: nowrap;
        }

        @keyframes verticalSlide {
            0%, 25% { transform: translateY(0); }
            33%, 58% { transform: translateY(-20px); }
            66%, 91% { transform: translateY(-40px); }
            100% { transform: translateY(0); }
        }

        /* --- BUTTONS --- */
        .action-btn {
            padding: 8px 18px;
            border-radius: 50px;
            border: none;
            color: white;
            font-weight: 900;
            font-size: 0.7rem;
            cursor: pointer;
            text-transform: uppercase;
        }

        /* --- IFRAME OVERLAY --- */
        #master-overlay {
            position: fixed;
            inset: 0;
            background: rgba(0,0,0,0.97);
            z-index: 20000;
            display: none;
            flex-direction: column;
        }

        .overlay-header {
            height: 60px;
            padding: 0 20px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            background: #111;
            border-bottom: 2px solid #333;
        }

        #master-frame { width: 100%; flex-grow: 1; border: none; background: white; }

        /* --- SMART TOGGLE DOCK --- */
        .mode-dock {
            position: fixed;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            background: var(--glass);
            padding: 8px;
            border-radius: 20px;
            display: flex;
            gap: 10px;
            border: 1px solid rgba(255,255,255,0.1);
            z-index: 9999;
        }

        .dock-dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            cursor: pointer;
            transition: 0.3s;
        }

        .dot-pink { background: var(--deep-pink); }
        .dot-red { background: var(--yt-red); }
        .dot-cyan { background: var(--cyber-cyan); }
        .dock-dot:hover { transform: scale(1.4); }

    </style>
</head>
<body>

    <div class="master-banner-container">
        
        <div id="banner-prod" class="floating-banner banner-productivity">
            <div class="banner-text-slider">
                <div class="slide-inner">
                    <span style="color: var(--deep-pink);">🚀 Lifestyle Productivity</span>
                    <span style="color: var(--deep-pink);">💡 Tools & Ideas</span>
                    <span style="color: var(--deep-pink);">📈 All in one place!</span>
                </div>
            </div>
            <button class="action-btn" style="background: var(--deep-pink);" onclick="launch('https://docs.google.com/document/d/1yTeRMaF8GEkTZf34EK7eOdxe6sCOCNxX/edit?usp=drivesdk&ouid=116845182021782803040&rtpof=true&sd=true', 'Productivity Hub')">Open Hub</button>
        </div>

        <div id="banner-ent" class="floating-banner banner-entertainment" style="display: none;">
            <div class="banner-text-slider">
                <div class="slide-inner">
                    <span style="color: var(--yt-red);">🎬 Entertainment Hub</span>
                    <span style="color: var(--yt-red);">🎵 Stream Playlists</span>
                    <span style="color: var(--yt-red);">🔴 Live Updates</span>
                </div>
            </div>
            <button class="action-btn" style="background: var(--yt-red);" onclick="launch('https://docs.google.com/document/d/1yTeRMaF8GEkTZf34EK7eOdxe6sCOCNxX/edit?usp=drivesdk&ouid=116845182021782803040&rtpof=true&sd=true', 'Entertainment Player')">Watch</button>
        </div>

        <div id="banner-ui" class="floating-banner banner-ui" style="display: none;">
            <div class="banner-text-slider">
                <div class="slide-inner">
                    <span style="color: var(--cyber-cyan);">🖥️ Browse UI & Interfaces</span>
                    <span style="color: var(--cyber-cyan);">🎨 Modern Styling</span>
                    <span style="color: var(--cyber-cyan);">📂 Design Systems</span>
                </div>
            </div>
            <button class="action-btn" style="background: var(--cyber-cyan); color: #000;" onclick="launch('https://debeatzgh1.github.io/me-/', 'UI Portfolio')">Explore</button>
        </div>

    </div>

    <div id="master-overlay">
        <div class="overlay-header" id="overlay-header-bar">
            <span id="overlay-title" style="font-weight: bold; text-transform: uppercase; font-size: 0.8rem;">Resource View</span>
            <div style="display:flex; gap: 10px;">
                <button onclick="closeOverlay()" style="background: #444; color: white; border: none; padding: 6px 15px; border-radius: 4px; cursor: pointer;">Close</button>
            </div>
        </div>
        <iframe id="master-frame" src=""></iframe>
    </div>

    <div class="mode-dock">
        <div class="dock-dot dot-pink" title="Productivity Mode" onclick="switchMode('prod')"></div>
        <div class="dock-dot dot-red" title="Entertainment Mode" onclick="switchMode('ent')"></div>
        <div class="dock-dot dot-cyan" title="UI/UX Mode" onclick="switchMode('ui')"></div>
    </div>

    <script>
        const banners = {
            prod: document.getElementById('banner-prod'),
            ent: document.getElementById('banner-ent'),
            ui: document.getElementById('banner-ui')
        };

        const overlay = document.getElementById('master-overlay');
        const frame = document.getElementById('master-frame');
        const header = document.getElementById('overlay-header-bar');

        // Switch Banner Modes
        function switchMode(mode) {
            Object.values(banners).forEach(b => b.style.display = 'none');
            banners[mode].style.display = 'flex';
            // Save preference
            localStorage.setItem('master-mode', mode);
        }

        // Launch Iframe
        function launch(url, title) {
            document.getElementById('overlay-title').innerText = title;
            frame.src = url;
            overlay.style.display = 'flex';
            document.body.style.overflow = 'hidden';

            // Change header color based on active mode
            const activeMode = localStorage.getItem('master-mode');
            const colors = { prod: '#FF1493', ent: '#FF0000', ui: '#00f2ff' };
            header.style.borderBottomColor = colors[activeMode];
        }

        function closeOverlay() {
            overlay.style.display = 'none';
            frame.src = '';
            document.body.style.overflow = 'auto';
        }

        // Load saved mode or default to prod
        window.onload = () => {
            const saved = localStorage.getItem('master-mode') || 'prod';
            switchMode(saved);
        };
    </script>

</body>
</html>






<!--  Universal Embed Launcher -->
<script>
(function(){

/* ================= CONFIG ================= */
const DBZ_HOME = "https://www.socialcreator.com/techshop/?s=314040";
const BTN_SIZE = 52;
const BTN_COLOR = "#0f2a44";

/* ================= STYLES ================= */
const css = `
#dbz-btn{
  position:fixed;
  right:16px;
  top:50%;
  transform:translateY(-50%);
  width:${BTN_SIZE}px;
  height:${BTN_SIZE}px;
  border-radius:50%;
  background:${BTN_COLOR};
  color:#fff;
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:22px;
  cursor:pointer;
  z-index:999999;
  box-shadow:0 12px 30px rgba(0,0,0,.35);
  animation:dbzPulse 1.6s infinite;
}
@keyframes dbzPulse{
  0%,100%{transform:translateY(-50%) scale(1)}
  50%{transform:translateY(-50%) scale(1.08)}
}

#dbz-overlay{
  position:fixed;
  inset:0;
  background:rgba(0,0,0,.72);
  backdrop-filter:blur(6px);
  display:none;
  z-index:999998;
}

#dbz-box{
  position:absolute;
  inset:12px;
  background:#fff;
  border-radius:16px;
  overflow:hidden;
  display:flex;
  flex-direction:column;
}

#dbz-bar{
  background:${BTN_COLOR};
  color:#fff;
  padding:8px 12px;
  display:flex;
  justify-content:space-between;
  align-items:center;
  font-size:14px;
}

#dbz-bar button{
  background:none;
  border:none;
  color:#fff;
  font-size:16px;
  cursor:pointer;
  margin-left:6px;
}
`;
const style = document.createElement("style");
style.innerHTML = css;
document.head.appendChild(style);

/* ================= HTML ================= */
const html = `
<div id="dbz-btn" title="Open Debeatzgh Hub">☰</div>

<div id="dbz-overlay">
  <div id="dbz-box">
    <div id="dbz-bar">
      <div>
        <button id="dbz-back">⟵</button>
        <button id="dbz-forward">⟶</button>
      </div>
      <div>
        <button id="dbz-full">⛶</button>
        <button id="dbz-close">✕</button>
      </div>
    </div>
    <iframe id="dbz-frame" style="flex:1;border:none"></iframe>
  </div>
</div>
`;
document.body.insertAdjacentHTML("beforeend", html);

/* ================= LOGIC ================= */
const btn = document.getElementById("dbz-btn");
const overlay = document.getElementById("dbz-overlay");
const frame = document.getElementById("dbz-frame");
const box = document.getElementById("dbz-box");

btn.onclick = ()=>{
  frame.src = DBZ_HOME;
  overlay.style.display = "block";
};

document.getElementById("dbz-close").onclick = ()=>{
  overlay.style.display = "none";
  frame.src = "";
  if(document.fullscreenElement) document.exitFullscreen();
};

document.getElementById("dbz-back").onclick = ()=>{
  try{frame.contentWindow.history.back()}catch(e){}
};

document.getElementById("dbz-forward").onclick = ()=>{
  try{frame.contentWindow.history.forward()}catch(e){}
};

document.getElementById("dbz-full").onclick = ()=>{
  if(!document.fullscreenElement){
    box.requestFullscreen();
  }else{
    document.exitFullscreen();
  }
};

})();
</script>
<!-- End Debeatzgh Embed -->




<!-- Elfsight Slider | Untitled Slider -->
<script src="https://elfsightcdn.com/platform.js" async></script>
<div class="elfsight-app-749254b7-56a7-4b52-b472-0417608aa2ae" data-elfsight-app-lazy></div>


<html lang="en">
<head>
    <style>
        :root {
            --glass-bg: rgba(13, 17, 23, 0.98);
            --glass-border: rgba(88, 166, 255, 0.4);
            --accent-glow: #58a6ff;
        }

        /* 1. TOP-CENTER OVERLAY */
        #promo-banner {
            position: fixed;
            top: 20px; /* Positioned at top */
            left: 50%;
            transform: translate(-50%, -150%); /* Hidden above screen */
            opacity: 0;
            visibility: hidden;
            
            width: 90%;
            max-width: 360px;
            background: var(--glass-bg);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            border-radius: 20px;
            padding: 20px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.6);
            z-index: 10000;
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.1);
            cursor: pointer;
        }

        #promo-banner.active {
            transform: translate(-50%, 0); /* Slides down into view */
            opacity: 1;
            visibility: visible;
        }

        /* 2. SLIDE CONTENT WITH THUMBNAILS */
        .slide-container {
            position: relative;
            height: 70px;
            overflow: hidden;
        }

        .slide {
            position: absolute;
            width: 100%;
            display: flex; /* Flex for Image + Text */
            align-items: center;
            gap: 15px;
            opacity: 0;
            transform: translateX(20px);
            transition: all 0.5s ease;
        }

        .slide.current {
            opacity: 1;
            transform: translateX(0);
        }

        .thumb {
            width: 50px;
            height: 50px;
            border-radius: 12px;
            object-fit: cover;
            border: 1px solid var(--glass-border);
        }

        .text-content {
            text-align: left;
            flex: 1;
        }

        #promo-banner p {
            margin: 0;
            font-size: 0.85rem;
            color: #ffffff;
            line-height: 1.3;
        }

        .highlight { color: var(--accent-glow); font-weight: 700; }

        .badge {
            background: var(--accent-glow);
            color: #000;
            font-size: 0.6rem;
            padding: 1px 8px;
            border-radius: 4px;
            font-weight: 800;
            text-transform: uppercase;
            margin-bottom: 4px;
            display: inline-block;
        }

        /* 3. TOP-RIGHT FLOATING LAUNCHER */
        #floating-trigger {
            position: fixed;
            right: 20px;
            top: 20px; /* Positioned at top */
            width: 50px;
            height: 50px;
            background: var(--accent-glow);
            border-radius: 15px;
            display: none;
            align-items: center;
            justify-content: center;
            color: #0d1117;
            cursor: pointer;
            box-shadow: 0 5px 15px rgba(88, 166, 255, 0.4);
            z-index: 9997;
            animation: pulse-top 2s infinite;
        }

        @keyframes pulse-top {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        /* 4. UTILS */
        .close-btn {
            position: absolute;
            bottom: -35px; /* Moved close button below for top-banner UX */
            left: 50%;
            transform: translateX(-50%);
            background: rgba(255,255,255,0.1);
            color: white;
            border: 1px solid rgba(255,255,255,0.2);
            border-radius: 20px;
            padding: 4px 15px;
            font-size: 0.7rem;
            cursor: pointer;
            backdrop-filter: blur(5px);
        }

        #progress-bar {
            position: absolute;
            top: 0;
            left: 0;
            height: 3px;
            background: var(--accent-glow);
            width: 0%;
            transition: width 3s linear;
            border-radius: 20px 20px 0 0;
        }
    </style>
</head>
<body>

    <div id="promo-banner">
        <div id="progress-bar"></div>
        
        <div class="slide-container">
            <div class="slide current" data-link="https://debeatzgh1.github.io/Home-/">
                <img src="https://picsum.photos/100?random=1" class="thumb" alt="icon">
                <div class="text-content">
                    <span class="badge">Ecosystem</span>
                    <p>Your sleek <span class="highlight">lifestyle hub</span> is ready.</p>
                </div>
            </div>
            <div class="slide" data-link="https://t.me/Miningstoncoin99_bot">
                <img src="https://picsum.photos/100?random=2" class="thumb" alt="icon">
                <div class="text-content">
                    <span class="badge">Mining</span>
                    <p>Verified <span class="highlight">Crypto Bots</span> active now.</p>
                </div>
            </div>
            <div class="slide" data-link="https://mybrandsonline.blogspot.com/">
                <img src="https://picsum.photos/100?random=3" class="thumb" alt="icon">
                <div class="text-content">
                    <span class="badge">Insights</span>
                    <p>Latest <span class="highlight">Brand News</span> and updates.</p>
                </div>
            </div>
        </div>

        <button class="close-btn" onclick="closeBanner(event)">Dismiss</button>
    </div>

    <div id="floating-trigger" onclick="showBannerSequence()">
        <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><path d="M18 15l-6-6-6 6"/></svg>
    </div>

    <script>
        const banner = document.getElementById('promo-banner');
        const fab = document.getElementById('floating-trigger');
        const slides = document.querySelectorAll('.slide');
        const progress = document.getElementById('progress-bar');
        
        let currentSlide = 0;
        let slideInterval;

        banner.onclick = () => {
            window.open(slides[currentSlide].getAttribute('data-link'), '_blank');
        };

        function resetProgress() {
            progress.style.transition = 'none';
            progress.style.width = '0%';
            setTimeout(() => {
                progress.style.transition = 'width 3s linear';
                progress.style.width = '100%';
            }, 50);
        }

        function startAutoSlide() {
            resetProgress();
            slideInterval = setInterval(() => {
                slides[currentSlide].classList.remove('current');
                currentSlide = (currentSlide + 1) % slides.length;
                slides[currentSlide].classList.add('current');
                resetProgress();
            }, 3000);
        }

        function showBannerSequence() {
            fab.style.display = 'none';
            banner.classList.add('active');
            startAutoSlide();
        }

        function closeBanner(event) {
            event.stopPropagation(); 
            banner.classList.remove('active');
            fab.style.display = 'flex';
            clearInterval(slideInterval);
        }

        window.onload = () => setTimeout(showBannerSequence, 1000);
    </script>
</body>
</html>



<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Brands Online | News Feed</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        .glass-morphism {
            background: rgba(255, 255, 255, 0.9);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }
        .carousel-track { transition: transform 0.5s ease-in-out; }
    </style>
</head>
<body class="bg-gray-50 font-sans">

    <div class="max-w-6xl mx-auto px-4 py-8">
        <header class="mb-10 text-center">
            <h1 class="text-4xl font-bold text-gray-800">My Brands Online</h1>
            <p class="text-gray-500 mt-2">Latest Professional Updates & Insights</p>
        </header>

        <section class="mb-12 relative overflow-hidden rounded-2xl shadow-xl bg-slate-900 text-white p-8">
            <div class="flex items-center mb-4">
                <span class="bg-blue-600 text-xs font-bold px-2 py-1 rounded mr-2">AI SUMMARY</span>
                <h2 class="text-xl font-semibold">Featured Highlights</h2>
            </div>
            
            <div id="carousel" class="h-48 relative">
                <div id="carousel-content" class="absolute w-full h-full flex flex-col justify-center">
                    <p id="ai-text" class="text-lg italic leading-relaxed text-gray-200">Loading latest summaries...</p>
                    <a id="ai-link" href="#" class="mt-4 text-blue-400 hover:underline inline-block">Read full story →</a>
                </div>
            </div>
        </section>

        <div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
            
            <div class="lg:col-span-1 space-y-4 overflow-y-auto max-h-[700px] pr-2" id="feed-list">
                <div class="animate-pulse flex flex-col space-y-4">
                    <div class="h-24 bg-gray-200 rounded-lg"></div>
                    <div class="h-24 bg-gray-200 rounded-lg"></div>
                    <div class="h-24 bg-gray-200 rounded-lg"></div>
                </div>
            </div>

            <div class="lg:col-span-2 sticky top-4">
                <div class="glass-morphism rounded-2xl shadow-2xl overflow-hidden border border-gray-200 h-[700px] flex flex-col">
                    <div class="bg-white p-4 border-b flex justify-between items-center">
                        <div class="flex items-center space-x-2">
                            <span class="w-3 h-3 rounded-full bg-red-400"></span>
                            <span class="w-3 h-3 rounded-full bg-yellow-400"></span>
                            <span class="w-3 h-3 rounded-full bg-green-400"></span>
                            <span id="preview-title" class="ml-4 text-sm font-medium text-gray-600 truncate max-w-xs">Select a post to preview</span>
                        </div>
                        <a id="new-tab-btn" href="https://mybrandsonline.blogspot.com/" target="_blank" class="bg-blue-600 hover:bg-blue-700 text-white px-4 py-2 rounded-lg text-sm transition flex items-center">
                            Open in New Tab <i class="fas fa-external-link-alt ml-2 text-xs"></i>
                        </a>
                    </div>
                    <iframe id="preview-iframe" src="https://mybrandsonline.blogspot.com/" class="w-full flex-grow border-none"></iframe>
                </div>
            </div>

        </div>
    </div>

    <script>
        const RSS_URL = 'https://mybrandsonline.blogspot.com/feeds/posts/default?alt=json';
        let posts = [];
        let currentCarouselIndex = 0;

        async function fetchFeed() {
            try {
                const response = await fetch(RSS_URL);
                const data = await response.json();
                posts = data.feed.entry;
                renderFeed();
                startCarousel();
            } catch (error) {
                console.error('Error fetching feed:', error);
            }
        }

        function renderFeed() {
            const container = document.getElementById('feed-list');
            container.innerHTML = '';

            posts.forEach((post, index) => {
                const title = post.title.$t;
                const link = post.link.find(l => l.rel === 'alternate').href;
                const published = new Date(post.published.$t).toLocaleDateString();
                const snippet = post.content.$t.replace(/<[^>]*>?/gm, '').substring(0, 100) + '...';

                const card = document.createElement('div');
                card.className = "p-4 bg-white rounded-xl shadow-sm border border-gray-100 cursor-pointer hover:border-blue-500 transition-all group";
                card.onclick = () => updatePreview(link, title);
                
                card.innerHTML = `
                    <p class="text-[10px] text-blue-600 font-bold uppercase mb-1">${published}</p>
                    <h3 class="font-bold text-gray-800 group-hover:text-blue-600 transition-colors line-clamp-2">${title}</h3>
                    <p class="text-sm text-gray-500 mt-2 line-clamp-2">${snippet}</p>
                `;
                container.appendChild(card);
            });
        }

        function updatePreview(url, title) {
            document.getElementById('preview-iframe').src = url;
            document.getElementById('preview-title').innerText = title;
            document.getElementById('new-tab-btn').href = url;
        }

        function startCarousel() {
            const aiText = document.getElementById('ai-text');
            const aiLink = document.getElementById('ai-link');

            function updateCarousel() {
                const post = posts[currentCarouselIndex];
                const title = post.title.$t;
                const snippet = post.content.$t.replace(/<[^>]*>?/gm, '').substring(0, 180) + '...';
                const link = post.link.find(l => l.rel === 'alternate').href;

                aiText.style.opacity = 0;
                setTimeout(() => {
                    aiText.innerText = `"${snippet}"`;
                    aiLink.href = link;
                    aiText.style.opacity = 1;
                }, 500);

                currentCarouselIndex = (currentCarouselIndex + 1) % posts.length;
            }

            updateCarousel();
            setInterval(updateCarousel, 6000); // Auto slide every 6 seconds
        }

        fetchFeed();
    </script>
</body>
</html>


<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Digital Products Catalog</title>
<style>
  body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background: #f5f5f5;
    margin: 0;
    padding: 20px;
  }

  h2 {
    text-align: center;
    color: #16a34a;
    margin-bottom: 20px;
  }

  .carousel {
    display: flex;
    overflow-x: auto;
    scroll-behavior: smooth;
    gap: 20px;
    padding-bottom: 10px;
  }

  .carousel::-webkit-scrollbar {
    height: 8px;
  }

  .carousel::-webkit-scrollbar-thumb {
    background: #16a34a;
    border-radius: 4px;
  }

  .product-card {
    background: #fff;
    border-radius: 12px;
    box-shadow: 0 4px 12px rgba(0,0,0,0.1);
    min-width: 250px;
    flex: 0 0 auto;
    padding: 15px;
    transition: transform 0.3s;
  }

  .product-card:hover {
    transform: translateY(-5px);
  }

  .product-card img {
    width: 100%;
    border-radius: 10px;
    object-fit: cover;
    height: 140px;
  }

  .product-title {
    font-size: 16px;
    font-weight: bold;
    margin: 10px 0 5px;
    color: #111;
  }

  .product-desc {
    font-size: 14px;
    color: #555;
    margin-bottom: 10px;
  }

  .product-btn {
    display: inline-block;
    padding: 8px 14px;
    background: #16a34a;
    color: #fff;
    text-decoration: none;
    border-radius: 6px;
    font-weight: bold;
    transition: background 0.3s;
    cursor: pointer;
  }

  .product-btn:hover {
    background: #13803d;
  }

  /* Fullscreen iframe overlay */
  #iframeOverlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0,0,0,0.85);
    display: none;
    align-items: center;
    justify-content: center;
    z-index: 999;
  }

  #iframeOverlay iframe {
    width: 90%;
    height: 90%;
    border: none;
    border-radius: 10px;
    box-shadow: 0 0 20px rgba(0,0,0,0.5);
  }

  #iframeOverlay .close-btn {
    position: absolute;
    top: 20px;
    right: 30px;
    font-size: 28px;
    color: #fff;
    cursor: pointer;
    font-weight: bold;
  }
</style>
</head>
<body>

<h2>Digital Products Catalog</h2>

<div class="carousel">
  <!-- Product Cards -->
  <div class="product-card">
    <img src="https://via.placeholder.com/300x140?text=Appgeyser" alt="Appgeyser">
    <div class="product-title">Appgeyser</div>
    <div class="product-desc">Create mobile apps quickly without coding.</div>
    <a class="product-btn" onclick="openLink('https://gitlab.com/debeatz4/Digital-creators-hub/-/wikis/home#note_2967486121')">View</a>
  </div>

  <div class="product-card">
    <img src="https://via.placeholder.com/300x140?text=Beehive" alt="Beehive">
    <div class="product-title">Beehive</div>
    <div class="product-desc">Manage your business workflow efficiently.</div>
    <a class="product-btn" onclick="openLink('https://gitlab.com/debeatz4/Digital-creators-hub/-/wikis/home#note_2967483111')">View</a>
  </div>

  <div class="product-card">
    <img src="https://via.placeholder.com/300x140?text=Adkeep" alt="Adkeep">
    <div class="product-title">Adkeep</div>
    <div class="product-desc">Track and optimize your ad campaigns easily.</div>
    <a class="product-btn" onclick="openLink('https://gitlab.com/debeatz4/Digital-creators-hub/-/wikis/home#note_2967348012')">View</a>
  </div>

  <div class="product-card">
    <img src="https://via.placeholder.com/300x140?text=Fiverr" alt="Fiverr">
    <div class="product-title">Fiverr</div>
    <div class="product-desc">Hire freelancers for any task or project.</div>
    <a class="product-btn" onclick="openLink('https://gitlab.com/debeatz4/Digital-creators-hub/-/wikis/home#note_2967513178')">View</a>
  </div>

  <div class="product-card">
    <img src="https://via.placeholder.com/300x140?text=Appcreator24" alt="Appcreator24">
    <div class="product-title">Appcreator24</div>
    <div class="product-desc">Build apps quickly and publish to stores.</div>
    <a class="product-btn" onclick="openLink('https://gitlab.com/debeatz4/Digital-creators-hub/-/wikis/home#note_2967511028')">View</a>
  </div>

  <div class="product-card">
    <img src="https://via.placeholder.com/300x140?text=Alibaba" alt="Alibaba">
    <div class="product-title">Alibaba</div>
    <div class="product-desc">Find suppliers and source products globally.</div>
    <a class="product-btn" onclick="openLink('https://gitlab.com/debeatz4/Digital-creators-hub/-/wikis/home#note_2967509414')">View</a>
  </div>

  <div class="product-card">
    <img src="https://via.placeholder.com/300x140?text=Help+Desk" alt="Help Desk">
    <div class="product-title">Help Desk</div>
    <div class="product-desc">Provide customer support with ease.</div>
    <a class="product-btn" onclick="openLink('https://gitlab.com/debeatz4/Digital-creators-hub/-/wikis/home#note_2967506031')">View</a>
  </div>

  <div class="product-card">
    <img src="https://via.placeholder.com/300x140?text=Takeapp" alt="Takeapp">
    <div class="product-title">Takeapp</div>
    <div class="product-desc">Create and manage mobile apps effortlessly.</div>
    <a class="product-btn" onclick="openLink('https://gitlab.com/debeatz4/Digital-creators-hub/-/wikis/home#note_2967505306')">View</a>
  </div>

  <div class="product-card">
    <img src="https://via.placeholder.com/300x140?text=Adsterra" alt="Adsterra">
    <div class="product-title">Adsterra</div>
    <div class="product-desc">Monetize your website traffic effectively.</div>
    <a class="product-btn" onclick="openLink('https://gitlab.com/debeatz4/Digital-creators-hub/-/wikis/home#note_2967503347')">View</a>
  </div>

  <div class="product-card">
    <img src="https://via.placeholder.com/300x140?text=Ecwid" alt="Ecwid">
    <div class="product-title">Ecwid</div>
    <div class="product-desc">Turn any website into an online store.</div>
    <a class="product-btn" onclick="openLink('https://gitlab.com/debeatz4/Digital-creators-hub/-/wikis/home#note_2967502392')">View</a>
  </div>

  <div class="product-card">
    <img src="https://via.placeholder.com/300x140?text=Logo+Maker" alt="Logo Maker">
    <div class="product-title">Logo Maker</div>
    <div class="product-desc">Design professional logos in minutes.</div>
    <a class="product-btn" onclick="openLink('https://gitlab.com/debeatz4/Digital-creators-hub/-/wikis/home#note_2967500184')">View</a>
  </div>

  <div class="product-card">
    <img src="https://via.placeholder.com/300x140?text=Yazing" alt="Yazing">
    <div class="product-title">Yazing</div>
    <div class="product-desc">Affiliate marketing made simple and profitable.</div>
    <a class="product-btn" onclick="openLink('https://gitlab.com/debeatz4/Digital-creators-hub/-/wikis/home#note_2967499210')">View</a>
  </div>

  <div class="product-card">
    <img src="https://via.placeholder.com/300x140?text=Elfsight" alt="Elfsight">
    <div class="product-title">Elfsight</div>
    <div class="product-desc">Add widgets and integrations to your website.</div>
    <a class="product-btn" onclick="openLink('https://gitlab.com/debeatz4/Digital-creators-hub/-/wikis/home#note_2967498283')">View</a>
  </div>

  <div class="product-card">
    <img src="https://via.placeholder.com/300x140?text=Technoant" alt="Technoant">
    <div class="product-title">Technoant</div>
    <div class="product-desc">Create professional apps for Android and iOS.</div>
    <a class="product-btn" onclick="openLink('https://gitlab.com/debeatz4/Digital-creators-hub/-/wikis/home#note_2967496836')">View</a>
  </div>

  <div class="product-card">
    <img src="https://via.placeholder.com/300x140?text=Website+Coin" alt="Website Coin">
    <div class="product-title">Website Coin</div>
    <div class="product-desc">Monetize websites and earn digital currency.</div>
    <a class="product-btn" onclick="openLink('https://gitlab.com/debeatz4/Digital-creators-hub/-/wikis/home#note_2967494603')">View</a>
  </div>

  <div class="product-card">
    <img src="https://via.placeholder.com/300x140?text=Discount" alt="Discount">
    <div class="product-title">Discount</div>
    <div class="product-desc">Get the best deals and coupon offers online.</div>
    <a class="product-btn" onclick="openLink('https://gitlab.com/debeatz4/Digital-creators-hub/-/wikis/home#note_2967491004')">View</a>
  </div>

  <div class="product-card">
    <img src="https://via.placeholder.com/300x140?text=Hosterbox" alt="Hosterbox">
    <div class="product-title">Hosterbox</div>
    <div class="product-desc">Reliable web hosting services for all needs.</div>
    <a class="product-btn" onclick="openLink('https://gitlab.com/debeatz4/Digital-creators-hub/-/wikis/home#note_2967488810')">View</a>
  </div>

  <div class="product-card">
    <img src="https://via.placeholder.com/300x140?text=Stylsi+AI" alt="Stylsi AI">
    <div class="product-title">Stylsi AI</div>
    <div class="product-desc">AI-powered tool for creative content generation.</div>
    <a class="product-btn" onclick="openLink('https://gitlab.com/debeatz4/Digital-creators-hub/-/wikis/home#note_2967487653')">View</a>
  </div>
</div>

<!-- Fullscreen iframe overlay -->
<div id="iframeOverlay">
  <span class="close-btn" onclick="closeIframe()">×</span>
  <iframe id="productIframe" src=""></iframe>
</div>

<script>
  function openLink(url) {
    // List of Blogger domains to open in iframe
    const bloggerDomains = ['blogspot', 'wordpress', 'tumblr'];

    const isBlogger = bloggerDomains.some(domain => url.includes(domain));
    if(isBlogger) {
      document.getElementById('productIframe').src = url;
      document.getElementById('iframeOverlay').style.display = 'flex';
    } else {
      window.open(url, '_blank');
    }
  }

  function closeIframe() {
    const iframe = document.getElementById('productIframe');
    iframe.src = '';
    document.getElementById('iframeOverlay').style.display = 'none';
  }
</script>

</body>
</html>


<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Telegram Tools & Bots | Official Links</title>

<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">

<style>
:root{
  --tg:#229ED9;
  --bg:#0f172a;
  --card:#020617;
  --border:#1e293b;
  --text:#e5e7eb;
  --muted:#94a3b8;
}

*{box-sizing:border-box;margin:0;padding:0}
body{
  font-family:Inter,system-ui;
  background:linear-gradient(180deg,#020617,#020617 60%,#020617);
  color:var(--text);
}

.container{
  max-width:900px;
  margin:auto;
  padding:20px;
}

header{
  text-align:center;
  padding:30px 15px;
}

header h1{
  font-size:28px;
  font-weight:700;
}

header p{
  color:var(--muted);
  margin-top:8px;
  font-size:15px;
}

.section{
  margin-top:35px;
}

.section h2{
  font-size:18px;
  margin-bottom:15px;
  color:#38bdf8;
}

.grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(260px,1fr));
  gap:15px;
}

.card{
  background:linear-gradient(180deg,#020617,#020617);
  border:1px solid var(--border);
  border-radius:14px;
  padding:16px;
  display:flex;
  flex-direction:column;
  gap:12px;
}

.card h3{
  font-size:16px;
  font-weight:600;
}

.card p{
  font-size:13px;
  color:var(--muted);
  line-height:1.5;
}

.card a{
  margin-top:auto;
  background:var(--tg);
  color:white;
  text-decoration:none;
  text-align:center;
  padding:12px;
  border-radius:10px;
  font-weight:600;
  transition:.2s;
}

.card a:hover{
  background:#1d8dc1;
}

footer{
  text-align:center;
  margin:40px 0 20px;
  color:var(--muted);
  font-size:13px;
}
</style>
</head>

<body>
<div class="container">

<header>
  <h1>🚀 Telegram Bots & Tools</h1>
  <p>Verified earning bots, crypto tools, VPNs & Telegram Stars services</p>
</header>

<!-- CRYPTO & MINING -->
<div class="section">
<h2>⛏️ Crypto & Mining Bots</h2>
<div class="grid">
  <div class="card">
    <h3>Mining Stone Coin</h3>
    <p>Automated mining & reward bot for Telegram users.</p>
    <a href="https://t.me/Miningstoncoin99_bot?start=_tgr_qqyyShM5Mjg0" target="_blank">Open Bot</a>
  </div>

  <div class="card">
    <h3>Metamon Bot</h3>
    <p>Play-to-earn crypto game bot with rewards.</p>
    <a href="https://t.me/Metamon969_Bot?start=_tgr_f4IOomcxNWM8" target="_blank">Open Bot</a>
  </div>

  <div class="card">
    <h3>Crypto Signals</h3>
    <p>Daily crypto trading signals & alerts.</p>
    <a href="https://t.me/cryptozsignals_bot?start=_tgr_oI6kA6VmNWU0" target="_blank">Join Signals</a>
  </div>
</div>
</div>

<!-- TELEGRAM STARS -->
<div class="section">
<h2>⭐ Telegram Stars & Payments</h2>
<div class="grid">
  <div class="card">
    <h3>Accept Telegram Stars</h3>
    <p>Accept and manage Telegram Stars payments easily.</p>
    <a href="https://t.me/Accepttelegramstarsbot?start=_tgr_ZukXam5iZWU8" target="_blank">Launch Bot</a>
  </div>

  <div class="card">
    <h3>Star Wallet Auto</h3>
    <p>Auto wallet for Telegram Stars transactions.</p>
    <a href="https://t.me/Starwalletauto_bot?start=_tgr_rpYLlQw5MmM0" target="_blank">Launch Bot</a>
  </div>

  <div class="card">
    <h3>Stars Buyer</h3>
    <p>Buy and manage Telegram Stars securely.</p>
    <a href="https://t.me/Starsbuyerro_bot?start=_tgr_eAkQRNsxMzdk" target="_blank">Open Bot</a>
  </div>
</div>
</div>

<!-- GAMES & REWARDS -->
<div class="section">
<h2>🎮 Games & Rewards</h2>
<div class="grid">
  <div class="card">
    <h3>Spin Star</h3>
    <p>Spin, play and earn rewards daily.</p>
    <a href="https://t.me/SpinStar5_bot?start=_tgr_TjzwOUxjYzU8" target="_blank">Play Now</a>
  </div>

  <div class="card">
    <h3>Sell Game</h3>
    <p>Game marketplace & earning bot.</p>
    <a href="https://t.me/Sellgameqt_bot?start=_tgr_u9i-SS1iY2I0" target="_blank">Open Bot</a>
  </div>

  <div class="card">
    <h3>Farmer Better</h3>
    <p>Farming-style earning game on Telegram.</p>
    <a href="https://t.me/farmer_better_bot?start=_tgr_JFEO8R1mYTQ0" target="_blank">Start Farming</a>
  </div>
</div>
</div>

<!-- VPN & TOOLS -->
<div class="section">
<h2>🔐 VPN & Utility Bots</h2>
<div class="grid">
  <div class="card">
    <h3>Blym VPN</h3>
    <p>Fast & secure VPN directly on Telegram.</p>
    <a href="https://t.me/BlymVpn_bot?start=_tgr_Ym32F-1jOWI0" target="_blank">Connect VPN</a>
  </div>

  <div class="card">
    <h3>Good Boy VPN</h3>
    <p>Simple VPN bot with instant access.</p>
    <a href="https://t.me/Vpn_for_good_boy_bot?start=_tgr_O09My4wzYjY0" target="_blank">Use VPN</a>
  </div>

  <div class="card">
    <h3>BP Proxy</h3>
    <p>Proxy services for Telegram access.</p>
    <a href="https://t.me/bpproxy_bot?start=_tgr_W4on3U4xMjFk" target="_blank">Open Proxy</a>
  </div>
</div>
</div>

<footer>
  © 2026 • Powered by Debeatzgh • Telegram Affiliate Hub
</footer>

</div>
</body>
</html>



