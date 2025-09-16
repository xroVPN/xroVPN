<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no">
    <title>فروشگاه VPN - ایکسرو</title>
    <style>
        :root {
            --primary-color: #000000;
            --primary-dark: #1a1a1a;
            --primary-light: #333333;
            --secondary-color: #000000;
            --accent-color: #000000;
            --success-color: #000000;
            --warning-color: #000000;
            --danger-color: #ff0000;
            --dark-blue: #000000;
            --dark-purple: #000000;
            --text-color: #000000;
            --text-light: #666666;
            --text-white: #ffffff;
            --bg-color: #ffffff;
            --card-bg: #f5f5f5;
            --card-hover: #e0e0e0;
            --border-color: rgba(0, 0, 0, 0.3);
            --shadow-color: rgba(0, 0, 0, 0.1);
            --glass-effect: linear-gradient(135deg, rgba(200, 200, 200, 0.15), rgba(230, 230, 230, 0.15));
            --glass-border: 1px solid rgba(200, 200, 200, 0.2);
            --glass-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            --transition: all .3s cubic-bezier(.4,0,.2,1);
            --glow-effect: 0 0 15px rgba(0, 0, 0, 0.4), 0 0 30px rgba(0, 0, 0, 0.2);
        }
        * { box-sizing: border-box; margin: 0; padding: 0; -webkit-tap-highlight-color: transparent; }
        body {
            font-family: 'Vazirmatn', 'Segoe UI', sans-serif;
            background: var(--bg-color);
            color: var(--text-color);
            height: 100vh;
            overflow: hidden;
            user-select: none;
            touch-action: manipulation;
            position: relative;
            background-image: linear-gradient(rgba(0, 0, 0, 0.1) 1px, transparent 1px);
            background-size: 100% 2em;
            background-position: top left;
            background-repeat: repeat-y;
        }
        .permanent-window { position: fixed; inset: 0; z-index: 10; background: transparent; display: flex; flex-direction: column; overflow: hidden; animation: fadeIn 1s ease-out; }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
        .top-bar { display: flex; justify-content: space-between; align-items: center; padding: 16px 20px; background: var(--card-bg); border-bottom: var(--glass-border); box-shadow: 0 4px 20px var(--shadow-color); z-index: 100; }
        .logo { font-size: 1.3rem; font-weight: 700; padding: 12px 18px; border-radius: 12px; cursor: pointer; background: var(--card-bg); display: flex; align-items: center; gap: 12px; transition: var(--transition); border: 1px solid var(--border-color); box-shadow: var(--glow-effect); color: var(--text-color); }
        .logo:hover { background: var(--card-hover); transform: translateY(-3px) scale(1.05); box-shadow: 0 8px 25px var(--shadow-color); }
        .logo i { font-size: 1.4rem; }
        .menu-btn { width: 44px; height: 44px; display: flex; justify-content: center; align-items: center; padding: 10px; border-radius: 12px; transition: var(--transition); background: var(--card-bg); border: 1px solid var(--border-color); cursor: pointer; box-shadow: var(--glow-effect); }
        .menu-btn:hover { background: var(--card-hover); transform: rotate(90deg) scale(1.1); box-shadow: 0 8px 20px var(--shadow-color); }
        .menu-btn i { font-size: 1.4rem; }
        .content { height: calc(100vh - 70px); display: flex; flex-direction: column; padding: 20px; overflow: hidden; }
        .welcome-container { flex: 1; display: flex; flex-direction: column; align-items: center; justify-content: center; margin-top: -20px; }
        .news-container { width: 100%; max-width: 90%; padding: 12px; border-radius: 16px; text-align: center; background: var(--card-bg); box-shadow: var(--glow-effect); border: 1px solid var(--border-color); }
        .news-content { color: var(--text-light); font-size: 0.95rem; text-align: right; }
        .info-box { background: var(--card-bg); border-radius: 14px; padding: 14px; margin-bottom: 12px; display: flex; align-items: center; gap: 12px; opacity: 0; border: 1px solid var(--primary-color); box-shadow: 0 4px 15px var(--shadow-color); }
        .info-box:nth-child(1) { animation: slideInLeft 0.6s ease-out 0.2s forwards; }
        .info-box:nth-child(2) { animation: slideInRight 0.6s ease-out 0.4s forwards; }
        .info-box:nth-child(3) { animation: slideInLeft 0.6s ease-out 0.6s forwards; }
        @keyframes slideInRight { from { opacity: 0; transform: translateX(50px); } to { opacity: 1; transform: translateX(0); } }
        @keyframes slideInLeft { from { opacity: 0; transform: translateX(-50px); } to { opacity: 1; transform: translateX(0); } }
        .info-icon { font-size: 1.4rem; color: var(--primary-color); min-width: 32px; display: flex; justify-content: center; }
        .info-text { font-weight: 600; min-width: 60px; color: var(--warning-color); }
        .info-value { font-weight: 600; min-width: 60px; flex: 1; text-align: left; direction: ltr; background: linear-gradient(45deg, var(--primary-color), var(--secondary-color), var(--accent-color)); background-size: 200% auto; -webkit-background-clip: text; background-clip: text; color: transparent; animation: gradientAnimation 3s ease infinite; }
        @keyframes gradientAnimation { 0% { background-position: 0% 50%; } 50% { background-position: 100% 50%; } 100% { background-position: 0% 50%; } }
        .floating-btn { position: fixed; bottom: 15px; left: 15px; width: 65px; height: 65px; background: linear-gradient(135deg, var(--primary-color), var(--primary-dark)); border-radius: 18px; display: flex; justify-content: center; align-items: center; font-size: 26px; color: var(--text-white); box-shadow: 0 10px 30px var(--shadow-color); cursor: pointer; border: none; transition: var(--transition); z-index: 100; }
        .floating-btn i { font-size: 1.6rem; }
        .floating-btn:hover { transform: translateY(-5px) scale(1.1); box-shadow: 0 15px 40px var(--shadow-color); background: linear-gradient(135deg, var(--primary-dark), var(--primary-color)); }
        .modal-window { position: fixed; background: var(--card-bg); z-index: 1000; transition: var(--transition); box-shadow: 0 12px 40px var(--shadow-color); border: var(--glass-border); border-radius: 18px; display: flex; flex-direction: column; max-height: 80vh; }
        .main-menu, .settings-panel, .about-panel, .report-problem-menu, .source-panel { top: -100%; right: 0; width: 100%; max-height: 65%; border-radius: 0 0 18px 18px; }
        .main-menu.open, .settings-panel.open, .about-panel.open, .report-problem-menu.open, .source-panel.open { top: 0; }
        .public-shop-menu { bottom: -100%; left: 0; width: 100%; max-height: 80%; border-radius: 18px 18px 0 0; }
        .public-shop-menu.open { bottom: 0; }
        .modal-overlay { position: fixed; inset: 0; background: rgba(0, 0, 0, 0.7); z-index: 999; display: none; transition: opacity .3s ease; }
        .modal-overlay.show { display: block; opacity: 1; }
        .modal-overlay.hidden { opacity: 0; }
        .modal-header { display: flex; justify-content: space-between; align-items: center; padding: 18px 20px; border-bottom: var(--glass-border); background: var(--card-bg); box-shadow: 0 4px 15px var(--shadow-color); }
        .modal-title-container { display: flex; align-items: center; gap: 10px; }
        .modal-title { font-weight: 700; font-size: 1.3rem; color: var(--text-color); }
        .modal-title-img { font-size: 1.4rem; cursor: pointer; transition: transform .5s ease; }
        .modal-title-img:hover, .modal-title-img.active { transform: rotate(360deg); }
        .home-btn { cursor: pointer; width: 40px; height: 40px; display: flex; align-items: center; justify-content: center; border-radius: 50%; transition: var(--transition); background: var(--card-bg); }
        .home-btn:hover { background: var(--card-hover); transform: scale(1.1); box-shadow: 0 6px 20px var(--shadow-color); }
        .home-btn i { font-size: 1.4rem; transition: transform .3s ease; }
        .home-btn:hover i { transform: scale(1.2); }
        .modal-content { flex: 1; overflow-y: auto; padding: 12px; background: var(--card-bg); }
        .menu-item { padding: 18px; margin-bottom: 14px; background: var(--card-bg); border-radius: 16px; cursor: pointer; transition: var(--transition); border: 1px solid var(--border-color); box-shadow: 0 6px 20px var(--shadow-color); }
        .menu-item:hover { transform: translateY(-4px) scale(1.02); background: var(--card-hover); border-color: var(--primary-light); box-shadow: 0 12px 30px var(--shadow-color); }
        .menu-item-title { font-weight: 700; font-size: 1.2rem; display: flex; align-items: center; gap: 12px; color: var(--text-color); }
        .menu-item-title i { font-size: 1.4rem; }
        .menu-item-desc { font-size: 0.95rem; color: var(--text-light); line-height: 1.6; }
        .notification { position: fixed; bottom: 20px; right: 20px; background: var(--card-bg); border-radius: 14px; padding: 14px; box-shadow: 0 8px 25px var(--shadow-color); z-index: 1100; transform: translateY(100px); opacity: 0; transition: var(--transition); display: flex; align-items: center; gap: 12px; border: 1px solid var(--border-color); max-width: 80%; }
        .notification.show { transform: translateY(0); opacity: 1; }
        .notification-icon { font-size: 1.4rem; width: 36px; height: 36px; display: flex; align-items: center; justify-content: center; border-radius: 50%; box-shadow: 0 0 10px var(--shadow-color); }
        .notification-success { background: var(--card-bg); color: var(--success-color); border: 1px solid rgba(0, 0, 0, 0.4); }
        .notification-info { background: var(--card-bg); color: var(--primary-color); border: 1px solid var(--border-color); }
        .notification-error { background: var(--card-bg); color: var(--danger-color); border: 1px solid rgba(255, 0, 0, 0.4); }
        .notification-message { font-size: 0.9rem; font-weight: 500; flex: 1; color: var(--text-color); }
        .configs-container { display: flex; gap: 12px; overflow-x: auto; padding: 12px; direction: rtl; scrollbar-width: none; position: relative; }
        .configs-container::-webkit-scrollbar { display: none; }
        .config-box { position: relative; background: var(--card-bg); padding: 12px; width: 153px; height: 176px; transition: var(--transition); cursor: move; display: flex; flex-direction: column; align-items: center; justify-content: space-between; text-align: center; flex-shrink: 0; border-radius: 14px; border: 2px solid transparent; opacity: 0; box-shadow: 0 6px 20px var(--shadow-color); }
        .config-box.dragging { opacity: 0.5; transform: scale(0.95); z-index: 1000; }
        .config-box:hover { transform: translateY(-5px) scale(1.05); box-shadow: 0 12px 30px var(--shadow-color); }
        .config-box[data-protocol="hysteria2"] { border-color: var(--success-color); }
        .config-box[data-protocol="vless"] { border-color: var(--primary-color); }
        .config-box[data-protocol="trojan"] { border-color: var(--secondary-color); }
        .config-box[data-protocol="ss"] { border-color: var(--warning-color); }
        .config-box[data-protocol="vmess"] { border-color: var(--accent-color); }
        .config-box[data-protocol="wireguard"] { border-color: var(--dark-purple); }
        .config-box::after { content: attr(data-protocol-fa); position: absolute; top: -12px; left: 50%; transform: translateX(-50%); background: var(--card-bg); color: var(--text-light); font-size: 0.85rem; padding: 5px 10px; border-radius: 10px; opacity: 0; transition: var(--transition); pointer-events: none; box-shadow: 0 4px 15px var(--shadow-color); }
        .config-box:hover::after { opacity: 1; }
        .config-logo-container { position: relative; width: 65px; height: 65px; display: flex; justify-content: center; align-items: center; background: transparent; }
        .config-logo { font-size: 2.2rem; margin-bottom: 10px; transition: transform .3s ease; background: transparent; }
        .config-box:hover .config-logo { transform: scale(1.15) rotate(5deg); }
        .ping-result { font-size: 0.9rem; display: flex; align-items: center; gap: 8px; width: 100%; justify-content: center; font-weight: 600; direction: rtl; }
        .ping-result.fast { color: var(--success-color); }
        .ping-result.medium { color: var(--warning-color); }
        .ping-result.slow { color: var(--danger-color); }
        .error { background: var(--card-bg); color: var(--danger-color); border: 1px solid rgba(255, 0, 0, 0.4); border-radius: 14px; padding: 16px; margin: 18px 0; font-size: 0.95rem; text-align: center; box-shadow: 0 4px 15px var(--shadow-color); }
        .loading-container { display: flex; align-items: center; justify-content: center; margin: 20px 0; direction: rtl; }
        .loading-dots { display: flex; justify-content: center; align-items: center; gap: 10px; }
        .loading-dot { width: 10px; height: 10px; background: linear-gradient(45deg, var(--primary-color), var(--secondary-color)); border-radius: 50%; animation: bounce 1.4s ease-in-out infinite; box-shadow: 0 0 10px var(--shadow-color); }
        .loading-dot:nth-child(2) { animation-delay: 0.2s; }
        .loading-dot:nth-child(3) { animation-delay: 0.4s; }
        @keyframes bounce { 0%, 100% { transform: translateY(0); opacity: 0.6; } 50% { transform: translateY(-12px); opacity: 1; } }
        .copy-btn { padding: 10px; border-radius: 12px; background: linear-gradient(135deg, var(--primary-color), var(--primary-dark)); color: var(--text-white); font-size: 0.9rem; font-weight: 600; cursor: pointer; border: none; transition: var(--transition); display: flex; align-items: center; gap: 8px; justify-content: center; width: 100%; box-shadow: 0 6px 20px var(--shadow-color); }
        .copy-btn i { font-size: 1.2rem; color: var(--text-white); }
        .copy-btn:hover { background: linear-gradient(135deg, var(--primary-dark), var(--primary-color)); transform: translateY(-3px) scale(1.05); box-shadow: 0 10px 25px var(--shadow-color); }
        .share-btn, .delete-btn { position: absolute; top: 8px; padding: 8px; border-radius: 8px; background: linear-gradient(135deg, var(--secondary-color), var(--primary-dark)); color: var(--text-white); font-size: 0.85rem; font-weight: 600; cursor: pointer; border: none; transition: var(--transition); display: flex; align-items: center; gap: 6px; justify-content: center; box-shadow: 0 4px 15px var(--shadow-color); }
        .share-btn { left: 8px; }
        .delete-btn { right: 8px; }
        .share-btn i, .delete-btn i { font-size: 1.1rem; color: var(--text-white); }
        .share-btn:hover, .delete-btn:hover { background: linear-gradient(135deg, var(--primary-dark), var(--secondary-color)); transform: translateY(-2px) scale(1.1); box-shadow: 0 8px 20px var(--shadow-color); }
        .filter-container { display: flex; gap: 12px; margin-bottom: 18px; overflow-x: auto; padding: 12px; scrollbar-width: none; direction: rtl; }
        .filter-container::-webkit-scrollbar { display: none; }
        .filter-btn { padding: 8px 14px; border-radius: 12px; background: var(--card-bg); color: var(--text-light); font-size: 0.85rem; font-weight: 500; cursor: pointer; border: 1px solid var(--border-color); transition: var(--transition); box-shadow: 0 4px 15px var(--shadow-color); }
        .filter-btn.active { background: linear-gradient(135deg, var(--primary-color), var(--primary-dark)); color: var(--text-white); box-shadow: 0 6px 20px var(--shadow-color); }
        .filter-btn:hover { transform: translateY(-3px) scale(1.05); box-shadow: 0 8px 25px var(--shadow-color); }
        .report-problem-content, .source-content { display: flex; flex-direction: column; gap: 18px; padding: 20px; }
        .report-problem-content textarea, .source-content input { width: 100%; min-height: 100px; padding: 12px; border-radius: 10px; border: 1px solid var(--border-color); background: var(--card-bg); color: var(--text-color); font-family: 'Vazirmatn', sans-serif; font-size: 0.9rem; resize: none; box-shadow: 0 0 10px var(--shadow-color); }
        .source-content input { min-height: 40px; }
        .report-problem-content textarea:focus, .source-content input:focus { outline: none; border-color: var(--primary-light); box-shadow: 0 0 12px var(--shadow-color); }
        .report-problem-content button, .source-content button { background: linear-gradient(135deg, var(--primary-color), var(--primary-dark)); color: var(--text-white); padding: 14px; border-radius: 12px; font-weight: 700; cursor: pointer; border: none; transition: var(--transition); box-shadow: 0 6px 20px var(--shadow-color); }
        .report-problem-content button i, .source-content button i { font-size: 1.2rem; margin-left: 10px; color: var(--text-white); }
        .report-problem-content button:hover, .source-content button:hover { transform: translateY(-3px) scale(1.05); box-shadow: 0 10px 25px var(--shadow-color); }
        .report-problem-content button:disabled, .source-content button:disabled { opacity: 0.6; cursor: not-allowed; transform: none; box-shadow: none; }
        .report-problem-content button .loading-spinner-small, .source-content button .loading-spinner-small { display: inline-block; width: 18px; height: 18px; border: 2px solid rgba(255, 255, 255, 0.3); border-radius: 50%; border-top-color: white; animation: spin 1s ease-in-out infinite; margin-left: 10px; }
        @keyframes spin { to { transform: rotate(360deg); } }
        .music-controls { display: flex; justify-content: center; gap: 18px; margin-top: 20px; }
        .music-btn { background: var(--card-bg); color: var(--text-color); padding: 12px; border-radius: 12px; font-weight: 600; cursor: pointer; border: 1px solid var(--border-color); transition: var(--transition); box-shadow: 0 4px 15px var(--shadow-color); }
        .music-btn i { font-size: 1.2rem; margin-right: 8px; }
        .music-btn:hover { transform: translateY(-3px) scale(1.05); background: var(--card-hover); box-shadow: 0 8px 25px var(--shadow-color); }
        .music-logo { font-size: 3rem; margin: 20px auto; display: block; animation: spin 18s linear infinite; }
    </style>
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@400;500;700&display=swap">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
</head>
<body class="theme-default">
    <audio id="bgMusic" loop>
        <source src="https://uploadkon.ir/uploads/833c07_25shervin-nahal-online-audio-converter-com-.mp3" type="audio/mpeg">
    </audio>
    <div class="permanent-window" id="permanentWindow">
        <div class="top-bar">
            <div class="logo" id="reportProblemBtn"><i class="fas fa-bug"></i><span>گزارش مشکل</span></div>
            <div class="menu-btn" id="mainMenuBtn"><i class="fas fa-cog"></i></div>
        </div>
        <div class="content">
            <div class="welcome-container">
                <div class="news-container">
                    <div class="news-content">
                        <div class="info-box">
                            <div class="info-icon"><i class="fas fa-laptop"></i></div>
                            <div class="info-text">سیستم:</div>
                            <div class="info-value" id="device">--</div>
                        </div>
                        <div class="info-box">
                            <div class="info-icon"><i class="fas fa-map-marker-alt"></i></div>
                            <div class="info-text">آیپی:</div>
                            <div class="info-value" id="ip">--</div>
                        </div>
                        <div class="info-box">
                            <div class="info-icon"><i class="fas fa-tachometer-alt"></i></div>
                            <div class="info-text">پینگ:</div>
                            <div class="info-value" id="ping">-- م‌ث</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <button class="floating-btn" id="configSelectBtn"><i class="fas fa-gift"></i></button>
    <div class="modal-overlay" id="mainMenuOverlay"></div>
    <div class="modal-window main-menu" id="mainMenu">
        <div class="modal-header">
            <div class="modal-title">منوی اصلی</div>
            <div class="home-btn" id="closeMainMenu"><i class="fas fa-times"></i></div>
        </div>
        <div class="modal-content">
            <div class="menu-item" id="settingsItem">
                <div class="menu-item-title"><i class="fas fa-headphones"></i><span>موزیک</span></div>
                <div class="menu-item-desc">کنترل موسیقی پس‌زمینه</div>
            </div>
            <div class="menu-item" id="sourceItem">
                <div class="menu-item-title"><i class="fas fa-cloud-download-alt"></i><span>منبع نما</span></div>
                <div class="menu-item-desc">تغییر منبع استخراج کانفیگ‌ها</div>
            </div>
            <div class="menu-item" id="aboutItem">
                <div class="menu-item-title"><i class="fas fa-users"></i><span>درباره ما</span></div>
                <div class="menu-item-desc">اطلاعات بیشتر درباره ایکسرو</div>
            </div>
        </div>
    </div>
    <div class="modal-overlay" id="configSelectOverlay"></div>
    <div class="modal-window public-shop-menu" id="publicShopMenu">
        <div class="modal-header">
            <div class="modal-title-container">
                <i class="fas fa-sync-alt modal-title-img" id="modalTitleImg"></i>
                <span class="modal-title" id="modalTitle">بروزرسانی کانفیگ‌ها</span>
                <span class="modal-progress-text" id="modalProgressText" style="display:none">۰ از ... انجام شده</span>
            </div>
            <div class="home-btn" id="closePublicShopMenu"><i class="fas fa-times"></i></div>
        </div>
        <div class="modal-content">
            <div class="filter-container" id="filterContainer">
                <button class="filter-btn active" data-protocol="all">همه</button>
                <button class="filter-btn" data-protocol="hysteria2">هیستریا۲</button>
                <button class="filter-btn" data-protocol="vless">وی‌لس</button>
                <button class="filter-btn" data-protocol="trojan">تروجان</button>
                <button class="filter-btn" data-protocol="ss">شدوساکس</button>
                <button class="filter-btn" data-protocol="vmess">وی‌مس</button>
                <button class="filter-btn" data-protocol="wireguard">وایرگارد</button>
            </div>
            <div class="tab-content active" id="mahsa-tab">
                <div class="configs-container" id="configsContainer">
                    <div class="loading-container">
                        <div class="loading-dots">
                            <div class="loading-dot"></div>
                            <div class="loading-dot"></div>
                            <div class="loading-dot"></div>
                        </div>
                    </div>
                    <div class="error" style="display:none">متاسفانه موجود نیست</div>
                </div>
            </div>
        </div>
    </div>
    <div class="modal-window settings-panel" id="settingsPanel">
        <div class="modal-header">
            <div class="modal-title">موزیک</div>
            <div class="home-btn" id="closeSettingsPanel"><i class="fas fa-times"></i></div>
        </div>
        <div class="modal-content">
            <i class="fas fa-headphones music-logo"></i>
            <div class="music-controls">
                <button class="music-btn" id="prevTrack"><i class="fas fa-backward"></i> قبلی</button>
                <button class="music-btn" id="playPause"><i class="fas fa-play-circle"></i> پخش</button>
                <button class="music-btn" id="nextTrack"><i class="fas fa-forward"></i> بعدی</button>
            </div>
        </div>
    </div>
    <div class="modal-window about-panel" id="aboutPanel">
        <div class="modal-header">
            <div class="modal-title">درباره ما</div>
            <div class="home-btn" id="closeAboutPanel"><i class="fas fa-times"></i></div>
        </div>
        <div class="modal-content">
            <p style="font-size:0.95rem;color:var(--text-light);text-align:center;padding:20px;">ایکسرو با بیش از ۵ سال فعالیت در زمینه ارائه خدمات فیلترشکن و VPN، با تکیه بر تجربه و تخصص، بهترین راهکارها را برای دسترسی امن و سریع به اینترنت ارائه می‌دهد. ما متعهد به حفظ حریم خصوصی و امنیت کاربران هستیم.</p>
            <a href="https://t.me/xrovpn" target="_blank" class="btn btn-primary btn-large"><i class="fab fa-telegram-plane"></i> کانال رسمی ایکسرو</a>
        </div>
    </div>
    <div class="modal-window report-problem-menu" id="reportProblemMenu">
        <div class="modal-header">
            <div class="modal-title">گزارش مشکل</div>
            <div class="home-btn" id="closeReportProblemMenu"><i class="fas fa-times"></i></div>
        </div>
        <div class="modal-content report-problem-content">
            <textarea id="reportProblemText" placeholder="مشکل خود را اینجا بنویسید..."></textarea>
            <button id="submitReportProblem"><i class="fas fa-comment-dots"></i> ارسال گزارش</button>
        </div>
    </div>
    <div class="modal-window source-panel" id="sourcePanel">
        <div class="modal-header">
            <div class="modal-title">منبع نما</div>
            <div class="home-btn" id="closeSourcePanel"><i class="fas fa-times"></i></div>
        </div>
        <div class="modal-content source-content">
            <input type="text" id="sourceUrlInput" placeholder="لینک منبع کانفیگ‌ها را وارد کنید...">
            <button id="submitSourceUrl"><i class="fas fa-save"></i> ثبت</button>
        </div>
    </div>
    <div class="modal-overlay" id="sourceOverlay"></div>
    <div class="modal-overlay" id="reportProblemOverlay"></div>
    <div class="notification" id="notification">
        <div class="notification-icon" id="notificationIcon"><i class="fas fa-check-circle"></i></div>
        <div class="notification-message" id="notificationMessage">عملیات با موفقیت انجام شد</div>
    </div>
    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const e = {
                permanentWindow: document.getElementById('permanentWindow'),
                mainMenuBtn: document.getElementById('mainMenuBtn'),
                mainMenu: document.getElementById('mainMenu'),
                mainMenuOverlay: document.getElementById('mainMenuOverlay'),
                configSelectBtn: document.getElementById('configSelectBtn'),
                publicShopMenu: document.getElementById('publicShopMenu'),
                configSelectOverlay: document.getElementById('configSelectOverlay'),
                settingsItem: document.getElementById('settingsItem'),
                settingsPanel: document.getElementById('settingsPanel'),
                aboutItem: document.getElementById('aboutItem'),
                aboutPanel: document.getElementById('aboutPanel'),
                sourceItem: document.getElementById('sourceItem'),
                sourcePanel: document.getElementById('sourcePanel'),
                sourceOverlay: document.getElementById('sourceOverlay'),
                sourceUrlInput: document.getElementById('sourceUrlInput'),
                submitSourceUrl: document.getElementById('submitSourceUrl'),
                closeSourcePanel: document.getElementById('closeSourcePanel'),
                notification: document.getElementById('notification'),
                notificationIcon: document.getElementById('notificationIcon'),
                notificationMessage: document.getElementById('notificationMessage'),
                bgMusic: document.getElementById('bgMusic'),
                configsContainer: document.getElementById('configsContainer'),
                filterContainer: document.getElementById('filterContainer'),
                device: document.getElementById('device'),
                ip: document.getElementById('ip'),
                ping: document.getElementById('ping'),
                reportProblemBtn: document.getElementById('reportProblemBtn'),
                reportProblemMenu: document.getElementById('reportProblemMenu'),
                reportProblemOverlay: document.getElementById('reportProblemOverlay'),
                reportProblemText: document.getElementById('reportProblemText'),
                submitReportProblem: document.getElementById('submitReportProblem'),
                closeReportProblemMenu: document.getElementById('closeReportProblemMenu'),
                playPause: document.getElementById('playPause'),
                prevTrack: document.getElementById('prevTrack'),
                nextTrack: document.getElementById('nextTrack'),
                closeAboutPanel: document.getElementById('closeAboutPanel'),
                closePublicShopMenu: document.getElementById('closePublicShopMenu'),
                closeSettingsPanel: document.getElementById('closeSettingsPanel'),
                closeMainMenu: document.getElementById('closeMainMenu'),
                modalTitleImg: document.getElementById('modalTitleImg'),
                modalTitle: document.getElementById('modalTitle'),
                modalProgressText: document.getElementById('modalProgressText')
            };

            Object.keys(e).forEach(key => {
                if (!e[key]) console.error(`Element ${key} not found in DOM`);
            });

            const UI_STATE_KEY = 'xro_vpn_ui_state';
            const CACHE_KEY = 'xro_vpn_configs';
            const SOURCE_URL_KEY = 'xro_vpn_source_url';
            const CACHE_EXPIRY = 5 * 60 * 1000;
            const DEFAULT_SOURCE_URL = 'https://gist.githubusercontent.com/xroVPN/12a0c02781cfed451da84e9b802c0912/raw';
            let currentProgress = 0;

            const toggleModal = (modalId, state, overlayId) => {
                if (!e[modalId] || !e[overlayId]) {
                    console.error(`Modal ${modalId} or Overlay ${overlayId} not found`);
                    return;
                }
                closeAllModals();
                const modal = e[modalId];
                const overlay = e[overlayId];
                modal.classList.toggle('open', state);
                overlay.classList.toggle('show', state);
                overlay.classList.toggle('hidden', !state);
                saveUIState();
                console.log(`Modal ${modalId} ${state ? 'opened' : 'closed'}`);
            };

            const closeAllModals = () => {
                ['mainMenu', 'publicShopMenu', 'settingsPanel', 'aboutPanel', 'reportProblemMenu', 'sourcePanel'].forEach(id => {
                    if (e[id]) e[id].classList.remove('open');
                });
                ['mainMenuOverlay', 'configSelectOverlay', 'reportProblemOverlay', 'sourceOverlay'].forEach(id => {
                    if (e[id]) {
                        e[id].classList.remove('show');
                        e[id].classList.add('hidden');
                    }
                });
                saveUIState();
                console.log('All modals closed');
            };

            const showNotification = (msg, type = 'success') => {
                if (!e.notification || !e.notificationIcon || !e.notificationMessage) return;
                e.notification.className = 'notification';
                e.notificationIcon.className = 'notification-icon';
                const icons = {
                    success: '<i class="fas fa-check-circle"></i>',
                    error: '<i class="fas fa-times-circle"></i>',
                    info: '<i class="fas fa-info-circle"></i>'
                };
                e.notification.classList.add(`notification-${type}`);
                e.notificationIcon.innerHTML = icons[type];
                e.notificationMessage.textContent = msg;
                e.notification.classList.add('show');
                setTimeout(() => e.notification.classList.remove('show'), 3000);
            };

            const isValidUrl = url => {
                try {
                    new URL(url);
                    return true;
                } catch {
                    return false;
                }
            };

            const submitSourceUrl = () => {
                if (!e.sourceUrlInput || !e.submitSourceUrl) return;
                const url = e.sourceUrlInput.value.trim();
                if (!url) {
                    showNotification('لطفاً لینک منبع را وارد کنید', 'error');
                    return;
                }
                if (!isValidUrl(url)) {
                    showNotification('لینک منبع نامعتبر است', 'error');
                    return;
                }
                localStorage.setItem(SOURCE_URL_KEY, url);
                showNotification('لینک منبع با موفقیت ثبت شد', 'success');
                e.sourceUrlInput.value = '';
                toggleModal('sourcePanel', false, 'sourceOverlay');
                extractConfigs(true);
            };

            const submitReportProblem = async () => {
                if (!e.reportProblemText || !e.submitReportProblem) return;
                const msg = e.reportProblemText.value.trim();
                if (!msg) {
                    showNotification('لطفاً متن گزارش را وارد کنید', 'error');
                    return;
                }
                const originalText = e.submitReportProblem.innerHTML;
                e.submitReportProblem.disabled = true;
                e.submitReportProblem.innerHTML = '<i class="fas fa-spinner loading-spinner-small"></i> در حال ارسال...';
                try {
                    const token = 'YOUR_TELEGRAM_BOT_TOKEN';
                    const adminId = 'YOUR_ADMIN_ID';
                    const res = await fetch(`https://api.telegram.org/bot${token}/sendMessage`, {
                        method: 'POST',
                        headers: { 'Content-Type': 'application/json' },
                        body: JSON.stringify({ chat_id: adminId, text: `گزارش مشکل جدید:\n${msg}` })
                    });
                    if (!res.ok) throw new Error('خطا در ارسال گزارش');
                    showNotification('گزارش با موفقیت ارسال شد', 'success');
                    e.reportProblemText.value = '';
                    toggleModal('reportProblemMenu', false, 'reportProblemOverlay');
                } catch (err) {
                    showNotification(`خطا: ${err.message}`, 'error');
                } finally {
                    e.submitReportProblem.disabled = false;
                    e.submitReportProblem.innerHTML = originalText;
                }
            };

            const toPersianDigits = str => str.replace(/[0-9]/g, d => '۰۱۲۳۴۵۶۷۸۹'[parseInt(d)]);

            const updateIP = async () => {
                if (!e.ip) return;
                try {
                    const res = await fetch('https://api.ipify.org?format=json', { cache: 'no-store' });
                    if (!res.ok) throw new Error('خطا در دریافت آی‌پی');
                    const data = await res.json();
                    e.ip.textContent = toPersianDigits(data.ip);
                } catch (err) {
                    console.error('IP fetch error:', err);
                    e.ip.textContent = 'نامشخص';
                }
            };

            const updatePing = async () => {
                if (!e.ping) return;
                try {
                    const start = performance.now();
                    await fetch('https://cloudflare.com/cdn-cgi/trace', { method: 'HEAD', cache: 'no-store' });
                    const pingValue = Math.round(performance.now() - start);
                    e.ping.textContent = `${toPersianDigits(pingValue.toString())} م‌ث`;
                } catch (err) {
                    console.error('Ping fetch error:', err);
                    e.ping.textContent = 'نامشخص';
                }
            };

            const refreshIP = () => {
                updateIP();
                setTimeout(refreshIP, 10000); // Increased interval to reduce load
            };

            const refreshPing = () => {
                updatePing();
                setTimeout(refreshPing, 5000); // Increased interval to reduce load
            };

            const parseConfig = config => {
                try {
                    const [, protocol, rest] = config.match(/^(hysteria2|vless|trojan|ss|vmess|wireguard):\/\/(.+)/i) || [];
                    if (!protocol) return null;
                    if (protocol.toLowerCase() === 'vmess') {
                        const data = JSON.parse(atob(rest.split('#')[0]));
                        return data.add ? { host: data.add, protocol } : null;
                    }
                    if (protocol.toLowerCase() === 'wireguard') {
                        const data = JSON.parse(rest.split('#')[0]);
                        return data.Address ? { host: data.Address, protocol } : null;
                    }
                    const host = rest.split('#')[0].split('?')[0].match(/@([^:@]+)/)?.[1];
                    return /^[a-zA-Z0-9.-]+$/.test(host) ? { host, protocol } : null;
                } catch {
                    return null;
                }
            };

            const formatConfig = config => {
                try {
                    const [, protocol, rest] = config.match(/^([^:]+):\/\/(.+)/i) || [];
                    if (!protocol) return config;
                    if (protocol.toLowerCase() === 'vmess') {
                        const [base, ...comment] = rest.split('#');
                        const data = JSON.parse(atob(base));
                        data.ps = 'insta ☜☞ aminxro';
                        return `vmess://${btoa(JSON.stringify(data))}${comment.length ? '#' + comment.join('#') : ''}`;
                    }
                    if (protocol.toLowerCase() === 'wireguard') {
                        const [base, ...comment] = rest.split('#');
                        const data = JSON.parse(base);
                        data.ps = 'insta ☜☞ aminxro';
                        return `wireguard://${JSON.stringify(data)}${comment.length ? '#' + comment.join('#') : ''}`;
                    }
                    if (['vless', 'trojan', 'ss'].includes(protocol.toLowerCase())) {
                        const [base, ...comment] = rest.split('#');
                        return comment.length ? `${protocol}://${base}#insta ☜☞ aminxro` : config;
                    }
                    return config;
                } catch {
                    return config;
                }
            };

            const testPing = host => new Promise(resolve => {
                const start = performance.now();
                const controller = new AbortController();
                const timeout = setTimeout(() => controller.abort(), 5000);
                fetch(`https://${host}/generate_204`, { method: 'HEAD', mode: 'no-cors', signal: controller.signal, cache: 'no-store' })
                    .then(() => {
                        clearTimeout(timeout);
                        resolve({ success: true, ping: Math.round(performance.now() - start) });
                    })
                    .catch(err => {
                        clearTimeout(timeout);
                        resolve({ success: false, error: err.name === 'AbortError' ? 'تایم‌اوت' : 'عدم اتصال' });
                    });
            });

            const getLocation = async host => {
                try {
                    const res = await fetch(`http://ip-api.com/json/${host}?fields=countryCode`, { cache: 'no-store' });
                    if (!res.ok) return null;
                    const data = await res.json();
                    return data.countryCode ? { countryCode: data.countryCode.toUpperCase() } : null;
                } catch {
                    return null;
                }
            };

            const flagIcons = {
                'CA': '<i class="fas fa-server"></i>',
                'FI': '<i class="fas fa-server"></i>',
                'DE': '<i class="fas fa-server"></i>',
                'IE': '<i class="fas fa-server"></i>',
                'US': '<i class="fas fa-server"></i>',
                'TR': '<i class="fas fa-server"></i>',
                'AU': '<i class="fas fa-server"></i>',
                'ES': '<i class="fas fa-server"></i>'
            };

            const getCountryIcon = countryCode => flagIcons[countryCode] || '<i class="fas fa-server"></i>';

            const getCachedConfigs = () => {
                try {
                    const cached = localStorage.getItem(CACHE_KEY);
                    if (!cached) return null;
                    const { data, timestamp } = JSON.parse(cached);
                    if (Date.now() - timestamp > CACHE_EXPIRY) {
                        localStorage.removeItem(CACHE_KEY);
                        return null;
                    }
                    return data;
                } catch (err) {
                    console.error('Cache parse error:', err);
                    localStorage.removeItem(CACHE_KEY);
                    return null;
                }
            };

            const setCachedConfigs = data => {
                try {
                    localStorage.setItem(CACHE_KEY, JSON.stringify({ data, timestamp: Date.now() }));
                } catch (err) {
                    console.error('Cache save error:', err);
                }
            };

            const deleteConfig = config => {
                const cachedConfigs = getCachedConfigs();
                if (cachedConfigs) {
                    const updatedConfigs = cachedConfigs.filter(c => c.config !== config);
                    setCachedConfigs(updatedConfigs);
                    renderConfigs(updatedConfigs);
                    showNotification('کانفیگ با موفقیت حذف شد', 'success');
                }
            };

            const saveUIState = () => {
                try {
                    const state = {
                        activeFilter: e.filterContainer?.querySelector('.filter-btn.active')?.dataset.protocol || 'all',
                        isPublicShopMenuOpen: e.publicShopMenu?.classList.contains('open'),
                        isMainMenuOpen: e.mainMenu?.classList.contains('open'),
                        isSettingsPanelOpen: e.settingsPanel?.classList.contains('open'),
                        isAboutPanelOpen: e.aboutPanel?.classList.contains('open'),
                        isReportProblemMenuOpen: e.reportProblemMenu?.classList.contains('open'),
                        isSourcePanelOpen: e.sourcePanel?.classList.contains('open')
                    };
                    sessionStorage.setItem(UI_STATE_KEY, JSON.stringify(state));
                } catch (err) {
                    console.error('UI state save error:', err);
                }
            };

            const loadUIState = () => {
                try {
                    const state = sessionStorage.getItem(UI_STATE_KEY);
                    if (!state) return;
                    const { activeFilter, isPublicShopMenuOpen, isMainMenuOpen, isSettingsPanelOpen, isAboutPanelOpen, isReportProblemMenuOpen, isSourcePanelOpen } = JSON.parse(state);
                    if (e.filterContainer) e.filterContainer.querySelectorAll('.filter-btn').forEach(btn => btn.classList.toggle('active', btn.dataset.protocol === activeFilter));
                    if (isPublicShopMenuOpen && e.publicShopMenu && e.configSelectOverlay) toggleModal('publicShopMenu', true, 'configSelectOverlay');
                    if (isMainMenuOpen && e.mainMenu && e.mainMenuOverlay) toggleModal('mainMenu', true, 'mainMenuOverlay');
                    if (isSettingsPanelOpen && e.settingsPanel && e.mainMenuOverlay) toggleModal('settingsPanel', true, 'mainMenuOverlay');
                    if (isAboutPanelOpen && e.aboutPanel && e.mainMenuOverlay) toggleModal('aboutPanel', true, 'mainMenuOverlay');
                    if (isReportProblemMenuOpen && e.reportProblemMenu && e.reportProblemOverlay) toggleModal('reportProblemMenu', true, 'reportProblemOverlay');
                    if (isSourcePanelOpen && e.sourcePanel && e.sourceOverlay) toggleModal('sourcePanel', true, 'sourceOverlay');
                } catch (err) {
                    console.error('UI state load error:', err);
                }
            };

            const updateProgress = (current, total) => {
                if (!e.modalProgressText || !e.modalTitle) return;
                currentProgress = current;
                e.modalTitle.style.display = 'none';
                e.modalProgressText.style.display = 'inline';
                e.modalProgressText.textContent = `${toPersianDigits(current.toString())} از ${toPersianDigits(total.toString())} انجام شده`;
                if (current >= total) {
                    setTimeout(() => {
                        e.modalProgressText.style.display = 'none';
                        e.modalTitle.style.display = 'inline';
                        currentProgress = 0;
                    }, 1000);
                }
            };

            const shareConfig = async config => {
                if (navigator.share) {
                    try {
                        await navigator.share({ title: 'کانفیگ VPN ایکسرو', text: 'کانفیگ VPN از ایکسرو', url: config });
                        showNotification('کانفیگ با موفقیت به اشتراک گذاشته شد', 'success');
                    } catch (err) {
                        showNotification('خطا در اشتراک‌گذاری کانفیگ', 'error');
                    }
                } else {
                    showNotification('اشتراک‌گذاری در این مرورگر پشتیبانی نمی‌شود', 'error');
                }
            };

            const updateConfigPing = async (config, pingElement) => {
                try {
                    if (!config || !pingElement) return;
                    const parsed = parseConfig(config.config);
                    if (!parsed) return;
                    const pingResult = await testPing(parsed.host);
                    if (pingResult.success) {
                        pingElement.textContent = `${toPersianDigits(pingResult.ping.toString())} م‌ث`;
                        pingElement.className = 'ping-result';
                        pingElement.classList.add(pingResult.ping < 300 ? 'fast' : pingResult.ping < 600 ? 'medium' : 'slow');
                    } else {
                        pingElement.textContent = 'نامشخص';
                        pingElement.className = 'ping-result slow';
                    }
                } catch (err) {
                    console.error('Config ping error:', err);
                    if (pingElement) {
                        pingElement.textContent = 'نامشخص';
                        pingElement.className = 'ping-result slow';
                    }
                }
            };

            const refreshConfigPings = () => {
                if (!e.configsContainer) return;
                const configBoxes = e.configsContainer.querySelectorAll('.config-box');
                if (configBoxes.length === 0) return;
                configBoxes.forEach(box => {
                    const config = box.dataset.config;
                    const pingElement = box.querySelector('.ping-result');
                    if (config && pingElement) {
                        try {
                            updateConfigPing(JSON.parse(config), pingElement);
                        } catch (err) {
                            console.error('Config parse error in refreshConfigPings:', err);
                        }
                    }
                });
                setTimeout(refreshConfigPings, 10000); // Increased interval to reduce load
            };

            const extractConfigs = async (forceRefresh = false) => {
                if (!e.configsContainer) return;
                currentProgress = 0;
                e.configsContainer.innerHTML = '<div class="loading-container"><div class="loading-dots"><div class="loading-dot"></div><div class="loading-dot"></div><div class="loading-dot"></div></div></div>';
                const cachedConfigs = !forceRefresh && getCachedConfigs();
                if (cachedConfigs) {
                    updateProgress(cachedConfigs.length, cachedConfigs.length);
                    renderConfigs(cachedConfigs);
                    return;
                }
                try {
                    const url = localStorage.getItem(SOURCE_URL_KEY) || DEFAULT_SOURCE_URL;
                    const res = await fetch(url, { mode: 'cors', cache: 'no-store' });
                    if (!res.ok) {
                        e.configsContainer.innerHTML = '<p class="error">خطا در دریافت کانفیگ‌ها</p>';
                        showNotification('خطا در دریافت کانفیگ‌ها: سرور پاسخ نداد', 'error');
                        updateProgress(0, 0);
                        return;
                    }
                    const configs = (await res.text()).split('\n').filter(c => c.trim());
                    if (!configs.length) {
                        e.configsContainer.innerHTML = '<p class="error">هیچ کانفیگی یافت نشد</p>';
                        showNotification('هیچ کانفیگی در فایل موجود نیست', 'error');
                        updateProgress(0, 0);
                        return;
                    }
                    const totalConfigs = configs.length;
                    let testedConfigs = 0;
                    updateProgress(testedConfigs, totalConfigs);
                    const batchSize = 10;
                    const validConfigs = [];
                    for (let i = 0; i < configs.length; i += batchSize) {
                        const batch = configs.slice(i, i + batchSize);
                        const results = await Promise.all(batch.map(async config => {
                            try {
                                const formattedConfig = formatConfig(config);
                                const parsed = parseConfig(config);
                                if (!parsed) return null;
                                const pingResult = await testPing(parsed.host);
                                testedConfigs++;
                                updateProgress(testedConfigs, totalConfigs);
                                if (!pingResult.success || pingResult.ping > 600) return null;
                                const location = await getLocation(parsed.host);
                                return { config: formattedConfig, ping: pingResult.ping, protocol: parsed.protocol, countryCode: location?.countryCode || null };
                            } catch {
                                return null;
                            }
                        }));
                        validConfigs.push(...results.filter(c => c));
                    }
                    if (!validConfigs.length) {
                        e.configsContainer.innerHTML = '<p class="error">هیچ کانفیگ معتبری یافت نشد</p>';
                        showNotification('هیچ کانفیگ معتبری یافت نشد', 'error');
                        updateProgress(testedConfigs, totalConfigs);
                        return;
                    }
                    setCachedConfigs(validConfigs);
                    renderConfigs(validConfigs);
                    updateProgress(testedConfigs, totalConfigs);
                } catch (err) {
                    e.configsContainer.innerHTML = '<p class="error">خطا در بارگذاری کانفیگ‌ها</p>';
                    showNotification(`خطا: ${err.message}`, 'error');
                    updateProgress(0, 0);
                    console.error('Config fetch error:', err);
                }
            };

            const renderConfigs = configs => {
                if (!e.configsContainer) return;
                e.configsContainer.innerHTML = '';
                const activeProtocol = e.filterContainer?.querySelector('.filter-btn.active')?.dataset.protocol || 'all';
                const filteredConfigs = configs.filter(c => activeProtocol === 'all' || c.protocol.toLowerCase() === activeProtocol);
                if (!filteredConfigs.length) {
                    e.configsContainer.innerHTML = '<p class="error">هیچ کانفیگی برای این فیلتر موجود نیست</p>';
                    return;
                }
                const protocolNames = {
                    'hysteria2': 'هیستریا۲',
                    'vless': 'وی‌لس',
                    'trojan': 'تروجان',
                    'ss': 'شدوساکس',
                    'vmess': 'وی‌مس',
                    'wireguard': 'وایرگارد'
                };
                filteredConfigs.sort((a, b) => a.ping - b.ping).forEach((c, i) => {
                    const box = document.createElement('div');
                    box.className = 'config-box';
                    box.draggable = true;
                    box.style.opacity = '0';
                    box.style.animation = `slideInRight 0.6s ease-out ${i * 0.1}s forwards`;
                    box.dataset.protocol = c.protocol.toLowerCase();
                    box.dataset.protocolFa = protocolNames[c.protocol.toLowerCase()];
                    box.dataset.config = JSON.stringify(c);
                    const pingClass = c.ping < 300 ? 'fast' : c.ping < 600 ? 'medium' : 'slow';
                    const logoContent = `<i class="fas fa-server config-logo"></i>`;
                    box.innerHTML = `
                        <button class="share-btn"><i class="fas fa-share-square"></i></button>
                        <button class="delete-btn"><i class="fas fa-trash"></i></button>
                        <div class="config-logo-container">${logoContent}</div>
                        <div class="ping-result ${pingClass}"><i class="fas fa-tachometer-alt"></i> ${toPersianDigits(c.ping.toString())} م‌ث</div>
                        <button class="copy-btn"><i class="fas fa-clipboard"></i> کپی</button>
                    `;
                    const copyBtn = box.querySelector('.copy-btn');
                    if (copyBtn) copyBtn.addEventListener('click', () => {
                        navigator.clipboard.writeText(c.config).then(() => showNotification('کانفیگ کپی شد', 'success')).catch(() => showNotification('خطا در کپی کردن کانفیگ', 'error'));
                    });
                    const shareBtn = box.querySelector('.share-btn');
                    if (shareBtn) shareBtn.addEventListener('click', () => shareConfig(c.config));
                    const deleteBtn = box.querySelector('.delete-btn');
                    if (deleteBtn) deleteBtn.addEventListener('click', () => {
                        box.remove();
                        deleteConfig(c.config);
                    });
                    let holdTimeout;
                    const startDrag = () => {
                        holdTimeout = setTimeout(() => box.classList.add('dragging'), 3000);
                    };
                    const endDrag = () => {
                        clearTimeout(holdTimeout);
                        box.classList.remove('dragging');
                    };
                    box.addEventListener('mousedown', startDrag);
                    box.addEventListener('mouseup', endDrag);
                    box.addEventListener('mouseleave', endDrag);
                    box.addEventListener('touchstart', startDrag);
                    box.addEventListener('touchend', endDrag);
                    box.addEventListener('touchcancel', endDrag);
                    box.addEventListener('dragstart', ev => {
                        ev.dataTransfer.setData('text/plain', JSON.stringify(c));
                        box.classList.add('dragging');
                    });
                    box.addEventListener('dragend', () => box.classList.remove('dragging'));
                    e.configsContainer.appendChild(box);
                });
                if (e.configsContainer) {
                    e.configsContainer.addEventListener('dragover', ev => ev.preventDefault());
                    e.configsContainer.addEventListener('drop', ev => {
                        ev.preventDefault();
                        const draggedData = ev.dataTransfer.getData('text/plain');
                        try {
                            const draggedConfig = JSON.parse(draggedData);
                            const configBoxes = Array.from(e.configsContainer.querySelectorAll('.config-box'));
                            const draggedBox = configBoxes.find(box => JSON.parse(box.dataset.config).config === draggedConfig.config);
                            const dropBox = ev.target.closest('.config-box');
                            if (draggedBox && dropBox && draggedBox !== dropBox) {
                                const cachedConfigs = getCachedConfigs();
                                if (cachedConfigs) {
                                    const draggedIndex = cachedConfigs.findIndex(c => c.config === draggedConfig.config);
                                    const dropIndex = configBoxes.findIndex(box => box === dropBox);
                                    const updatedConfigs = [...cachedConfigs];
                                    updatedConfigs.splice(draggedIndex, 1);
                                    updatedConfigs.splice(dropIndex, 0, draggedConfig);
                                    setCachedConfigs(updatedConfigs);
                                    renderConfigs(updatedConfigs);
                                }
                            }
                        } catch (err) {
                            console.error('Drag and drop error:', err);
                        }
                    });
                }
                saveUIState();
                refreshConfigPings();
            };

            const setupFilters = () => {
                if (!e.filterContainer) return;
                e.filterContainer.querySelectorAll('.filter-btn').forEach(btn => {
                    btn.addEventListener('click', () => {
                        e.filterContainer.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
                        btn.classList.add('active');
                        const cachedConfigs = getCachedConfigs();
                        if (cachedConfigs) renderConfigs(cachedConfigs);
                        else extractConfigs();
                    });
                });
            };

            const togglePlayPause = () => {
                if (!e.bgMusic || !e.playPause) return;
                if (e.bgMusic.paused) {
                    e.bgMusic.play().then(() => {
                        e.playPause.innerHTML = '<i class="fas fa-pause-circle"></i> مکث';
                        showNotification('موسیقی در حال پخش', 'success');
                    }).catch(() => showNotification('برای پخش موسیقی، ابتدا با صفحه تعامل کنید', 'info'));
                } else {
                    e.bgMusic.pause();
                    e.playPause.innerHTML = '<i class="fas fa-play-circle"></i> پخش';
                    showNotification('موسیقی متوقف شد', 'info');
                }
            };

            // Event Listeners
            if (e.modalTitleImg) e.modalTitleImg.addEventListener('click', () => {
                e.modalTitleImg.classList.add('active');
                setTimeout(() => e.modalTitleImg.classList.remove('active'), 500);
                extractConfigs(true);
            });
            if (e.mainMenuBtn) e.mainMenuBtn.addEventListener('click', () => toggleModal('mainMenu', true, 'mainMenuOverlay'));
            if (e.configSelectBtn) e.configSelectBtn.addEventListener('click', () => {
                toggleModal('publicShopMenu', true, 'configSelectOverlay');
                extractConfigs();
            });
            if (e.settingsItem) e.settingsItem.addEventListener('click', () => toggleModal('settingsPanel', true, 'mainMenuOverlay'));
            if (e.sourceItem) e.sourceItem.addEventListener('click', () => toggleModal('sourcePanel', true, 'sourceOverlay'));
            if (e.aboutItem) e.aboutItem.addEventListener('click', () => toggleModal('aboutPanel', true, 'mainMenuOverlay'));
            if (e.reportProblemBtn) e.reportProblemBtn.addEventListener('click', () => toggleModal('reportProblemMenu', true, 'reportProblemOverlay'));
            if (e.submitReportProblem) e.submitReportProblem.addEventListener('click', submitReportProblem);
            if (e.submitSourceUrl) e.submitSourceUrl.addEventListener('click', submitSourceUrl);
            if (e.closeMainMenu) e.closeMainMenu.addEventListener('click', () => toggleModal('mainMenu', false, 'mainMenuOverlay'));
            if (e.closePublicShopMenu) e.closePublicShopMenu.addEventListener('click', () => toggleModal('publicShopMenu', false, 'configSelectOverlay'));
            if (e.closeSettingsPanel) e.closeSettingsPanel.addEventListener('click', () => toggleModal('settingsPanel', false, 'mainMenuOverlay'));
            if (e.closeAboutPanel) e.closeAboutPanel.addEventListener('click', () => toggleModal('aboutPanel', false, 'mainMenuOverlay'));
            if (e.closeReportProblemMenu) e.closeReportProblemMenu.addEventListener('click', () => toggleModal('reportProblemMenu', false, 'reportProblemOverlay'));
            if (e.closeSourcePanel) e.closeSourcePanel.addEventListener('click', () => toggleModal('sourcePanel', false, 'sourceOverlay'));
            if (e.mainMenuOverlay) e.mainMenuOverlay.addEventListener('click', closeAllModals);
            if (e.configSelectOverlay) e.configSelectOverlay.addEventListener('click', closeAllModals);
            if (e.reportProblemOverlay) e.reportProblemOverlay.addEventListener('click', closeAllModals);
            if (e.sourceOverlay) e.sourceOverlay.addEventListener('click', closeAllModals);
            if (e.playPause) e.playPause.addEventListener('click', togglePlayPause);

            // Initialize
            if (e.device) e.device.textContent = /Mobile|Android|iPhone|iPad/i.test(navigator.userAgent) ? 'موبایل' : 'دسکتاپ';
            setupFilters();
            loadUIState();
            if (e.permanentWindow) e.permanentWindow.style.display = 'flex';
            showNotification('به ایکسرو خوش آمدید', 'success');
            if (e.bgMusic) e.bgMusic.play().catch(() => showNotification('برای پخش موسیقی، ابتدا با صفحه تعامل کنید', 'info'));
            if (e.publicShopMenu?.classList.contains('open')) extractConfigs();
            refreshIP();
            refreshPing();
        });
    </script>
</body>
</html>
