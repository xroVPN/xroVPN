<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no">
    <title>فروشگاه VPN - ایکسرو</title>
    <style>
        :root {
            --primary-color: #81D4FA;
            --primary-dark: #0288D1;
            --primary-light: #4FC3F7;
            --red-color: #F44336;
            --orange-color: #FF9800;
            --yellow-color: #FFEB3B;
            --purple-color: #AB47BC;
            --green-color: #4CAF50;
            --wireguard-color: #881337;
            --text-color: #E1F5FE;
            --text-light: #FFF59D;
            --bg-color: #0A1A2F;
            --card-bg: #1E2A44;
            --card-hover: #2A3B5B;
            --border-color: rgba(129, 212, 250, 0.3);
            --shadow-color: rgba(2, 136, 209, 0.4);
            --glass-effect: linear-gradient(135deg, rgba(129, 212, 250, 0.2), rgba(171, 71, 188, 0.2));
            --glass-border: 1px solid rgba(129, 212, 250, 0.15);
            --glass-shadow: 0 8px 24px rgba(2, 136, 209, 0.3);
            --transition: all .3s cubic-bezier(.4, 0, .2, 1);
            --bg-image: url('https://biaupload.com/do.php?imgf=org-adcb3c9c5c972.png');
            --overlay-image: url('https://biaupload.com/do.php?imgf=org-ee8b030e7b561.png');
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            -webkit-tap-highlight-color: transparent;
        }

        body {
            font-family: 'Vazirmatn', 'Segoe UI', sans-serif;
            background: var(--bg-color);
            color: var(--text-color);
            height: 100vh;
            overflow: hidden;
            user-select: none;
            touch-action: manipulation;
            position: relative;
        }

        .permanent-window {
            position: fixed;
            inset: 0;
            z-index: 10;
            background: var(--bg-image) center/cover fixed, var(--glass-effect);
            background-blend-mode: overlay;
            backdrop-filter: blur(15px);
            border: var(--glass-border);
            box-shadow: var(--glass-shadow);
            display: flex;
            flex-direction: column;
            overflow: hidden;
        }

        .permanent-window::after {
            content: '';
            position: absolute;
            inset: 0;
            background: var(--overlay-image) center/cover no-repeat;
            opacity: 0;
            animation: fadeInOut 5s ease-in-out infinite;
            z-index: -1;
        }

        @keyframes fadeInOut {
            0%, 100% { opacity: 0; }
            50% { opacity: 0.4; }
        }

        .top-bar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 16px 20px;
            background: var(--glass-effect);
            border-bottom: var(--glass-border);
            box-shadow: var(--glass-shadow);
            backdrop-filter: blur(12px);
            z-index: 100;
        }

        .logo {
            font-size: 1.2rem;
            font-weight: 700;
            padding: 10px 15px;
            border-radius: 10px;
            cursor: pointer;
            background: rgba(129, 212, 250, 0.15);
            display: flex;
            align-items: center;
            gap: 10px;
            transition: var(--transition);
            border: 1px solid var(--border-color);
        }

        .logo:hover {
            background: rgba(129, 212, 250, 0.25);
            transform: translateY(-2px);
            box-shadow: 0 5px 15px var(--shadow-color);
        }

        .menu-btn {
            width: 40px;
            height: 40px;
            display: flex;
            flex-direction: column;
            justify-content: space-around;
            align-items: center;
            padding: 8px;
            border-radius: 10px;
            transition: var(--transition);
            background: rgba(129, 212, 250, 0.1);
            border: 1px solid var(--border-color);
            cursor: pointer;
        }

        .menu-btn:hover {
            background: rgba(129, 212, 250, 0.2);
            transform: rotate(90deg);
        }

        .menu-line {
            width: 100%;
            height: 3px;
            background: var(--text-color);
            border-radius: 2px;
            transition: var(--transition);
        }

        .menu-btn:hover .menu-line {
            background: var(--primary-color);
        }

        .content {
            height: calc(100vh - 70px);
            display: flex;
            flex-direction: column;
            padding: 20px;
            overflow: hidden;
        }

        .welcome-container {
            flex: 1;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            margin-top: -20px;
        }

        .news-container {
            width: 100%;
            max-width: 400px;
            margin: 0 auto;
            padding: 15px;
            border-radius: 16px;
            text-align: center;
            background: transparent;
        }

        .news-content {
            color: var(--text-light);
            font-size: 0.9rem;
            text-align: right;
        }

        .info-box {
            background: transparent;
            border-radius: 12px;
            padding: 12px;
            margin-bottom: 10px;
            display: flex;
            align-items: center;
            gap: 10px;
            opacity: 0;
            border: 1px solid var(--primary-color);
        }

        .info-box:nth-child(1) {
            animation: slideInLeft 0.5s ease-out 0.2s forwards;
        }

        .info-box:nth-child(2) {
            animation: slideInRight 0.5s ease-out 0.4s forwards;
        }

        .info-box:nth-child(3) {
            animation: slideInLeft 0.5s ease-out 0.6s forwards;
        }

        @keyframes slideInRight {
            from { opacity: 0; transform: translateX(50px); }
            to { opacity: 1; transform: translateX(0); }
        }

        @keyframes slideInLeft {
            from { opacity: 0; transform: translateX(-50px); }
            to { opacity: 1; transform: translateX(0); }
        }

        .info-icon {
            font-size: 1.3rem;
            color: var(--primary-color);
            min-width: 30px;
            display: flex;
            justify-content: center;
        }

        .info-text {
            font-weight: 500;
            min-width: 60px;
            color: var(--yellow-color);
        }

        .info-value {
            font-weight: 500;
            min-width: 60px;
            flex: 1;
            text-align: left;
            direction: ltr;
            background: linear-gradient(45deg, var(--red-color), var(--orange-color), var(--yellow-color), var(--purple-color), var(--primary-color));
            background-size: 400%;
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            animation: gradientAnimation 5s ease infinite;
        }

        @keyframes gradientAnimation {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .floating-btn {
            position: fixed;
            bottom: 30px;
            left: 20px;
            width: 70px;
            height: 70px;
            background: linear-gradient(135deg, var(--primary-light), var(--primary-dark));
            border-radius: 16px;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 26px;
            color: var(--text-color);
            box-shadow: 0 8px 24px var(--shadow-color);
            cursor: pointer;
            border: none;
            transition: var(--transition);
            z-index: 100;
        }

        .floating-btn:hover {
            transform: translateY(-4px) scale(1.05);
            box-shadow: 0 12px 32px var(--shadow-color);
        }

        .modal-window {
            position: fixed;
            background: var(--glass-effect);
            z-index: 1000;
            transition: var(--transition);
            box-shadow: var(--glass-shadow);
            border: var(--glass-border);
            backdrop-filter: blur(15px);
            border-radius: 16px;
            display: flex;
            flex-direction: column;
        }

        .main-menu, .settings-panel, .about-panel, .report-problem-menu {
            top: -100%;
            right: 0;
            width: 100%;
            max-height: 65%;
            border-radius: 0 0 16px 16px;
        }

        .main-menu.open, .settings-panel.open, .about-panel.open, .report-problem-menu.open {
            top: 0;
        }

        .public-shop-menu {
            bottom: -100%;
            left: 0;
            width: 100%;
            max-height: 80%;
            border-radius: 16px 16px 0 0;
        }

        .public-shop-menu.open {
            bottom: 0;
        }

        .modal-overlay {
            position: fixed;
            inset: 0;
            background: rgba(10, 26, 47, 0.5);
            z-index: 999;
            display: none;
            transition: opacity .3s ease;
        }

        .modal-overlay.show {
            display: block;
            opacity: 1;
        }

        .modal-overlay.hidden {
            opacity: 0;
        }

        .loading-window {
            position: fixed;
            inset: 0;
            background: url('https://biaupload.com/do.php?imgf=org-08678b2cf3b81.png') center/cover;
            z-index: 2000;
            display: flex;
            flex-direction: column;
            justify-content: flex-end;
            align-items: center;
        }

        .loading-window::after {
            content: '';
            position: absolute;
            inset: 0;
            background: url('https://biaupload.com/do.php?imgf=org-380b798a2fcd2.png') center/cover;
            opacity: 0;
            animation: fadeInOut 3s ease-in-out infinite;
        }

        .loading-window.hidden {
            display: none;
            opacity: 0;
        }

        .loading-content {
            position: absolute;
            bottom: 40px;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 10px;
        }

        .loading-messages {
            width: 100%;
            height: 30px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
            color: var(--text-color);
            white-space: nowrap;
        }

        .loading-messages span {
            position: static;
            opacity: 1;
        }

        .loading-spinner {
            width: 48px;
            height: 48px;
            background: url('https://biaupload.com/do.php?imgf=org-0e160aa5093e1.png') center/cover;
            border-radius: 50%;
            position: relative;
        }

        .loading-frame {
            width: 60px;
            height: 60px;
            background: url('https://biaupload.com/do.php?imgf=org-14607935dcc21.png') center/contain no-repeat;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            z-index: 1;
        }

        .loading-footer {
            font-size: 1.2rem;
            color: var(--yellow-color);
        }

        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 16px 18px 12px;
            border-bottom: var(--glass-border);
        }

        .modal-title-container {
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .modal-title {
            font-weight: 700;
            font-size: 1.2rem;
            color: var(--text-color);
        }

        .modal-title-img {
            width: 27px;
            height: 27px;
            cursor: pointer;
        }

        .home-btn {
            cursor: pointer;
            width: 38px;
            height: 38px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            transition: var(--transition);
        }

        .home-btn:hover {
            background: rgba(129, 212, 250, 0.15);
        }

        .home-btn img {
            width: 24px;
            height: 24px;
            transition: var(--transition);
        }

        .home-btn:hover img {
            transform: scale(1.15);
        }

        .modal-content {
            flex: 1;
            overflow-y: auto;
            padding: 15px;
        }

        .menu-item {
            padding: 16px;
            margin-bottom: 12px;
            background: var(--card-bg);
            border-radius: 14px;
            cursor: pointer;
            transition: var(--transition);
            border: var(--glass-border);
            box-shadow: var(--glass-shadow);
        }

        .menu-item:hover {
            transform: translateY(-3px);
            background: var(--card-hover);
            border-color: var(--primary-light);
            box-shadow: 0 10px 20px var(--shadow-color);
        }

        .menu-item-title {
            font-weight: 700;
            font-size: 1.1rem;
            display: flex;
            align-items: center;
            gap: 10px;
            color: var(--text-color);
        }

        .menu-item-title i {
            color: var(--primary-color);
            font-size: 1.3rem;
        }

        .menu-item-desc {
            font-size: 0.9rem;
            color: var(--text-light);
            line-height: 1.6;
        }

        .notification {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: var(--card-bg);
            border-radius: 12px;
            padding: 12px;
            box-shadow: 0 6px 18px var(--shadow-color);
            z-index: 1100;
            transform: translateY(100px);
            opacity: 0;
            transition: var(--transition);
            display: flex;
            align-items: center;
            gap: 10px;
            border: var(--glass-border);
            max-width: 280px;
            backdrop-filter: blur(10px);
        }

        .notification.show {
            transform: translateY(0);
            opacity: 1;
        }

        .notification-icon {
            font-size: 1.3rem;
            width: 34px;
            height: 34px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
        }

        .notification-success {
            background: rgba(171, 71, 188, 0.15);
            color: var(--purple-color);
            border: 1px solid rgba(171, 71, 188, 0.3);
        }

        .notification-info {
            background: rgba(129, 212, 250, 0.15);
            color: var(--primary-color);
            border: 1px solid var(--border-color);
        }

        .notification-error {
            background: rgba(244, 67, 54, 0.15);
            color: var(--red-color);
            border: 1px solid rgba(244, 67, 54, 0.3);
        }

        .notification-message {
            font-size: 0.85rem;
            font-weight: 500;
            flex: 1;
            color: var(--text-color);
        }

        .configs-container {
            display: flex;
            gap: 12px;
            overflow-x: auto;
            padding: 15px;
            direction: rtl;
            scrollbar-width: none;
        }

        .configs-container::-webkit-scrollbar {
            display: none;
        }

        .config-box {
            background: transparent;
            padding: 14px;
            width: 170px;
            height: 190px;
            transition: var(--transition);
            cursor: pointer;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: space-between;
            text-align: center;
            flex-shrink: 0;
            border-radius: 12px;
            border: 2px solid transparent;
            opacity: 0;
        }

        .config-box:hover {
            transform: translateY(-4px);
            box-shadow: 0 6px 16px var(--shadow-color);
        }

        .config-box[data-protocol="hysteria2"] {
            border-color: var(--green-color);
        }

        .config-box[data-protocol="vless"] {
            border-color: #2196F3;
        }

        .config-box[data-protocol="trojan"] {
            border-color: var(--purple-color);
        }

        .config-box[data-protocol="ss"] {
            border-color: var(--orange-color);
        }

        .config-box[data-protocol="vmess"] {
            border-color: var(--yellow-color);
        }

        .config-box[data-protocol="wireguard"] {
            border-color: var(--wireguard-color);
        }

        .config-box::after {
            content: attr(data-protocol);
            position: absolute;
            top: -10px;
            left: 50%;
            transform: translateX(-50%);
            background: var(--card-bg);
            color: var(--text-light);
            font-size: 0.8rem;
            padding: 4px 8px;
            border-radius: 8px;
            opacity: 0;
            transition: var(--transition);
            pointer-events: none;
        }

        .config-box:hover::after {
            opacity: 1;
        }

        .config-logo-container {
            position: relative;
            width: 70px;
            height: 70px;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .config-logo {
            width: 60px;
            height: 60px;
            margin-bottom: 10px;
            transition: var(--transition);
            z-index: 2;
        }

        .config-box:hover .config-logo {
            transform: scale(1.1);
        }

        .ping-result {
            font-size: 0.95rem;
            display: flex;
            align-items: center;
            gap: 6px;
            width: 100%;
            justify-content: center;
            font-weight: 600;
            direction: rtl;
        }

        .ping-result.fast {
            color: var(--purple-color);
        }

        .ping-result.medium {
            color: var(--orange-color);
        }

        .ping-result.slow {
            color: var(--red-color);
        }

        .error {
            background: rgba(244, 67, 54, 0.15);
            color: var(--red-color);
            border: 1px solid rgba(244, 67, 54, 0.3);
            border-radius: 12px;
            padding: 14px;
            margin: 15px 0;
            font-size: 0.9rem;
            text-align: center;
        }

        .loading-container {
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 20px 0;
            direction: rtl;
        }

        .loading-dots {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 8px;
        }

        .loading-dot {
            width: 10px;
            height: 10px;
            background: var(--primary-color);
            border-radius: 50%;
            animation: bounce 1.2s ease-in-out infinite;
        }

        .loading-dot:nth-child(2) {
            animation-delay: 0.2s;
        }

        .loading-dot:nth-child(3) {
            animation-delay: 0.4s;
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); opacity: 0.6; }
            50% { transform: translateY(-10px); opacity: 1; }
        }

        .copy-btn {
            padding: 10px;
            border-radius: 10px;
            background: var(--yellow-color);
            color: var(--bg-color);
            font-size: 0.9rem;
            font-weight: 600;
            cursor: pointer;
            border: none;
            transition: var(--transition);
            display: flex;
            align-items: center;
            gap: 6px;
            justify-content: center;
            width: 100%;
            box-shadow: 0 4px 12px rgba(255, 235, 59, 0.3);
        }

        .copy-btn:hover {
            background: #FBC02D;
            transform: translateY(-2px);
            box-shadow: 0 6px 16px rgba(255, 235, 59, 0.4);
        }

        .filter-container {
            display: flex;
            gap: 10px;
            margin-bottom: 15px;
            overflow-x: auto;
            padding: 10px;
            scrollbar-width: none;
            direction: rtl;
        }

        .filter-container::-webkit-scrollbar {
            display: none;
        }

        .filter-btn {
            padding: 8px 16px;
            border-radius: 10px;
            background: rgba(129, 212, 250, 0.1);
            color: var(--text-light);
            font-size: 0.85rem;
            font-weight: 500;
            cursor: pointer;
            border: var(--glass-border);
            transition: var(--transition);
        }

        .filter-btn.active {
            background: linear-gradient(135deg, var(--primary-light), var(--primary-dark));
            color: var(--text-color);
            box-shadow: 0 4px 12px var(--shadow-color);
        }

        .filter-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 12px var(--shadow-color);
        }

        .report-problem-content {
            display: flex;
            flex-direction: column;
            gap: 15px;
            padding: 20px;
        }

        .report-problem-content textarea {
            width: 100%;
            min-height: 100px;
            padding: 10px;
            border-radius: 8px;
            border: 1px solid var(--border-color);
            background: rgba(255, 255, 255, 0.1);
            color: var(--text-color);
            font-family: 'Vazirmatn', sans-serif;
            font-size: 0.9rem;
            resize: none;
        }

        .report-problem-content textarea:focus {
            outline: none;
            border-color: var(--primary-light);
            box-shadow: 0 0 8px var(--shadow-color);
        }

        .report-problem-content button {
            background: linear-gradient(135deg, var(--primary-light), var(--primary-dark));
            color: var(--text-color);
            padding: 12px;
            border-radius: 10px;
            font-weight: 700;
            cursor: pointer;
            border: none;
            transition: var(--transition);
        }

        .report-problem-content button:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 12px var(--shadow-color);
        }

        .report-problem-content button:disabled {
            opacity: 0.6;
            cursor: not-allowed;
            transform: none;
            box-shadow: none;
        }

        .report-problem-content button .loading-spinner-small {
            display: inline-block;
            width: 16px;
            height: 16px;
            border: 2px solid rgba(255, 255, 255, 0.3);
            border-radius: 50%;
            border-top-color: white;
            animation: spin 1s ease-in-out infinite;
            margin-left: 8px;
        }

        @keyframes spin {
            to { transform: rotate(360deg); }
        }

        .music-controls {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-top: 20px;
        }

        .music-logo {
            width: 130px;
            height: 130px;
            margin: 20px auto;
            display: block;
            border-radius: 50%;
            animation: spin 20s linear infinite;
        }

        @keyframes spin {
            to { transform: rotate(360deg); }
        }

        .modal-progress-text {
            display: none;
            color: var(--yellow-color);
            font-size: 1rem;
            font-weight: 700;
            text-align: center;
            margin-left: 8px;
        }

        @media (max-width: 768px) {
            .news-container {
                max-width: 90%;
                padding: 12px;
            }

            .modal-window {
                max-height: 80vh;
            }

            .modal-content {
                padding: 12px;
            }

            .floating-btn {
                width: 60px;
                height: 60px;
                font-size: 24px;
                bottom: 15px;
                left: 15px;
            }

            .notification {
                max-width: 80%;
            }

            .configs-container {
                padding: 10px;
                gap: 10px;
            }

            .config-box {
                width: 140px;
                height: 160px;
                padding: 12px;
            }

            .config-logo-container {
                width: 60px;
                height: 60px;
            }

            .config-logo {
                width: 50px;
                height: 50px;
                margin-bottom: 8px;
            }

            .ping-result {
                font-size: 0.85rem;
            }

            .copy-btn {
                font-size: 0.85rem;
                padding: 8px;
            }

            .loading-dot {
                width: 8px;
                height: 8px;
            }

            .filter-btn {
                padding: 6px 12px;
                font-size: 0.8rem;
            }

            .report-problem-content textarea {
                font-size: 0.85rem;
                min-height: 80px;
            }

            .music-logo {
                width: 110px;
                height: 110px;
            }
        }
    </style>
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@400;500;700&display=swap">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
</head>
<body class="theme-default">
    <audio id="bgMusic" loop>
        <source src="https://uploadkon.ir/uploads/833c07_25shervin-nahal-online-audio-converter-com-.mp3" type="audio/mpeg">
    </audio>
    <div class="loading-window" id="loadingWindow">
        <div class="loading-content">
            <div class="loading-messages"><span>چند لحظه صبر کنید</span></div>
            <div class="loading-spinner">
                <div class="loading-frame"></div>
            </div>
            <div class="loading-footer">آقای ایکسرو</div>
        </div>
    </div>
    <div class="permanent-window" id="permanentWindow">
        <div class="top-bar">
            <div class="logo" id="reportProblemBtn"><i class="fas fa-exclamation-triangle"></i><span>گزارش مشکل</span></div>
            <div class="menu-btn" id="mainMenuBtn">
                <div class="menu-line"></div>
                <div class="menu-line"></div>
                <div class="menu-line"></div>
            </div>
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
                            <div class="info-value" id="ping">-- م‌ثبت</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <button class="floating-btn" id="configSelectBtn"><i class="fas fa-shopping-cart"></i></button>
        <div class="modal-overlay" id="mainMenuOverlay"></div>
        <div class="modal-window main-menu" id="mainMenu">
            <div class="modal-header">
                <div class="modal-title">منوی اصلی</div>
                <div class="home-btn" id="closeMainMenu">
                    <img src="https://biaupload.com/do.php?imgf=org-19fb842c16fb1.png" alt="Close">
                </div>
            </div>
            <div class="modal-content">
                <div class="menu-item" id="settingsItem">
                    <div class="menu-item-title"><i class="fas fa-music"></i><span>موزیک</span></div>
                    <div class="menu-item-desc">کنترل موسیقی پس‌زمینه</div>
                </div>
                <div class="menu-item" id="aboutItem">
                    <div class="menu-item-title"><i class="fas fa-info-circle"></i><span>درباره ما</span></div>
                    <div class="menu-item-desc">اطلاعات بیشتر درباره ایکسرو</div>
                </div>
            </div>
        </div>
        <div class="modal-overlay" id="configSelectOverlay"></div>
        <div class="modal-window public-shop-menu" id="publicShopMenu">
            <div class="modal-header">
                <div class="modal-title-container">
                    <img src="https://biaupload.com/do.php?imgf=org-c58378daa9411.png" class="modal-title-img" id="modalTitleImg" alt="Config Update">
                    <span class="modal-title" id="modalTitle">بروزرسانی کانفیگ‌ها</span>
                    <span class="modal-progress-text" id="modalProgressText">...%تکمیل شده</span>
                </div>
                <div class="home-btn" id="closePublicShopMenu">
                    <img src="https://biaupload.com/do.php?imgf=org-19fb842c16fb1.png" alt="Close">
                </div>
            </div>
            <div class="modal-content">
                <div class="filter-container" id="filterContainer">
                    <button class="filter-btn active" data-protocol="all">همه</button>
                    <button class="filter-btn" data-protocol="hysteria2">Hysteria2</button>
                    <button class="filter-btn" data-protocol="vless">Vless</button>
                    <button class="filter-btn" data-protocol="trojan">Trojan</button>
                    <button class="filter-btn" data-protocol="ss">Shadowsocks</button>
                    <button class="filter-btn" data-protocol="vmess">Vmess</button>
                    <button class="filter-btn" data-protocol="wireguard">WireGuard</button>
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
                <div class="home-btn" id="closeSettingsPanel">
                    <img src="https://biaupload.com/do.php?imgf=org-19fb842c16fb1.png" alt="Close">
                </div>
            </div>
            <div class="modal-content">
                <img src="https://is1-ssl.mzstatic.com/image/thumb/Music122/v4/d0/51/00/d0510085-dd1d-039b-5fe1-d60c71722735/artwork.jpg/360x360bb.webp" class="music-logo" alt="Music Logo">
                <div class="music-controls">
                    <button class="music-btn" id="prevTrack"><i class="fas fa-backward"></i> قبلی</button>
                    <button class="music-btn" id="playPause"><i class="fas fa-play"></i> پخش</button>
                    <button class="music-btn" id="nextTrack"><i class="fas fa-forward"></i> بعدی</button>
                </div>
            </div>
        </div>
        <div class="modal-window about-panel" id="aboutPanel">
            <div class="modal-header">
                <div class="modal-title">درباره ما</div>
                <div class="home-btn" id="closeAboutPanel">
                    <img src="https://biaupload.com/do.php?imgf=org-19fb842c16fb1.png" alt="Close">
                </div>
            </div>
            <div class="modal-content">
                <p style="font-size:0.9rem;color:var(--text-light);text-align:center;padding:20px">
                    ایکسرو با بیش از ۵ سال فعالیت در زمینه ارائه خدمات فیلترشکن و VPN، با تکیه بر تجربه و تخصص، بهترین راهکارها را برای دسترسی امن و سریع به اینترنت ارائه می‌دهد. ما متعهد به حفظ حریم خصوصی و امنیت کاربران هستیم.
                </p>
                <a href="https://t.me/xrovpn" target="_blank" class="btn btn-primary btn-large"><i class="fas fa-telegram"></i> کانال رسمی ایکسرو</a>
            </div>
        </div>
        <div class="modal-window report-problem-menu" id="reportProblemMenu">
            <div class="modal-header">
                <div class="modal-title">گزارش مشکل</div>
                <div class="home-btn" id="closeReportProblemMenu">
                    <img src="https://biaupload.com/do.php?imgf=org-19fb842c16fb1.png" alt="Close">
                </div>
            </div>
            <div class="modal-content report-problem-content">
                <textarea id="reportProblemText" placeholder="مشکل خود را اینجا بنویسید..."></textarea>
                <button id="submitReportProblem"><i class="fas fa-paper-plane"></i> ارسال گزارش</button>
            </div>
        </div>
        <div class="modal-overlay" id="reportProblemOverlay"></div>
        <div class="notification" id="notification">
            <div class="notification-icon" id="notificationIcon"><i class="fas fa-check-circle"></i></div>
            <div class="notification-message" id="notificationMessage">عملیات با موفقیت انجام شد</div>
        </div>
    </div>
    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const e = {
                permanentWindow: document.getElementById('permanentWindow'),
                loadingWindow: document.getElementById('loadingWindow'),
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

            const UI_STATE_KEY = 'xro_vpn_ui_state';
            const CACHE_KEY = 'xro_vpn_configs';
            const CACHE_EXPIRY = 5 * 60 * 1000;

            const toggleModal = (modalId, state, overlayId) => {
                closeAllModals();
                const modal = e[modalId], overlay = e[overlayId];
                if (!modal) {
                    console.error(`Modal ${modalId} not found`);
                    return;
                }
                modal.classList.toggle('open', state);
                if (overlay) {
                    overlay.classList.toggle('show', state);
                    overlay.classList.toggle('hidden', !state);
                }
                saveUIState();
                console.log(`Modal ${modalId} ${state ? 'opened' : 'closed'}`);
            };

            const closeAllModals = () => {
                ['mainMenu', 'publicShopMenu', 'settingsPanel', 'aboutPanel', 'reportProblemMenu'].forEach(id => e[id]?.classList.remove('open'));
                ['mainMenuOverlay', 'configSelectOverlay', 'reportProblemOverlay'].forEach(id => {
                    e[id]?.classList.remove('show');
                    e[id]?.classList.add('hidden');
                });
                saveUIState();
                console.log('All modals closed');
            };

            const showNotification = (msg, type = 'success') => {
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

            const submitReportProblem = async () => {
                const msg = e.reportProblemText.value.trim();
                if (!msg) {
                    showNotification('لطفاً متن گزارش را وارد کنید', 'error');
                    return;
                }
                const originalText = e.submitReportProblem.innerHTML;
                e.submitReportProblem.disabled = true;
                e.submitReportProblem.innerHTML = '<i class="fas fa-circle-notch"></i> در حال ارسال...';
                try {
                    const token = '6881799898:AAH6pU-1-Jvdp7VHxHCMbx_fLDpnH-kLzqQ';
                    const adminId = '8402261840';
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
                try {
                    const res = await fetch('https://api.ipify.org?format=json');
                    const data = await res.json();
                    e.ip.textContent = toPersianDigits(data.ip);
                } catch {
                    e.ip.textContent = 'نامشخص';
                }
            };

            const refreshIP = () => {
                updateIP();
                setTimeout(refreshIP, 5000);
            };

            const updatePing = async () => {
                try {
                    const start = performance.now();
                    await fetch('https://www.google.com', { method: 'HEAD', mode: 'no-cors', cache: 'no-store' });
                    e.ping.textContent = toPersianDigits(Math.round(performance.now() - start).toString()) + ' م‌ثبت';
                } catch {
                    e.ping.textContent = 'نامشخص';
                }
            };

            const refreshPing = () => {
                updatePing();
                setTimeout(refreshPing, 1000);
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
                        data.ps = 'telegram ☜☞ v2xro';
                        return `vmess://${btoa(JSON.stringify(data))}${comment.length ? '#' + comment.join('#') : ''}`;
                    }
                    if (protocol.toLowerCase() === 'wireguard') {
                        const [base, ...comment] = rest.split('#');
                        const data = JSON.parse(base);
                        data.ps = 'telegram ☜☞ v2xro';
                        return `wireguard://${JSON.stringify(data)}${comment.length ? '#' + comment.join('#') : ''}`;
                    }
                    if (['vless', 'trojan', 'ss'].includes(protocol.toLowerCase())) {
                        const [base, ...comment] = rest.split('#');
                        return comment.length ? `${protocol}://${base}#telegram ☜☞ v2xro` : config;
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

            const flagImages = {
                'CA': 'https://biaupload.com/do.php?imgf=org-2365ab5b670f1.png',
                'FI': 'https://biaupload.com/do.php?imgf=org-a721bfe2628f2.png',
                'DE': 'https://biaupload.com/do.php?imgf=org-ccc23c0b39f63.png',
                'IE': 'https://biaupload.com/do.php?imgf=org-edb9149665d04.png',
                'US': 'https://biaupload.com/do.php?imgf=org-8c420612f1d81.png',
                'TR': 'https://biaupload.com/do.php?imgf=org-e65fe7e1e3cf2.png',
                'AU': 'https://biaupload.com/do.php?imgf=org-8dfd0db6b87d3.png',
                'ES': 'https://biaupload.com/do.php?imgf=org-e5b8c992c01b4.png'
            };

            const getCountryImage = countryCode => flagImages[countryCode] || 'https://biaupload.com/do.php?imgf=org-7a7eb985bb052.png';

            const getCachedConfigs = () => {
                try {
                    const cached = localStorage.getItem(CACHE_KEY);
                    if (!cached) return null;
                    const { data, timestamp } = JSON.parse(cached);
                    if (Date.now() - timestamp > CACHE_EXPIRY) return null;
                    return data;
                } catch {
                    return null;
                }
            };

            const setCachedConfigs = data => localStorage.setItem(CACHE_KEY, JSON.stringify({ data, timestamp: Date.now() }));

            const saveUIState = () => {
                const state = {
                    activeFilter: e.filterContainer.querySelector('.filter-btn.active')?.dataset.protocol || 'all',
                    isPublicShopMenuOpen: e.publicShopMenu.classList.contains('open'),
                    isMainMenuOpen: e.mainMenu.classList.contains('open'),
                    isSettingsPanelOpen: e.settingsPanel.classList.contains('open'),
                    isAboutPanelOpen: e.aboutPanel.classList.contains('open'),
                    isReportProblemMenuOpen: e.reportProblemMenu.classList.contains('open')
                };
                sessionStorage.setItem(UI_STATE_KEY, JSON.stringify(state));
            };

            const loadUIState = () => {
                const state = sessionStorage.getItem(UI_STATE_KEY);
                if (!state) return;
                const { activeFilter, isPublicShopMenuOpen, isMainMenuOpen, isSettingsPanelOpen, isAboutPanelOpen, isReportProblemMenuOpen } = JSON.parse(state);
                e.filterContainer.querySelectorAll('.filter-btn').forEach(btn => {
                    btn.classList.toggle('active', btn.dataset.protocol === activeFilter);
                });
                if (isPublicShopMenuOpen) toggleModal('publicShopMenu', true, 'configSelectOverlay');
                if (isMainMenuOpen) toggleModal('mainMenu', true, 'mainMenuOverlay');
                if (isSettingsPanelOpen) toggleModal('settingsPanel', true, 'mainMenuOverlay');
                if (isAboutPanelOpen) toggleModal('aboutPanel', true, 'mainMenuOverlay');
                if (isReportProblemMenuOpen) toggleModal('reportProblemMenu', true, 'reportProblemOverlay');
            };

            const updateProgress = (percent) => {
                e.modalTitle.style.display = 'none';
                e.modalProgressText.style.display = 'inline';
                e.modalProgressText.textContent = `${toPersianDigits(percent.toString())}% تکمیل شده`;
                if (percent >= 100) {
                    setTimeout(() => {
                        e.modalProgressText.style.display = 'none';
                        e.modalTitle.style.display = 'inline';
                    }, 1000);
                }
            };

            const extractConfigs = async (forceRefresh = false) => {
                e.configsContainer.innerHTML = '<div class="loading-container"><div class="loading-dots"><div class="loading-dot"></div><div class="loading-dot"></div><div class="loading-dot"></div></div></div>';
                updateProgress(0);
                const cachedConfigs = !forceRefresh && getCachedConfigs();
                if (cachedConfigs) {
                    updateProgress(50);
                    renderConfigs(cachedConfigs);
                    updateProgress(100);
                    return;
                }
                try {
                    updateProgress(10);
                    const url = 'https://gist.githubusercontent.com/xroVPN/12a0c02781cfed451da84e9b802c0912/raw';
                    const res = await fetch(url, { mode: 'cors', cache: 'no-store' });
                    updateProgress(30);
                    if (!res.ok) {
                        e.configsContainer.innerHTML = '<p class="error">خطا در دریافت کانفیگ‌ها</p>';
                        showNotification('خطا در دریافت کانفیگ‌ها: سرور پاسخ نداد', 'error');
                        updateProgress(100);
                        return;
                    }
                    const configs = (await res.text()).split('\n').filter(c => c.trim());
                    if (!configs.length) {
                        e.configsContainer.innerHTML = '<p class="error">هیچ کانفیگی یافت نشد</p>';
                        showNotification('هیچ کانفیگی در فایل موجود نیست', 'error');
                        updateProgress(100);
                        return;
                    }
                    updateProgress(50);
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
                                if (!pingResult.success || pingResult.ping > 600) return null;
                                const location = await getLocation(parsed.host);
                                return {
                                    config: formattedConfig,
                                    ping: pingResult.ping,
                                    protocol: parsed.protocol,
                                    countryCode: location?.countryCode || null
                                };
                            } catch {
                                return null;
                            }
                        }));
                        validConfigs.push(...results.filter(c => c));
                        updateProgress(50 + (i + batchSize) / configs.length * 40);
                    }
                    if (!validConfigs.length) {
                        e.configsContainer.innerHTML = '<p class="error">هیچ کانفیگ معتبری یافت نشد</p>';
                        showNotification('هیچ کانفیگ معتبری یافت نشد', 'error');
                        updateProgress(100);
                        return;
                    }
                    setCachedConfigs(validConfigs);
                    renderConfigs(validConfigs);
                    updateProgress(100);
                } catch (err) {
                    e.configsContainer.innerHTML = '<p class="error">خطا در بارگذاری کانفیگ‌ها</p>';
                    showNotification(`خطا: ${err.message}`, 'error');
                    updateProgress(100);
                    console.error('Config fetch error:', err);
                }
            };

            const renderConfigs = configs => {
                e.configsContainer.innerHTML = '';
                const activeProtocol = e.filterContainer.querySelector('.filter-btn.active')?.dataset.protocol || 'all';
                const filteredConfigs = configs.filter(c => activeProtocol === 'all' || c.protocol.toLowerCase() === activeProtocol);
                if (!filteredConfigs.length) {
                    e.configsContainer.innerHTML = '<p class="error">هیچ کانفیگی برای این فیلتر موجود نیست</p>';
                    return;
                }
                filteredConfigs.sort((a, b) => a.ping - b.ping).forEach((c, i) => {
                    const box = document.createElement('div');
                    box.className = 'config-box';
                    box.style.opacity = '0';
                    box.style.animation = `slideInRight 0.5s ease-out ${i * 0.1}s forwards`;
                    box.dataset.protocol = c.protocol.toLowerCase();
                    const pingClass = c.ping < 300 ? 'fast' : c.ping < 600 ? 'medium' : 'slow';
                    const logoContent = `<img src="${getCountryImage(c.countryCode)}" class="config-logo" alt="Config Logo">`;
                    box.innerHTML = `
                        <div class="config-logo-container">${logoContent}</div>
                        <div class="ping-result ${pingClass}"><i class="fas fa-tachometer-alt"></i> ${toPersianDigits(c.ping.toString())} م‌ثبت</div>
                        <button class="copy-btn"><i class="fas fa-copy"></i> کپی</button>
                    `;
                    box.querySelector('.copy-btn').addEventListener('click', () => {
                        navigator.clipboard.writeText(c.config).then(() => {
                            showNotification('کانفیگ کپی شد', 'success');
                        }).catch(() => {
                            showNotification('خطا در کپی کردن کانفیگ', 'error');
                        });
                    });
                    e.configsContainer.appendChild(box);
                });
                saveUIState();
            };

            const setupFilters = () => {
                e.filterContainer.querySelectorAll('.filter-btn').forEach(btn => btn.addEventListener('click', () => {
                    e.filterContainer.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
                    btn.classList.add('active');
                    const cachedConfigs = getCachedConfigs();
                    if (cachedConfigs) {
                        renderConfigs(cachedConfigs);
                    } else {
                        extractConfigs();
                    }
                }));
            };

            const togglePlayPause = () => {
                if (e.bgMusic.paused) {
                    e.bgMusic.play().then(() => {
                        e.playPause.innerHTML = '<i class="fas fa-pause"></i> مکث';
                        showNotification('موسیقی در حال پخش', 'success');
                    }).catch(() => {
                        showNotification('برای پخش موسیقی، ابتدا با صفحه تعامل کنید', 'info');
                    });
                } else {
                    e.bgMusic.pause();
                    e.playPause.innerHTML = '<i class="fas fa-play"></i> پخش';
                    showNotification('موسیقی متوقف شد', 'info');
                }
            };

            e.modalTitleImg.addEventListener('click', () => {
                extractConfigs(true);
            });

            e.device.textContent = /Mobile|Android|iPhone|iPad/i.test(navigator.userAgent) ? 'موبایل' : 'دسکتاپ';
            setupFilters();
            loadUIState();
            setTimeout(() => {
                e.loadingWindow.classList.add('hidden');
                e.permanentWindow.style.display = 'flex';
                showNotification('به ایکسرو خوش آمدید', 'success');
                e.bgMusic.play().catch(() => {
                    showNotification('برای پخش موسیقی، ابتدا با صفحه تعامل کنید', 'info');
                });
                if (e.publicShopMenu.classList.contains('open')) {
                    extractConfigs();
                }
            }, 5000); // Changed to 5 seconds

            e.mainMenuBtn.addEventListener('click', () => toggleModal('mainMenu', true, 'mainMenuOverlay'));
            e.configSelectBtn.addEventListener('click', () => {
                toggleModal('publicShopMenu', true, 'configSelectOverlay');
                extractConfigs();
            });
            e.settingsItem.addEventListener('click', () => toggleModal('settingsPanel', true, 'mainMenuOverlay'));
            e.aboutItem.addEventListener('click', () => toggleModal('aboutPanel', true, 'mainMenuOverlay'));
            e.reportProblemBtn.addEventListener('click', () => toggleModal('reportProblemMenu', true, 'reportProblemOverlay'));
            e.submitReportProblem.addEventListener('click', submitReportProblem);
            e.closeMainMenu.addEventListener('click', () => toggleModal('mainMenu', false, 'mainMenuOverlay'));
            e.closePublicShopMenu.addEventListener('click', () => toggleModal('publicShopMenu', false, 'configSelectOverlay'));
            e.closeSettingsPanel.addEventListener('click', () => toggleModal('settingsPanel', false, 'mainMenuOverlay'));
            e.closeAboutPanel.addEventListener('click', () => toggleModal('aboutPanel', false, 'mainMenuOverlay'));
            e.closeReportProblemMenu.addEventListener('click', () => toggleModal('reportProblemMenu', false, 'reportProblemOverlay'));
            e.mainMenuOverlay.addEventListener('click', closeAllModals);
            e.configSelectOverlay.addEventListener('click', closeAllModals);
            e.reportProblemOverlay.addEventListener('click', closeAllModals);
            e.playPause.addEventListener('click', togglePlayPause);
        });
    </script>
</body>
</html>
