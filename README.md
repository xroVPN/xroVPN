<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>VPN Manager - ایکسرو</title>
    <style>
        /* فونت و متغیرهای اصلی */
        :root {
            --primary-color: #6e8efb;
            --primary-dark: #5a7df8;
            --secondary-color: #4CAF50;
            --danger-color: #e74c3c;
            --warning-color: #f39c12;
            --text-color: #2c3e50;
            --text-light: #7f8c8d;
            --bg-color: #f8f9fa;
            --card-bg: white;
            --border-color: #e0e0e0;
            --shadow-color: rgba(0,0,0,0.1);
            --overlay-color: rgba(0,0,0,0.3);
            --transition-theme: all 0.3s ease;
            --gradient-primary: linear-gradient(135deg, #6e8efb, #4a6cf7);
            --gradient-danger: linear-gradient(135deg, #ff7675, #d63031);
            --gradient-success: linear-gradient(135deg, #55efc4, #00b894);
            --gradient-warning: linear-gradient(135deg, #ffeaa7, #fbc2eb);
            --gradient-purple: linear-gradient(135deg, #a29bfe, #6c5ce7);
            --gradient-orange: linear-gradient(135deg, #fab1a0, #e17055);
            --gradient-blue: linear-gradient(135deg, #74b9ff, #0984e3);
            --gradient-pink: linear-gradient(135deg, #fd79a8, #e84393);
            --gradient-teal: linear-gradient(135deg, #00cec9, #0984e3);
            --gradient-gaming: linear-gradient(135deg, #ff6b6b, #ff8e8e);
            --gradient-social: linear-gradient(135deg, #4facfe, #00f2fe);
            --gradient-combo: linear-gradient(135deg, #a18cd1, #fbc2eb);
        }
        
        .dark-mode {
            --primary-color: #7d9eff;
            --primary-dark: #6a8eff;
            --secondary-color: #5cb85c;
            --danger-color: #ff6b6b;
            --warning-color: #ffbe76;
            --text-color: #ecf0f1;
            --text-light: #bdc3c7;
            --bg-color: #121212;
            --card-bg: #1e1e1e;
            --border-color: #333333;
            --shadow-color: rgba(0,0,0,0.5);
            --overlay-color: rgba(0,0,0,0.7);
            --gradient-primary: linear-gradient(135deg, #7d9eff, #5a7dff);
            --gradient-gaming: linear-gradient(135deg, #ff4757, #ff6b81);
            --gradient-social: linear-gradient(135deg, #3a7bd5, #00d2ff);
            --gradient-combo: linear-gradient(135deg, #8e2de2, #4a00e0);
        }
        
        /* ریست استایل‌ها و فونت */
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            transition: background-color 0.3s, color 0.3s, border-color 0.3s;
        }
        
        body {
            font-family: 'Vazirmatn', system-ui, -apple-system, sans-serif;
            background-color: var(--bg-color);
            color: var(--text-color);
            height: 100vh;
            overflow: hidden;
            -webkit-user-select: none;
            user-select: none;
            touch-action: manipulation;
        }
        
        /* صفحه لودینگ */
        .loading-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--gradient-primary);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 2000;
            transition: opacity 0.5s ease;
        }
        
        .loading-logo {
            width: 120px;
            height: 120px;
            margin-bottom: 30px;
            animation: pulse 2s infinite;
        }
        
        .loading-text {
            color: white;
            font-size: 1.5rem;
            margin-bottom: 20px;
            font-weight: 700;
        }
        
        .loading-bar-container {
            width: 80%;
            max-width: 300px;
            height: 10px;
            background: rgba(255, 255, 255, 0.2);
            border-radius: 10px;
            overflow: hidden;
        }
        
        .loading-bar {
            height: 100%;
            width: 0;
            background: white;
            border-radius: 10px;
            transition: width 0.1s linear;
        }
        
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }
        
        /* استایل‌های اصلی */
        .top-bar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 20px;
            background: var(--card-bg);
            border-bottom: 1px solid var(--border-color);
            box-shadow: 0 2px 10px var(--shadow-color);
            position: relative;
            z-index: 10;
        }
        
        .logo {
            font-size: 1rem;
            font-weight: 700;
            color: var(--primary-color);
            padding: 8px 12px;
            border-radius: 10px;
            cursor: pointer;
            background: rgba(110, 142, 251, 0.1);
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        .content {
            height: calc(100vh - 60px);
            display: flex;
            flex-direction: column;
            padding: 20px;
            position: relative;
            overflow-y: auto;
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.5s ease, transform 0.5s ease;
        }
        
        .content.show {
            opacity: 1;
            transform: translateY(0);
        }
        
        .welcome-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            flex: 1;
        }
        
        .emoji-container {
            width: 140px;
            height: 140px;
            background: var(--gradient-primary);
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            margin-bottom: 25px;
            box-shadow: 0 10px 30px rgba(110, 142, 251, 0.3);
            border: 3px solid var(--primary-color);
            overflow: hidden;
        }
        
        .emoji {
            width: 80%;
            height: 80%;
            object-fit: contain;
            border-radius: 50%;
        }
        
        .creator {
            font-size: 1rem;
            color: var(--text-light);
            margin-top: 15px;
            text-align: center;
            height: 24px;
        }
        
        /* دکمه‌ها و منوها */
        .floating-btn {
            position: fixed;
            bottom: 25px;
            left: 25px;
            width: 70px;
            height: 70px;
            background: var(--gradient-primary);
            border-radius: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 30px;
            color: white;
            box-shadow: 0 8px 25px rgba(110, 142, 251, 0.4);
            cursor: pointer;
            z-index: 100;
            border: none;
            outline: none;
            transition: transform 0.2s, box-shadow 0.2s;
        }
        
        .floating-btn:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 12px 30px rgba(110, 142, 251, 0.5);
        }
        
        .menu-btn {
            width: 32px;
            height: 32px;
            display: flex;
            flex-direction: column;
            justify-content: space-around;
            align-items: center;
            cursor: pointer;
            padding: 5px;
            border-radius: 8px;
            transition: all 0.3s;
        }
        
        .menu-btn:hover {
            background: rgba(110, 142, 251, 0.1);
        }
        
        .menu-line {
            width: 100%;
            height: 3px;
            background-color: var(--text-color);
            border-radius: 2px;
            transition: all 0.3s;
        }
        
        .menu-btn:hover .menu-line {
            background-color: var(--primary-color);
        }
        
        /* پنجره‌های مدال */
        .overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--overlay-color);
            z-index: 999;
            opacity: 0;
            visibility: hidden;
            transition: all 0.3s;
            backdrop-filter: blur(5px);
        }
        
        .overlay.open {
            opacity: 1;
            visibility: visible;
        }
        
        .modal-window {
            position: fixed;
            background: var(--card-bg);
            z-index: 1000;
            transition: all 0.3s ease-out;
            box-shadow: 0 10px 30px var(--shadow-color);
            overflow: hidden;
            display: flex;
            flex-direction: column;
        }
        
        /* پنجره منو اصلی */
        .main-menu {
            top: -100%;
            right: 0;
            width: 100%;
            height: auto;
            max-height: 70%;
            border-radius: 0 0 20px 20px;
        }
        
        .main-menu.open {
            top: 0;
        }
        
        /* پنجره منو سریع */
        .quick-menu {
            bottom: -50%;
            left: 0;
            width: 100%;
            height: auto;
            max-height: 60%;
            border-radius: 20px 20px 0 0;
        }
        
        .quick-menu.open {
            bottom: 0;
        }
        
        /* پنجره فروشگاه */
        .shop-menu {
            bottom: -100%;
            left: 0;
            width: 100%;
            height: 80%;
            max-height: 650px;
            border-radius: 20px 20px 0 0;
        }
        
        .shop-menu.open {
            bottom: 0;
        }
        
        /* پنجره راهنما */
        .help-window {
            top: -100%;
            right: 0;
            width: 100%;
            height: 75%;
            max-height: 650px;
            border-radius: 0 0 20px 20px;
        }
        
        .help-window.open {
            top: 0;
        }
        
        /* پنجره چالش و گیم */
        .challenge-window {
            top: -100%;
            right: 0;
            width: 100%;
            height: 55%;
            max-height: 550px;
            border-radius: 0 0 20px 20px;
        }
        
        .challenge-window.open {
            top: 0;
        }
        
        /* پنجره بکاپ */
        .backup-window {
            top: -100%;
            right: 0;
            width: 100%;
            height: 65%;
            max-height: 550px;
            border-radius: 0 0 20px 20px;
        }
        
        .backup-window.open {
            top: 0;
        }
        
        /* پنجره وایرگارد */
        .wireguard-window {
            bottom: -100%;
            left: 0;
            width: 100%;
            height: 65%;
            max-height: 550px;
            border-radius: 20px 20px 0 0;
        }
        
        .wireguard-window.open {
            bottom: 0;
        }
        
        /* پنجره تنظیمات */
        .settings-panel {
            top: -100%;
            right: 0;
            width: 100%;
            height: 35%;
            border-radius: 0 0 20px 20px;
        }
        
        .settings-panel.open {
            top: 0;
        }
        
        /* پنجره تایید */
        .confirm-window {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%) scale(0.9);
            width: 90%;
            max-width: 350px;
            border-radius: 20px;
            padding: 25px;
            z-index: 1007;
            opacity: 0;
            visibility: hidden;
            border: 1px solid var(--border-color);
            background: var(--card-bg);
            box-shadow: 0 15px 40px var(--shadow-color);
        }
        
        .confirm-window.open {
            transform: translate(-50%, -50%) scale(1);
            opacity: 1;
            visibility: visible;
        }
        
        /* استایل‌های داخلی پنجره‌ها */
        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
            padding: 20px;
            padding-bottom: 15px;
            border-bottom: 1px solid var(--border-color);
        }
        
        .modal-title {
            font-weight: 700;
            color: var(--text-color);
            font-size: 1.25rem;
        }
        
        .close-btn {
            cursor: pointer;
            font-size: 1.5rem;
            color: var(--text-color);
            transition: all 0.3s;
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
        }
        
        .close-btn:hover {
            background: var(--bg-color);
            transform: rotate(90deg);
            color: var(--primary-color);
        }
        
        .modal-content {
            flex: 1;
            overflow-y: auto;
            padding: 20px;
        }
        
        /* آیتم‌های منو */
        .menu-item {
            padding: 18px;
            margin-bottom: 12px;
            background: var(--bg-color);
            border-radius: 12px;
            cursor: pointer;
            transition: all 0.3s;
            border: 1px solid var(--border-color);
            box-shadow: 0 3px 10px var(--shadow-color);
        }
        
        .menu-item:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px var(--shadow-color);
            border-color: var(--primary-color);
        }
        
        .menu-item-title {
            font-weight: 700;
            margin-bottom: 8px;
            color: var(--text-color);
            font-size: 1.125rem;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .menu-item-title i {
            color: var(--primary-color);
        }
        
        .menu-item-desc {
            font-size: 0.875rem;
            color: var(--text-light);
            line-height: 1.6;
        }
        
        /* تب‌ها */
        .tabs {
            display: flex;
            border-bottom: 1px solid var(--border-color);
            margin-bottom: 20px;
            gap: 5px;
            overflow-x: auto;
            padding: 0 20px;
        }
        
        .tab {
            padding: 12px 20px;
            cursor: pointer;
            border-bottom: 3px solid transparent;
            font-weight: 500;
            transition: all 0.3s;
            border-radius: 8px 8px 0 0;
            white-space: nowrap;
        }
        
        .tab:hover {
            background: var(--bg-color);
        }
        
        .tab.active {
            border-bottom: 3px solid var(--primary-color);
            color: var(--primary-color);
            font-weight: 700;
        }
        
        .tab-content {
            display: none;
        }
        
        .tab-content.active {
            display: block;
        }
        
        /* اشتراک‌ها */
        .subscription-option {
            padding: 18px;
            margin-bottom: 15px;
            background: var(--bg-color);
            border-radius: 15px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            transition: all 0.3s;
            border: 1px solid var(--border-color);
            box-shadow: 0 3px 10px var(--shadow-color);
        }
        
        .subscription-option:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px var(--shadow-color);
        }
        
        .subscription-info {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .subscription-icon {
            font-size: 1.5rem;
            width: 50px;
            height: 50px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 12px;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
        }
        
        /* رنگ‌بندی آیکون‌های اشتراک */
        .gaming1 { background: var(--gradient-gaming); color: white; }
        .gaming2 { background: var(--gradient-gaming); color: white; }
        .gaming3 { background: var(--gradient-gaming); color: white; }
        .gaming4 { background: var(--gradient-gaming); color: white; }
        .gaming5 { background: var(--gradient-gaming); color: white; }
        .gaming6 { background: var(--gradient-gaming); color: white; }
        
        .social1 { background: var(--gradient-social); color: white; }
        .social2 { background: var(--gradient-social); color: white; }
        .social3 { background: var(--gradient-social); color: white; }
        .social4 { background: var(--gradient-social); color: white; }
        .social5 { background: var(--gradient-social); color: white; }
        .social6 { background: var(--gradient-social); color: white; }
        
        .combo1 { background: var(--gradient-combo); color: white; }
        .combo2 { background: var(--gradient-combo); color: white; }
        .combo3 { background: var(--gradient-combo); color: white; }
        .combo4 { background: var(--gradient-combo); color: white; }
        .combo5 { background: var(--gradient-combo); color: white; }
        .combo6 { background: var(--gradient-combo); color: white; }
        
        .subscription-details {
            display: flex;
            flex-direction: column;
            gap: 5px;
        }
        
        .subscription-name {
            font-weight: 700;
            color: var(--text-color);
            font-size: 1rem;
        }
        
        .subscription-features {
            font-size: 0.75rem;
            color: var(--text-light);
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
        }
        
        .subscription-features i {
            margin-left: 3px;
        }
        
        .subscription-price {
            font-weight: 800;
            color: var(--primary-color);
            font-size: 1.125rem;
            white-space: nowrap;
            margin-left: 10px;
        }
        
        /* دکمه‌ها */
        .btn {
            padding: 10px 20px;
            border-radius: 10px;
            font-family: inherit;
            cursor: pointer;
            font-weight: 700;
            font-size: 0.875rem;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            gap: 8px;
            justify-content: center;
            border: none;
        }
        
        .btn-primary {
            background: var(--gradient-primary);
            color: white;
            box-shadow: 0 3px 10px rgba(110, 142, 251, 0.3);
        }
        
        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(110, 142, 251, 0.4);
        }
        
        .btn-secondary {
            background: linear-gradient(135deg, #4CAF50, #2E7D32);
            color: white;
            box-shadow: 0 3px 10px rgba(76, 175, 80, 0.3);
        }
        
        .btn-secondary:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(76, 175, 80, 0.4);
        }
        
        .btn-large {
            padding: 18px;
            font-size: 1rem;
            width: 100%;
        }
        
        /* نوتیفیکیشن */
        .notification {
            position: fixed;
            bottom: 30px;
            right: 30px;
            background: var(--card-bg);
            border-radius: 15px;
            padding: 18px 25px;
            box-shadow: 0 8px 25px var(--shadow-color);
            z-index: 1100;
            transform: translateY(100px);
            opacity: 0;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            display: flex;
            align-items: center;
            gap: 15px;
            border: 1px solid var(--border-color);
            max-width: 350px;
        }
        
        .notification.show {
            transform: translateY(0);
            opacity: 1;
        }
        
        .notification-icon {
            font-size: 1.5rem;
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
        }
        
        .notification-success {
            background: rgba(76, 175, 80, 0.1);
            color: #4CAF50;
        }
        
        .notification-info {
            background: rgba(110, 142, 251, 0.1);
            color: var(--primary-color);
        }
        
        .notification-error {
            background: rgba(231, 76, 60, 0.1);
            color: #e74c3c;
        }
        
        .notification-message {
            font-size: 0.875rem;
            font-weight: 500;
        }
        
        /* راهنما */
        .usage-guide {
            font-size: 0.875rem;
            color: var(--text-light);
            line-height: 1.8;
            margin-top: 20px;
            padding: 15px;
            background: var(--bg-color);
            border-radius: 15px;
            border: 1px solid var(--border-color);
        }
        
        .usage-guide h4 {
            color: var(--primary-color);
            margin-bottom: 10px;
            font-size: 1rem;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        /* انیمیشن‌ها */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        @keyframes slideIn {
            from { transform: translateY(-30px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }
        
        .fade-in {
            animation: fadeIn 0.5s ease-out;
        }
        
        .slide-in {
            animation: slideIn 0.5s ease-out;
        }
        
        /* اسکرول بار سفارشی */
        ::-webkit-scrollbar {
            width: 8px;
            height: 8px;
        }
        
        ::-webkit-scrollbar-track {
            background: var(--bg-color);
            border-radius: 10px;
        }
        
        ::-webkit-scrollbar-thumb {
            background: var(--primary-color);
            border-radius: 10px;
        }
        
        /* حالت شب - ستاره‌ها */
        .dark-mode::before {
            content: "";
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: 
                radial-gradient(white 1px, transparent 1px),
                radial-gradient(white 1px, transparent 1px);
            background-size: 30px 30px;
            background-position: 0 0, 15px 15px;
            opacity: 0.1;
            pointer-events: none;
            z-index: -1;
        }
        
        /* ریسپانسیو برای موبایل */
        @media (max-width: 768px) {
            .subscription-option {
                flex-direction: column;
                align-items: flex-start;
                gap: 15px;
            }
            
            .subscription-info {
                width: 100%;
            }
            
            .order-btn {
                width: 100%;
            }
            
            .shop-menu, .wireguard-window {
                height: 80%;
                max-height: none;
            }
            
            .tabs {
                overflow-x: auto;
                padding-bottom: 5px;
            }
            
            .tab {
                padding: 10px 15px;
                font-size: 0.875rem;
            }
            
            .modal-content {
                padding: 15px;
            }
            
            .floating-btn {
                width: 60px;
                height: 60px;
                font-size: 25px;
                bottom: 20px;
                left: 20px;
            }
        }

        /* استایل‌های جدید برای دکمه‌های دانلود */
        .download-buttons {
            display: flex;
            flex-direction: column;
            gap: 15px;
            margin-bottom: 20px;
        }
    </style>
    <!-- بارگذاری فونت با پیش‌بارگذاری -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@400;500;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
</head>
<body>
    <!-- صفحه لودینگ -->
    <div class="loading-screen" id="loadingScreen">
        <img src="https://uploadkon.ir/uploads/78d303_25InShot-۲۰۲۵۰۷۰۳-۰۹۲۶۱۸۶۷۵.png" class="loading-logo" alt="Logo">
        <div class="loading-text">در حال بارگذاری...</div>
        <div class="loading-bar-container">
            <div class="loading-bar" id="loadingBar"></div>
        </div>
    </div>
    
    <!-- نوار بالایی -->
    <div class="top-bar">
        <div class="logo" id="helpBtn">
            <i class="fas fa-question-circle"></i>
            راهنمای سایت
        </div>
        <div class="menu-btn" id="mainMenuBtn">
            <div class="menu-line"></div>
            <div class="menu-line"></div>
            <div class="menu-line"></div>
        </div>
    </div>
    
    <!-- محتوای اصلی -->
    <div class="content" id="mainContent">
        <div class="welcome-container" id="welcomeContainer">
            <div class="emoji-container">
                <img src="https://uploadkon.ir/uploads/78d303_25InShot-۲۰۲۵۰۷۰۳-۰۹۲۶۱۸۶۷۵.png" class="emoji" alt="Logo" loading="lazy">
            </div>
            <div class="creator" id="todayDate"></div>
        </div>
    </div>
    
    <!-- دکمه شناور -->
    <button class="floating-btn" id="quickMenuBtn">
        <i class="fas fa-plus"></i>
    </button>
    
    <!-- منوی اصلی -->
    <div class="modal-window main-menu" id="mainMenu">
        <div class="modal-header">
            <div class="modal-title">منوی اصلی</div>
            <div class="close-btn" id="closeMainMenu">×</div>
        </div>
        <div class="modal-content">
            <div class="menu-item" id="challengeItem">
                <div class="menu-item-title">
                    <i class="fas fa-gamepad"></i>
                    چالش و گیم
                </div>
                <div class="menu-item-desc">با شرکت در چالش‌ها سرویس رایگان ببر</div>
            </div>
            <div class="menu-item" id="backupItem">
                <div class="menu-item-title">
                    <i class="fas fa-database"></i>
                    بکاپ تونل‌ها
                </div>
                <div class="menu-item-desc">تهیه بکاپ یا بازیابی اطلاعات قبلی</div>
            </div>
            <div class="menu-item" id="themeItem">
                <div class="menu-item-title">
                    <i class="fas fa-cog"></i>
                    تنظیمات
                </div>
                <div class="menu-item-desc">شخصی‌سازی سیستم مطابق سلیقه شما</div>
            </div>
        </div>
    </div>
    
    <!-- تنظیمات -->
    <div class="modal-window settings-panel" id="settingsPanel">
        <div class="modal-header">
            <div class="modal-title">تنظیمات کاربری</div>
            <div class="close-btn" id="closeSettings">×</div>
        </div>
        <div class="modal-content">
            <div class="setting-item">
                <div class="setting-label">حالت شب / روز</div>
                <label class="theme-switch">
                    <input type="checkbox" id="themeToggle">
                    <span class="slider"></span>
                </label>
            </div>
        </div>
    </div>
    
    <!-- منوی سریع -->
    <div class="modal-window quick-menu" id="quickMenu">
        <div class="modal-content">
            <div class="menu-item" id="quickShopItem">
                <div class="menu-item-title">
                    <i class="fas fa-shopping-bag"></i>
                    فروشگاه سرویس
                </div>
                <div class="menu-item-desc">خرید اشتراک جدید یا تمدید اشتراک فعلی</div>
            </div>
            <div class="menu-item" id="quickWireguardItem">
                <div class="menu-item-title">
                    <i class="fas fa-download"></i>
                    دانلود اپلیکیشن
                </div>
                <div class="menu-item-desc">دانلود کلاینت رسمی برای دستگاه‌های مختلف</div>
            </div>
        </div>
    </div>
    
    <!-- فروشگاه -->
    <div class="modal-window shop-menu" id="shopWindow">
        <div class="modal-header">
            <div class="modal-title">فروشگاه سرویس</div>
            <div class="close-btn" id="closeShop">×</div>
        </div>
        <div class="tabs">
            <div class="tab active" data-tab="gaming">گیمینگ</div>
            <div class="tab" data-tab="social">اجتمائی</div>
            <div class="tab" data-tab="combo">گیمینگ و اجتمائی</div>
        </div>
        <div class="modal-content">
            <div class="tab-content active" id="gaming-tab">
                <!--  گیمینگ -->
                <div class="subscription-option">
                    <div class="subscription-info">
                        <div class="subscription-icon gaming1"><i class="fas fa-gamepad"></i></div>
                        <div class="subscription-details">
                            <div class="subscription-name">اشتراک ۱ ماهه گیمینگ</div>
                            <div class="subscription-features">
                                <span><i class="fas fa-hdd"></i> حجم ۵۰ گیگ</span>
                                <span><i class="fas fa-bolt"></i> سرعت بالا</span>
                                <span><i class="fas fa-user"></i> ۱ کاربر</span>
                            </div>
                        </div>
                    </div>
                    <div class="subscription-price">۹۹,۰۰۰ تومان</div>
                    <button class="btn btn-primary" onclick="orderSubscription(1, 'gaming')">
                        <i class="fas fa-shopping-cart"></i>
                        برای سفارش و تست سرویس کلیک کنید
                    </button>
                </div>
                
                <!-- اشتراک 2 ماهه گیمینگ -->
                <div class="subscription-option">
                    <div class="subscription-info">
                        <div class="subscription-icon gaming2"><i class="fas fa-gamepad"></i></div>
                        <div class="subscription-details">
                            <div class="subscription-name">اشتراک ۱ ماهه گیمینگ</div>
                            <div class="subscription-features">
                                <span><i class="fas fa-infinity"></i> حجم نامحدود</span>
                                <span><i class="fas fa-bolt"></i> سرعت بالا</span>
                                <span><i class="fas fa-user"></i> ۱ کاربر</span>
                            </div>
                        </div>
                    </div>
                    <div class="subscription-price">۲۸۹,۰۰۰ تومان</div>
                    <button class="btn btn-primary" onclick="orderSubscription(2, 'gaming')">
                        <i class="fas fa-shopping-cart"></i>
                        برای سفارش کلیک کنید
                    </button>
                </div>
                
                <!-- اشتراک 3 ماهه گیمینگ -->
                <div class="subscription-option">
                    <div class="subscription-info">
                        <div class="subscription-icon gaming3"><i class="fas fa-gamepad"></i></div>
                        <div class="subscription-details">
                            <div class="subscription-name">اشتراک ۲ ماهه گیمینگ</div>
                            <div class="subscription-features">
                                <span><i class="fas fa-infinity"></i> حجم نامحدود</span>
                                <span><i class="fas fa-bolt"></i> سرعت بالا</span>
                                <span><i class="fas fa-user"></i> ۱ کاربر</span>
                            </div>
                        </div>
                    </div>
                    <div class="subscription-price">۴۵۹,۰۰۰ تومان</div>
                    <button class="btn btn-primary" onclick="orderSubscription(3, 'gaming')">
                        <i class="fas fa-shopping-cart"></i>
                        برای سفارش کلیک کنید
                    </button>
                </div>
                
                <!-- اشتراک 4 ماهه گیمینگ -->
                <div class="subscription-option">
                    <div class="subscription-info">
                        <div class="subscription-icon gaming4"><i class="fas fa-gamepad"></i></div>
                        <div class="subscription-details">
                            <div class="subscription-name">اشتراک ۳ ماهه گیمینگ</div>
                            <div class="subscription-features">
                                <span><i class="fas fa-infinity"></i> حجم نامحدود</span>
                                <span><i class="fas fa-bolt"></i> سرعت بالا</span>
                                <span><i class="fas fa-user"></i> ۱ کاربر</span>
                            </div>
                        </div>
                    </div>
                    <div class="subscription-price">۶۲۴,۰۰۰ تومان</div>
                    <button class="btn btn-primary" onclick="orderSubscription(4, 'gaming')">
                        <i class="fas fa-shopping-cart"></i>
                        برای سفارش کلیک کنید
                    </button>
                </div>
                
                <!-- اشتراک 5 ماهه گیمینگ -->
                <div class="subscription-option">
                    <div class="subscription-info">
                        <div class="subscription-icon gaming5"><i class="fas fa-gamepad"></i></div>
                        <div class="subscription-details">
                            <div class="subscription-name">اشتراک ۴ ماهه گیمینگ</div>
                            <div class="subscription-features">
                                <span><i class="fas fa-infinity"></i> حجم نامحدود</span>
                                <span><i class="fas fa-bolt"></i> سرعت بالا</span>
                                <span><i class="fas fa-user"></i> ۱ کاربر</span>
                            </div>
                        </div>
                    </div>
                    <div class="subscription-price">۷۸۶,۰۰۰ تومان</div>
                    <button class="btn btn-primary" onclick="orderSubscription(5, 'gaming')">
                        <i class="fas fa-shopping-cart"></i>
                        برای سفارش کلیک کنید
                    </button>
                </div>
                
                <!-- اشتراک 6 ماهه گیمینگ -->
                <div class="subscription-option">
                    <div class="subscription-info">
                        <div class="subscription-icon gaming6"><i class="fas fa-gamepad"></i></div>
                        <div class="subscription-details">
                            <div class="subscription-name">اشتراک ۵ ماهه گیمینگ</div>
                            <div class="subscription-features">
                                <span><i class="fas fa-infinity"></i> حجم نامحدود</span>
                                <span><i class="fas fa-bolt"></i> سرعت بالا</span>
                                <span><i class="fas fa-user"></i> ۱ کاربر</span>
                            </div>
                        </div>
                    </div>
                    <div class="subscription-price">۹۶۱,۰۰۰ تومان</div>
                    <button class="btn btn-primary" onclick="orderSubscription(6, 'gaming')">
                        <i class="fas fa-shopping-cart"></i>
                        برای سفارش کلیک کنید
                    </button>
                </div>
            </div>
            
            <div class="tab-content" id="social-tab">
                <!-- اشتراک 1 ماهه اجتمائی -->
                <div class="subscription-option">
                    <div class="subscription-info">
                        <div class="subscription-icon social1"><i class="fas fa-users"></i></div>
                        <div class="subscription-details">
                            <div class="subscription-name">اشتراک 1 ماهه اجتمائی</div>
                            <div class="subscription-features">
                                <span><i class="fas fa-hdd"></i> حجم ۵۰ گیگ</span>
                                <span><i class="fas fa-bolt"></i> سرعت بالا</span>
                                <span><i class="fas fa-user"></i> 1 کاربر</span>
                            </div>
                        </div>
                    </div>
                    <div class="subscription-price">۹۸,۰۰۰ تومان</div>
                    <button class="btn btn-primary" onclick="orderSubscription(1, 'social')">
                        <i class="fas fa-shopping-cart"></i>
                        برای سفارش و تست سرویس کلیک کنید
                    </button>
                </div>
                
                <!-- اشتراک 2 ماهه اجتمائی -->
                <div class="subscription-option">
                    <div class="subscription-info">
                        <div class="subscription-icon social2"><i class="fas fa-users"></i></div>
                        <div class="subscription-details">
                            <div class="subscription-name">اشتراک ۱ ماهه اجتمائی</div>
                            <div class="subscription-features">
                                <span><i class="fas fa-infinity"></i> حجم نامحدود</span>
                                <span><i class="fas fa-bolt"></i> سرعت بالا</span>
                                <span><i class="fas fa-user"></i> 1 کاربر</span>
                            </div>
                        </div>
                    </div>
                    <div class="subscription-price">۲۲۷,۰۰۰ تومان</div>
                    <button class="btn btn-primary" onclick="orderSubscription(2, 'social')">
                        <i class="fas fa-shopping-cart"></i>
                        برای سفارش کلیک کنید
                    </button>
                </div>
                
                <!-- اشتراک 3 ماهه اجتمائی -->
                <div class="subscription-option">
                    <div class="subscription-info">
                        <div class="subscription-icon social3"><i class="fas fa-users"></i></div>
                        <div class="subscription-details">
                            <div class="subscription-name">اشتراک ۲ ماهه اجتمائی</div>
                            <div class="subscription-features">
                                <span><i class="fas fa-infinity"></i> حجم نامحدود</span>
                                <span><i class="fas fa-bolt"></i> سرعت بالا</span>
                                <span><i class="fas fa-user"></i> 1 کاربر</span>
                            </div>
                        </div>
                    </div>
                    <div class="subscription-price">۴۱۸,۰۰۰ تومان</div>
                    <button class="btn btn-primary" onclick="orderSubscription(3, 'social')">
                        <i class="fas fa-shopping-cart"></i>
                        برای سفارش کلیک کنید 
                    </button>
                </div>
                
                <!-- اشتراک 4 ماهه اجتمائی -->
                <div class="subscription-option">
                    <div class="subscription-info">
                        <div class="subscription-icon social4"><i class="fas fa-users"></i></div>
                        <div class="subscription-details">
                            <div class="subscription-name">اشتراک ۳ ماهه اجتمائی</div>
                            <div class="subscription-features">
                                <span><i class="fas fa-infinity"></i> حجم نامحدود</span>
                                <span><i class="fas fa-bolt"></i> سرعت بالا</span>
                                <span><i class="fas fa-user"></i> 1 کاربر</span>
                            </div>
                        </div>
                    </div>
                    <div class="subscription-price">۵۸۰,۰۰۰ تومان</div>
                    <button class="btn btn-primary" onclick="orderSubscription(4, 'social')">
                        <i class="fas fa-shopping-cart"></i>
                        برای سفارش کلیک کنید
                    </button>
                </div>
                
                <!-- اشتراک 5 ماهه اجتمائی -->
                <div class="subscription-option">
                    <div class="subscription-info">
                        <div class="subscription-icon social5"><i class="fas fa-users"></i></div>
                        <div class="subscription-details">
                            <div class="subscription-name">اشتراک ۴ ماهه اجتمائی</div>
                            <div class="subscription-features">
                                <span><i class="fas fa-infinity"></i> حجم نامحدود</span>
                                <span><i class="fas fa-bolt"></i> سرعت بالا</span>
                                <span><i class="fas fa-user"></i> 1 کاربر</span>
                            </div>
                        </div>
                    </div>
                    <div class="subscription-price">۷۲۹,۰۰۰ تومان</div>
                    <button class="btn btn-primary" onclick="orderSubscription(5, 'social')">
                        <i class="fas fa-shopping-cart"></i>
                        برای سفارش کلیک کنید
                    </button>
                </div>
                
                <!-- اشتراک 6 ماهه اجتمائی -->
                <div class="subscription-option">
                    <div class="subscription-info">
                        <div class="subscription-icon social6"><i class="fas fa-users"></i></div>
                        <div class="subscription-details">
                            <div class="subscription-name">اشتراک ۵ ماهه اجتمائی</div>
                            <div class="subscription-features">
                                <span><i class="fas fa-infinity"></i> حجم نامحدود</span>
                                <span><i class="fas fa-bolt"></i> سرعت بالا</span>
                                <span><i class="fas fa-user"></i> ۱ کاربر</span>
                            </div>
                        </div>
                    </div>
                    <div class="subscription-price">۹۱۱,۰۰۰ تومان</div>
                    <button class="btn btn-primary" onclick="orderSubscription(6, 'social')">
                        <i class="fas fa-shopping-cart"></i>
                        برای سفارش کلیک کنید
                    </button>
                </div>
            </div>
            
            <div class="tab-content" id="combo-tab">
                <!-- اشتراک 1 ماهه گیمینگ و اجتمائی -->
                <div class="subscription-option">
                    <div class="subscription-info">
                        <div class="subscription-icon combo1"><i class="fas fa-gamepad"></i> <i class="fas fa-users"></i></div>
                        <div class="subscription-details">
                            <div class="subscription-name">اشتراک 1 ماهه گیمینگ و اجتمائی</div>
                            <div class="subscription-features">
                                <span><i class="fas fa-infinity"></i> حجم نامحدود</span>
                                <span><i class="fas fa-bolt"></i> سرعت بالا</span>
                                <span><i class="fas fa-user"></i> 1 کاربر</span>
                            </div>
                        </div>
                    </div>
                    <div class="subscription-price">۳۵۰,۰۰۰ تومان</div>
                    <button class="btn btn-primary" onclick="orderSubscription(1, 'combo')">
                        <i class="fas fa-shopping-cart"></i>
                        برای سفارش کلیک کنید
                    </button>
                </div>
                
                <!-- اشتراک 2 ماهه گیمینگ و اجتمائی -->
                <div class="subscription-option">
                    <div class="subscription-info">
                        <div class="subscription-icon combo2"><i class="fas fa-gamepad"></i> <i class="fas fa-users"></i></div>
                        <div class="subscription-details">
                            <div class="subscription-name">اشتراک 2 ماهه گیمینگ و اجتمائی</div>
                            <div class="subscription-features">
                                <span><i class="fas fa-infinity"></i> حجم نامحدود</span>
                                <span><i class="fas fa-bolt"></i> سرعت بالا</span>
                                <span><i class="fas fa-user"></i> 1 کاربر</span>
                            </div>
                        </div>
                    </div>
                    <div class="subscription-price">۶۵۰,۰۰۰ تومان</div>
                    <button class="btn btn-primary" onclick="orderSubscription(2, 'combo')">
                        <i class="fas fa-shopping-cart"></i>
                        برای سفارش کلیک کنید
                    </button>
                </div>
                
                <!-- اشتراک 3 ماهه گیمینگ و اجتمائی -->
                <div class="subscription-option">
                    <div class="subscription-info">
                        <div class="subscription-icon combo3"><i class="fas fa-gamepad"></i> <i class="fas fa-users"></i></div>
                        <div class="subscription-details">
                            <div class="subscription-name">اشتراک 3 ماهه گیمینگ و اجتمائی</div>
                            <div class="subscription-features">
                                <span><i class="fas fa-infinity"></i> حجم نامحدود</span>
                                <span><i class="fas fa-bolt"></i> سرعت بالا</span>
                                <span><i class="fas fa-user"></i> 1 کاربر</span>
                            </div>
                        </div>
                    </div>
                    <div class="subscription-price">۹۵۰,۰۰۰ تومان</div>
                    <button class="btn btn-primary" onclick="orderSubscription(3, 'combo')">
                        <i class="fas fa-shopping-cart"></i>
                        برای سفارش کلیک کنید
                    </button>
                </div>
                
                <!-- اشتراک 4 ماهه گیمینگ و اجتمائی -->
                <div class="subscription-option">
                    <div class="subscription-info">
                        <div class="subscription-icon combo4"><i class="fas fa-gamepad"></i> <i class="fas fa-users"></i></div>
                        <div class="subscription-details">
                            <div class="subscription-name">اشتراک 4 ماهه گیمینگ و اجتمائی</div>
                            <div class="subscription-features">
                                <span><i class="fas fa-infinity"></i> حجم نامحدود</span>
                                <span><i class="fas fa-bolt"></i> سرعت بالا</span>
                                <span><i class="fas fa-user"></i> 1 کاربر</span>
                            </div>
                        </div>
                    </div>
                    <div class="subscription-price">۱,۲۵۰,۰۰۰ تومان</div>
                    <button class="btn btn-primary" onclick="orderSubscription(4, 'combo')">
                        <i class="fas fa-shopping-cart"></i>
                        برای سفارش کلیک کنید
                    </button>
                </div>
                
                <!-- اشتراک 5 ماهه گیمینگ و اجتمائی -->
                <div class="subscription-option">
                    <div class="subscription-info">
                        <div class="subscription-icon combo5"><i class="fas fa-gamepad"></i> <i class="fas fa-users"></i></div>
                        <div class="subscription-details">
                            <div class="subscription-name">اشتراک 5 ماهه گیمینگ و اجتمائی</div>
                            <div class="subscription-features">
                                <span><i class="fas fa-infinity"></i> حجم نامحدود</span>
                                <span><i class="fas fa-bolt"></i> سرعت بالا</span>
                                <span><i class="fas fa-user"></i> 1 کاربر</span>
                            </div>
                        </div>
                    </div>
                    <div class="subscription-price">۱,۵۵۰,۰۰۰ تومان</div>
                    <button class="btn btn-primary" onclick="orderSubscription(5, 'combo')">
                        <i class="fas fa-shopping-cart"></i>
                        برای سفارش کلیک کنید
                    </button>
                </div>
                
                <!-- اشتراک 6 ماهه گیمینگ و اجتمائی -->
                <div class="subscription-option">
                    <div class="subscription-info">
                        <div class="subscription-icon combo6"><i class="fas fa-gamepad"></i> <i class="fas fa-users"></i></div>
                        <div class="subscription-details">
                            <div class="subscription-name">اشتراک 6 ماهه گیمینگ و اجتمائی</div>
                            <div class="subscription-features">
                                <span><i class="fas fa-infinity"></i> حجم نامحدود</span>
                                <span><i class="fas fa-bolt"></i> سرعت بالا</span>
                                <span><i class="fas fa-user"></i> 1 کاربر</span>
                            </div>
                        </div>
                    </div>
                    <div class="subscription-price">۱,۸۵۰,۰۰۰ تومان</div>
                    <button class="btn btn-primary" onclick="orderSubscription(6, 'combo')">
                        <i class="fas fa-shopping-cart"></i>
                        برای سفارش کلیک کنید
                    </button>
                </div>
            </div>
            
            <div class="usage-guide">
                <h4><i class="fas fa-info-circle"></i> راهنمای استفاده از سرویس</h4>
                <ol>
                    <li>دریافت فایل از پشتیبانی فروش</li>
                    <li>وارد کردن در برنامه وایرگارد</li>
                    <li>اتصال سرویس و تمام</li>
                </ol>
            </div>
        </div>
    </div>
    
    <!-- راهنما -->
    <div class="modal-window help-window" id="helpWindow">
        <div class="modal-header">
            <div class="modal-title">راهنمای کامل سایت</div>
            <div class="close-btn" id="closeHelp">×</div>
        </div>
        <div class="modal-content">
            <div style="text-align: center; margin: 20px 0;">
                <div class="emoji-container" style="width: 100px; height: 100px; margin: 0 auto 20px;">
                    <i class="fas fa-question-circle" style="font-size: 40px;"></i>
                </div>
            </div>
            <div class="help-items">
                <div class="menu-item">
                    <h3 class="menu-item-title"><i class="fas fa-shopping-bag"></i> فروشگاه سرویس</h3>
                    <p class="menu-item-desc">در این بخش می‌توانید اشتراک‌های مختلف را مشاهده و خریداری کنید. دو نوع سرویس گیمینگ و اجتمائی موجود است که هر کدام ویژگی‌های خاص خود را دارند.</p>
                </div>
                <div class="menu-item">
                    <h3 class="menu-item-title"><i class="fas fa-download"></i> دانلود اپلیکیشن</h3>
                    <p class="menu-item-desc">در این بخش می‌توانید نسخه‌های رسمی اپلیکیشن را برای دستگاه‌های مختلف دانلود کنید. اپلیکیشن‌های ارائه شده کاملا بهینه شده هستند.</p>
                </div>
            </div>
        </div>
    </div>
    
    <!-- چالش و گیم -->
    <div class="modal-window challenge-window" id="challengeWindow">
        <div class="modal-header">
            <div class="modal-title">چالش و گیم</div>
            <div class="close-btn" id="closeChallenge">×</div>
        </div>
        <div class="modal-content" style="display: flex; flex-direction: column; justify-content: center; align-items: center; text-align: center; padding: 40px;">
            <div class="emoji-container" style="width: 100px; height: 100px; background: var(--gradient-primary); margin-bottom: 20px;">
                <i class="fas fa-gamepad" style="font-size: 40px; color: white;"></i>
            </div>
            <h3 style="margin-bottom: 10px;">با شرکت در چالش‌ها سرویس رایگان ببر</h3>
            <p style="color: var(--text-light); margin-bottom: 30px;">در چالش‌های ما شرکت کنید و شانس برنده شدن سرویس رایگان را داشته باشید</p>
            <button class="btn btn-primary" onclick="showComingSoonNotification()">
                <i class="fas fa-play"></i>
                شروع چالش
            </button>
        </div>
    </div>
    
    <!-- بکاپ -->
    <div class="modal-window backup-window" id="backupWindow">
        <div class="modal-header">
            <div class="modal-title">مدیریت بکاپ تونل‌ها</div>
            <div class="close-btn" id="closeBackup">×</div>
        </div>
        <div class="modal-content" style="display: flex; flex-direction: column; justify-content: center; gap: 20px; padding: 20px;">
            <button class="btn btn-primary btn-large" id="exportBackup">
                <i class="fas fa-file-export"></i>
                گرفتن بکاپ از تونل‌ها
            </button>
            <button class="btn btn-secondary btn-large" id="importBackup">
                <i class="fas fa-file-import"></i>
                بازیابی تونل‌ها از فایل
            </button>
            <input type="file" id="backupFileInput" accept=".json" style="display: none;">
        </div>
    </div>
    
    <!-- دانلود وایرگارد -->
    <div class="modal-window wireguard-window" id="wireguardWindow">
        <div class="modal-header">
            <div class="modal-title">دانلود اپلیکیشن رسمی</div>
            <div class="close-btn" id="closeWireguard">×</div>
        </div>
        <div class="modal-content">
            <div class="download-buttons">
                <button class="btn btn-primary btn-large" onclick="downloadWireguard('windows')">
                    <i class="fab fa-windows"></i>
                    دانلود برای ویندوز
                </button>
                <button class="btn btn-primary btn-large" onclick="downloadWireguard('mac')">
                    <i class="fab fa-apple"></i>
                    دانلود برای مک
                </button>
                <button class="btn btn-primary btn-large" onclick="downloadWireguard('ios')">
                    <i class="fab fa-apple"></i>
                    دانلود برای iOS
                </button>
                <button class="btn btn-primary btn-large" onclick="downloadWireguard('android')">
                    <i class="fab fa-android"></i>
                    دانلود برای اندروید
                </button>
            </div>
            <div class="usage-guide">
                <h4>راهنمای نصب:</h4>
                <ol>
                    <li>فایل مربوط به سیستم عامل خود را دانلود کنید</li>
                    <li>برنامه را نصب و اجرا کنید</li>
                    <li>فایل پیکربندی را وارد برنامه کنید</li>
                    <li>اتصال را فعال کنید</li>
                </ol>
            </div>
        </div>
    </div>
    
    <!-- پنجره تایید -->
    <div class="modal-window confirm-window" id="confirmWindow">
        <div class="modal-title">تایید عملیات</div>
        <div class="menu-item-desc" style="margin: 15px 0 25px; text-align: center;">آیا از انجام این عملیات مطمئن هستید؟ این عمل غیرقابل بازگشت است.</div>
        <div style="display: flex; justify-content: center; gap: 15px;">
            <button class="btn btn-primary" id="confirmYes" style="flex: 1; max-width: 120px;">تایید</button>
            <button class="btn" id="confirmNo" style="flex: 1; max-width: 120px; background: var(--bg-color); border: 1px solid var(--border-color);">انصراف</button>
        </div>
    </div>
    
    <!-- نوتیفیکیشن -->
    <div class="notification" id="notification">
        <div class="notification-icon" id="notificationIcon"></div>
        <div class="notification-message" id="notificationMessage"></div>
    </div>
    
    <!-- overlay -->
    <div class="overlay" id="overlay"></div>
    
    <script>
        // مدیریت حالت‌های برنامه
        const state = {
            darkMode: localStorage.getItem('darkMode') === 'true',
            activityLogs: JSON.parse(localStorage.getItem('activityLogs')) || [
                {
                    title: 'ورود به سیستم',
                    date: getFormattedTime(),
                    desc: 'شما با موفقیت وارد حساب کاربری خود شدید.'
                }
            ],
            lastDayChecked: new Date().getDate(),
            currentMessageIndex: 0,
            typingInterval: null
        };

        // عناصر DOM
        const elements = {
            loadingScreen: document.getElementById('loadingScreen'),
            loadingBar: document.getElementById('loadingBar'),
            mainContent: document.getElementById('mainContent'),
            mainMenuBtn: document.getElementById('mainMenuBtn'),
            quickMenuBtn: document.getElementById('quickMenuBtn'),
            mainMenu: document.getElementById('mainMenu'),
            quickMenu: document.getElementById('quickMenu'),
            shopWindow: document.getElementById('shopWindow'),
            helpWindow: document.getElementById('helpWindow'),
            challengeWindow: document.getElementById('challengeWindow'),
            backupWindow: document.getElementById('backupWindow'),
            wireguardWindow: document.getElementById('wireguardWindow'),
            confirmWindow: document.getElementById('confirmWindow'),
            settingsPanel: document.getElementById('settingsPanel'),
            notification: document.getElementById('notification'),
            overlay: document.getElementById('overlay'),
            todayDate: document.getElementById('todayDate'),
            themeToggle: document.getElementById('themeToggle'),
            exportBackup: document.getElementById('exportBackup'),
            importBackup: document.getElementById('importBackup'),
            backupFileInput: document.getElementById('backupFileInput')
        };

        // رویدادهای کلیک
        const setupEventListeners = () => {
            // منوها و پنجره‌ها
            elements.mainMenuBtn.addEventListener('click', () => toggleModal(elements.mainMenu));
            elements.quickMenuBtn.addEventListener('click', () => toggleModal(elements.quickMenu));
            elements.overlay.addEventListener('click', closeAllModals);
            
            // آیتم‌های منو
            document.getElementById('helpBtn').addEventListener('click', () => toggleModal(elements.helpWindow));
            document.getElementById('challengeItem').addEventListener('click', () => toggleModal(elements.challengeWindow));
            document.getElementById('backupItem').addEventListener('click', () => toggleModal(elements.backupWindow));
            document.getElementById('themeItem').addEventListener('click', () => toggleModal(elements.settingsPanel));
            document.getElementById('quickShopItem').addEventListener('click', () => toggleModal(elements.shopWindow));
            document.getElementById('quickWireguardItem').addEventListener('click', () => toggleModal(elements.wireguardWindow));
            
            // دکمه‌های بستن
            document.querySelectorAll('.close-btn').forEach(btn => {
                btn.addEventListener('click', closeAllModals);
            });
            
            // تب‌ها
            document.querySelectorAll('.tab').forEach(tab => {
                tab.addEventListener('click', () => {
                    const tabId = tab.dataset.tab;
                    const tabType = tab.closest('.tabs').parentElement.id.includes('shop') ? 'shop' : 'wireguard';
                    changeTab(tabId, tabType);
                });
            });
            
            // مدیریت حالت شب/روز
            elements.themeToggle.addEventListener('change', toggleDarkMode);
            
            // مدیریت بکاپ
            elements.exportBackup.addEventListener('click', exportBackupData);
            elements.importBackup.addEventListener('click', () => elements.backupFileInput.click());
            elements.backupFileInput.addEventListener('change', (e) => {
                if (e.target.files.length > 0) {
                    importBackupData(e.target.files[0]);
                }
            });
            
            // بستن با کلید ESC
            document.addEventListener('keydown', (e) => {
                if (e.key === 'Escape') {
                    closeAllModals();
                }
            });
        };

        // توابع کمکی
        function getFormattedTime() {
            const now = new Date();
            const hours = now.getHours();
            const minutes = now.getMinutes();
            return `امروز - ${hours}:${minutes < 10 ? '0' + minutes : minutes}`;
        }

        function getMonthName(monthIndex) {
            const months = [
                'فروردین', 'اردیبهشت', 'خرداد', 'تیر', 'مرداد', 'شهریور',
                'مهر', 'آبان', 'آذر', 'دی', 'بهمن', 'اسفند'
            ];
            return months[monthIndex];
        }

        // مدیریت پنجره‌ها
        function toggleModal(modal) {
            if (modal.classList.contains('open')) {
                modal.classList.remove('open');
                elements.overlay.classList.remove('open');
                document.body.style.overflow = 'auto';
            } else {
                closeAllModals();
                modal.classList.add('open');
                elements.overlay.classList.add('open');
                document.body.style.overflow = 'hidden';
            }
        }

        function closeAllModals() {
            document.querySelectorAll('.modal-window').forEach(modal => {
                modal.classList.remove('open');
            });
            elements.overlay.classList.remove('open');
            document.body.style.overflow = 'auto';
        }

        // تغییر تب‌ها
        function changeTab(tabId, tabType) {
            const prefix = tabType === 'shop' ? 'shop' : 'wireguard';
            
            // غیرفعال کردن همه تب‌های مربوطه
            document.querySelectorAll(`.${prefix}-menu .tab`).forEach(tab => {
                tab.classList.remove('active');
            });
            
            document.querySelectorAll(`.${prefix}-menu .tab-content`).forEach(content => {
                content.classList.remove('active');
            });
            
            // فعال کردن تب انتخاب شده
            document.querySelector(`.${prefix}-menu .tab[data-tab="${tabId}"]`).classList.add('active');
            document.getElementById(`${tabId}-tab`).classList.add('active');
            
            addActivityLog(
                `تغییر تب ${tabType === 'shop' ? 'فروشگاه' : 'دانلود'}`,
                `تب ${tabId === 'gaming' ? 'گیمینگ' : tabId === 'social' ? 'اجتمائی' : 'ترکیبی'} انتخاب شد`
            );
        }

        // مدیریت حالت شب/روز
        function toggleDarkMode() {
            state.darkMode = !state.darkMode;
            applyTheme();
            
            showNotification(
                `حالت ${state.darkMode ? 'شب' : 'روز'} فعال شد`,
                'info'
            );
        }

        function applyTheme() {
            if (state.darkMode) {
                document.body.classList.add('dark-mode');
                elements.themeToggle.checked = true;
            } else {
                document.body.classList.remove('dark-mode');
                elements.themeToggle.checked = false;
            }
            localStorage.setItem('darkMode', state.darkMode);
            
            addActivityLog(
                'تغییر حالت نمایش',
                state.darkMode ? 'حالت شب فعال شد' : 'حالت روز فعال شد'
            );
        }

        // نمایش نوتیفیکیشن
        function showNotification(message, type) {
            elements.notification.className = 'notification';
            document.getElementById('notificationIcon').className = 'notification-icon';
            
            document.getElementById('notificationMessage').textContent = message;
            
            if (type === 'success') {
                document.getElementById('notificationIcon').classList.add('notification-success');
                document.getElementById('notificationIcon').innerHTML = '<i class="fas fa-check-circle"></i>';
            } else if (type === 'info') {
                document.getElementById('notificationIcon').classList.add('notification-info');
                document.getElementById('notificationIcon').innerHTML = '<i class="fas fa-info-circle"></i>';
            } else if (type === 'error') {
                document.getElementById('notificationIcon').classList.add('notification-error');
                document.getElementById('notificationIcon').innerHTML = '<i class="fas fa-exclamation-circle"></i>';
            }
            
            elements.notification.classList.add('show');
            
            setTimeout(() => {
                elements.notification.classList.remove('show');
            }, 3000);
        }

        // نمایش نوتیفیکیشن نسخه بعدی
        function showComingSoonNotification() {
            closeAllModals();
            showNotification(
                'در نسخه بعدی اضافه خواهد شد',
                'info'
            );
        }

        // مدیریت گزارش فعالیت
        function addActivityLog(title, desc) {
            state.activityLogs.unshift({
                title: title,
                date: getFormattedTime(),
                desc: desc
            });
            
            if (state.activityLogs.length > 50) {
                state.activityLogs = state.activityLogs.slice(0, 50);
            }
            
            saveActivityLogs();
        }

        function saveActivityLogs() {
            localStorage.setItem('activityLogs', JSON.stringify(state.activityLogs));
        }

        // مدیریت بکاپ
        function exportBackupData() {
            const backupData = {
                timestamp: new Date().toISOString(),
                version: '1.0',
                tunnels: []
            };
            
            const dataStr = JSON.stringify(backupData, null, 2);
            const dataUri = 'data:application/json;charset=utf-8,'+ encodeURIComponent(dataStr);
            
            const exportFileName = `xserv-backup-${new Date().toISOString().slice(0,10)}.json`;
            
            const link = document.createElement('a');
            link.setAttribute('href', dataUri);
            link.setAttribute('download', exportFileName);
            document.body.appendChild(link);
            link.click();
            document.body.removeChild(link);
            
            closeAllModals();
            
            addActivityLog(
                'تهیه بکاپ',
                'بکاپ از تونل‌ها با موفقیت تهیه شد'
            );
            
            showNotification(
                'بکاپ از تونل‌ها با موفقیت دانلود شد',
                'success'
            );
        }

        function importBackupData(file) {
            const reader = new FileReader();
            
            reader.onload = function(e) {
                try {
                    const backupData = JSON.parse(e.target.result);
                    console.log('Backup data loaded:', backupData);
                    
                    closeAllModals();
                    
                    addActivityLog(
                        'بازیابی بکاپ',
                        'فایل بکاپ با موفقیت بارگذاری شد'
                    );
                    
                    showNotification(
                        'فایل بکاپ با موفقیت بارگذاری شد',
                        'success'
                    );
                } catch (error) {
                    console.error('Error parsing backup file:', error);
                    showNotification(
                        'خطا در پردازش فایل بکاپ',
                        'error'
                    );
                }
            };
            
            reader.onerror = function() {
                showNotification(
                    'خطا در خواندن فایل بکاپ',
                    'error'
                );
            };
            
            reader.readAsText(file);
        }

        // سفارش اشتراک
        function orderSubscription(months, type = 'gaming') {
            let price;
            let typeName;
            
            if (type === 'gaming') {
                price = getGamingSubscriptionPrice(months);
                typeName = 'گیمینگ';
            } else if (type === 'social') {
                price = getSocialSubscriptionPrice(months);
                typeName = 'اجتمائی';
            } else if (type === 'combo') {
                price = getComboSubscriptionPrice(months);
                typeName = 'گیمینگ و اجتمائی';
            }
            
            const message = `درود آقای ایکسرو!\n\nپروتکل سرویس: ${typeName}\nحجم سرویس: ${months === 1 && type === 'gaming' ? '50 گیگ' : type === 'social' && months === 1 ? '50 گیگ' : 'نامحدود'}\nتعداد کاربر سرویس: 1\nانقضا سرویس: ${months} ماه\n\nقیمت نهایی: ${price} تومان\n\nاطلاعات لازم همراه شماره کارت برای بنده ارسال کنید ، باتشکر`;
            
            window.open(`https://t.me/u0v0n?text=${encodeURIComponent(message)}`, '_blank');
            closeAllModals();
            
            addActivityLog(
                'درخواست اشتراک',
                `درخواست اشتراک ${months} ماهه ${typeName} ارسال شد`
            );
            
            showNotification(
                `درخواست اشتراک ${months} ماهه با موفقیت ارسال شد`,
                'success'
            );
        }

        function getGamingSubscriptionPrice(months) {
            const prices = {
                1: '۹۹,۰۰۰',
                2: '۲۸۹,۰۰۰',
                3: '۴۵۹,۰۰۰',
                4: '۶۱۹,۰۰۰',
                5: '۷۷۹,۰۰۰',
                6: '۹۳۹,۰۰۰'
            };
            
            return prices[months] || 'نامشخص';
        }

        function getSocialSubscriptionPrice(months) {
            const prices = {
                1: '۸۹,۰۰۰',
                2: '۱۸۹,۰۰۰',
                3: '۲۷۹,۰۰۰',
                4: '۳۶۹,۰۰۰',
                5: '۴۵۹,۰۰۰',
                6: '۵۴۹,۰۰۰'
            };
            
            return prices[months] || 'نامشخص';
        }
        
        function getComboSubscriptionPrice(months) {
            const prices = {
                1: '۳۵۰,۰۰۰',
                2: '۶۵۰,۰۰۰',
                3: '۹۵۰,۰۰۰',
                4: '۱,۲۵۰,۰۰۰',
                5: '۱,۵۵۰,۰۰۰',
                6: '۱,۸۵۰,۰۰۰'
            };
            
            return prices[months] || 'نامشخص';
        }

        // دانلود وایرگارد
        function downloadWireguard(platform) {
            let downloadUrl = '';
            let fileName = '';
            
            switch (platform) {
                case 'windows':
                    downloadUrl = 'https://download.wireguard.com/windows-client/wireguard-installer.exe';
                    fileName = 'wireguard-windows-installer.exe';
                    break;
                case 'mac':
                    downloadUrl = 'https://download.wireguard.com/macos-client/WireGuard.dmg';
                    fileName = 'wireguard-macos.dmg';
                    break;
                case 'ios':
                    downloadUrl = 'https://apps.apple.com/us/app/wireguard/id41195209';
                    break;
                case 'android':
                    downloadUrl = 'https://play.google.com/store/apps/details?id=com.wireguard.android';
                    break;
                default:
                    showNotification('پلتفرم انتخاب شده نامعتبر است', 'error');
                    return;
            }
            
            if (platform === 'ios' || platform === 'android') {
                window.open(downloadUrl, '_blank');
            } else {
                const link = document.createElement('a');
                link.href = downloadUrl;
                link.download = fileName;
                document.body.appendChild(link);
                link.click();
                document.body.removeChild(link);
            }
            
            closeAllModals();
            
            addActivityLog(
                'درخواست دانلود',
                `دانلود کلاینت برای ${platform} آغاز شد`
            );
            
            showNotification(
                `دانلود برای ${platform} با موفقیت آغاز شد`,
                'success'
            );
        }

        // انیمیشن تایپ متن
        function startTypingAnimation() {
            const messages = [
                "درحال انجام سفارشات هستیم...",
                "آقای ایکسرو با نسخه جدید برگشت!",
                "سرویس گیمینگ برای گیمر ها اضافه شده :)",
                "پشتیبانی آنلاین 24 ساعته در دسترس است",
                "سرورهای جدید در اروپا و آمریکا اضافه شد"
            ];
            
            let currentCharIndex = 0;
            let isDeleting = false;
            let waitBeforeNextMessage = false;
            
            function typeWriter() {
                const currentMessage = messages[state.currentMessageIndex];
                
                if (isDeleting) {
                    elements.todayDate.textContent = currentMessage.substring(0, currentCharIndex - 1);
                    currentCharIndex--;
                    
                    if (currentCharIndex === 0) {
                        isDeleting = false;
                        state.currentMessageIndex = (state.currentMessageIndex + 1) % messages.length;
                        waitBeforeNextMessage = true;
                        setTimeout(() => {
                            waitBeforeNextMessage = false;
                        }, 1000);
                    }
                } else if (waitBeforeNextMessage) {
                    return;
                } else {
                    elements.todayDate.textContent = currentMessage.substring(0, currentCharIndex + 1);
                    currentCharIndex++;
                    
                    if (currentCharIndex === currentMessage.length) {
                        setTimeout(() => {
                            isDeleting = true;
                        }, 2000);
                    }
                }
                
                const typingSpeed = isDeleting ? 50 : 100;
                setTimeout(typeWriter, typingSpeed);
            }
            
            typeWriter();
        }

        // نمایش تاریخ امروز
        function showTodayDate() {
            const days = ['یکشنبه', 'دوشنبه', 'سه شنبه', 'چهارشنبه', 'پنجشنبه', 'جمعه', 'شنبه'];
            const today = new Date();
            const dayName = days[today.getDay()];
            const dateStr = `${dayName}، ${today.getDate()} ${getMonthName(today.getMonth())} ${today.getFullYear()}`;
            
            startTypingAnimation();
        }

        // بررسی تغییر روز برای ریست گزارشات
        function checkForDayChange() {
            const now = new Date();
            const currentDay = now.getDate();
            
            if (currentDay !== state.lastDayChecked) {
                state.lastDayChecked = currentDay;
                state.activityLogs = [];
                saveActivityLogs();
                
                addActivityLog(
                    'شروع روز جدید',
                    'گزارشات روز قبل پاک شد و روز جدید شروع شد.'
                );
            }
        }

        // صفحه لودینگ
        function showLoadingScreen() {
            let progress = 0;
            const duration = 4000; // 4 ثانیه
            const interval = 50; // هر 50 میلی‌ثانیه
            const increment = (interval / duration) * 100;
            
            const loadingInterval = setInterval(() => {
                progress += increment;
                elements.loadingBar.style.width = `${Math.min(progress, 100)}%`;
                
                if (progress >= 100) {
                    clearInterval(loadingInterval);
                    setTimeout(() => {
                        elements.loadingScreen.style.opacity = '0';
                        setTimeout(() => {
                            elements.loadingScreen.style.display = 'none';
                            elements.mainContent.classList.add('show');
                        }, 500);
                    }, 300);
                }
            }, interval);
        }

        // مقداردهی اولیه
        function init() {
            showLoadingScreen();
            setupEventListeners();
            showTodayDate();
            applyTheme();
            
            // بررسی تغییر روز هر دقیقه
            setInterval(checkForDayChange, 60000);
            checkForDayChange();
        }

        // اجرای برنامه
        document.addEventListener('DOMContentLoaded', init);
    </script>
</body>
</html>
