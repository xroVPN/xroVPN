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
            --border-color: rgba(0,0,0,0.3);
            --shadow-color: rgba(0,0,0,0.1);
            --glass-effect: linear-gradient(135deg, rgba(200,200,200,0.15), rgba(230,230,230,0.15));
            --glass-border: 1px solid rgba(200,200,200,0.2);
            --glass-shadow: 0 10px 30px rgba(0,0,0,0.1);
            --transition: all .3s cubic-bezier(.4,0,.2,1);
            --glow-effect: 0 0 15px rgba(0,0,0,0.4), 0 0 30px rgba(0,0,0,0.2);
            --bg-line1: #e0e0e0;
            --bg-line2: #d0d0d0;
            --accent-dark: #1a1a1a;
            --accent-mid: #3a3a3a;
            --glass: #ffffffcc;
            --loader-height: 7vh;
            --loader-max-h: 48px;
            --z-index-modal: 1000;
            --z-index-overlay: 999;
            --z-index-notification: 10000;
            --z-index-loading: 100000;
            --notebook-lines: repeating-linear-gradient(0deg, transparent, transparent 49px, var(--bg-line1) 49px, var(--bg-line1) 50px);
        }

        /* قالب Notebook XRO برای صفحه لودینگ */
        .loading-overlay {
            position: fixed;
            inset: 0;
            z-index: var(--z-index-loading);
            background: white;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100%;
            margin: 0;
            padding: 0;
            overflow: hidden;
            font-family: Tahoma, Arial, sans-serif;
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
            opacity: 0;
            visibility: hidden;
            transition: all 0.5s ease;
        }

        .loading-overlay.show {
            opacity: 1;
            visibility: visible;
        }

        .loading-overlay.fade-out {
            opacity: 0;
            visibility: hidden;
        }

        .notebook {
            width: 100%;
            height: 100%;
            background: repeating-linear-gradient(
                to bottom,
                transparent,
                transparent 8.2vw,
                #e0e0e0 8.4vw
            );
            background-size: 100% 8.4vw;
            position: absolute;
            top: 0;
            left: 0;
        }

        .loading-text {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-family: 'Permanent Marker', 'Comic Sans MS', 'Arial', sans-serif;
            font-size: 20vw;
            font-weight: bold;
            display: flex;
            justify-content: center;
            align-items: center;
            user-select: none;
            text-shadow: 
                1vw 1vw 2vw rgba(0, 0, 0, 0.3),
                -0.5vw -0.5vw 1.5vw rgba(255, 255, 255, 0.5);
        }

        .x {
            color: red;
            text-shadow: 
                1vw 1vw 2vw rgba(0, 0, 0, 0.3),
                -0.5vw -0.5vw 1.5vw rgba(255, 255, 255, 0.5);
            animation: flicker 4s 1;
            margin-right: 6vw;
        }

        .ro {
            position: relative;
            color: transparent;
            background: linear-gradient(to bottom, black 40%, rgba(0, 0, 0, 0.7) 60%, transparent 100%);
            -webkit-background-clip: text;
            background-clip: text;
            text-shadow: none;
            animation: melt 3s infinite ease-in-out;
        }

        .ro:not(:last-child) {
            margin-right: 6vw;
        }

        .ro:last-child {
            margin-right: 0;
        }

        @keyframes flicker {
            0% { opacity: 1; }
            10% { opacity: 0.4; }
            20% { opacity: 0.4; }
            25% { opacity: 1; }
            30% { opacity: 0.4; }
            35% { opacity: 1; }
            40% { opacity: 0.4; }
            45% { opacity: 1; }
            50% { opacity: 0.4; }
            70% { opacity: 1; }
            100% { opacity: 1; }
        }

        @keyframes melt {
            0% {
                background-position: 0 0;
            }
            50% {
                background-position: 0 5vw;
            }
            100% {
                background-position: 0 0;
            }
        }

        /* بقیه استایل‌ها بدون تغییر */
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            -webkit-tap-highlight-color: transparent;
            touch-action: manipulation;
        }

        body {
            font-family: 'Vazirmatn', 'Segoe UI', sans-serif;
            background: var(--bg-color) var(--notebook-lines);
            color: var(--text-color);
            height: 100vh;
            overflow: hidden;
            user-select: none;
            position: relative;
            background-size: 100% 51px;
            background-position: top right;
            background-repeat: repeat-y;
        }

        .permanent-window {
            position: fixed;
            inset: 0;
            z-index: 10;
            background: transparent;
            display: flex;
            flex-direction: column;
            overflow: hidden;
            animation: fadeIn 1s ease-out;
            display: none;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .top-bar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 6px 20px;
            background: var(--card-bg);
            border-bottom: var(--border-color);
            box-shadow: 0 4px 20px var(--shadow-color);
            z-index: 100;
        }

        .logo {
            font-size: 1.3rem;
            font-weight: 700;
            padding: 12px 18px;
            border-radius: 12px;
            cursor: pointer;
            background: var(--card-bg);
            display: flex;
            align-items: center;
            gap: 12px;
            transition: var(--transition);
            border: 3px solid #000000;
            box-shadow: var(--glow-effect);
            color: var(--text-color);
        }

        .logo:hover {
            background: var(--card-hover);
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 8px 25px var(--shadow-color);
        }

        .logo i {
            font-size: 1.4rem;
        }

        .menu-btn {
            position: relative;
            width: 44px;
            height: 44px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--primary-color), var(--primary-dark));
            border: 2px solid rgba(255,255,255,0.2);
            cursor: pointer;
            display: flex;
            justify-content: center;
            align-items: center;
            transition: var(--transition);
            box-shadow: 0 6px 20px var(--shadow-color);
            overflow: hidden;
        }

        .menu-btn::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(135deg, rgba(255,255,255,0.1), rgba(255,255,255,0.05));
            border-radius: 50%;
            opacity: 0;
            transition: var(--transition);
        }

        .menu-btn:hover::before {
            opacity: 1;
        }

        .menu-btn::after {
            content: "";
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 28px;
            height: 28px;
            border-radius: 50%;
            background-size: cover;
            background-image: url('https://www.jowhareh.com/images/Jowhareh/galleries/large_a386cbed-ecf1-4dae-b850-d1902ad6c452.webp');
            animation: slowSpin 20s linear infinite;
            filter: blur(0.5px);
            transition: var(--transition);
        }

        .menu-btn:hover::after {
            animation: mediumSpin 12s linear infinite;
            filter: blur(0);
            transform: translate(-50%, -50%) scale(1.1);
        }

        .menu-btn i {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 1.4rem;
            color: var(--text-white);
            z-index: 2;
            transition: var(--transition);
            opacity: 0.8;
        }

        .menu-btn:hover i {
            opacity: 1;
            transform: translate(-50%, -50%) scale(1.1);
        }

        @keyframes slowSpin {
            from { transform: translate(-50%, -50%) rotate(0deg); }
            to { transform: translate(-50%, -50%) rotate(360deg); }
        }

        @keyframes mediumSpin {
            from { transform: translate(-50%, -50%) rotate(0deg); }
            to { transform: translate(-50%, -50%) rotate(360deg); }
        }

        @media (max-width: 480px) {
            .menu-btn {
                width: 40px;
                height: 40px;
            }
            .menu-btn::after {
                width: 22px;
                height: 22px;
            }
            .menu-btn i {
                font-size: 1.2rem;
            }
        }

        .content {
            height: calc(100vh - 50px);
            display: flex;
            flex-direction: column;
            padding: 10px;
            overflow: hidden;
        }

        .welcome-container {
            flex: 1;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            margin-top: -10px;
        }

        .news-container {
            width: 100%;
            max-width: 90%;
            padding: 12px;
            border-radius: 16px;
            text-align: center;
            background: transparent;
            box-shadow: var(--glow-effect);
            border: 1px solid var(--border-color);
        }

        .news-content {
            color: var(--text-light);
            font-size: 0.95rem;
            text-align: right;
        }

        .info-box {
            background: transparent;
            border-radius: 14px;
            padding: 14px;
            margin-bottom: 12px;
            display: flex;
            align-items: center;
            gap: 12px;
            opacity: 0;
            border: 1px solid var(--primary-color);
            box-shadow: 0 4px 15px var(--shadow-color);
            cursor: pointer;
            transition: var(--transition);
        }

        .info-box:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px var(--shadow-color);
        }

        .info-box:nth-child(1) {
            animation: slideInLeft 0.6s ease-out 0.2s forwards;
        }

        .info-box:nth-child(2) {
            animation: slideInRight 0.6s ease-out 0.4s forwards;
        }

        .info-box:nth-child(3) {
            animation: slideInLeft 0.6s ease-out 0.6s forwards;
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
            font-size: 1.4rem;
            color: var(--primary-color);
            min-width: 32px;
            display: flex;
            justify-content: center;
            transition: var(--transition);
        }

        .info-box:hover .info-icon {
            transform: scale(1.1);
        }

        .info-text {
            font-weight: 600;
            min-width: 60px;
            color: var(--warning-color);
        }

        .info-value {
            font-weight: 600;
            min-width: 60px;
            flex: 1;
            text-align: left;
            direction: ltr;
            color: var(--text-color);
        }

        .floating-btn {
            position: fixed;
            bottom: 15px;
            left: 15px;
            width: 70px;
            height: 70px;
            background: linear-gradient(135deg, var(--primary-color), var(--primary-dark));
            border-radius: 18px;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 26px;
            color: var(--text-white);
            box-shadow: 0 10px 30px var(--shadow-color);
            cursor: pointer;
            border: none;
            transition: var(--transition);
            z-index: 100;
            bottom: 28px;
            animation: gentleFloat 6s ease-in-out infinite;
        }

        .floating-btn::after {
            content: '';
            position: absolute;
            bottom: -13px;
            left: 50%;
            transform: translateX(-50%);
            width: 35px;
            height: 4px;
            background: linear-gradient(90deg, #666, #333);
            border-radius: 2px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.4);
            transition: all 0.3s ease;
        }

        .floating-btn i {
            font-size: 1.6rem;
            transition: var(--transition);
        }

        .floating-btn:hover {
            box-shadow: 0 15px 40px var(--shadow-color);
            background: linear-gradient(135deg, var(--primary-dark), var(--primary-color));
            animation-play-state: paused;
        }

        .floating-btn:hover::after {
            width: 40px;
            box-shadow: 0 2px 12px rgba(0,0,0,0.6);
            animation: basePulse 1s ease-in-out infinite alternate;
        }

        .floating-btn:hover i {
            transform: rotate(360deg);
        }

        @keyframes gentleFloat {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-5px); }
        }

        @keyframes basePulse {
            0% { box-shadow: 0 2px 8px rgba(0,0,0,0.4); }
            100% { box-shadow: 0 2px 12px rgba(0,0,0,0.6); }
        }

        @media (max-width: 480px) {
            .floating-btn {
                width: 65px;
                height: 65px;
                font-size: 24px;
                bottom: 25px;
            }
            .floating-btn i {
                font-size: 1.4rem;
            }
            .floating-btn::after {
                width: 30px;
                height: 4px;
                bottom: -11px;
            }
        }

        .modal-overlay {
            position: fixed;
            inset: 0;
            background: rgba(0,0,0,0.7);
            z-index: var(--z-index-overlay);
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

        .modal-window {
            position: fixed;
            background: var(--card-bg);
            z-index: var(--z-index-modal);
            transition: var(--transition);
            box-shadow: 0 12px 40px var(--shadow-color);
            border: var(--border-color);
            border-radius: 18px;
            display: flex;
            flex-direction: column;
            max-height: 80vh;
            overflow: hidden;
        }

        .public-shop-menu {
            bottom: -100%;
            left: 0;
            width: 100%;
            max-height: 80%;
            border-radius: 18px 18px 0 0;
            transition: bottom .3s ease;
        }

        .public-shop-menu.open {
            bottom: 0;
        }

        .source-panel {
            bottom: -100%;
            right: 0;
            width: 100%;
            max-height: 50%;
            border-radius: 18px 18px 0 0;
            transition: bottom .3s ease;
        }

        .source-panel.open {
            bottom: 0;
        }

        .music-panel {
            position: fixed;
            background: transparent;
            z-index: var(--z-index-modal);
            transition: var(--transition);
            box-shadow: 0 12px 40px var(--shadow-color);
            border: var(--border-color);
            border-radius: 18px;
            display: flex;
            flex-direction: column;
            max-height: 80vh;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%) scale(0.8);
            width: 90%;
            max-width: 500px;
            opacity: 0;
            transition: all .3s ease;
        }

        .music-panel.open {
            transform: translate(-50%, -50%) scale(1);
            opacity: 1;
        }

        .report-problem-menu {
            top: -100%;
            right: 0;
            width: 100%;
            max-height: 65%;
            border-radius: 0 0 18px 18px;
            transition: top .3s ease;
        }

        .report-problem-menu.open {
            top: 0;
        }

        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 18px 20px;
            border-bottom: var(--border-color);
            background: var(--card-bg);
            box-shadow: 0 4px 15px var(--shadow-color);
        }

        .modal-title-container {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .modal-title {
            font-weight: 700;
            font-size: 1.3rem;
            color: var(--text-color);
        }

        .modal-title-img {
            font-size: 1.4rem;
            cursor: pointer;
            transition: var(--transition);
        }

        .modal-title-img:hover,
        .modal-title-img.active {
            transform: rotate(360deg);
        }

        .home-btn {
            cursor: pointer;
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            transition: var(--transition);
            background: var(--card-bg);
            border: 1px solid var(--border-color);
        }

        .home-btn:hover {
            background: var(--card-hover);
            transform: scale(1.1);
            box-shadow: 0 6px 20px var(--shadow-color);
        }

        .home-btn i {
            font-size: 1.4rem;
            transition: var(--transition);
        }

        .home-btn:hover i {
            transform: scale(1.2);
        }

        .config-source-section {
            margin: 20px 0 10px 0;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 10px;
            flex-wrap: wrap;
        }

        .freedom-text {
            color: #000000;
            font-size: 1rem;
            font-weight: 600;
            text-align: center;
            white-space: nowrap;
            pointer-events: none;
            cursor: default;
            display: inline;
        }

        .login-btn-modal {
            padding: 8px 16px;
            background: linear-gradient(135deg, #ff0000, #cc0000);
            color: var(--text-white);
            border-radius: 12px;
            font-weight: 600;
            cursor: pointer;
            border: none;
            transition: var(--transition);
            box-shadow: 0 6px 20px var(--shadow-color);
            display: inline-flex;
            align-items: center;
            gap: 8px;
            font-size: 0.9rem;
            margin-right: 10px;
        }

        .login-btn-modal:hover {
            background: linear-gradient(135deg, #cc0000, #ff0000);
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 10px 25px var(--shadow-color);
        }

        .login-btn-modal i {
            font-size: 1.1rem;
            transition: var(--transition);
        }

        .login-btn-modal:hover i {
            transform: scale(1.1);
        }

        @media (max-width: 480px) {
            .freedom-text {
                font-size: 0.9rem;
            }
            .config-source-section {
                flex-direction: row;
                gap: 8px;
            }
            .login-btn-modal {
                padding: 6px 12px;
                font-size: 0.85rem;
            }
        }

        .modal-content {
            display: flex;
            flex-direction: column;
            padding: 12px;
            background: var(--card-bg);
            height: 100%;
        }

        .modal-content-main {
            flex: 1;
            overflow-y: auto;
            padding: 8px 0;
        }

        .config-content-bottom {
            margin-top: auto;
            padding-top: 15px;
            border-top: 1px solid var(--border-color);
        }

        .music-panel-content {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 20px;
            text-align: center;
            position: relative;
            background: transparent;
            height: 100%;
        }

        .music-logo-container {
            position: relative;
            perspective: 1000px;
            margin-bottom: 30px;
            flex: 1;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .music-logo {
            width: 260px;
            height: 260px;
            border-radius: 50%;
            object-fit: cover;
            box-shadow: 0 0 0 rgba(255,255,255,0.8),
                       0 0 40px rgba(255,255,255,0.6),
                       0 0 80px rgba(255,255,255,0.4),
                       0 0 120px rgba(255,255,255,0.2),
                       inset 0 0 20px rgba(255,255,255,0.3);
            animation: slowSpin 20s linear infinite, pulse 3s ease-in-out infinite alternate;
            transform-style: preserve-3d;
            transition: var(--transition);
            border: 3px solid rgba(255,255,255,0.2);
            backdrop-filter: blur(10px);
            position: relative;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .music-logo.playing {
            animation: mediumSpin 15s linear infinite, pulse 2s ease-in-out infinite alternate;
        }

        .music-logo.paused {
            animation: slowSpin 25s linear infinite, pulse 4s ease-in-out infinite alternate;
        }

        .music-logo:hover {
            animation: mediumSpin 12s linear infinite, pulse 1.5s ease-in-out infinite alternate;
            transform: scale(1.1) rotateY(10deg) rotateX(5deg);
            box-shadow: 0 0 0 rgba(255,255,255,1),
                       0 0 60px rgba(255,255,255,0.8),
                       0 0 100px rgba(255,255,255,0.6),
                       0 0 150px rgba(255,255,255,0.4),
                       0 0 200px rgba(255,255,255,0.2),
                       inset 0 0 30px rgba(255,255,255,0.5);
            border-color: rgba(255,255,255,0.4);
        }

        .music-logo img {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            object-fit: cover;
        }

        .music-logo .play-pause-icon {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 3rem;
            color: rgba(255,255,255,0.9);
            z-index: 4;
            transition: var(--transition);
            text-shadow: 0 2px 10px rgba(0,0,0,0.5);
        }

        .music-logo .play-pause-icon:hover {
            color: rgba(255,255,255,1);
            text-shadow: 0 2px 15px rgba(0,0,0,0.7);
            transform: translate(-50%, -50%) scale(1.1);
        }

        .music-logo::after {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 70px;
            height: 70px;
            background: linear-gradient(135deg, rgba(0,0,0,0.7), rgba(0,0,0,0.5));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            transition: var(--transition);
            z-index: 2;
        }

        .music-logo:hover::after,
        .music-logo.playing::after {
            opacity: 1;
            transform: translate(-50%, -50%) scale(1.1);
        }

        .music-logo::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 0;
            height: 0;
            border-left: 20px solid rgba(255,255,255,0.9);
            border-top: 12px solid transparent;
            border-bottom: 12px solid transparent;
            opacity: 0;
            transition: var(--transition);
            z-index: 3;
        }

        .music-logo.playing::before {
            opacity: 1;
            border-left: 16px solid rgba(255,255,255,1);
        }

        .music-logo.paused::before {
            width: 0;
            height: 0;
            border-left: 12px solid rgba(255,255,255,0.9);
            border-top: 12px solid transparent;
            border-bottom: 12px solid transparent;
            opacity: 1;
            border-left: 16px solid rgba(255,255,255,1);
        }

        .music-logo .play-icon {
            display: block;
        }

        .music-logo .pause-icon {
            display: none;
        }

        .music-logo.playing .play-icon {
            display: none;
        }

        .music-logo.playing .pause-icon {
            display: block;
        }

        @keyframes slowSpin {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        @keyframes mediumSpin {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        @keyframes pulse {
            0% {
                box-shadow: 0 0 0 rgba(255,255,255,0.8),
                           0 0 40px rgba(255,255,255,0.6),
                           0 0 80px rgba(255,255,255,0.4),
                           0 0 120px rgba(255,255,255,0.2),
                           inset 0 0 20px rgba(255,255,255,0.3);
            }
            100% {
                box-shadow: 0 0 20px rgba(255,255,255,1),
                           0 0 60px rgba(255,255,255,0.8),
                           0 0 100px rgba(255,255,255,0.6),
                           0 0 140px rgba(255,255,255,0.4),
                           inset 0 0 30px rgba(255,255,255,0.4);
            }
        }

        @media (max-width: 480px) {
            .music-logo {
                width: 220px;
                height: 220px;
            }
            .music-logo .play-pause-icon {
                font-size: 2.5rem;
            }
            .music-logo::after {
                width: 55px;
                height: 55px;
            }
            .music-logo::before {
                border-left: 16px solid rgba(255,255,255,0.9);
                border-top: 10px solid transparent;
                border-bottom: 10px solid transparent;
            }
        }

        .configs-container {
            display: flex;
            gap: 27px;
            overflow-x: auto;
            padding: 12px;
            direction: rtl;
            scrollbar-width: none;
            position: relative;
            max-height: calc(100vh - 200px);
            background: linear-gradient(60deg, rgba(0,0,0,0.8) 0%, rgba(0,0,0,0.4) 30%, rgba(0,0,0,0.1) 70%, transparent 100%);
            border-radius: 16px;
            margin: 10px 0;
        }

        .configs-container::-webkit-scrollbar {
            display: none;
        }

        .configs-container {
            -ms-overflow-style: none;
            scrollbar-width: none;
        }

        .configs-container::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            border-radius: 16px;
            background: linear-gradient(60deg, rgba(0,0,0,0.2) 0%, transparent 30%);
            pointer-events: none;
            z-index: 1;
        }

        .configs-container > * {
            position: relative;
            z-index: 2;
        }

        .config-box {
            position: relative;
            background: linear-gradient(60deg, rgba(0,0,0,0.15) 0%, transparent 50%), var(--card-bg);
            padding: 12px;
            width: 153px;
            height: 176px;
            transition: var(--transition);
            cursor: move;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: space-between;
            text-align: center;
            flex-shrink: 0;
            border-radius: 14px;
            border: 2px solid transparent;
            opacity: 0;
            box-shadow: 0 6px 20px var(--shadow-color),
                       inset 2px 2px 8px rgba(255,255,255,0.1),
                       inset -2px -2px 8px rgba(0,0,0,0.1);
        }

        .config-box.dragging {
            opacity: 0.5;
            transform: scale(0.95);
            z-index: 1000;
        }

        .config-box:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 12px 30px var(--shadow-color),
                       0 0 30px rgba(0,0,0,0.3),
                       inset 3px 3px 12px rgba(255,255,255,0.15),
                       inset -3px -3px 12px rgba(0,0,0,0.15);
            background: linear-gradient(60deg, rgba(0,0,0,0.25) 0%, transparent 50%), var(--card-bg);
        }

        .config-box[data-protocol="hysteria2"] {
            border-color: var(--success-color);
        }

        .config-box[data-protocol="vless"] {
            border-color: var(--primary-color);
        }

        .config-box[data-protocol="trojan"] {
            border-color: var(--secondary-color);
        }

        .config-box[data-protocol="ss"] {
            border-color: var(--warning-color);
        }

        .config-box[data-protocol="vmess"] {
            border-color: var(--accent-color);
        }

        .config-box[data-protocol="wireguard"] {
            border-color: var(--dark-purple);
        }

        .config-box::after {
            content: attr(data-protocol-fa);
            position: absolute;
            top: -12px;
            left: 50%;
            transform: translateX(-50%);
            background: var(--card-bg);
            color: var(--text-light);
            font-size: 0.85rem;
            padding: 5px 10px;
            border-radius: 10px;
            opacity: 0;
            transition: var(--transition);
            pointer-events: none;
            box-shadow: 0 4px 15px var(--shadow-color);
            white-space: nowrap;
        }

        .config-box:hover::after {
            opacity: 1;
        }

        .config-logo-container {
            position: relative;
            width: 65px;
            height: 65px;
            display: flex;
            justify-content: center;
            align-items: center;
            background: transparent;
            margin-bottom: 10px;
            font-size: 2.5rem;
        }

        .config-logo {
            font-size: inherit;
            transition: var(--transition);
            background: transparent;
        }

        .config-box:hover .config-logo {
            transform: scale(1.15) rotate(5deg);
        }

        .ping-result {
            font-size: 0.9rem;
            display: flex;
            align-items: center;
            gap: 8px;
            width: 100%;
            justify-content: center;
            font-weight: 600;
            direction: rtl;
            transition: var(--transition);
        }

        .ping-result.fast {
            color: var(--success-color);
        }

        .ping-result.medium {
            color: var(--warning-color);
        }

        .ping-result.slow {
            color: var(--danger-color);
        }

        .error {
            background: var(--card-bg);
            color: var(--danger-color);
            border: 1px solid rgba(255,0,0,0.4);
            border-radius: 14px;
            padding: 16px;
            margin: 18px 0;
            font-size: 0.95rem;
            text-align: center;
            box-shadow: 0 4px 15px var(--shadow-color);
        }

        .loading-container {
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 20px 0;
            direction: rtl;
            min-height: 50px;
        }

        .loading-dots {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 10px;
        }

        .loading-dot {
            width: 10px;
            height: 10px;
            background: linear-gradient(45deg, var(--primary-color), var(--secondary-color));
            border-radius: 50%;
            animation: bounce 1.4s ease-in-out infinite;
            box-shadow: 0 0 10px var(--shadow-color);
        }

        .loading-dot:nth-child(2) {
            animation-delay: 0.2s;
        }

        .loading-dot:nth-child(3) {
            animation-delay: 0.4s;
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); opacity: 0.6; }
            50% { transform: translateY(-12px); opacity: 1; }
        }

        .copy-btn {
            padding: 10px;
            border-radius: 12px;
            background: linear-gradient(135deg, var(--primary-color), var(--primary-dark));
            color: var(--text-white);
            font-size: 0.9rem;
            font-weight: 600;
            cursor: pointer;
            border: none;
            transition: var(--transition);
            display: flex;
            align-items: center;
            gap: 8px;
            justify-content: center;
            width: 100%;
            box-shadow: 0 6px 20px var(--shadow-color);
        }

        .copy-btn i {
            font-size: 1.2rem;
            color: var(--text-white);
            transition: var(--transition);
        }

        .copy-btn:hover {
            background: linear-gradient(135deg, var(--primary-dark), var(--primary-color));
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 10px 25px var(--shadow-color);
        }

        .copy-btn:hover i {
            transform: scale(1.1);
        }

        .share-btn,
        .delete-btn {
            position: absolute;
            top: 8px;
            padding: 8px;
            border-radius: 8px;
            background: linear-gradient(135deg, var(--secondary-color), var(--primary-dark));
            color: var(--text-white);
            font-size: 0.85rem;
            font-weight: 600;
            cursor: pointer;
            border: none;
            transition: var(--transition);
            display: flex;
            align-items: center;
            gap: 6px;
            justify-content: center;
            box-shadow: 0 4px 15px var(--shadow-color);
        }

        .share-btn {
            left: 8px;
        }

        .delete-btn {
            right: 8px;
        }

        .share-btn i,
        .delete-btn i {
            font-size: 1.1rem;
            color: var(--text-white);
            transition: var(--transition);
        }

        .share-btn:hover,
        .delete-btn:hover {
            background: linear-gradient(135deg, var(--primary-dark), var(--secondary-color));
            transform: translateY(-2px) scale(1.1);
            box-shadow: 0 8px 20px var(--shadow-color);
        }

        .share-btn:hover i,
        .delete-btn:hover i {
            transform: scale(1.2);
        }

        .filter-container {
            display: flex;
            gap: 12px;
            margin-bottom: 18px;
            overflow-x: auto;
            padding: 12px;
            scrollbar-width: none;
            direction: rtl;
            border-bottom: 1px solid var(--border-color);
        }

        .filter-container::-webkit-scrollbar {
            display: none;
        }

        .filter-btn {
            padding: 8px 14px;
            border-radius: 12px;
            background: #000000;
            color: #ffffff;
            font-size: 0.85rem;
            font-weight: 500;
            cursor: pointer;
            border: 1px solid #ffffff;
            transition: var(--transition);
            box-shadow: 0 4px 15px var(--shadow-color);
            white-space: nowrap;
            flex-shrink: 0;
        }

        .filter-btn:hover {
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 8px 25px var(--shadow-color);
            background: #111111;
        }

        .filter-btn.active {
            background: #111111;
            border-color: #ffffff;
        }

        .filter-btn.inactive {
            cursor: default;
            pointer-events: none;
            opacity: 0.5;
        }

        .filter-btn.inactive:hover {
            transform: none;
            box-shadow: 0 4px 15px var(--shadow-color);
        }

        .report-problem-content {
            display: flex;
            flex-direction: column;
            gap: 18px;
            padding: 20px;
            height: 100%;
        }

        .report-problem-content textarea {
            width: 100%;
            min-height: 100px;
            padding: 12px;
            border-radius: 10px;
            border: 1px solid var(--border-color);
            background: var(--card-bg);
            color: var(--text-color);
            font-family: 'Vazirmatn', sans-serif;
            font-size: 0.9rem;
            resize: vertical;
            box-shadow: 0 0 10px var(--shadow-color);
            transition: var(--transition);
        }

        .report-problem-content textarea:focus {
            outline: none;
            border-color: var(--primary-light);
            box-shadow: 0 0 12px var(--shadow-color);
        }

        .report-problem-content button {
            background: linear-gradient(135deg, var(--primary-color), var(--primary-dark));
            color: var(--text-white);
            padding: 14px;
            border-radius: 12px;
            font-weight: 700;
            cursor: pointer;
            border: none;
            transition: var(--transition);
            box-shadow: 0 6px 20px var(--shadow-color);
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }

        .report-problem-content button i {
            font-size: 1.2rem;
            color: var(--text-white);
            transition: var(--transition);
        }

        .report-problem-content button:hover {
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 10px 25px var(--shadow-color);
        }

        .report-problem-content button:hover i {
            transform: scale(1.1);
        }

        .report-problem-content button:disabled {
            opacity: 0.6;
            cursor: not-allowed;
            transform: none;
            box-shadow: none;
        }

        .report-problem-content button .loading-spinner-small {
            display: inline-block;
            width: 18px;
            height: 18px;
            border: 2px solid rgba(255,255,255,0.3);
            border-radius: 50%;
            border-top-color: white;
            animation: spin 1s ease-in-out infinite;
        }

        @keyframes spin {
            to { transform: rotate(360deg); }
        }

        .source-content {
            display: flex;
            flex-direction: column;
            gap: 18px;
            padding: 20px;
            height: 100%;
        }

        .source-content input {
            width: 100%;
            min-height: 40px;
            padding: 12px;
            border-radius: 10px;
            border: 1px solid var(--border-color);
            background: var(--card-bg);
            color: var(--text-color);
            font-family: 'Vazirmatn', sans-serif;
            font-size: 0.9rem;
            box-shadow: 0 0 10px var(--shadow-color);
            transition: var(--transition);
        }

        .source-content input:focus {
            outline: none;
            border-color: var(--primary-light);
            box-shadow: 0 0 12px var(--shadow-color);
        }

        .source-content button {
            background: linear-gradient(135deg, var(--primary-color), var(--primary-dark));
            color: var(--text-white);
            padding: 14px;
            border-radius: 12px;
            font-weight: 700;
            cursor: pointer;
            border: none;
            transition: var(--transition);
            box-shadow: 0 6px 20px var(--shadow-color);
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }

        .source-content button i {
            font-size: 1.2rem;
            color: var(--text-white);
            transition: var(--transition);
        }

        .source-content button:hover {
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 10px 25px var(--shadow-color);
        }

        .source-content button:hover i {
            transform: scale(1.1);
        }

        .source-content button:disabled {
            opacity: 0.6;
            cursor: not-allowed;
            transform: none;
            box-shadow: none;
        }

        .source-content button .loading-spinner-small {
            display: inline-block;
            width: 18px;
            height: 18px;
            border: 2px solid rgba(255,255,255,0.3);
            border-radius: 50%;
            border-top-color: white;
            animation: spin 1s ease-in-out infinite;
        }

        @media (max-width: 480px) {
            .music-logo {
                width: 220px;
                height: 220px;
            }
            .music-logo .play-pause-icon {
                font-size: 2.5rem;
            }
            .music-logo::after {
                width: 55px;
                height: 55px;
            }
            .music-logo::before {
                border-left: 16px solid rgba(255,255,255,0.9);
                border-top: 10px solid transparent;
                border-bottom: 10px solid transparent;
            }
        }

        .notification {
            position: fixed;
            bottom: 20px;
            right: 20px;
            top: auto;
            left: auto;
            z-index: var(--z-index-notification);
            display: flex;
            align-items: center;
            gap: 12px;
            padding: 16px 20px;
            border-radius: 12px;
            background: var(--card-bg);
            color: var(--text-color);
            box-shadow: 0 8px 25px var(--shadow-color);
            transform: translateX(100%);
            opacity: 0;
            transition: var(--transition);
            border: 1px solid var(--border-color);
            width: auto;
            min-width: 280px;
            max-width: 90vw;
            word-wrap: break-word;
            word-break: break-word;
            overflow-wrap: break-word;
            hyphens: auto;
        }

        .notification.show {
            transform: translateX(0);
            opacity: 1;
        }

        .notification-success {
            border-left: 4px solid var(--success-color);
        }

        .notification-error {
            border-left: 4px solid var(--danger-color);
        }

        .notification-info {
            border-left: 4px solid var(--primary-color);
        }

        .notification-icon {
            font-size: 1.2rem;
            min-width: 20px;
            flex-shrink: 0;
        }

        .notification-message {
            font-weight: 600;
            flex: 1;
            word-break: break-word;
            overflow-wrap: break-word;
            hyphens: auto;
        }

        @media (max-width: 480px) {
            .notification {
                bottom: 10px;
                right: 10px;
                padding: 12px 16px;
                min-width: 250px;
                max-width: calc(100vw - 20px);
            }
            .notification-icon {
                font-size: 1rem;
            }
            .notification-message {
                font-size: 0.9rem;
            }
        }

        .progress-text {
            font-size: 0.9rem;
            font-weight: 500;
            color: var(--text-light);
        }
    </style>
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@400;500;700&display=swap">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Permanent+Marker&display=swap" rel="stylesheet">
</head>
<body class="theme-default">
    <!-- صفحه لودینگ با قالب Notebook XRO -->
    <div class="loading-overlay" id="loadingOverlay">
        <div class="notebook"></div>
        <div class="loading-text">
            <span class="x">X</span><span class="ro">R</span><span class="ro">O</span>
        </div>
    </div>

    <audio id="bgMusic" loop preload="metadata">
        <source src="https://dl.musicdel.ir/Music/99/10/Music/Hamid%20Sefat%20%E2%80%93%20Satoori%20(64).mp3" type="audio/mpeg">
    </audio>
    <audio id="buttonClickSound" preload="auto">
        <source src="https://sedatoseda.com/wp-content/uploads/interface-124464.mp3" type="audio/mpeg">
    </audio>
    <audio id="generalClickSound" preload="auto">
        <source src="https://sedatoseda.com/wp-content/uploads/button-31.mp3" type="audio/mpeg">
    </audio>
    <audio id="errorSound" preload="auto">
        <source src="https://sedatoseda.com/wp-content/uploads/error-warning-login-denied-132113.mp3" type="audio/mpeg">
    </audio>
    <audio id="successSound" preload="auto">
        <source src="https://dl4.fara-download.ir/audio/sound_effect/alarms/check/Twitch%20Follower%20Alert%20Sound%20Effect%20SFX.mp3" type="audio/mpeg">
    </audio>

    <div class="permanent-window" id="permanentWindow" role="main">
        <div class="top-bar" role="banner">
            <div class="logo" id="reportProblemBtn" role="button" tabindex="0" aria-label="گزارش مشکل">
                <i class="fas fa-bug" aria-hidden="true"></i>
                <span>گزارش مشکل</span>
            </div>
            <div class="menu-btn" id="musicPanelBtn" role="button" tabindex="0" aria-label="پنل موسیقی">
                <i class="fas fa-music" aria-hidden="true"></i>
            </div>
        </div>
        <div class="content">
            <div class="welcome-container">
                <div class="news-container" role="region" aria-label="اطلاعات سیستم">
                    <div class="news-content">
                        <div class="info-box" role="group">
                            <div class="info-icon">
                                <i class="fas fa-laptop" aria-hidden="true"></i>
                            </div>
                            <div class="info-text">سیستم:</div>
                            <div class="info-value" id="device" aria-live="polite">--</div>
                        </div>
                        <div class="info-box" role="group">
                            <div class="info-icon">
                                <i class="fas fa-map-marker-alt" aria-hidden="true"></i>
                            </div>
                            <div class="info-text">آیپی:</div>
                            <div class="info-value" id="ip" aria-live="polite">--</div>
                        </div>
                        <div class="info-box" role="group">
                            <div class="info-icon">
                                <i class="fas fa-tachometer-alt" aria-hidden="true"></i>
                            </div>
                            <div class="info-text">پینگ:</div>
                            <div class="info-value" id="ping" aria-live="polite">-- م‌ث</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <button class="floating-btn" id="configSelectBtn" role="button" aria-label="انتخاب کانفیگ">
        <i class="fas fa-gift" aria-hidden="true"></i>
    </button>

    <div class="modal-overlay" id="configSelectOverlay" aria-hidden="true"></div>
    <div class="modal-window public-shop-menu" id="publicShopMenu" role="dialog" aria-modal="true" aria-labelledby="modalTitle" aria-hidden="true">
        <div class="modal-header">
            <div class="modal-title-container">
                <i class="fas fa-sync-alt modal-title-img" id="modalTitleImg" role="button" tabindex="0" aria-label="بروزرسانی کانفیگ‌ها"></i>
                <span class="modal-title" id="modalTitle">بروزرسانی کانفیگ‌ها</span>
                <span class="modal-progress-text progress-text" id="modalProgressText" style="display:none" aria-live="polite">۰ از ... انجام شده</span>
            </div>
            <div class="home-btn" id="closePublicShopMenu" role="button" tabindex="0" aria-label="بستن">
                <i class="fas fa-times" aria-hidden="true"></i>
            </div>
        </div>
        <div class="modal-content">
            <div class="modal-content-main">
                <div class="filter-container" id="filterContainer">
                    <button class="filter-btn active" id="configsBtn" role="button">
                        <i class="fas fa-server"></i> کانفیگ
                    </button>
                    <button class="filter-btn" id="proxyBtn" role="button">
                        <i class="fas fa-globe"></i> پروکسی
                    </button>
                </div>
                <div class="tab-content active" id="configs-tab" role="tabpanel">
                    <div class="configs-container" id="configsContainer" aria-live="polite">
                        <div class="loading-container">
                            <div class="loading-dots">
                                <div class="loading-dot"></div>
                                <div class="loading-dot"></div>
                                <div class="loading-dot"></div>
                            </div>
                        </div>
                        <div class="error" style="display:none" role="alert">متاسفانه موجود نیست</div>
                    </div>
                </div>
                <div class="tab-content" id="proxy-tab" role="tabpanel" style="display:none">
                    <div class="configs-container" id="proxyContainer" aria-live="polite">
                        <div class="error">در حال ساخت این بخش</div>
                    </div>
                </div>
                <div class="config-content-bottom">
                    <div class="config-source-section">
                        <span class="freedom-text">درزمان قطعی افلاین گفتگو کن:</span>
                        <button class="login-btn-modal" id="loginBtnModal" role="button" aria-label="نصب">
                            <i class="fas fa-sign-in-alt" aria-hidden="true"></i>نصب
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <div class="modal-overlay" id="musicOverlay" aria-hidden="true"></div>
    <div class="modal-window music-panel" id="musicPanel" role="dialog" aria-modal="true" aria-label="پنل موسیقی" aria-hidden="true">
        <div class="modal-content music-panel-content">
            <div class="music-logo-container">
                <img src="https://www.jowhareh.com/images/Jowhareh/galleries/large_a386cbed-ecf1-4dae-b850-d1902ad6c452.webp" alt="پخش موسیقی" class="music-logo" id="musicLogo" loading="lazy">
                <div class="play-pause-icon" role="button" tabindex="0" aria-label="پخش/توقف موسیقی">
                    <i class="fas fa-play play-icon" aria-hidden="true"></i>
                    <i class="fas fa-pause pause-icon" aria-hidden="true"></i>
                </div>
            </div>
        </div>
    </div>

    <div class="modal-overlay" id="reportProblemOverlay" aria-hidden="true"></div>
    <div class="modal-window report-problem-menu" id="reportProblemMenu" role="dialog" aria-modal="true" aria-labelledby="reportProblemTitle" aria-hidden="true">
        <div class="modal-header">
            <div class="modal-title" id="reportProblemTitle">گزارش مشکل</div>
            <div class="home-btn" id="closeReportProblemMenu" role="button" tabindex="0" aria-label="بستن">
                <i class="fas fa-times" aria-hidden="true"></i>
            </div>
        </div>
        <div class="modal-content report-problem-content">
            <textarea id="reportProblemText" placeholder="مشکل خود را اینجا بنویسید..." aria-label="متن گزارش مشکل" maxlength="1000"></textarea>
            <button id="submitReportProblem" role="button">
                <i class="fas fa-comment-dots" aria-hidden="true"></i>ارسال گزارش
            </button>
        </div>
    </div>

    <div class="modal-overlay" id="sourceOverlay" aria-hidden="true"></div>
    <div class="modal-window source-panel" id="sourcePanel" role="dialog" aria-modal="true" aria-labelledby="sourceTitle" aria-hidden="true">
        <div class="modal-header">
            <div class="modal-title" id="sourceTitle">منبع نما</div>
            <div class="home-btn" id="closeSourcePanel" role="button" tabindex="0" aria-label="بستن">
                <i class="fas fa-times" aria-hidden="true"></i>
            </div>
        </div>
        <div class="modal-content source-content">
            <input type="url" id="sourceUrlInput" placeholder="لینک منبع کانفیگ‌ها را وارد کنید..." aria-label="لینک منبع کانفیگ‌ها">
            <button id="submitSourceUrl" role="button">
                <i class="fas fa-save" aria-hidden="true"></i>ثبت
            </button>
        </div>
    </div>

    <div class="notification" id="notification" role="alert" aria-live="assertive" aria-atomic="true">
        <div class="notification-icon" id="notificationIcon">
            <i class="fas fa-check-circle" aria-hidden="true"></i>
        </div>
        <div class="notification-message" id="notificationMessage">عملیات با موفقیت انجام شد</div>
    </div>

    <script>
        class XroVPN {
            constructor() {
                this.elements = {};
                this.state = {
                    activeFilter: 'configs',
                    modals: {},
                    currentTab: 'configs'
                };
                this.cache = {
                    key: 'xro_vpn_configs',
                    expiry: 24 * 60 * 60 * 1000
                };
                // تغییر منبع کانفیگ‌ها و پروکسی‌ها
                this.source = {
                    key: 'xro_vpn_source_url',
                    configs: 'https://gist.githubusercontent.com/xroVPN/12a0c02781cfed451da84e9b802c0912/raw',
                    proxies: 'https://gist.githubusercontent.com/xroVPN/af64cada6eb688cf67a09ea140860b81/raw'
                };
                this.currentProgress = 0;
                this.expiryTimer = null;
                this.init();
            }

            init() {
                this.cacheElements();
                this.bindEvents();
                this.initializeAudio();
                this.loadUIState();
                this.updateSystemInfo();
                this.startBackgroundTasks();
                this.showWelcome();
                this.initializeTabs();
                this.extractConfigs(true);
            }

            cacheElements() {
                const selectors = {
                    loadingOverlay: '#loadingOverlay',
                    permanentWindow: '#permanentWindow',
                    musicPanelBtn: '#musicPanelBtn',
                    musicPanel: '#musicPanel',
                    musicOverlay: '#musicOverlay',
                    configSelectBtn: '#configSelectBtn',
                    publicShopMenu: '#publicShopMenu',
                    configSelectOverlay: '#configSelectOverlay',
                    sourcePanel: '#sourcePanel',
                    sourceOverlay: '#sourceOverlay',
                    sourceUrlInput: '#sourceUrlInput',
                    submitSourceUrl: '#submitSourceUrl',
                    closeSourcePanel: '#closeSourcePanel',
                    notification: '#notification',
                    notificationIcon: '#notificationIcon',
                    notificationMessage: '#notificationMessage',
                    bgMusic: '#bgMusic',
                    buttonClickSound: '#buttonClickSound',
                    generalClickSound: '#generalClickSound',
                    errorSound: '#errorSound',
                    successSound: '#successSound',
                    configsContainer: '#configsContainer',
                    proxyContainer: '#proxyContainer',
                    filterContainer: '#filterContainer',
                    device: '#device',
                    ip: '#ip',
                    ping: '#ping',
                    reportProblemBtn: '#reportProblemBtn',
                    reportProblemMenu: '#reportProblemMenu',
                    reportProblemOverlay: '#reportProblemOverlay',
                    reportProblemText: '#reportProblemText',
                    submitReportProblem: '#submitReportProblem',
                    closeReportProblemMenu: '#closeReportProblemMenu',
                    musicLogo: '#musicLogo',
                    closePublicShopMenu: '#closePublicShopMenu',
                    modalTitleImg: '#modalTitleImg',
                    modalTitle: '#modalTitle',
                    modalProgressText: '#modalProgressText',
                    configsBtn: '#configsBtn',
                    proxyBtn: '#proxyBtn',
                    loginBtnModal: '#loginBtnModal' // اضافه کردن دکمه ورود در مودال
                };

                Object.entries(selectors).forEach(([key, selector]) => {
                    this.elements[key] = document.querySelector(selector);
                    if (!this.elements[key]) console.warn(`Element ${key} not found`);
                });
            }

            initializeTabs() {
                if (this.elements.configsBtn) this.elements.configsBtn.addEventListener('click', () => {
                    this.switchTab('configs');
                });
                if (this.elements.proxyBtn) this.elements.proxyBtn.addEventListener('click', () => {
                    this.switchTab('proxy');
                });
            }

            switchTab(tabName) {
                this.state.currentTab = tabName;
                document.querySelectorAll('.filter-btn').forEach(btn => btn.classList.remove('active'));
                document.querySelectorAll('.tab-content').forEach(tab => tab.style.display = 'none');

                const filterBtns = [this.elements.configsBtn, this.elements.proxyBtn];
                filterBtns.forEach((btn, i) => {
                    if ((i === 0 && tabName === 'configs') || (i === 1 && tabName === 'proxy')) {
                        btn.classList.add('active');
                    } else {
                        btn.classList.remove('active');
                    }
                });

                if (tabName === 'configs') {
                    document.getElementById('configs-tab').style.display = 'block';
                    this.elements.modalTitle.textContent = 'بروزرسانی کانفیگ‌ها';
                    this.extractConfigs(false);
                } else if (tabName === 'proxy') {
                    document.getElementById('proxy-tab').style.display = 'block';
                    this.elements.modalTitle.textContent = 'بروزرسانی پروکسی‌ها';
                    this.loadProxies();
                }
                this.playButtonSound();
            }

            bindEvents() {
                this.bindLoadingAnimation();
                this.bindModalEvents();
                this.bindMusicEvents();
                this.bindConfigEvents();
                this.bindGlobalEvents();
                
                // اضافه کردن رویداد برای دکمه ورود در مودال
                if (this.elements.loginBtnModal) {
                    this.elements.loginBtnModal.addEventListener('click', () => {
                        this.playButtonSound();
                        window.open('https://xrovpn.github.io/bridgefy', '_blank');
                    });
                }
            }

            bindLoadingAnimation() {
                const loadingOverlay = this.elements.loadingOverlay;
                if (!loadingOverlay) return;

                loadingOverlay.classList.add('show');
                
                // نمایش صفحه لودینگ به مدت 3 ثانیه
                setTimeout(() => {
                    loadingOverlay.classList.add('fade-out');
                    setTimeout(() => {
                        loadingOverlay.style.display = 'none';
                        if (this.elements.permanentWindow) {
                            this.elements.permanentWindow.style.display = 'flex';
                        }
                    }, 500);
                }, 3000);
            }

            bindModalEvents() {
                const modals = [
                    { btn: 'configSelectBtn', modal: 'publicShopMenu', overlay: 'configSelectOverlay', close: 'closePublicShopMenu' },
                    { btn: 'musicPanelBtn', modal: 'musicPanel', overlay: 'musicOverlay' },
                    { btn: 'reportProblemBtn', modal: 'reportProblemMenu', overlay: 'reportProblemOverlay', close: 'closeReportProblemMenu' }
                ];

                modals.forEach(({ btn, modal, overlay, close }) => {
                    if (this.elements[btn]) this.elements[btn].addEventListener('click', () => {
                        this.playButtonSound();
                        this.toggleModal(modal, true, overlay);
                        if (close) this.bindCloseEvent(close, modal, overlay);
                    });

                    if (this.elements[overlay]) this.elements[overlay].addEventListener('click', () => {
                        this.playGeneralSound();
                        this.closeAllModals();
                    });
                });

                if (this.elements.closeSourcePanel) {
                    this.elements.closeSourcePanel.addEventListener('click', () => {
                        this.playButtonSound();
                        this.toggleModal('sourcePanel', false, 'sourceOverlay');
                    });
                }

                if (this.elements.modalTitleImg) this.elements.modalTitleImg.addEventListener('click', () => {
                    this.playButtonSound();
                    this.elements.modalTitleImg.classList.add('active');
                    setTimeout(() => this.elements.modalTitleImg.classList.remove('active'), 500);
                    if (this.state.currentTab === 'configs') {
                        this.extractConfigs(true);
                    }
                });
            }

            bindCloseEvent(closeBtn, modalId, overlayId) {
                if (this.elements[closeBtn]) this.elements[closeBtn].addEventListener('click', () => {
                    this.playButtonSound();
                    this.toggleModal(modalId, false, overlayId);
                });
            }

            bindMusicEvents() {
                if (!this.elements.musicLogo || !this.elements.bgMusic) return;
                this.elements.musicLogo.addEventListener('click', () => {
                    this.togglePlayPause();
                });
            }

            bindConfigEvents() {
                if (this.elements.submitReportProblem) this.elements.submitReportProblem.addEventListener('click', () => this.submitReportProblem());
            }

            bindGlobalEvents() {
                document.addEventListener('keydown', event => {
                    if (event.key === 'Escape') this.closeAllModals();
                });

                // جلوگیری از کپی و انتخاب متن
                document.addEventListener('copy', (e) => {
                    e.preventDefault();
                    return false;
                });

                document.addEventListener('selectstart', (e) => {
                    e.preventDefault();
                    return false;
                });

                // جلوگیری از کلیک راست
                document.addEventListener('contextmenu', (e) => {
                    e.preventDefault();
                    return false;
                });
            }

            initializeAudio() {
                this.buttonClickSound = this.elements.buttonClickSound;
                this.generalClickSound = this.elements.generalClickSound;
                this.errorSound = this.elements.errorSound;
                this.successSound = this.elements.successSound;

                if (this.elements.bgMusic) {
                    this.elements.bgMusic.volume = 0.3;
                    this.elements.bgMusic.pause();
                }
            }

            playButtonSound() {
                if (this.buttonClickSound) {
                    this.buttonClickSound.currentTime = 0;
                    this.buttonClickSound.play().catch(err => console.log('Button sound play failed:', err));
                }
            }

            playGeneralSound() {
                if (this.generalClickSound) {
                    this.generalClickSound.currentTime = 0;
                    this.generalClickSound.play().catch(err => console.log('General sound play failed:', err));
                }
            }

            playErrorSound() {
                if (this.errorSound) {
                    this.errorSound.currentTime = 0;
                    this.errorSound.play().catch(err => console.log('Error sound play failed:', err));
                }
            }

            playSuccessSound() {
                if (this.successSound) {
                    this.successSound.currentTime = 0;
                    this.successSound.play().catch(err => console.log('Success sound play failed:', err));
                }
            }

            togglePlayPause() {
                if (!this.elements.bgMusic || !this.elements.musicLogo) return;
                const music = this.elements.bgMusic,
                      logo = this.elements.musicLogo;

                if (music.paused) {
                    music.play().then(() => {
                        logo.classList.add('playing');
                        logo.classList.remove('paused');
                        logo.setAttribute('aria-label', 'توقف موسیقی');
                        this.showNotification('موسیقی در حال پخش', 'success');
                    }).catch(() => this.showNotification('برای پخش موسیقی، ابتدا با صفحه تعامل کنید', 'info'));
                } else {
                    music.pause();
                    logo.classList.remove('playing');
                    logo.classList.add('paused');
                    logo.setAttribute('aria-label', 'پخش موسیقی');
                    this.showNotification('موسیقی متوقف شد', 'info');
                }
            }

            toggleModal(modalId, state, overlayId) {
                if (!this.elements[modalId] || !this.elements[overlayId]) return;

                this.closeAllModals();
                const modal = this.elements[modalId],
                      overlay = this.elements[overlayId];

                if (state) {
                    modal.classList.add('open');
                    overlay.classList.add('show');
                    overlay.classList.remove('hidden');
                    modal.setAttribute('aria-hidden', 'false');
                    overlay.setAttribute('aria-hidden', 'false');
                } else {
                    modal.classList.remove('open');
                    overlay.classList.remove('show');
                    overlay.classList.add('hidden');
                    modal.setAttribute('aria-hidden', 'true');
                    overlay.setAttribute('aria-hidden', 'true');
                }
                this.saveUIState();
            }

            closeAllModals() {
                ['publicShopMenu', 'musicPanel', 'reportProblemMenu', 'sourcePanel'].forEach(id => {
                    if (this.elements[id]) this.elements[id].classList.remove('open');
                });

                ['configSelectOverlay', 'musicOverlay', 'reportProblemOverlay', 'sourceOverlay'].forEach(id => {
                    if (this.elements[id]) {
                        this.elements[id].classList.remove('show');
                        this.elements[id].classList.add('hidden');
                    }
                });
                this.saveUIState();
            }

            showNotification(message, type = 'success') {
                if (!this.elements.notification) return;

                this.elements.notification.className = 'notification';
                this.elements.notificationIcon.className = 'notification-icon';

                const icons = {
                    success: '<i class="fas fa-check-circle"></i>',
                    error: '<i class="fas fa-times-circle"></i>',
                    info: '<i class="fas fa-info-circle"></i>'
                };

                this.elements.notification.classList.add(`notification-${type}`);
                this.elements.notificationIcon.innerHTML = icons[type] || icons.success;
                this.elements.notificationMessage.textContent = message;

                if (type === 'error') {
                    this.playErrorSound();
                } else if (type === 'success') {
                    this.playSuccessSound();
                }

                this.elements.notification.classList.add('show');
                setTimeout(() => this.elements.notification.classList.remove('show'), 3000);
            }

            updateSystemInfo() {
                if (this.elements.device) this.elements.device.textContent = /Mobile|Android|iPhone|iPad/i.test(navigator.userAgent) ? 'موبایل' : 'دسکتاپ';
                this.updateIP();
                this.updatePing();
            }

            updateIP() {
                if (!this.elements.ip) return;

                fetch('https://api.ipify.org?format=json', { cache: 'no-store' })
                    .then(res => res.ok ? res.json() : Promise.reject('IP fetch failed'))
                    .then(data => {
                        if (this.elements.ip) this.elements.ip.textContent = this.toPersianDigits(data.ip);
                    })
                    .catch(() => {
                        if (this.elements.ip) this.elements.ip.textContent = 'نامشخص';
                    });
            }

            updatePing() {
                if (!this.elements.ping) return;

                const start = performance.now();
                fetch('https://cloudflare.com/cdn-cgi/trace', { method: 'HEAD', cache: 'no-store' })
                    .then(() => Math.round(performance.now() - start))
                    .then(ping => {
                        if (this.elements.ping) this.elements.ping.textContent = `${this.toPersianDigits(ping.toString())} م‌ث`;
                    })
                    .catch(() => {
                        if (this.elements.ping) this.elements.ping.textContent = 'نامشخص';
                    });
            }

            startBackgroundTasks() {
                setInterval(() => this.updateIP(), 10000);
                setInterval(() => this.updatePing(), 5000);
                setInterval(() => this.refreshConfigPings(), 10000);
            }

            showWelcome() {
                this.showNotification('به ایکسرو خوش آمدید', 'success');
            }

            toPersianDigits(str) {
                return str.replace(/[0-9]/g, d => '۰۱۲۳۴۵۶۷۸۹'[parseInt(d)]);
            }

            getRemainingTime() {
                const cached = localStorage.getItem(this.cache.key);
                if (!cached) return 24 * 60 * 60 * 1000;

                try {
                    const { data, timestamp, expiry } = JSON.parse(cached);
                    const timeElapsed = Date.now() - timestamp;
                    return Math.max(0, expiry - timeElapsed);
                } catch {
                    return 24 * 60 * 60 * 1000;
                }
            }

            async submitReportProblem() {
                this.playButtonSound();
                const textarea = this.elements.reportProblemText,
                      btn = this.elements.submitReportProblem;
                if (!textarea || !btn) return;

                const message = textarea.value.trim();
                if (!message) {
                    this.showNotification('لطفاً متن گزارش را وارد کنید', 'error');
                    return;
                }

                const originalText = btn.innerHTML;
                btn.disabled = true;
                btn.innerHTML = '<i class="fas fa-spinner loading-spinner-small" aria-hidden="true"></i> در حال ارسال...';

                try {
                    const token = 'YOUR_TELEGRAM_BOT_TOKEN',
                          adminId = 'YOUR_ADMIN_ID';

                    const response = await fetch(`https://api.telegram.org/bot${token}/sendMessage`, {
                        method: 'POST',
                        headers: { 'Content-Type': 'application/json' },
                        body: JSON.stringify({
                            chat_id: adminId,
                            text: `گزارش مشکل جدید:\n${message}`
                        })
                    });

                    if (!response.ok) throw new Error('خطا در ارسال گزارش');
                    this.showNotification('گزارش با موفقیت ارسال شد', 'success');
                    textarea.value = '';
                    this.toggleModal('reportProblemMenu', false, 'reportProblemOverlay');
                } catch (error) {
                    this.showNotification(`خطا: ${error.message}`, 'error');
                } finally {
                    btn.disabled = false;
                    btn.innerHTML = originalText;
                }
            }

            parseConfig(config) {
                try {
                    const match = config.match(/^(hysteria2|vless|trojan|ss|vmess|wireguard):\/\/(.+)/i);
                    if (!match) return null;

                    const [, protocol, rest] = match;

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
            }

            formatConfig(config) {
                try {
                    const match = config.match(/^([^:]+):\/\/(.+)/i);
                    if (!match) return config;

                    const [, protocol, rest] = match;

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
            }

            async testPing(host) {
                return new Promise(resolve => {
                    const start = performance.now(),
                          controller = new AbortController(),
                          timeout = setTimeout(() => controller.abort(), 5000);

                    fetch(`https://${host}/generate_204`, {
                        method: 'HEAD',
                        mode: 'no-cors',
                        signal: controller.signal,
                        cache: 'no-store'
                    }).then(() => {
                        clearTimeout(timeout);
                        resolve({ success: true, ping: Math.round(performance.now() - start) });
                    }).catch(err => {
                        clearTimeout(timeout);
                        resolve({ success: false, error: err.name === 'AbortError' ? 'تایم‌اوت' : 'عدم اتصال' });
                    });
                });
            }

            getCachedConfigs() {
                try {
                    const cached = localStorage.getItem(this.cache.key);
                    if (!cached) return null;

                    const { data, timestamp, expiry } = JSON.parse(cached);
                    const timeElapsed = Date.now() - timestamp;

                    if (timeElapsed > this.cache.expiry) {
                        localStorage.removeItem(this.cache.key);
                        return null;
                    }
                    return data;
                } catch {
                    localStorage.removeItem(this.cache.key);
                    return null;
                }
            }

            setCachedConfigs(data) {
                try {
                    localStorage.setItem(this.cache.key, JSON.stringify({
                        data,
                        timestamp: Date.now(),
                        expiry: this.cache.expiry,
                        cachedAt: new Date().toLocaleString('fa-IR')
                    }));
                } catch (error) {
                    console.error('Cache save error:', error);
                }
            }

            deleteConfig(config) {
                const cachedConfigs = this.getCachedConfigs();
                if (cachedConfigs) {
                    const updatedConfigs = cachedConfigs.filter(c => c.config !== config);
                    this.setCachedConfigs(updatedConfigs);
                    this.renderConfigs(updatedConfigs);
                    this.showNotification('کانفیگ با موفقیت حذف شد', 'success');
                }
            }

            saveUIState() {
                try {
                    const state = {
                        isPublicShopMenuOpen: !!this.elements.publicShopMenu?.classList.contains('open'),
                        isMusicPanelOpen: !!this.elements.musicPanel?.classList.contains('open'),
                        isReportProblemMenuOpen: !!this.elements.reportProblemMenu?.classList.contains('open'),
                        isSourcePanelOpen: !!this.elements.sourcePanel?.classList.contains('open'),
                        currentTab: this.state.currentTab
                    };
                    sessionStorage.setItem('xro_vpn_ui_state', JSON.stringify(state));
                } catch {}
            }

            loadUIState() {
                try {
                    const state = sessionStorage.getItem('xro_vpn_ui_state');
                    if (!state) return;

                    const { isPublicShopMenuOpen, isMusicPanelOpen, isReportProblemMenuOpen, isSourcePanelOpen, currentTab } = JSON.parse(state);
                    this.state.currentTab = currentTab || 'configs';

                    if (isPublicShopMenuOpen && this.elements.publicShopMenu && this.elements.configSelectOverlay) {
                        this.toggleModal('publicShopMenu', true, 'configSelectOverlay');
                        setTimeout(() => {
                            this.switchTab(this.state.currentTab);
                        }, 100);
                    }
                    if (isMusicPanelOpen && this.elements.musicPanel && this.elements.musicOverlay) this.toggleModal('musicPanel', true, 'musicOverlay');
                    if (isReportProblemMenuOpen && this.elements.reportProblemMenu && this.elements.reportProblemOverlay) this.toggleModal('reportProblemMenu', true, 'reportProblemOverlay');
                    if (isSourcePanelOpen && this.elements.sourcePanel && this.elements.sourceOverlay) this.toggleModal('sourcePanel', true, 'sourceOverlay');
                } catch {}
            }

            updateProgress(current, total) {
                if (!this.elements.modalProgressText || !this.elements.modalTitle) return;

                this.currentProgress = current;
                this.elements.modalTitle.style.display = 'none';
                this.elements.modalProgressText.style.display = 'inline';
                this.elements.modalProgressText.textContent = `${this.toPersianDigits(current.toString())} از ${this.toPersianDigits(total.toString())} انجام شده`;

                if (current >= total) {
                    setTimeout(() => {
                        this.elements.modalProgressText.style.display = 'none';
                        this.elements.modalTitle.style.display = 'inline';
                        this.currentProgress = 0;
                    }, 1000);
                }
            }

            async shareConfig(config) {
                this.playButtonSound();
                
                const shareText = `کانفیگ ارسالی از کانال @xroVPN\n\n${config}`;
                
                if (navigator.share) {
                    try {
                        await navigator.share({
                            title: 'کانفیگ VPN ایکسرو',
                            text: shareText
                        });
                        this.showNotification('کانفیگ با موفقیت به اشتراک گذاشته شد', 'success');
                    } catch (error) {
                        if (error.name !== 'AbortError') {
                            this.showNotification('خطا در اشتراک‌گذاری کانفیگ', 'error');
                        }
                    }
                } else if (navigator.clipboard) {
                    try {
                        await navigator.clipboard.writeText(shareText);
                        this.showNotification('کانفیگ در کلیپ‌بورد کپی شد', 'success');
                    } catch {
                        this.showNotification('خطا در کپی کردن کانفیگ', 'error');
                    }
                } else {
                    this.showNotification('اشتراک‌گذاری در این مرورگر پشتیبانی نمی‌شود', 'error');
                }
            }

            async updateConfigPing(config, pingElement) {
                try {
                    if (!config || !pingElement) return;

                    const parsed = this.parseConfig(config.config);
                    if (!parsed) return;

                    const pingResult = await this.testPing(parsed.host);
                    if (pingResult.success) {
                        pingElement.textContent = `${this.toPersianDigits(pingResult.ping.toString())} م‌ث`;
                        pingElement.className = 'ping-result';
                        pingElement.classList.add(pingResult.ping < 300 ? 'fast' : pingResult.ping < 600 ? 'medium' : 'slow');
                    } else {
                        pingElement.textContent = 'نامشخص';
                        pingElement.className = 'ping-result slow';
                    }
                } catch {
                    console.error('Config ping error');
                    if (pingElement) {
                        pingElement.textContent = 'نامشخص';
                        pingElement.className = 'ping-result slow';
                    }
                }
            }

            refreshConfigPings() {
                if (!this.elements.configsContainer) return;

                const configBoxes = this.elements.configsContainer.querySelectorAll('.config-box');
                if (configBoxes.length === 0) return;

                configBoxes.forEach(box => {
                    const config = box.dataset.config,
                          pingElement = box.querySelector('.ping-result');
                    if (config && pingElement) {
                        try {
                            this.updateConfigPing(JSON.parse(config), pingElement);
                        } catch {}
                    }
                });
            }

            async extractConfigs(forceRefresh = false) {
                if (!this.elements.configsContainer || this.state.currentTab !== 'configs') return;

                this.currentProgress = 0;
                if (!forceRefresh) {
                    const cachedConfigs = this.getCachedConfigs();
                    if (cachedConfigs) {
                        this.updateProgress(cachedConfigs.length, cachedConfigs.length);
                        this.renderConfigs(cachedConfigs);
                        return;
                    }
                }

                this.elements.configsContainer.innerHTML = '<div class="loading-container"><div class="loading-dots"><div class="loading-dot"></div><div class="loading-dot"></div><div class="loading-dot"></div></div></div>';

                try {
                    const url = this.source.configs;
                    const response = await fetch(url, { mode: 'cors', cache: 'no-store' });

                    if (!response.ok) {
                        this.elements.configsContainer.innerHTML = '<div class="error" role="alert">خطا در دریافت کانفیگ‌ها</div>';
                        this.showNotification('خطا در دریافت کانفیگ‌ها: سرور پاسخ نداد', 'error');
                        return;
                    }

                    const textContent = await response.text();
                    let configs = textContent.split(/[\n\r]+/).map(c => c.trim()).filter(Boolean);

                    if (!configs.length) {
                        this.elements.configsContainer.innerHTML = '<div class="error" role="alert">هیچ کانفیگی یافت نشد</div>';
                        this.showNotification('هیچ کانفیگی در فایل موجود نیست', 'error');
                        return;
                    }

                    const totalConfigs = configs.length,
                          validConfigs = [],
                          batchSize = 10;

                    for (let i = 0; i < configs.length; i += batchSize) {
                        const batch = configs.slice(i, i + batchSize),
                              results = await Promise.all(batch.map(async config => {
                                  try {
                                      const formattedConfig = this.formatConfig(config),
                                            parsed = this.parseConfig(config);
                                      if (!parsed) return null;

                                      const pingResult = await this.testPing(parsed.host);
                                      this.updateProgress(++this.currentProgress, totalConfigs);

                                      if (!pingResult.success || pingResult.ping > 600) return null;

                                      return {
                                          config: formattedConfig,
                                          ping: pingResult.ping,
                                          protocol: parsed.protocol
                                      };
                                  } catch {
                                      return null;
                                  }
                              }));

                        validConfigs.push(...results.filter(Boolean));
                    }

                    if (!validConfigs.length) {
                        this.elements.configsContainer.innerHTML = '<div class="error" role="alert">هیچ کانفیگ معتبری یافت نشد</div>';
                        this.showNotification('هیچ کانفیگ معتبری یافت نشد', 'error');
                        return;
                    }

                    this.setCachedConfigs(validConfigs);
                    this.renderConfigs(validConfigs);
                    this.updateProgress(this.currentProgress, totalConfigs);
                } catch (error) {
                    this.elements.configsContainer.innerHTML = '<div class="error" role="alert">خطا در بارگذاری کانفیگ‌ها</div>';
                    this.showNotification(`خطا: ${error.message}`, 'error');
                    console.error('Config fetch error:', error);
                }
            }

            renderConfigs(configs) {
                if (!this.elements.configsContainer || this.state.currentTab !== 'configs') return;

                this.elements.configsContainer.innerHTML = '';
                if (!configs || configs.length === 0) {
                    this.elements.configsContainer.innerHTML = '<div class="error" role="alert">هیچ کانفیگی موجود نیست</div>';
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

                configs.sort((a, b) => a.ping - b.ping).forEach((config, i) => {
                    const box = document.createElement('div');
                    box.className = 'config-box';
                    box.draggable = true;
                    box.style.opacity = '0';
                    box.style.animation = `slideInRight 0.6s ease-out ${i * 0.1}s forwards`;
                    box.dataset.protocol = config.protocol.toLowerCase();
                    box.dataset.protocolFa = protocolNames[config.protocol.toLowerCase()] || config.protocol;
                    box.dataset.config = JSON.stringify(config);
                    box.setAttribute('role', 'button');
                    box.setAttribute('tabindex', '0');

                    const pingClass = config.ping < 300 ? 'fast' : config.ping < 600 ? 'medium' : 'slow';

                    // تغییر متن دکمه کپی به "کپی"
                    box.innerHTML = `
                        <button class="share-btn" aria-label="اشتراک‌گذاری">
                            <i class="fas fa-share-square" aria-hidden="true"></i>
                        </button>
                        <button class="delete-btn" aria-label="حذف">
                            <i class="fas fa-trash" aria-hidden="true"></i>
                        </button>
                        <div class="config-logo-container" aria-hidden="true">
                            <span class="config-logo"><i class="fas fa-server"></i></span>
                        </div>
                        <div class="ping-result ${pingClass}" aria-live="polite">
                            <i class="fas fa-tachometer-alt" aria-hidden="true"></i> ${this.toPersianDigits(config.ping.toString())} م‌ث
                        </div>
                        <button class="copy-btn" aria-label="کپی کانفیگ">
                            <i class="fas fa-clipboard" aria-hidden="true"></i> کپی
                        </button>
                    `;

                    const copyBtn = box.querySelector('.copy-btn'),
                          shareBtn = box.querySelector('.share-btn'),
                          deleteBtn = box.querySelector('.delete-btn');

                    if (copyBtn) copyBtn.addEventListener('click', e => {
                        e.stopPropagation();
                        this.playButtonSound();
                        navigator.clipboard.writeText(config.config).then(() => this.showNotification('کانفیگ کپی شد', 'success')).catch(() => this.showNotification('خطا در کپی کردن کانفیگ', 'error'));
                    });

                    if (shareBtn) shareBtn.addEventListener('click', e => {
                        e.stopPropagation();
                        this.shareConfig(config.config);
                    });

                    if (deleteBtn) deleteBtn.addEventListener('click', e => {
                        e.stopPropagation();
                        this.playButtonSound();
                        box.remove();
                        this.deleteConfig(config.config);
                    });

                    box.addEventListener('click', e => {
                        if (!e.target.closest('button')) {
                            return;
                        }
                    });

                    let holdTimeout;
                    const startDrag = () => {
                        holdTimeout = setTimeout(() => box.classList.add('dragging'), 3000);
                    }, endDrag = () => {
                        clearTimeout(holdTimeout);
                        box.classList.remove('dragging');
                    };

                    ['mousedown', 'touchstart'].forEach(event => box.addEventListener(event, startDrag));
                    ['mouseup', 'mouseleave', 'touchend', 'touchcancel'].forEach(event => box.addEventListener(event, endDrag));

                    box.addEventListener('dragstart', ev => {
                        ev.dataTransfer.setData('text/plain', JSON.stringify(config));
                        box.classList.add('dragging');
                    });

                    box.addEventListener('dragend', () => box.classList.remove('dragging'));

                    this.elements.configsContainer.appendChild(box);
                });

                if (this.elements.configsContainer) {
                    this.elements.configsContainer.addEventListener('dragover', ev => ev.preventDefault());
                    this.elements.configsContainer.addEventListener('drop', ev => {
                        ev.preventDefault();
                        const draggedData = ev.dataTransfer.getData('text/plain');
                        try {
                            const draggedConfig = JSON.parse(draggedData),
                                  configBoxes = Array.from(this.elements.configsContainer.querySelectorAll('.config-box')),
                                  draggedBox = configBoxes.find(box => JSON.parse(box.dataset.config).config === draggedConfig.config),
                                  dropBox = ev.target.closest('.config-box');

                            if (draggedBox && dropBox && draggedBox !== dropBox) {
                                const cachedConfigs = this.getCachedConfigs();
                                if (cachedConfigs) {
                                    const draggedIndex = cachedConfigs.findIndex(c => c.config === draggedConfig.config),
                                          dropIndex = configBoxes.findIndex(box => box === dropBox),
                                          updatedConfigs = [...cachedConfigs];

                                    updatedConfigs.splice(draggedIndex, 1);
                                    updatedConfigs.splice(dropIndex, 0, draggedConfig);
                                    this.setCachedConfigs(updatedConfigs);
                                    this.renderConfigs(updatedConfigs);
                                }
                            }
                        } catch {}
                    });
                }
                this.saveUIState();
                this.refreshConfigPings();
            }

            // اضافه کردن متد برای بارگذاری پروکسی‌ها
            async loadProxies() {
                if (!this.elements.proxyContainer || this.state.currentTab !== 'proxy') return;

                this.elements.proxyContainer.innerHTML = '<div class="loading-container"><div class="loading-dots"><div class="loading-dot"></div><div class="loading-dot"></div><div class="loading-dot"></div></div></div>';

                try {
                    const url = this.source.proxies;
                    const response = await fetch(url, { mode: 'cors', cache: 'no-store' });

                    if (!response.ok) {
                        this.elements.proxyContainer.innerHTML = '<div class="error" role="alert">خطا در دریافت پروکسی‌ها</div>';
                        return;
                    }

                    const textContent = await response.text();
                    let proxies = textContent.split(/[\n\r]+/).map(p => p.trim()).filter(Boolean);

                    if (!proxies.length) {
                        this.elements.proxyContainer.innerHTML = '<div class="error" role="alert">هیچ پروکسی یافت نشد</div>';
                        return;
                    }

                    this.renderProxies(proxies);
                } catch (error) {
                    this.elements.proxyContainer.innerHTML = '<div class="error" role="alert">خطا در بارگذاری پروکسی‌ها</div>';
                    console.error('Proxy fetch error:', error);
                }
            }

            renderProxies(proxies) {
                if (!this.elements.proxyContainer) return;

                this.elements.proxyContainer.innerHTML = '';
                proxies.forEach((proxy, i) => {
                    const box = document.createElement('div');
                    box.className = 'config-box';
                    box.style.opacity = '0';
                    box.style.animation = `slideInRight 0.6s ease-out ${i * 0.1}s forwards`;
                    box.setAttribute('role', 'button');
                    box.setAttribute('tabindex', '0');

                    // تغییر متن دکمه اتصال برای پروکسی‌ها به "اتصال"
                    box.innerHTML = `
                        <div class="config-logo-container" aria-hidden="true">
                            <span class="config-logo"><i class="fas fa-globe"></i></span>
                        </div>
                        <div class="ping-result" aria-live="polite">
                            <i class="fas fa-link" aria-hidden="true"></i> پروکسی
                        </div>
                        <button class="copy-btn connect-proxy-btn" aria-label="اتصال به پروکسی" data-proxy="${proxy}">
                            <i class="fas fa-plug" aria-hidden="true"></i> اتصال
                        </button>
                    `;

                    const connectBtn = box.querySelector('.connect-proxy-btn');
                    if (connectBtn) {
                        connectBtn.addEventListener('click', e => {
                            e.stopPropagation();
                            this.playButtonSound();
                            this.connectToProxy(proxy);
                        });
                    }

                    this.elements.proxyContainer.appendChild(box);
                });
            }

            connectToProxy(proxy) {
                // باز کردن تلگرام با پروکسی
                try {
                    // تلاش برای باز کردن تلگرام با پروکسی
                    window.open(`tg://proxy?server=${proxy.split(':')[0]}&port=${proxy.split(':')[1] || '443'}`, '_blank');
                    
                    // اگر تلگرام نصب نباشد، باز کردن لینک وب تلگرام
                    setTimeout(() => {
                        window.open('https://web.telegram.org', '_blank');
                    }, 1000);
                    
                    this.showNotification('اتصال به تلگرام با پروکسی انجام شد', 'success');
                } catch (error) {
                    this.showNotification('خطا در اتصال به پروکسی', 'error');
                }
            }
        }

        new XroVPN();
    </script>
</body>
</html>
