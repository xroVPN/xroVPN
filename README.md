<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>XRO VPN | فروشگاه کانفیگ اختصاصی</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@400;500;700&display=swap" rel="stylesheet">
    <style>
        /* سیستم طراحی پیشرفته */
        :root {
            --primary: #6e45e2;
            --primary-light: #9d8aff;
            --primary-dark: #4a2bbd;
            --secondary: #ff4757;
            --secondary-light: #ff6b81;
            --accent: #ff7e5f;
            --accent-dark: #f95a3b;
            --background: #0f0f1a;
            --surface: #1a1a2e;
            --surface-light: #2a2a3e;
            --on-surface: #ffffff;
            --on-surface-light: rgba(255,255,255,0.8);
            --success: #2ed573;
            --info: #1e90ff;
            --warning: #ffa502;
            --error: #ff4757;
            --radius-lg: 24px;
            --radius-md: 16px;
            --radius-sm: 12px;
            --shadow-sm: 0 2px 8px rgba(0,0,0,0.1);
            --shadow-md: 0 4px 16px rgba(0,0,0,0.2);
            --shadow-lg: 0 8px 32px rgba(0,0,0,0.3);
            --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            --transition-slow: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            -webkit-tap-highlight-color: transparent;
            -webkit-user-select: none;
            -moz-user-select: none;
            -ms-user-select: none;
            user-select: none;
        }

        body {
            font-family: 'Vazirmatn', sans-serif;
            background: var(--background);
            color: var(--on-surface);
            line-height: 1.6;
            overflow-x: hidden;
            background-image: 
                radial-gradient(circle at 20% 30%, rgba(110, 69, 226, 0.15) 0%, transparent 30%),
                radial-gradient(circle at 80% 70%, rgba(255, 71, 87, 0.15) 0%, transparent 30%);
            touch-action: manipulation;
        }

        /* صفحه لودینگ پیشرفته */
        .loading-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--background);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 1000;
            overflow: hidden;
        }

        .logo-container {
            position: relative;
            margin-bottom: 60px;
            animation: fadeIn 0.8s both;
        }

        .logo-animation {
            width: 150px;
            height: 150px;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
        }

        .logo-text {
            font-size: 72px;
            font-weight: 700;
            position: relative;
        }

        .logo-text span {
            position: relative;
            z-index: 2;
        }

        .logo-text .heart {
            color: var(--secondary);
            animation: pulse 1.5s infinite;
        }

        .logo-text .x {
            color: white;
        }

        .heart-progress {
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 0;
            background: var(--secondary);
            z-index: 1;
            border-radius: 0 0 10px 10px;
            transition: height 0.3s ease;
        }

        .loading-progress {
            width: 80%;
            max-width: 300px;
            height: 12px;
            background: rgba(255,255,255,0.1);
            border-radius: 6px;
            overflow: hidden;
            position: relative;
        }

        .progress-bar {
            height: 100%;
            width: 0%;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            border-radius: 6px;
            transition: width 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .progress-bar::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(90deg, 
                transparent, 
                rgba(255,255,255,0.4), 
                transparent);
            animation: loadingShine 1.5s infinite;
        }

        /* صفحه لاگین */
        .login-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--background);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 1001;
            opacity: 0;
            pointer-events: none;
            transition: var(--transition-slow);
        }

        .login-screen.active {
            opacity: 1;
            pointer-events: all;
        }

        .login-container {
            background: var(--surface);
            border-radius: var(--radius-lg);
            padding: 40px;
            width: 90%;
            max-width: 400px;
            text-align: center;
            box-shadow: var(--shadow-lg);
            transform: scale(0.9);
            transition: var(--transition-slow);
            position: relative;
            overflow: hidden;
        }

        .login-container::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(
                to bottom right,
                transparent,
                transparent,
                rgba(110, 69, 226, 0.1),
                rgba(255, 71, 87, 0.1)
            );
            transform: rotate(30deg);
            animation: shine 6s linear infinite;
        }

        .login-screen.active .login-container {
            transform: scale(1);
        }

        .login-title {
            font-size: 24px;
            margin-bottom: 24px;
            color: var(--primary);
            position: relative;
            z-index: 2;
        }

        .fingerprint-container {
            position: relative;
            width: 180px;
            height: 180px;
            margin: 0 auto 20px;
        }

        .fingerprint-circle {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            background: var(--surface-light);
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
            box-shadow: 
                inset 0 0 30px rgba(0,0,0,0.5),
                0 0 0 10px rgba(110, 69, 226, 0.2),
                0 0 0 20px rgba(110, 69, 226, 0.1);
        }

        .fingerprint-icon {
            font-size: 80px;
            color: var(--primary);
            transition: var(--transition);
            position: relative;
            z-index: 2;
        }

        .fingerprint-progress {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border-radius: 50%;
            background: conic-gradient(var(--primary) 0%, transparent 0%);
            transition: var(--transition-slow);
            z-index: 1;
        }

        .fingerprint-scan {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 20px;
            background: linear-gradient(to bottom, 
                rgba(110, 69, 226, 0.5), 
                transparent);
            z-index: 3;
            animation: scan 3s infinite;
            opacity: 0;
        }

        .fingerprint-btn {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 140px;
            height: 140px;
            border-radius: 50%;
            background: var(--primary);
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            border: none;
            outline: none;
            z-index: 4;
            box-shadow: 
                0 0 0 6px rgba(110, 69, 226, 0.3),
                0 0 0 12px rgba(110, 69, 226, 0.2),
                0 0 30px rgba(110, 69, 226, 0.4);
            transition: var(--transition);
        }

        .fingerprint-btn i {
            font-size: 60px;
            color: white;
            transition: var(--transition);
        }

        .fingerprint-btn.active {
            transform: translate(-50%, -50%) scale(0.95);
            box-shadow: 
                0 0 0 4px rgba(110, 69, 226, 0.4),
                0 0 0 10px rgba(110, 69, 226, 0.3),
                0 0 25px rgba(110, 69, 226, 0.5);
        }

        .fingerprint-btn.active i {
            transform: scale(0.9);
        }

        .login-text {
            margin-top: 20px;
            font-size: 14px;
            color: var(--on-surface-light);
            position: relative;
            z-index: 2;
        }

        .login-error {
            color: var(--secondary);
            margin-top: 10px;
            font-size: 13px;
            display: none;
            position: relative;
            z-index: 2;
        }

        /* صفحه اصلی */
        .app-container {
            display: none;
            max-width: 100%;
            margin: 0 auto;
            opacity: 0;
            animation: fadeInUp 0.8s 0.3s forwards;
        }

        /* هدر */
        .app-header {
            padding: 20px 16px;
            position: relative;
            z-index: 10;
        }

        .header-content {
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .logo {
            display: flex;
            align-items: center;
        }

        .logo-icon {
            width: 48px;
            height: 48px;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            border-radius: 14px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-left: 12px;
            box-shadow: var(--shadow-md);
        }

        .logo-icon i {
            font-size: 20px;
            color: white;
        }

        .logo-text-header {
            font-size: 20px;
            font-weight: 700;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        /* کنترل موزیک */
        .music-control-btn {
            background: transparent;
            border: none;
            color: var(--on-surface);
            font-size: 20px;
            cursor: pointer;
            transition: var(--transition);
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            position: relative;
        }

        .music-control-btn::after {
            content: '';
            position: absolute;
            top: -5px;
            right: -5px;
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background: var(--secondary);
            opacity: 0;
            transition: var(--transition);
        }

        .music-control-btn.active::after {
            opacity: 1;
        }

        .music-control-btn:hover {
            background: rgba(255,255,255,0.1);
        }

        /* مودال کنترل موزیک */
        .music-modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.8);
            display: none;
            align-items: center;
            justify-content: center;
            z-index: 1000;
            backdrop-filter: blur(10px);
            animation: fadeIn 0.3s ease;
        }

        .music-content {
            background: var(--surface);
            border-radius: var(--radius-lg);
            width: 90%;
            max-width: 400px;
            padding: 24px;
            box-shadow: var(--shadow-lg);
            position: relative;
            text-align: center;
            transform: translateY(20px);
            opacity: 0;
            transition: var(--transition-slow);
        }

        .music-modal.active .music-content {
            transform: translateY(0);
            opacity: 1;
        }

        .close-music {
            position: absolute;
            top: 16px;
            left: 16px;
            font-size: 24px;
            color: var(--on-surface-light);
            cursor: pointer;
            transition: var(--transition);
        }

        .close-music:hover {
            color: var(--accent);
            transform: rotate(90deg);
        }

        .music-title {
            font-size: 20px;
            margin-bottom: 24px;
            color: var(--primary);
        }

        .music-cover {
            width: 180px;
            height: 180px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
            color: white;
            font-size: 60px;
            box-shadow: 0 10px 40px rgba(110, 69, 226, 0.5);
            position: relative;
            overflow: hidden;
        }

        .music-cover::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, 
                rgba(255,255,255,0.1), 
                transparent);
            opacity: 0;
            transition: var(--transition);
        }

        .music-cover:hover::before {
            opacity: 1;
        }

        .song-info {
            margin-bottom: 24px;
        }

        .song-name {
            font-size: 18px;
            font-weight: 600;
            margin-bottom: 4px;
        }

        .song-artist {
            font-size: 14px;
            color: var(--on-surface-light);
        }

        .music-progress-container {
            margin-bottom: 20px;
        }

        .music-progress {
            height: 6px;
            background: rgba(255,255,255,0.1);
            border-radius: 3px;
            margin-bottom: 8px;
            overflow: hidden;
        }

        .music-progress-bar {
            height: 100%;
            width: 0%;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            transition: width 0.1s linear;
        }

        .music-time {
            display: flex;
            justify-content: space-between;
            font-size: 12px;
            color: var(--on-surface-light);
        }

        .music-controls {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 20px;
        }

        .control-btn {
            background: var(--surface-light);
            color: var(--on-surface);
            border: none;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: var(--transition);
            box-shadow: var(--shadow-sm);
        }

        .control-btn:hover {
            transform: scale(1.05);
            box-shadow: var(--shadow-md);
            background: var(--primary);
            color: white;
        }

        .control-btn i {
            font-size: 20px;
        }

        .play-btn {
            width: 70px;
            height: 70px;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            color: white;
        }

        .play-btn i {
            font-size: 28px;
        }

        /* استوری‌های پیشرفته */
        .stories-container {
            padding: 16px 8px;
            display: flex;
            gap: 16px;
            overflow-x: auto;
            scroll-snap-type: x mandatory;
            scrollbar-width: none;
        }

        .stories-container::-webkit-scrollbar {
            display: none;
        }

        .story-item {
            scroll-snap-align: start;
            flex: 0 0 auto;
            width: 100px;
            display: flex;
            flex-direction: column;
            align-items: center;
            text-decoration: none;
            position: relative;
        }

        .story-avatar {
            width: 90px;
            height: 90px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            margin-bottom: 8px;
        }

        .story-avatar::before {
            content: '';
            position: absolute;
            inset: -4px;
            border-radius: 50%;
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            z-index: -1;
            filter: blur(10px);
            opacity: 0.8;
            animation: rotateGradient 4s linear infinite;
        }

        .story-avatar-inner {
            width: 84px;
            height: 84px;
            border-radius: 50%;
            background: var(--surface);
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
            border: 3px solid var(--primary);
            transition: var(--transition);
        }

        .story-item:hover .story-avatar-inner {
            transform: scale(1.05);
        }

        .story-avatar-inner img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .story-badge {
            position: absolute;
            bottom: 0;
            right: 0;
            width: 28px;
            height: 28px;
            border-radius: 50%;
            background: var(--accent);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 14px;
            border: 3px solid var(--surface);
            box-shadow: var(--shadow-sm);
        }

        .story-label {
            font-size: 13px;
            color: var(--on-surface);
            text-align: center;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
            max-width: 100%;
            font-weight: 500;
            transition: var(--transition);
        }

        .story-item:hover .story-label {
            color: var(--primary);
        }

        .story-new {
            position: absolute;
            top: -5px;
            right: -5px;
            width: 24px;
            height: 24px;
            border-radius: 50%;
            background: var(--secondary);
            border: 3px solid var(--surface);
            animation: pulse 1.5s infinite;
        }

        /* مودال استوری */
        .story-modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--background);
            display: none;
            align-items: center;
            justify-content: center;
            z-index: 1000;
            animation: fadeIn 0.3s ease;
        }

        .story-content {
            background: var(--surface);
            border-radius: var(--radius-lg);
            width: 90%;
            max-width: 400px;
            padding: 24px;
            box-shadow: var(--shadow-lg);
            position: relative;
            text-align: center;
            transform: translateY(20px);
            opacity: 0;
            transition: var(--transition-slow);
        }

        .story-modal.active .story-content {
            transform: translateY(0);
            opacity: 1;
        }

        .close-story {
            position: absolute;
            top: 16px;
            left: 16px;
            font-size: 24px;
            color: var(--on-surface-light);
            cursor: pointer;
            transition: var(--transition);
        }

        .close-story:hover {
            color: var(--accent);
            transform: rotate(90deg);
        }

        .story-title {
            font-size: 20px;
            margin-bottom: 16px;
            color: var(--primary);
        }

        .story-text {
            font-size: 14px;
            line-height: 1.8;
            margin-bottom: 20px;
            white-space: pre-line;
        }

        /* اعلانات */
        .announcement-container {
            padding: 0 16px;
            margin-bottom: 16px;
        }

        .announcement-box {
            background: var(--surface);
            border-radius: var(--radius-md);
            padding: 16px;
            box-shadow: var(--shadow-sm);
            border: 1px solid rgba(110, 69, 226, 0.2);
            overflow: hidden;
            position: relative;
        }

        .announcement-box::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, 
                rgba(110, 69, 226, 0.1) 0%, 
                transparent 50%, 
                rgba(255, 71, 87, 0.1) 100%);
            z-index: 0;
        }

        .announcement-text {
            position: relative;
            z-index: 1;
            font-size: 14px;
            line-height: 1.6;
            color: var(--on-surface);
            min-height: 48px;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
        }

        /* تب‌های اصلی */
        .main-tabs {
            display: flex;
            background: var(--surface);
            border-radius: var(--radius-md);
            margin: 16px;
            overflow: hidden;
            box-shadow: var(--shadow-sm);
        }

        .main-tab {
            flex: 1;
            padding: 12px;
            border: none;
            background: transparent;
            font-family: inherit;
            font-weight: 500;
            color: var(--on-surface-light);
            cursor: pointer;
            transition: var(--transition);
            position: relative;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 6px;
        }

        .main-tab.active {
            color: var(--on-surface);
        }

        .main-tab.active::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 60%;
            height: 3px;
            background: var(--primary);
            border-radius: 3px 3px 0 0;
        }

        .main-tab i {
            font-size: 20px;
        }

        /* محتوای تب‌ها */
        .tab-content {
            display: none;
            padding: 16px;
            animation: fadeIn 0.4s ease;
        }

        .tab-content.active {
            display: block;
        }

        /* کارت‌های سرویس */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
            gap: 16px;
            margin-top: 16px;
        }

        .service-card {
            background: var(--surface);
            border-radius: var(--radius-md);
            padding: 20px 16px;
            text-align: center;
            transition: var(--transition);
            box-shadow: var(--shadow-sm);
            border: 1px solid transparent;
            position: relative;
            overflow: hidden;
            cursor: pointer;
        }

        .service-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(255,255,255,0.05), transparent);
            opacity: 0;
            transition: var(--transition);
        }

        .service-card:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow-md);
            border-color: var(--primary);
        }

        .service-card:hover::before {
            opacity: 1;
        }

        .service-icon {
            font-size: 36px;
            margin-bottom: 12px;
            display: inline-block;
            transition: var(--transition);
            background: linear-gradient(to right, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .service-card:hover .service-icon {
            transform: scale(1.1);
        }

        .service-title {
            font-weight: 600;
            margin-bottom: 8px;
            font-size: 16px;
        }

        .service-description {
            font-size: 12px;
            color: var(--on-surface-light);
            opacity: 0;
            max-height: 0;
            overflow: hidden;
            transition: var(--transition-slow);
        }

        .service-card:hover .service-description {
            opacity: 1;
            max-height: 100px;
        }

        /* کارت‌های کشورها */
        .country-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 12px;
            margin-top: 16px;
        }

        .country-card {
            background: var(--surface);
            border-radius: var(--radius-md);
            padding: 16px;
            text-align: center;
            transition: var(--transition);
            box-shadow: var(--shadow-sm);
            border: 1px solid transparent;
            position: relative;
            overflow: hidden;
            cursor: pointer;
        }

        .country-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(255,255,255,0.05), transparent);
            opacity: 0;
            transition: var(--transition);
        }

        .country-card:hover {
            transform: translateY(-3px);
            box-shadow: var(--shadow-md);
            border-color: var(--info);
        }

        .country-card:hover::before {
            opacity: 1;
        }

        .country-flag {
            width: 60px;
            height: 40px;
            object-fit: cover;
            border-radius: 4px;
            margin-bottom: 8px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.2);
        }

        .country-name {
            font-weight: 600;
            margin-bottom: 4px;
            font-size: 14px;
        }

        .country-speed {
            font-size: 11px;
            color: var(--on-surface-light);
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 4px;
        }

        .country-speed i {
            color: var(--success);
            font-size: 12px;
        }

        /* بخش DNS */
        .dns-container {
            background: var(--surface);
            border-radius: var(--radius-md);
            padding: 16px;
            margin-top: 16px;
            box-shadow: var(--shadow-sm);
        }

        .dns-item {
            display: flex;
            align-items: center;
            background: var(--surface-light);
            border-radius: var(--radius-sm);
            padding: 12px 16px;
            margin-bottom: 12px;
        }

        .dns-label {
            font-size: 12px;
            color: var(--secondary);
            font-weight: 600;
            min-width: 70px;
        }

        .dns-value {
            flex: 1;
            font-family: monospace;
            font-size: 14px;
            direction: ltr;
            text-align: center;
            overflow: hidden;
            text-overflow: ellipsis;
        }

        .copy-btn {
            background: rgba(110, 69, 226, 0.1);
            color: var(--primary);
            border: none;
            padding: 8px 12px;
            border-radius: var(--radius-sm);
            font-family: inherit;
            font-weight: 600;
            font-size: 12px;
            cursor: pointer;
            transition: var(--transition);
            display: flex;
            align-items: center;
            gap: 6px;
        }

        .copy-btn:hover {
            background: var(--primary);
            color: white;
        }

        /* بخش دانلود */
        .download-list {
            margin-top: 16px;
        }

        .download-item {
            background: var(--surface);
            border-radius: var(--radius-md);
            padding: 16px;
            margin-bottom: 12px;
            box-shadow: var(--shadow-sm);
            transition: var(--transition);
        }

        .download-item:hover {
            transform: translateY(-3px);
            box-shadow: var(--shadow-md);
        }

        .download-header {
            display: flex;
            align-items: center;
            margin-bottom: 12px;
        }

        .download-icon {
            width: 40px;
            height: 40px;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-left: 12px;
            color: white;
        }

        .download-title {
            font-weight: 600;
            flex: 1;
        }

        .download-meta {
            display: flex;
            gap: 12px;
            margin-bottom: 12px;
            flex-wrap: wrap;
        }

        .meta-item {
            display: flex;
            align-items: center;
            gap: 4px;
            font-size: 12px;
            color: var(--on-surface-light);
        }

        .meta-item i {
            font-size: 14px;
        }

        .download-description {
            font-size: 13px;
            line-height: 1.6;
            margin-bottom: 16px;
            color: var(--on-surface-light);
        }

        .download-btn {
            display: block;
            text-align: center;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            color: white;
            padding: 12px;
            border-radius: var(--radius-sm);
            text-decoration: none;
            font-weight: 600;
            transition: var(--transition);
            box-shadow: 0 4px 12px rgba(110, 69, 226, 0.3);
        }

        .download-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 16px rgba(110, 69, 226, 0.4);
        }

        /* مودال خرید */
        .purchase-modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.8);
            display: none;
            align-items: center;
            justify-content: center;
            z-index: 1000;
            backdrop-filter: blur(10px);
            animation: fadeIn 0.3s ease;
        }

        .purchase-content {
            background: var(--surface);
            border-radius: var(--radius-lg);
            width: 90%;
            max-width: 500px;
            max-height: 90vh;
            overflow-y: auto;
            padding: 24px;
            box-shadow: var(--shadow-lg);
            position: relative;
            transform: translateY(20px);
            opacity: 0;
            transition: var(--transition-slow);
        }

        .purchase-modal.active .purchase-content {
            transform: translateY(0);
            opacity: 1;
        }

        .close-purchase {
            position: absolute;
            top: 16px;
            left: 16px;
            font-size: 24px;
            color: var(--on-surface-light);
            cursor: pointer;
            transition: var(--transition);
        }

        .close-purchase:hover {
            color: var(--accent);
            transform: rotate(90deg);
        }

        .purchase-title {
            text-align: center;
            margin-bottom: 24px;
            color: var(--primary);
            font-size: 24px;
            font-weight: 700;
        }

        .purchase-icon {
            width: 80px;
            height: 80px;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
            font-size: 32px;
            color: white;
            box-shadow: 0 6px 20px rgba(110, 69, 226, 0.4);
        }

        .purchase-description {
            line-height: 1.8;
            margin-bottom: 16px;
            text-align: center;
        }

        .purchase-plans {
            margin: 24px 0;
        }

        .plan-item {
            background: var(--surface-light);
            border-radius: var(--radius-md);
            padding: 16px;
            margin-bottom: 12px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            cursor: pointer;
            transition: var(--transition);
            border: 2px solid transparent;
        }

        .plan-item:hover {
            border-color: var(--primary);
        }

        .plan-item.active {
            background: rgba(110, 69, 226, 0.1);
            border-color: var(--primary);
        }

        .plan-info {
            flex: 1;
        }

        .plan-name {
            font-weight: 600;
            margin-bottom: 4px;
        }

        .plan-details {
            font-size: 12px;
            color: var(--on-surface-light);
        }

        .plan-price {
            font-weight: 700;
            color: var(--primary);
        }

        .purchase-btn {
            display: block;
            width: 100%;
            padding: 16px;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            color: white;
            border: none;
            border-radius: var(--radius-md);
            font-family: inherit;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
            margin-top: 16px;
            box-shadow: 0 4px 12px rgba(110, 69, 226, 0.3);
        }

        .purchase-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 16px rgba(110, 69, 226, 0.4);
        }

        /* اعلان */
        .notification {
            position: fixed;
            top: 20px;
            left: 50%;
            transform: translateX(-50%);
            background: var(--surface);
            color: var(--on-surface);
            padding: 12px 24px;
            border-radius: var(--radius-md);
            box-shadow: var(--shadow-md);
            z-index: 1000;
            display: none;
            animation: fadeIn 0.3s ease;
        }

        /* انیمیشن‌ها */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes fadeInUp {
            from { 
                opacity: 0;
                transform: translateY(20px);
            }
            to { 
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        @keyframes loadingShine {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }

        @keyframes ripple {
            to {
                transform: scale(4);
                opacity: 0;
            }
        }

        @keyframes rotateGradient {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        @keyframes scan {
            0% { top: -20px; opacity: 0; }
            10% { opacity: 1; }
            90% { opacity: 1; }
            100% { top: 100%; opacity: 0; }
        }

        @keyframes shine {
            0% { transform: rotate(30deg) translate(-30%, -30%); }
            100% { transform: rotate(30deg) translate(30%, 30%); }
        }

        /* رسپانسیو */
        @media (max-width: 480px) {
            .services-grid, .country-grid {
                grid-template-columns: 1fr;
            }
            
            .main-tab {
                font-size: 11px;
            }
            
            .login-container {
                padding: 30px 20px;
            }
            
            .fingerprint-container {
                width: 140px;
                height: 140px;
            }
            
            .fingerprint-btn {
                width: 110px;
                height: 110px;
            }
            
            .fingerprint-btn i {
                font-size: 45px;
            }
            
            .story-avatar {
                width: 80px;
                height: 80px;
            }
            
            .story-avatar-inner {
                width: 74px;
                height: 74px;
            }
            
            .music-cover {
                width: 150px;
                height: 150px;
                font-size: 50px;
            }
            
            .play-btn {
                width: 60px;
                height: 60px;
            }
        }
    </style>
</head>
<body>
    <!-- صفحه لودینگ -->
    <div class="loading-screen" id="loadingScreen">
        <div class="logo-container">
            <div class="logo-animation">
                <div class="logo-text">
                    <span class="x">X</span>
                    <span class="heart">♥</span>
                    <span class="x">O</span>
                </div>
                <div class="heart-progress" id="heartProgress"></div>
            </div>
        </div>
        <div class="loading-progress">
            <div class="progress-bar" id="progressBar"></div>
        </div>
    </div>

    <!-- صفحه لاگین با اثر انگشت -->
    <div class="login-screen" id="loginScreen">
        <div class="login-container">
            <h2 class="login-title">ورود به XRO VPN</h2>
            <div class="fingerprint-container">
                <div class="fingerprint-circle">
                    <div class="fingerprint-progress" id="fingerprintProgress"></div>
                    <i class="fas fa-fingerprint fingerprint-icon" id="fingerprintIcon"></i>
                    <div class="fingerprint-scan"></div>
                </div>
                <button class="fingerprint-btn" id="fingerprintBtn">
                    <i class="fas fa-fingerprint"></i>
                </button>
            </div>
            <p class="login-text">برای ورود، انگشت خود را روی دکمه نگه دارید</p>
            <p class="login-error" id="loginError">احراز هویت ناموفق بود. لطفاً مجدد تلاش کنید.</p>
        </div>
    </div>

    <!-- صفحه اصلی -->
    <div class="app-container" id="appContainer">
        <!-- هدر -->
        <header class="app-header">
            <div class="header-content">
                <div class="logo">
                    <div class="logo-icon">
                        <i class="fas fa-shield-alt"></i>
                    </div>
                    <h1 class="logo-text-header">XRO VPN</h1>
                </div>
                <button class="music-control-btn" id="musicControlBtn">
                    <i class="fas fa-music"></i>
                </button>
            </div>
        </header>

        <!-- استوری‌ها -->
        <div class="stories-container">
            <a href="#" class="story-item" onclick="openStory('security')">
                <div class="story-avatar">
                    <div class="story-avatar-inner">
                        <i class="fas fa-lock"></i>
                    </div>
                    <div class="story-badge">
                        <i class="fas fa-check"></i>
                    </div>
                </div>
                <span class="story-label">امنیت</span>
            </a>
            <a href="#" class="story-item" onclick="openStory('speed')">
                <div class="story-avatar">
                    <div class="story-avatar-inner">
                        <i class="fas fa-bolt"></i>
                    </div>
                    <div class="story-new"></div>
                </div>
                <span class="story-label">سرعت</span>
            </a>
            <a href="#" class="story-item" onclick="openStory('support')">
                <div class="story-avatar">
                    <div class="story-avatar-inner">
                        <i class="fas fa-headset"></i>
                    </div>
                </div>
                <span class="story-label">پشتیبانی</span>
            </a>
            <a href="#" class="story-item" onclick="openStory('guide')">
                <div class="story-avatar">
                    <div class="story-avatar-inner">
                        <i class="fas fa-book"></i>
                    </div>
                </div>
                <span class="story-label">راهنما</span>
            </a>
        </div>

        <!-- اعلانات -->
        <div class="announcement-container">
            <div class="announcement-box">
                <div class="announcement-text" id="announcementText">
                    سرویس‌های جدید XRO VPN با سرعت و پایداری فوق‌العاده
                </div>
            </div>
        </div>

        <!-- تب‌های اصلی -->
        <div class="main-tabs">
            <button class="main-tab active" onclick="showTab('services')">
                <i class="fas fa-store"></i>
                <span>سرویس‌ها</span>
            </button>
            <button class="main-tab" onclick="showTab('dns')">
                <i class="fas fa-network-wired"></i>
                <span>DNS</span>
            </button>
            <button class="main-tab" onclick="showTab('download')">
                <i class="fas fa-download"></i>
                <span>دانلود</span>
            </button>
        </div>

        <!-- محتوای تب‌ها -->
        <div class="tab-content active" id="servicesTab">
            <div class="services-grid">
                <div class="service-card" onclick="openPurchaseModal('sim')">
                    <div class="service-icon">
                        <i class="fas fa-sim-card"></i>
                    </div>
                    <h3 class="service-title">کانفیگ جنگی سیمکارت</h3>
                    <p class="service-description">
                        سرویس ویژه برای سیمکارت با حجم نامحدود و اتصال پایدار
                    </p>
                </div>
                <div class="service-card" onclick="openPurchaseModal('modem')">
                    <div class="service-icon">
                        <i class="fas fa-wifi"></i>
                    </div>
                    <h3 class="service-title">کانفیگ جنگی مودم</h3>
                    <p class="service-description">
                        سرویس ویژه برای مودم با حجم انتخابی و پایداری بالا
                    </p>
                </div>
            </div>

            <h3 style="margin: 24px 0 16px; text-align: center; color: var(--primary);">سرورهای مولتی انتخواب کشورها</h3>
            <div class="country-grid">
                <div class="country-card" onclick="showNotification('سرویس کشورها در حال حاضر غیرفعال است')">
                    <img src="https://flagcdn.com/w80/us.png" class="country-flag" alt="آمریکا">
                    <div class="country-name">آمریکا</div>
                    <div class="country-speed">
                        <i class="fas fa-bolt"></i>
                        سرعت بالا
                    </div>
                </div>
                <div class="country-card" onclick="showNotification('سرویس کشورها در حال حاضر غیرفعال است')">
                    <img src="https://flagcdn.com/w80/gb.png" class="country-flag" alt="انگلیس">
                    <div class="country-name">انگلیس</div>
                    <div class="country-speed">
                        <i class="fas fa-bolt"></i>
                        سرعت بالا
                    </div>
                </div>
                <div class="country-card" onclick="showNotification('سرویس کشورها در حال حاضر غیرفعال است')">
                    <img src="https://flagcdn.com/w80/fr.png" class="country-flag" alt="فرانسه">
                    <div class="country-name">فرانسه</div>
                    <div class="country-speed">
                        <i class="fas fa-bolt"></i>
                        سرعت بالا
                    </div>
                </div>
                <div class="country-card" onclick="showNotification('سرویس کشورها در حال حاضر غیرفعال است')">
                    <img src="https://flagcdn.com/w80/de.png" class="country-flag" alt="آلمان">
                    <div class="country-name">آلمان</div>
                    <div class="country-speed">
                        <i class="fas fa-bolt"></i>
                        سرعت بالا
                    </div>
                </div>
                <div class="country-card" onclick="showNotification('سرویس کشورها در حال حاضر غیرفعال است')">
                    <img src="https://flagcdn.com/w80/tr.png" class="country-flag" alt="ترکیه">
                    <div class="country-name">ترکیه</div>
                    <div class="country-speed">
                        <i class="fas fa-bolt"></i>
                        سرعت بالا
                    </div>
                </div>
            </div>
        </div>

        <div class="tab-content" id="dnsTab">
            <div class="dns-container">
                <div class="dns-item">
                    <span class="dns-label">DNS اول:</span>
                    <span class="dns-value" id="dns1">78.157.42.100</span>
                    <button class="copy-btn" onclick="copyToClipboard('dns1')">
                        <i class="fas fa-copy"></i>
                        کپی
                    </button>
                </div>
                <div class="dns-item">
                    <span class="dns-label">DNS دوم:</span>
                    <span class="dns-value" id="dns2">78.157.42.101</span>
                    <button class="copy-btn" onclick="copyToClipboard('dns2')">
                        <i class="fas fa-copy"></i>
                        کپی
                    </button>
                </div>
            </div>
        </div>

        <div class="tab-content" id="downloadTab">
            <div class="download-list">
                <div class="download-item">
                    <div class="download-header">
                        <div class="download-icon">
                            <i class="fas fa-mobile-alt"></i>
                        </div>
                        <h3 class="download-title">نسخه اندروید</h3>
                    </div>
                    <div class="download-meta">
                        <div class="meta-item">
                            <i class="fas fa-code-branch"></i>
                            نسخه 2.5.1
                        </div>
                        <div class="meta-item">
                            <i class="fas fa-calendar-alt"></i>
                            1403/02/15
                        </div>
                        <div class="meta-item">
                            <i class="fas fa-download"></i>
                            45MB
                        </div>
                    </div>
                    <p class="download-description">
                        نرم‌افزار هیدیفای برای دستگاه‌های اندروید. بهترین انتخاب برای کاربران اندروید با رابط کاربری ساده و امکانات پیشرفته.
                    </p>
                    <a href="https://play.google.com/store/apps/details?id=io.github.hid3dclient.hid3d" class="download-btn" target="_blank">
                        دانلود از گوگل پلی
                    </a>
                </div>
                
                <div class="download-item">
                    <div class="download-header">
                        <div class="download-icon">
                            <i class="fas fa-mobile"></i>
                        </div>
                        <h3 class="download-title">نسخه iOS</h3>
                    </div>
                    <div class="download-meta">
                        <div class="meta-item">
                            <i class="fas fa-code-branch"></i>
                            نسخه 1.8.2
                        </div>
                        <div class="meta-item">
                            <i class="fas fa-calendar-alt"></i>
                            1402/12/15
                        </div>
                    </div>
                    <p class="download-description">
                        نرم‌افزار هیدیفای برای دستگاه‌های iOS. بهترین انتخاب برای کاربران آیفون و آیپد با رابط کاربری ساده و امکانات کامل.
                    </p>
                    <a href="https://apps.apple.com/us/app/hid3d/id6472582787" class="download-btn" target="_blank">
                        دانلود از اپ استور
                    </a>
                </div>
                
                <div class="download-item">
                    <div class="download-header">
                        <div class="download-icon">
                            <i class="fas fa-desktop"></i>
                        </div>
                        <h3 class="download-title">نسخه ویندوز</h3>
                    </div>
                    <div class="download-meta">
                        <div class="meta-item">
                            <i class="fas fa-code-branch"></i>
                            نسخه 3.1.0
                        </div>
                        <div class="meta-item">
                            <i class="fas fa-calendar-alt"></i>
                            1403/01/28
                        </div>
                        <div class="meta-item">
                            <i class="fas fa-download"></i>
                            62MB
                        </div>
                    </div>
                    <p class="download-description">
                        نرم‌افزار هیدیفای برای سیستم‌عامل ویندوز. پشتیبانی از ویندوز 7 به بالا با قابلیت‌های مدیریت چند کانفیگ.
                    </p>
                    <a href="#" class="download-btn" onclick="showNotification('نسخه ویندوز به زودی منتشر می‌شود')">
                        به زودی...
                    </a>
                </div>
            </div>
        </div>
    </div>

    <!-- مودال کنترل موزیک -->
    <div class="music-modal" id="musicModal">
        <div class="music-content">
            <span class="close-music" onclick="closeMusicModal()">×</span>
            <h2 class="music-title">کنترل موزیک</h2>
            <div class="music-cover">
                <i class="fas fa-music"></i>
            </div>
            <div class="song-info">
                <div class="song-name">Kajfusha (Remix)</div>
                <div class="song-artist">Santiz</div>
            </div>
            <div class="music-progress-container">
                <div class="music-progress">
                    <div class="music-progress-bar" id="musicProgressBar"></div>
                </div>
                <div class="music-time">
                    <span id="currentTime">0:00</span>
                    <span id="duration">3:45</span>
                </div>
            </div>
            <div class="music-controls">
                <button class="control-btn" onclick="prevSong()">
                    <i class="fas fa-step-backward"></i>
                </button>
                <button class="control-btn play-btn" id="modalPlayBtn" onclick="togglePlay()">
                    <i class="fas fa-pause"></i>
                </button>
                <button class="control-btn" onclick="nextSong()">
                    <i class="fas fa-step-forward"></i>
                </button>
            </div>
        </div>
    </div>

    <!-- مودال استوری -->
    <div class="story-modal" id="storyModal">
        <div class="story-content">
            <span class="close-story" onclick="closeStoryModal()">×</span>
            <h2 class="story-title" id="storyTitle">امنیت پیشرفته</h2>
            <div class="story-text" id="storyText">
                ما از آخرین تکنولوژی‌های رمزنگاری برای محافظت از حریم خصوصی شما استفاده می‌کنیم. تمام ارتباطات شما به صورت end-to-end رمزنگاری می‌شوند.
            </div>
        </div>
    </div>

    <!-- مودال خرید -->
    <div class="purchase-modal" id="purchaseModal">
        <div class="purchase-content">
            <span class="close-purchase" onclick="closePurchaseModal()">×</span>
            <h2 class="purchase-title" id="purchaseTitle">خرید سرویس</h2>
            <div class="purchase-icon" id="purchaseIcon">
                <i class="fas fa-wifi"></i>
            </div>
            <p class="purchase-description" id="purchaseDescription">
                انتخاب پلن مناسب برای نیازهای شما
            </p>
            
            <div class="purchase-plans" id="purchasePlans">
                <!-- Plans will be dynamically inserted here -->
            </div>
            
            <button class="purchase-btn" onclick="requestService()">
                درخواست این سرویس
            </button>
        </div>
    </div>

    <!-- اعلان -->
    <div class="notification" id="notification">
        این سرویس در حال حاضر غیرفعال می‌باشد
    </div>

    <script>
        // شبیه‌سازی لودینگ
        let progress = 0;
        const progressBar = document.getElementById('progressBar');
        const heartProgress = document.getElementById('heartProgress');
        const loadingScreen = document.getElementById('loadingScreen');
        const loginScreen = document.getElementById('loginScreen');
        const appContainer = document.getElementById('appContainer');
        
        const loadingInterval = setInterval(() => {
            progress += Math.random() * 10;
            if (progress > 100) progress = 100;
            progressBar.style.width = `${progress}%`;
            heartProgress.style.height = `${progress}%`;
            
            if (progress >= 100) {
                clearInterval(loadingInterval);
                setTimeout(() => {
                    loadingScreen.style.opacity = '0';
                    setTimeout(() => {
                        loadingScreen.style.display = 'none';
                        loginScreen.classList.add('active');
                    }, 300);
                }, 500);
            }
        }, 200);

        // سیستم اثر انگشت
        const fingerprintBtn = document.getElementById('fingerprintBtn');
        const fingerprintProgress = document.getElementById('fingerprintProgress');
        const fingerprintIcon = document.getElementById('fingerprintIcon');
        const fingerprintScan = document.querySelector('.fingerprint-scan');
        const loginError = document.getElementById('loginError');
        let isAuthenticating = false;
        let progressInterval;
        let progressValue = 0;
        
        fingerprintBtn.addEventListener('mousedown', startAuthentication);
        fingerprintBtn.addEventListener('touchstart', startAuthentication);
        
        fingerprintBtn.addEventListener('mouseup', cancelAuthentication);
        fingerprintBtn.addEventListener('touchend', cancelAuthentication);
        fingerprintBtn.addEventListener('mouseleave', cancelAuthentication);
        
        function startAuthentication() {
            if (isAuthenticating) return;
            
            isAuthenticating = true;
            loginError.style.display = 'none';
            fingerprintBtn.classList.add('active');
            fingerprintIcon.style.color = 'white';
            fingerprintScan.style.opacity = '1';
            
            // شروع پیشرفت
            progressValue = 0;
            progressInterval = setInterval(() => {
                progressValue += 1;
                fingerprintProgress.style.background = `conic-gradient(var(--primary) ${progressValue}%, transparent 0%)`;
                
                if (progressValue >= 100) {
                    completeAuthentication();
                }
            }, 30);
        }
        
        function cancelAuthentication() {
            if (!isAuthenticating) return;
            
            clearInterval(progressInterval);
            isAuthenticating = false;
            fingerprintBtn.classList.remove('active');
            fingerprintIcon.style.color = 'var(--primary)';
            fingerprintScan.style.opacity = '0';
            
            if (progressValue < 100 && progressValue > 10) {
                loginError.style.display = 'block';
                setTimeout(() => {
                    fingerprintProgress.style.background = 'conic-gradient(var(--primary) 0%, transparent 0%)';
                }, 500);
            } else if (progressValue <= 10) {
                fingerprintProgress.style.background = 'conic-gradient(var(--primary) 0%, transparent 0%)';
            }
            
            progressValue = 0;
        }
        
        function completeAuthentication() {
            clearInterval(progressInterval);
            fingerprintProgress.style.background = 'conic-gradient(var(--primary) 100%, transparent 0%)';
            fingerprintScan.style.opacity = '0';
            
            setTimeout(() => {
                loginScreen.classList.remove('active');
                setTimeout(() => {
                    appContainer.style.display = 'block';
                    startMusicPlayer();
                }, 500);
            }, 500);
        }

        // سیستم پخش موزیک
        const musicControlBtn = document.getElementById('musicControlBtn');
        const musicModal = document.getElementById('musicModal');
        const modalPlayBtn = document.getElementById('modalPlayBtn');
        const musicProgressBar = document.getElementById('musicProgressBar');
        const currentTimeEl = document.getElementById('currentTime');
        const durationEl = document.getElementById('duration');
        let isPlaying = false;
        let audio = new Audio('https://kmuzon.com/uploads/files/2022-01/santiz-kajfusha-swerodo-remix_(kmuzon.com).mp3');
        
        function startMusicPlayer() {
            audio.play();
            isPlaying = true;
            updateMusicIcon();
            updateProgressBar();
            musicControlBtn.classList.add('active');
            
            // تنظیم مدت زمان کل
            audio.addEventListener('loadedmetadata', function() {
                const duration = audio.duration;
                const minutes = Math.floor(duration / 60);
                const seconds = Math.floor(duration % 60);
                durationEl.textContent = `${minutes}:${seconds < 10 ? '0' : ''}${seconds}`;
            });
        }
        
        function togglePlay() {
            if (isPlaying) {
                pauseMusic();
            } else {
                playMusic();
            }
        }
        
        function playMusic() {
            audio.play();
            isPlaying = true;
            modalPlayBtn.innerHTML = '<i class="fas fa-pause"></i>';
            updateMusicIcon();
            updateProgressBar();
            musicControlBtn.classList.add('active');
        }
        
        function pauseMusic() {
            audio.pause();
            isPlaying = false;
            modalPlayBtn.innerHTML = '<i class="fas fa-play"></i>';
            updateMusicIcon();
            musicControlBtn.classList.remove('active');
        }
        
        function prevSong() {
            showNotification('آهنگ قبلی پخش می‌شود');
            // در اینجا می‌توانید آهنگ قبلی را پیاده‌سازی کنید
        }
        
        function nextSong() {
            showNotification('آهنگ بعدی پخش می‌شود');
            // در اینجا می‌توانید آهنگ بعدی را پیاده‌سازی کنید
        }
        
        function updateProgressBar() {
            if (!isPlaying) return;
            
            const progress = (audio.currentTime / audio.duration) * 100;
            musicProgressBar.style.width = `${progress}%`;
            
            // به روز رسانی زمان فعلی
            const currentTime = audio.currentTime;
            const minutes = Math.floor(currentTime / 60);
            const seconds = Math.floor(currentTime % 60);
            currentTimeEl.textContent = `${minutes}:${seconds < 10 ? '0' : ''}${seconds}`;
            
            if (audio.currentTime < audio.duration) {
                requestAnimationFrame(updateProgressBar);
            } else {
                isPlaying = false;
                modalPlayBtn.innerHTML = '<i class="fas fa-play"></i>';
                updateMusicIcon();
                musicControlBtn.classList.remove('active');
            }
        }
        
        function updateMusicIcon() {
            musicControlBtn.innerHTML = isPlaying ? '<i class="fas fa-pause"></i>' : '<i class="fas fa-music"></i>';
        }
        
        musicControlBtn.addEventListener('click', function() {
            musicModal.style.display = 'flex';
            setTimeout(() => {
                musicModal.classList.add('active');
            }, 10);
            document.body.style.overflow = 'hidden';
        });
        
        function closeMusicModal() {
            musicModal.classList.remove('active');
            setTimeout(() => {
                musicModal.style.display = 'none';
            }, 300);
            document.body.style.overflow = 'auto';
        }
        
        // نمایش تب‌ها
        function showTab(tabId) {
            const tabs = document.querySelectorAll('.main-tab');
            const tabContents = document.querySelectorAll('.tab-content');
            
            tabs.forEach(tab => tab.classList.remove('active'));
            tabContents.forEach(content => content.classList.remove('active'));
            
            document.querySelector(`.main-tab[onclick="showTab('${tabId}')"]`).classList.add('active');
            document.getElementById(`${tabId}Tab`).classList.add('active');
        }

        // کپی DNS
        function copyToClipboard(elementId) {
            const text = document.getElementById(elementId).textContent;
            navigator.clipboard.writeText(text).then(() => {
                showNotification('DNS با موفقیت کپی شد');
            }).catch(err => {
                console.error('خطا در کپی کردن متن: ', err);
                showNotification('خطا در کپی کردن DNS');
            });
        }

        // نمایش اعلان
        function showNotification(message = 'این سرویس در حال حاضر غیرفعال می‌باشد') {
            const notification = document.getElementById('notification');
            notification.textContent = message;
            notification.style.display = 'block';
            
            setTimeout(() => {
                notification.style.display = 'none';
            }, 3000);
        }

        // نمایش مودال خرید
        function openPurchaseModal(serviceType) {
            const modal = document.getElementById('purchaseModal');
            const title = document.getElementById('purchaseTitle');
            const icon = document.getElementById('purchaseIcon');
            const description = document.getElementById('purchaseDescription');
            const plansContainer = document.getElementById('purchasePlans');
            
            switch(serviceType) {
                case 'sim':
                    title.textContent = 'خرید کانفیگ جنگی سیمکارت';
                    icon.innerHTML = '<i class="fas fa-sim-card"></i>';
                    description.textContent = 'سرویس ویژه برای سیمکارت با حجم نامحدود و اتصال پایدار';
                    
                    // پلن‌های سیمکارت
                    plansContainer.innerHTML = `
                        <div class="plan-item" onclick="selectPlan(this)">
                            <div class="plan-info">
                                <div class="plan-name">پلن یک ماهه</div>
                                <div class="plan-details">حجم نامحدود - پشتیبانی 24/7</div>
                            </div>
                            <div class="plan-price">310,000 تومان</div>
                        </div>
                        <div class="plan-item active" onclick="selectPlan(this)">
                            <div class="plan-info">
                                <div class="plan-name">پلن سه ماهه</div>
                                <div class="plan-details">حجم نامحدود - پشتیبانی VIP</div>
                            </div>
                            <div class="plan-price">628,000 تومان</div>
                        </div>
                        <div class="plan-item" onclick="selectPlan(this)">
                            <div class="plan-info">
                                <div class="plan-name">پلن شش ماهه</div>
                                <div class="plan-details">حجم نامحدود - سرعت اختصاصی</div>
                            </div>
                            <div class="plan-price">914,000 تومان</div>
                        </div>
                    `;
                    break;
                case 'modem':
                    title.textContent = 'خرید کانفیگ جنگی مودم';
                    icon.innerHTML = '<i class="fas fa-wifi"></i>';
                    description.textContent = 'سرویس ویژه برای مودم با حجم انتخابی و پایداری بالا';
                    
                    // پلن‌های مودم
                    plansContainer.innerHTML = `
                        <div class="plan-item" onclick="selectPlan(this)">
                            <div class="plan-info">
                                <div class="plan-name">پلن یک ماهه</div>
                                <div class="plan-details">حجم نامحدود - پشتیبانی 24/7</div>
                            </div>
                            <div class="plan-price">120,000 تومان</div>
                        </div>
                        <div class="plan-item active" onclick="selectPlan(this)">
                            <div class="plan-info">
                                <div class="plan-name">پلن سه ماهه</div>
                                <div class="plan-details">حجم نامحدود - پشتیبانی VIP</div>
                            </div>
                            <div class="plan-price">300,000 تومان</div>
                        </div>
                        <div class="plan-item" onclick="selectPlan(this)">
                            <div class="plan-info">
                                <div class="plan-name">پلن شش ماهه</div>
                                <div class="plan-details">حجم نامحدود - سرعت اختصاصی</div>
                            </div>
                            <div class="plan-price">540,000 تومان</div>
                        </div>
                    `;
                    break;
            }
            
            modal.style.display = 'flex';
            setTimeout(() => {
                modal.classList.add('active');
            }, 10);
            document.body.style.overflow = 'hidden';
        }

        function closePurchaseModal() {
            document.getElementById('purchaseModal').classList.remove('active');
            setTimeout(() => {
                document.getElementById('purchaseModal').style.display = 'none';
            }, 300);
            document.body.style.overflow = 'auto';
        }

        function selectPlan(planElement) {
            document.querySelectorAll('.plan-item').forEach(item => {
                item.classList.remove('active');
            });
            planElement.classList.add('active');
        }

        function requestService() {
            const modal = document.getElementById('purchaseModal');
            const serviceType = modal.querySelector('.purchase-title').textContent.includes('سیمکارت') ? 'سیمکارت' : 'مودم';
            const selectedPlan = modal.querySelector('.plan-item.active .plan-name').textContent;
            const price = modal.querySelector('.plan-item.active .plan-price').textContent;
            
            let duration = '';
            if (selectedPlan.includes('یک ماهه')) duration = '30 روزه';
            else if (selectedPlan.includes('سه ماهه')) duration = '90 روزه';
            else if (selectedPlan.includes('شش ماهه')) duration = '180 روزه';
            
            const telegramUrl = `https://t.me/u0v0n?text=${encodeURIComponent(
                `سلام ادمین رسمی ایکسرو!\n\n` +
                `سرویس: ${serviceType}\n` +
                `نوع: ${selectedPlan}\n` +
                `زمان: ${duration}\n` +
                `حجم: نامحدود\n\n` +
                `قیمت: ${price}\n\n` +
                `برای بنده فعال و اطلاعات لازم رو به بنده دهید ، با تشکر .`
            )}`;
            
            window.open(telegramUrl, '_blank');
            closePurchaseModal();
            showNotification('درخواست شما ارسال شد. لطفاً در تلگرام پیام دهید.');
        }

        // باز کردن استوری
        function openStory(storyId) {
            const modal = document.getElementById('storyModal');
            const title = document.getElementById('storyTitle');
            const text = document.getElementById('storyText');
            
            switch(storyId) {
                case 'security':
                    title.textContent = 'امنیت پیشرفته';
                    text.textContent = 'ما از آخرین تکنولوژی‌های رمزنگاری برای محافظت از حریم خصوصی شما استفاده می‌کنیم. تمام ارتباطات شما به صورت end-to-end رمزنگاری می‌شوند.';
                    break;
                case 'speed':
                    title.textContent = 'سرعت فوق‌العاده';
                    text.textContent = 'با استفاده از سرورهای پرسرعت در نقاط مختلف جهان، بهترین تجربه وبگردی را برای شما فراهم می‌کنیم.';
                    break;
                case 'support':
                    title.textContent = 'پشتیبانی 24/7';
                    text.textContent = 'تیم پشتیبانی ما به صورت 24 ساعته و 7 روز هفته آماده پاسخگویی به سوالات و مشکلات شماست.';
                    break;
                case 'guide':
                    title.textContent = 'راهنمای استفاده';
                    text.textContent = '1. اپلیکیشن را دانلود و نصب کنید\n2. حساب کاربری ایجاد کنید\n3. از سرویس‌های ما لذت ببرید';
                    break;
                default:
                    title.textContent = 'XRO VPN';
                    text.textContent = 'به XRO VPN خوش آمدید';
            }
            
            modal.style.display = 'flex';
            setTimeout(() => {
                modal.classList.add('active');
            }, 10);
            document.body.style.overflow = 'hidden';
        }

        function closeStoryModal() {
            document.getElementById('storyModal').classList.remove('active');
            setTimeout(() => {
                document.getElementById('storyModal').style.display = 'none';
            }, 300);
            document.body.style.overflow = 'auto';
        }

        // شبیه‌سازی اعلانات متوالی
        const announcements = [
            "آقای ایکسرا حامی آزادی است",
            "در بدترین شرایط خدمات ما پایدار می‌ماند",
            "فروش ماهانه +۱۰هزار کانفیگ شد!",
            "سرویس‌های جدید با سرعت فوق‌العاده"
        ];
        
        let currentAnnouncement = 0;
        const announcementText = document.getElementById('announcementText');
        
        function rotateAnnouncements() {
            announcementText.style.opacity = '0';
            
            setTimeout(() => {
                currentAnnouncement = (currentAnnouncement + 1) % announcements.length;
                announcementText.textContent = announcements[currentAnnouncement];
                announcementText.style.opacity = '1';
            }, 500);
        }
        
        setInterval(rotateAnnouncements, 3000);

        // بستن با کلید ESC
        document.addEventListener('keydown', function(e) {
            if (e.key === 'Escape') {
                closePurchaseModal();
                closeMusicModal();
                closeStoryModal();
            }
        });

        // جلوگیری از زوم صفحه
        document.addEventListener('gesturestart', function (e) {
            e.preventDefault();
        });

        // جلوگیری از انتخاب متن
        document.addEventListener('selectstart', function(e) {
            e.preventDefault();
        });
    </script>
</body>
</html>
