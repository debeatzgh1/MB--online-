<!DOCTYPE html>
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
