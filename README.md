<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>XRO VPN | فروشگاه کانفیگ اختصاصی</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* استایل صفحه لودینگ */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: #0a0a0a;
            color: #f0f0f0;
            overflow-x: hidden;
        }
        
        /* صفحه لودینگ */
        .loading-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: #000000;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 1000;
        }
        
        .logo-container {
            text-align: center;
            margin-bottom: 80px;
            margin-top: -30px;
        }
        
        .logo-text {
            font-size: 48px;
            font-weight: bold;
            display: flex;
            justify-content: center;
            gap: 15px;
            text-shadow: 0 0 10px rgba(255, 215, 0, 0.7);
        }
        
        .mr {
            color: #FFD700;
            opacity: 0;
            animation: slideInRight 1s forwards 0.5s;
        }
        
        .xero {
            color: #FFFF00;
            opacity: 0;
            animation: slideInLeft 1s forwards 0.5s;
        }
        
        @keyframes slideInRight {
            0% {
                transform: translateX(100px);
                opacity: 0;
            }
            100% {
                transform: translateX(0);
                opacity: 1;
            }
        }
        
        @keyframes slideInLeft {
            0% {
                transform: translateX(-100px);
                opacity: 0;
            }
            100% {
                transform: translateX(0);
                opacity: 1;
            }
        }
        
        @keyframes slideOutRight {
            0% {
                transform: translateX(0);
                opacity: 1;
            }
            100% {
                transform: translateX(100px);
                opacity: 0;
            }
        }
        
        @keyframes slideOutLeft {
            0% {
                transform: translateX(0);
                opacity: 1;
            }
            100% {
                transform: translateX(-100px);
                opacity: 0;
            }
        }
        
        .loading-footer {
            position: absolute;
            bottom: 120px;
            width: 80%;
            max-width: 500px;
        }
        
        @keyframes slideDown {
            0% { transform: translateY(0); opacity: 1; }
            100% { transform: translateY(100px); opacity: 0; }
        }
        
        .waiting-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
        }
        
        .waiting-text {
            font-size: 18px;
            color: #FFFFFF;
            display: flex;
            align-items: center;
        }
        
        .dot {
            opacity: 0;
            animation: dotAnimation 1.5s infinite;
            margin-right: 2px;
        }
        
        .dot:nth-child(1) {
            animation-delay: 0.2s;
        }
        
        .dot:nth-child(2) {
            animation-delay: 0.4s;
        }
        
        .dot:nth-child(3) {
            animation-delay: 0.6s;
        }
        
        @keyframes dotAnimation {
            0%, 100% { opacity: 0; }
            50% { opacity: 1; }
        }
        
        .loading-bar-container {
            width: 100%;
            height: 15px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 8px;
            overflow: hidden;
            margin-bottom: 8px;
            box-shadow: 0 0 15px rgba(255, 165, 0, 0.3);
        }
        
        .loading-bar {
            height: 100%;
            background: linear-gradient(90deg, #FFA500, #FFD700);
            width: 0%;
            transition: width 0.3s;
            border-radius: 8px;
        }
        
        .counter {
            font-size: 16px;
            color: #FFD700;
            font-weight: bold;
        }
        
        /* صفحه اصلی */
        .main-screen {
            display: none;
            animation: fadeIn 1s ease;
            opacity: 0;
            min-height: 100vh;
            overflow-y: auto;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        /* متغیرهای اصلی */
        :root {
            --primary: #FF6B35;
            --primary-dark: #EF5621;
            --secondary: #4361EE;
            --secondary-dark: #3A56D4;
            --dark: #0F0F0F;
            --dark-light: #1A1A1A;
            --darker: #121212;
            --light: rgba(255,255,255,0.95);
            --lighter: rgba(255,255,255,0.7);
            --radius: 16px;
            --radius-sm: 10px;
            --shadow: 0 8px 20px rgba(0,0,0,0.3);
            --shadow-lg: 0 15px 40px rgba(0,0,0,0.4);
            --transition: all 0.3s ease;
            --transition-slow: all 0.5s ease;
            --menu-color: #6a11cb;
            --war-color: #FF5252;
        }
        
        .container {
            max-width: 100%;
            margin: 0 auto;
            padding: 0 15px;
            -webkit-user-select: none;
            -moz-user-select: none;
            -ms-user-select: none;
            user-select: none;
            touch-action: pan-y;
        }
        
        /* هدر */
        .app-header {
            padding: 2rem 0 1rem;
            text-align: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 1.5rem;
        }
        
        .logo-icon {
            width: 50px;
            height: 50px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            border-radius: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-left: 12px;
            box-shadow: var(--shadow);
            position: relative;
        }
        
        .logo-icon:after {
            content: '';
            position: absolute;
            top: -5px;
            left: -5px;
            right: -5px;
            bottom: -5px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            border-radius: 18px;
            z-index: -1;
            opacity: 0.5;
            filter: blur(10px);
        }
        
        .logo-text {
            font-size: 1.8rem;
            font-weight: 800;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            position: relative;
        }
        
        .logo-text:after {
            content: 'ویرایش ۷';
            position: absolute;
            top: -10px;
            left: 0;
            font-size: 0.6rem;
            background: #FFC107;
            color: #000;
            padding: 2px 8px;
            border-radius: 50px;
            font-weight: 700;
        }
        
        .announcement-box {
            font-size: 0.95rem;
            color: var(--light);
            max-width: 90%;
            margin: 1.5rem auto;
            background: rgba(30, 30, 30, 0.8);
            padding: 1rem;
            border-radius: var(--radius);
            border: 1px solid rgba(255,255,255,0.1);
            animation: fadeIn 1s both 0.5s;
            min-height: 60px;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            box-shadow: var(--shadow);
        }
        
        .typing-text {
            display: inline-block;
            overflow: hidden;
            border-right: 2px solid var(--primary);
            white-space: nowrap;
            margin: 0 auto;
            letter-spacing: 1px;
            animation: blink-caret 0.75s step-end infinite;
        }
        
        /* استوری‌ها */
        .stories-container {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin: 1.5rem 0;
            padding: 0 10px;
            overflow-x: auto;
            scrollbar-width: none;
        }
        
        .stories-container::-webkit-scrollbar {
            display: none;
        }
        
        .story-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            cursor: pointer;
            flex: 0 0 auto;
        }
        
        .story-circle {
            width: 70px;
            height: 70px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            position: relative;
            margin-bottom: 8px;
        }
        
        .story-circle:before {
            content: '';
            position: absolute;
            top: -3px;
            left: -3px;
            right: -3px;
            bottom: -3px;
            border-radius: 50%;
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            z-index: -1;
            opacity: 0.6;
            filter: blur(5px);
        }
        
        .story-icon {
            width: 60px;
            height: 60px;
            background: var(--dark-light);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.5rem;
        }
        
        .story-label {
            font-size: 0.8rem;
            color: var(--lighter);
            text-align: center;
        }
        
        /* مودال استوری */
        .story-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--darker);
            z-index: 2000;
            touch-action: pan-y;
        }
        
        .story-header {
            position: absolute;
            top: 20px;
            right: 20px;
            left: 20px;
            z-index: 10;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .story-progress {
            display: flex;
            gap: 5px;
            width: 100%;
            padding: 0 10px;
        }
        
        .progress-bar {
            height: 3px;
            background: rgba(255,255,255,0.3);
            border-radius: 3px;
            flex: 1;
            overflow: hidden;
        }
        
        .progress-fill {
            height: 100%;
            background: white;
            width: 0%;
            transition: width linear;
        }
        
        .close-story {
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
            background: rgba(0,0,0,0.3);
            width: 30px;
            height: 30px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
        }
        
        .story-content {
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 60px 20px;
            text-align: center;
            position: relative;
        }
        
        .story-text {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            color: white;
            max-width: 80%;
            line-height: 1.6;
            opacity: 0;
            transform: translateY(20px);
            transition: all 0.5s ease;
        }
        
        .story-text.show {
            opacity: 1;
            transform: translateY(0);
        }
        
        .story-image {
            width: 200px;
            height: 200px;
            border-radius: var(--radius);
            margin-bottom: 1.5rem;
            object-fit: cover;
            box-shadow: var(--shadow-lg);
            opacity: 0;
            transform: scale(0.9);
            transition: all 0.5s ease;
        }
        
        .story-image.show {
            opacity: 1;
            transform: scale(1);
        }
        
        .story-comments {
            width: 100%;
            max-width: 300px;
            margin-top: 1.5rem;
        }
        
        .comment {
            display: flex;
            margin-bottom: 1rem;
            opacity: 0;
            transform: translateY(20px);
            transition: all 0.5s ease;
        }
        
        .comment.show {
            opacity: 1;
            transform: translateY(0);
        }
        
        .comment.left {
            justify-content: flex-start;
        }
        
        .comment.right {
            justify-content: flex-end;
        }
        
        .comment-avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            margin: 0 10px;
            flex-shrink: 0;
        }
        
        .comment-text {
            background: rgba(255,255,255,0.1);
            padding: 0.8rem 1rem;
            border-radius: var(--radius-sm);
            max-width: 70%;
            position: relative;
        }
        
        .comment.left .comment-text {
            border-top-right-radius: 0;
        }
        
        .comment.right .comment-text {
            border-top-left-radius: 0;
        }
        
        .nav-area {
            position: absolute;
            top: 0;
            bottom: 0;
            width: 50%;
            cursor: pointer;
        }
        
        .nav-area.left {
            left: 0;
        }
        
        .nav-area.right {
            right: 0;
        }
        
        /* تب‌های اصلی */
        .main-tabs {
            display: flex;
            margin: 1.5rem 0;
            background: var(--dark-light);
            border-radius: var(--radius);
            overflow: hidden;
            border: 1px solid rgba(255,255,255,0.1);
            box-shadow: var(--shadow);
            position: relative;
        }
        
        .main-tab {
            flex: 1;
            padding: 1rem;
            background: transparent;
            border: none;
            cursor: pointer;
            font-weight: 600;
            color: var(--lighter);
            transition: var(--transition);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            gap: 5px;
        }
        
        .main-tab i {
            font-size: 1.2rem;
        }
        
        .main-tab.active {
            color: white;
            background: linear-gradient(135deg, var(--primary), var(--primary-dark));
        }
        
        /* محتوا */
        .main-tab-content {
            margin: 1rem 0;
            display: none;
        }
        
        .main-tab-content.active {
            display: block;
            animation: fadeIn 0.5s ease;
        }
        
        .message {
            background: rgba(67,97,238,0.2);
            padding: 1rem;
            border-radius: var(--radius);
            margin: 1rem 0;
            border: 1px solid rgba(67,97,238,0.2);
            display: flex;
            align-items: center;
            color: #e0e0e0;
        }
        
        .notice-label {
            background: var(--secondary);
            color: white;
            padding: 0.3rem 0.8rem;
            border-radius: 50px;
            font-weight: 700;
            font-size: 0.8rem;
            margin-left: 0;
            margin-right: 10px;
            box-shadow: 0 3px 10px rgba(67,97,238,0.3);
        }
        
        /* فلگ‌ها */
        .flag-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 1rem;
            padding: 1rem 0;
        }
        
        .flag-item {
            background: var(--dark);
            padding: 1rem;
            text-align: center;
            border-radius: var(--radius);
            cursor: pointer;
            border: 1px solid rgba(255,255,255,0.1);
            transition: var(--transition);
            position: relative;
            overflow: hidden;
            box-shadow: var(--shadow);
        }
        
        .flag-item.war {
            background: rgba(255, 82, 82, 0.1);
            border: 1px solid rgba(255, 82, 82, 0.2);
        }
        
        .flag-item.war:before {
            background: linear-gradient(135deg, rgba(255, 82, 82, 0.2), rgba(67,97,238,0.1));
        }
        
        .flag-item.war:hover {
            transform: translateY(-5px) scale(1.03);
        }
        
        .flag-item:before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(255,107,53,0.1), rgba(67,97,238,0.1));
            z-index: -1;
            opacity: 0;
            transition: var(--transition);
        }
        
        .flag-item:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow-lg);
        }
        
        .flag-item:hover:before {
            opacity: 1;
        }
        
        .flag-item span {
            font-size: 2.5rem;
            display: block;
            margin-bottom: 0.5rem;
        }
        
        .flag-item p {
            margin: 0;
            font-size: 0.95rem;
            font-weight: 600;
            color: #f0f0f0;
        }
        
        .country-info {
            font-size: 0.8rem;
            color: var(--lighter);
            margin-top: 0.5rem;
            opacity: 0;
            max-height: 0;
            overflow: hidden;
            transition: var(--transition-slow);
        }
        
        .flag-item:hover .country-info {
            opacity: 1;
            max-height: 100px;
        }
        
        .status-badge {
            position: absolute;
            top: 10px;
            left: 10px;
            font-size: 0.7rem;
            padding: 0.3rem 0.6rem;
            border-radius: 50px;
            font-weight: 700;
        }
        
        .status-badge.active {
            background: rgba(76,175,80,0.2);
            color: #4CAF50;
            border: 1px solid #4CAF50;
        }
        
        .status-badge.war {
            background: rgba(255, 82, 82, 0.2);
            color: var(--war-color);
            border: 1px solid var(--war-color);
        }
        
        .status-badge.inactive {
            background: rgba(158,158,158,0.2);
            color: #9E9E9E;
            border: 1px solid #9E9E9E;
        }
        
        /* بخش DNS */
        .dns-container {
            background: linear-gradient(135deg, rgba(67,97,238,0.2), rgba(255,107,53,0.2));
            padding: 1.5rem;
            border-radius: var(--radius);
            margin: 1.5rem 0;
            text-align: center;
            border: 1px solid rgba(255,255,255,0.1);
            box-shadow: var(--shadow);
            position: relative;
            overflow: hidden;
        }
        
        .dns-container:before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, transparent, rgba(255,255,255,0.05), transparent);
            z-index: 0;
        }
        
        .dns-item {
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin: 1rem 0;
            padding: 1rem;
            background: rgba(30,30,30,0.7);
            border-radius: var(--radius-sm);
            position: relative;
            z-index: 1;
        }
        
        .dns-label {
            font-weight: 600;
            color: var(--primary);
        }
        
        .dns-value {
            font-family: monospace;
            font-size: 1.1rem;
            color: white;
        }
        
        .copy-btn {
            padding: 0.5rem 1rem;
            background: var(--secondary);
            color: white;
            border: none;
            border-radius: var(--radius-sm);
            cursor: pointer;
            transition: var(--transition);
        }
        
        .copy-btn:hover {
            background: var(--secondary-dark);
            transform: translateY(-2px);
        }
        
        /* مودال سفارش */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.95);
            z-index: 1000;
            overflow-y: auto;
        }
        
        .modal-content {
            background: var(--dark-light);
            border-radius: var(--radius);
            max-width: 95%;
            width: 100%;
            margin: 5% auto;
            overflow: hidden;
            border: 1px solid rgba(255,255,255,0.1);
            box-shadow: var(--shadow-lg);
        }
        
        .modal-header {
            padding: 1.5rem;
            background: linear-gradient(90deg, var(--primary), var(--primary-dark));
            color: white;
            text-align: center;
            position: relative;
        }
        
        .modal-header.war {
            background: linear-gradient(90deg, var(--war-color), #C62828);
        }
        
        .modal-header h2 {
            font-size: 1.3rem;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .modal-header h2 span {
            margin-left: 10px;
            font-size: 1.6rem;
        }
        
        .close-modal {
            position: absolute;
            top: 1rem;
            left: 1.5rem;
            font-size: 1.8rem;
            cursor: pointer;
            color: white;
        }
        
        .modal-body {
            padding: 1.5rem;
        }
        
        .modal-tabs {
            display: flex;
            border-bottom: 1px solid rgba(255,255,255,0.1);
            margin-bottom: 1.5rem;
            overflow-x: auto;
            white-space: nowrap;
        }
        
        .modal-tab {
            padding: 0.8rem 1.2rem;
            cursor: pointer;
            font-weight: 600;
            color: var(--lighter);
            position: relative;
            transition: var(--transition);
        }
        
        .modal-tab:after {
            content: '';
            position: absolute;
            bottom: -1px;
            right: 0;
            width: 0;
            height: 3px;
            background: var(--primary);
            transition: var(--transition);
        }
        
        .modal-tab.war:after {
            background: var(--war-color);
        }
        
        .modal-tab.active {
            color: var(--primary);
        }
        
        .modal-tab.war.active {
            color: var(--war-color);
        }
        
        .modal-tab.active:after {
            width: 100%;
        }
        
        .modal-tab-content {
            display: none;
        }
        
        .modal-tab-content.active {
            display: block;
        }
        
        /* اسلایدرها */
        .slider-container {
            margin: 1.5rem 0;
        }
        
        .slider-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 1rem;
        }
        
        .slider-value {
            font-weight: 700;
            color: var(--primary);
            background: rgba(255,107,53,0.1);
            padding: 0.4rem 0.8rem;
            border-radius: 50px;
        }
        
        .slider-value.war {
            color: var(--war-color);
            background: rgba(255, 82, 82, 0.1);
        }
        
        .slider {
            -webkit-appearance: none;
            width: 100%;
            height: 8px;
            border-radius: 4px;
            background: var(--dark);
            outline: none;
            margin: 1rem 0;
        }
        
        .slider::-webkit-slider-thumb {
            -webkit-appearance: none;
            width: 24px;
            height: 24px;
            border-radius: 50%;
            background: var(--primary);
            cursor: pointer;
            border: 3px solid white;
            box-shadow: 0 4px 10px rgba(0,0,0,0.3);
        }
        
        .slider.war::-webkit-slider-thumb {
            background: var(--war-color);
        }
        
        .price-info {
            background: rgba(255,107,53,0.1);
            padding: 1rem;
            border-radius: var(--radius-sm);
            margin-top: 1.5rem;
            text-align: center;
            border: 1px solid rgba(255,255,255,0.1);
        }
        
        .price-info.war {
            background: rgba(255, 82, 82, 0.1);
        }
        
        .price-info span {
            color: var(--primary);
            font-weight: 700;
        }
        
        .price-info.war span {
            color: var(--war-color);
        }
        
        /* قیمت نهایی */
        .final-price {
            text-align: center;
            margin: 2rem 0;
            font-size: 1.3rem;
            position: relative;
        }
        
        .final-price span {
            color: var(--primary);
            font-weight: 800;
            font-size: 1.8rem;
        }
        
        .final-price.war span {
            color: var(--war-color);
        }
        
        /* خلاصه سفارش */
        .order-summary {
            background: rgba(30,30,30,0.7);
            padding: 1.5rem;
            border-radius: var(--radius-sm);
            margin: 2rem 0;
            border-left: 3px solid var(--primary);
        }
        
        .order-summary.war {
            border-left: 3px solid var(--war-color);
        }
        
        .order-summary p {
            margin-bottom: 0.8rem;
            display: flex;
            justify-content: space-between;
            padding: 0.4rem 0;
            border-bottom: 1px dashed rgba(255,255,255,0.1);
        }
        
        .order-summary .value {
            color: var(--primary);
            font-weight: 600;
        }
        
        .order-summary.war .value {
            color: var(--war-color);
        }
        
        /* فوتر مودال */
        .modal-footer {
            display: flex;
            justify-content: space-between;
            padding: 1.5rem;
            border-top: 1px solid rgba(255,255,255,0.1);
            gap: 15px;
        }
        
        /* دکمه‌ها */
        .btn {
            padding: 1rem 1.8rem;
            border-radius: 50px;
            font-family: inherit;
            font-weight: 600;
            cursor: pointer;
            border: none;
            transition: var(--transition);
            display: inline-flex;
            align-items: center;
            justify-content: center;
            flex: 1;
        }
        
        .btn-primary {
            background: linear-gradient(135deg, var(--primary), var(--primary-dark));
            color: white;
            box-shadow: 0 8px 20px rgba(255,107,53,0.3);
        }
        
        .btn-war {
            background: linear-gradient(135deg, var(--war-color), #C62828);
            color: white;
            box-shadow: 0 8px 20px rgba(255, 82, 82, 0.3);
        }
        
        .btn-secondary {
            background: var(--dark);
            color: var(--light);
            border: 1px solid rgba(255,255,255,0.1);
        }
        
        /* صفحات دانلود و درباره ما */
        .download-page, .about-page {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.95);
            z-index: 1000;
            padding: 1rem;
            overflow-y: auto;
        }
        
        .download-content, .about-content {
            max-width: 95%;
            margin: 2rem auto;
            background: var(--dark-light);
            padding: 2rem;
            border-radius: var(--radius);
            border: 1px solid rgba(255,255,255,0.1);
            box-shadow: var(--shadow-lg);
        }
        
        .download-header, .about-header {
            text-align: center;
            margin-bottom: 2rem;
            position: relative;
        }
        
        .download-header h2, .about-header h2 {
            color: var(--primary);
            font-size: 1.8rem;
            margin-bottom: 1rem;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .close-download, .close-about {
            position: absolute;
            top: 0;
            left: 0;
            font-size: 2rem;
            cursor: pointer;
            color: var(--lighter);
            padding: 0.5rem;
        }
        
        /* آیتم‌های دانلود */
        .download-items {
            display: grid;
            gap: 1.5rem;
        }
        
        .download-item {
            background: rgba(30,30,30,0.7);
            padding: 1.5rem;
            border-radius: var(--radius-sm);
            border-left: 3px solid var(--primary);
            transition: var(--transition);
            box-shadow: var(--shadow);
        }
        
        .download-item:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow-lg);
        }
        
        .download-item h3 {
            color: var(--primary);
            margin-bottom: 1rem;
            font-size: 1.3rem;
            display: flex;
            align-items: center;
        }
        
        .download-item p {
            font-size: 0.95rem;
            color: var(--lighter);
            margin-bottom: 1.5rem;
        }
        
        .download-meta {
            display: flex;
            justify-content: space-between;
            margin-bottom: 1.5rem;
            font-size: 0.85rem;
            color: var(--lighter);
        }
        
        .download-btn {
            display: inline-flex;
            align-items: center;
            padding: 0.8rem 1.5rem;
            background: linear-gradient(135deg, var(--secondary), var(--secondary-dark));
            color: white;
            border-radius: 50px;
            font-weight: 600;
            text-decoration: none;
            transition: var(--transition);
            box-shadow: 0 5px 15px rgba(67,97,238,0.3);
        }
        
        .download-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(67,97,238,0.4);
        }
        
        /* متن درباره ما */
        .about-text {
            line-height: 1.8;
            margin-bottom: 2rem;
            font-size: 0.95rem;
            color: var(--lighter);
        }
        
        /* آمار و ارقام */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 1.5rem;
            margin: 2rem 0;
        }
        
        .stat-card {
            background: rgba(30,30,30,0.7);
            padding: 1.5rem;
            border-radius: var(--radius-sm);
            text-align: center;
            border: 1px solid rgba(255,255,255,0.1);
            transition: var(--transition);
        }
        
        .stat-card:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow);
        }
        
        .stat-value {
            font-size: 2rem;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 0.5rem;
        }
        
        /* تیم ما */
        .team-members {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1.5rem;
            margin: 2rem 0;
        }
        
        .team-member {
            background: rgba(30,30,30,0.7);
            padding: 1.5rem;
            border-radius: var(--radius-sm);
            text-align: center;
            border: 1px solid rgba(255,255,255,0.1);
        }
        
        .member-avatar {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            font-weight: bold;
            margin: 0 auto 1rem;
        }
        
        /* لینک‌های اجتماعی */
        .social-links {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin-top: 2rem;
        }
        
        .social-link {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 60px;
            height: 60px;
            border-radius: 50%;
            color: white;
            font-size: 1.5rem;
            transition: var(--transition);
            border: 1px solid rgba(255,255,255,0.1);
        }
        
        .telegram {
            background: #0088CC;
        }
        
        .instagram {
            background: linear-gradient(45deg, #405DE6, #5851DB, #833AB4, #C13584, #E1306C, #FD1D1D);
        }
        
        /* اعلان‌ها */
        .notification {
            position: fixed;
            bottom: 70px;
            right: 50%;
            transform: translateX(50%);
            background: var(--secondary);
            color: white;
            padding: 1rem 1.8rem;
            border-radius: 50px;
            z-index: 100;
            box-shadow: var(--shadow);
            display: none;
            max-width: 90%;
            text-align: center;
        }
        
        /* نوار پایینی */
        .bottom-nav {
            position: fixed;
            bottom: 0;
            left: 0;
            right: 0;
            display: flex;
            justify-content: center;
            background: var(--dark-light);
            padding: 1rem;
            border-top: 1px solid rgba(255,255,255,0.1);
            z-index: 99;
            box-shadow: 0 -8px 25px rgba(0,0,0,0.3);
        }
        
        .bottom-nav-btn {
            flex: 1;
            max-width: 220px;
            padding: 1rem;
            border-radius: 50px;
            background: var(--dark);
            color: var(--light);
            border: none;
            font-family: inherit;
            cursor: pointer;
            border: 1px solid rgba(255,255,255,0.1);
            display: flex;
            align-items: center;
            justify-content: center;
            transition: var(--transition);
        }
        
        #aboutBtn {
            color: var(--primary);
        }
        
        #downloadBtn {
            color: var(--secondary);
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
        
        @keyframes blink-caret {
            from, to { border-color: transparent }
            50% { border-color: var(--primary); }
        }
        
        /* منوی شناور */
        #floatingBtn {
            position: fixed;
            width: 60px;
            height: 60px;
            background: linear-gradient(145deg, var(--menu-color), #2575fc);
            border-radius: 18px;
            display: flex;
            justify-content: center;
            align-items: center;
            color: white;
            cursor: pointer;
            box-shadow: 0 10px 30px rgba(0,0,0,0.4);
            z-index: 100;
            bottom: 80px;
            right: 15px;
            border: none;
            transition: var(--transition);
            font-size: 1.5rem;
        }
        
        #floatingBtn:hover {
            transform: scale(1.1) rotate(90deg);
            box-shadow: 0 15px 40px rgba(0,0,0,0.5);
        }
        
        #menuContainer {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 99;
            opacity: 0;
            pointer-events: none;
            transition: var(--transition-slow);
        }
        
        #menuContainer.active {
            opacity: 1;
            pointer-events: auto;
        }
        
        #menuBackdrop {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.9);
        }
        
        #menuItems {
            background: var(--dark-light);
            border-radius: var(--radius);
            padding: 2rem;
            width: 90%;
            max-width: 400px;
            border-top: 6px solid var(--menu-color);
            box-shadow: 0 20px 50px rgba(0,0,0,0.5);
            transform: scale(0.9);
            transition: var(--transition-slow);
        }
        
        #menuContainer.active #menuItems {
            transform: scale(1);
        }
        
        .menu-item {
            padding: 1.2rem;
            margin: 0.8rem 0;
            border-radius: var(--radius-sm);
            cursor: pointer;
            display: flex;
            align-items: center;
            transition: var(--transition);
            background: rgba(255,255,255,0.05);
            border: 1px solid rgba(255,255,255,0.1);
        }
        
        .menu-item:hover {
            background: rgba(255,255,255,0.1);
            transform: translateX(-8px);
            border-color: var(--menu-color);
        }
        
        .menu-item i {
            margin-left: 1.2rem;
            font-size: 1.5rem;
            color: var(--menu-color);
            min-width: 30px;
            text-align: center;
        }
        
        .menu-item span {
            font-weight: 600;
        }
        
        /* رسپانسیو */
        @media (max-width: 768px) {
            .logo-icon {
                width: 45px;
                height: 45px;
            }
            
            .logo-text {
                font-size: 1.5rem;
            }
            
            .flag-item {
                padding: 0.8rem;
            }
            
            .flag-item span {
                font-size: 2rem;
            }
            
            #floatingBtn {
                width: 55px;
                height: 55px;
                bottom: 75px;
                font-size: 1.3rem;
            }
            
            .bottom-nav-btn {
                padding: 0.8rem;
                font-size: 0.9rem;
            }
            
            .menu-item {
                padding: 1rem;
            }
            
            .volume-number {
                font-size: 1.5rem;
            }
        }
    </style>
</head>
<body>
    <!-- صفحه لودینگ -->
    <div class="loading-screen" id="loadingScreen">
        <div class="logo-container">
            <div class="logo-text">
                <div class="mr">آقای</div>
                <div class="xero">ایکسرو</div>
            </div>
        </div>
        
        <div class="loading-footer">
            <div class="waiting-container">
                <div class="waiting-text">
                    منتظر باشید
                    <span class="dot">.</span>
                    <span class="dot">.</span>
                    <span class="dot">.</span>
                </div>
                <div class="counter" id="counter">0%</div>
            </div>
            <div class="loading-bar-container">
                <div class="loading-bar" id="loadingBar"></div>
            </div>
        </div>
    </div>
    
    <!-- صفحه اصلی -->
    <div class="main-screen" id="mainScreen">
        <div class="container">
            <header class="app-header">
                <div class="logo">
                    <div class="logo-icon">
                        <i class="fas fa-shield-alt"></i>
                    </div>
                    <div class="logo-text">XRO VPN</div>
                </div>
            </header>

            <!-- بخش استوری‌ها -->
            <div class="stories-container">
                <div class="story-item" onclick="openStory('you')">
                    <div class="story-circle">
                        <div class="story-icon">
                            <i class="fas fa-user"></i>
                        </div>
                    </div>
                    <div class="story-label">نظرات کاربران</div>
                </div>
                <div class="story-item" onclick="openStory('security')">
                    <div class="story-circle">
                        <div class="story-icon">
                            <i class="fas fa-lock"></i>
                        </div>
                    </div>
                    <div class="story-label">امنیت</div>
                </div>
                <div class="story-item" onclick="openStory('guide')">
                    <div class="story-circle">
                        <div class="story-icon">
                            <i class="fas fa-question"></i>
                        </div>
                    </div>
                    <div class="story-label">راهنمای خرید</div>
                </div>
            </div>

            <!-- کادر اعلانات -->
            <div class="announcement-box">
                <div id="typingText" class="typing-text"></div>
            </div>

            <!-- تب‌های اصلی -->
            <div class="main-tabs">
                <button class="main-tab active" onclick="showMainTab('home')">
                    <i class="fas fa-store"></i>
                    <span>فروشگاه</span>
                </button>
                <button class="main-tab" onclick="showMainTab('dns')">
                    <i class="fas fa-network-wired"></i>
                    <span>DNS</span>
                </button>
                <button class="main-tab" onclick="showMainTab('download')">
                    <i class="fas fa-download"></i>
                    <span>دانلود</span>
                </button>
            </div>
            
            <!-- محتوای تب‌های اصلی -->
            <div id="home-tab" class="main-tab-content active">
                <div class="message">
                    <span class="notice-label">توجه</span>
                    <span>این بخش مخصوص سفارش کانفیگ برای استفاده شخصی است</span>
                </div>
                <div class="flag-grid">
                    <!-- کادر شرایط جنگی -->
                    <div class="flag-item war active" onclick="openModal('شرایط جنگی', 1170, 170, false)">
                        <span>🇮🇷 ⚔️ 🇮🇱</span>
                        <p>شرایط جنگی</p>
                        <div class="country-info">سرورهای ویژه برای شرایط فعلی با پینگ بسیار پایین و اتصال پایدار</div>
                        <div class="status-badge war">ویژه</div>
                    </div>
                    
                    <div class="flag-item active" onclick="openModal('آمریکا', 1390, 298, false)">
                        <span>🇺🇸</span>
                        <p>آمریکا</p>
                        <div class="country-info">سرورهای پرسرعت در نیویورک و لس آنجلس با پینگ پایین</div>
                        <div class="status-badge active">سرویس فعال</div>
                    </div>
                    
                    <div class="flag-item active" onclick="openModal('انگلیس', 1390, 298, false)">
                        <span>🇬🇧</span>
                        <p>انگلیس</p>
                        <div class="country-info">سرورهای لندن با پهنای باند بالا و اتصال پایدار</div>
                        <div class="status-badge active">سرویس فعال</div>
                    </div>
                    
                    <div class="flag-item active" onclick="openModal('ترکیه', 1390, 198, false)">
                        <span>🇹🇷</span>
                        <p>ترکیه</p>
                        <div class="country-info">سرورهای استانبول با پینگ بسیار پایین برای کاربران ایرانی</div>
                        <div class="status-badge active">سرویس فعال</div>
                    </div>
                    
                    <div class="flag-item active" onclick="openModal('آلمان', 1390, 298, false)">
                        <span>🇩🇪</span>
                        <p>آلمان</p>
                        <div class="country-info">سرورهای فرانکفورت با اتصال پایدار و بدون قطعی</div>
                        <div class="status-badge active">سرویس فعال</div>
                    </div>
                    
                    <div class="flag-item active" onclick="openModal('لهستان', 1390, 298, false)">
                        <span>🇵🇱</span>
                        <p>لهستان</p>
                        <div class="country-info">سرورهای ورشو با پهنای باند بالا و اتصال پایدار</div>
                        <div class="status-badge active">سرویس فعال</div>
                    </div>
                    
                    <div class="flag-item active" onclick="openModal('فرانسه', 1390, 298, false)">
                        <span>🇫🇷</span>
                        <p>فرانسه</p>
                        <div class="country-info">سرورهای پاریس با پهنای باند بالا و اتصال پایدار</div>
                        <div class="status-badge active">سرویس فعال</div>
                    </div>
                    
                    <div class="flag-item active" onclick="openModal('هند', 1390, 198, false)">
                        <span>🇮🇳</span>
                        <p>هند</p>
                        <div class="country-info">سرورهای بمبئی با پهنای باند بالا و اتصال پایدار</div>
                        <div class="status-badge active">سرویس فعال</div>
                    </div>
                    
                    <div class="flag-item active" onclick="openModal('برزیل', 1390, 298, false)">
                        <span>🇧🇷</span>
                        <p>برزیل</p>
                        <div class="country-info">سرورهای سائوپائولو با پهنای باند بالا و اتصال پایدار</div>
                        <div class="status-badge active">سرویس فعال</div>
                    </div>
                    
                    <div class="flag-item inactive" onclick="showNotification('این سرویس به زودی فعال خواهد شد')">
                        <span>🇸🇦</span>
                        <p>عربستان</p>
                        <div class="country-info">سرورهای ریاض با پهنای باند بالا (به زودی)</div>
                        <div class="status-badge inactive">غیرفعال</div>
                    </div>
                    
                    <div class="flag-item inactive" onclick="showNotification('این سرویس به زودی فعال خواهد شد')">
                        <span>🇮🇶</span>
                        <p>عراق</p>
                        <div class="country-info">سرورهای بغداد با پهنای باند بالا (به زودی)</div>
                        <div class="status-badge inactive">غیرفعال</div>
                    </div>
                </div>
            </div>
            
            <div id="dns-tab" class="main-tab-content">
                <div class="message">
                    <span class="notice-label">توجه</span>
                    <span>این بخش با استفاده از DNS سرعتی، پایدار برای بازی برقرار کنید. کاهش پینگ و جلوگیری از نوسان در بازی‌های آنلاین</span>
                </div>
                
                <!-- بخش DNS -->
                <div class="dns-container">
                    <div class="dns-item">
                        <span class="dns-label">DNS اول:</span>
                        <span class="dns-value" id="dns1">78.157.42.100</span>
                        <button class="copy-btn" onclick="copyToClipboard('dns1')">کپی</button>
                    </div>
                    <div class="dns-item">
                        <span class="dns-label">DNS دوم:</span>
                        <span class="dns-value" id="dns2">78.157.42.101</span>
                        <button class="copy-btn" onclick="copyToClipboard('dns2')">کپی</button>
                    </div>
                </div>
            </div>
            
            <div id="download-tab" class="main-tab-content">
                <div class="message">
                    <span class="notice-label">توجه</span>
                    <span>این بخش مخصوص دانلود اپلیکیشن ویتوری برای سیستم شما است</span>
                </div>
                <div class="download-items">
                    <div class="download-item">
                        <h3>
                            <i class="fas fa-mobile-alt"></i>
                            نسخه اندروید
                        </h3>
                        <div class="download-meta">
                            <div class="meta-item"><i class="fas fa-code-branch"></i> نسخه 1.8.5</div>
                            <div class="meta-item"><i class="fas fa-calendar-alt"></i> 1402/05/12</div>
                        </div>
                        <p>نرم‌افزار v2rayNG برای دستگاه‌های اندروید. بهترین انتخاب برای کاربران اندروید با رابط کاربری ساده و امکانات پیشرفته.</p>
                        <a href="https://myket.ir/app/com.v2ray.ang" class="download-btn" target="_blank">
                            دانلود از مایکت
                            <i class="fas fa-download"></i>
                        </a>
                    </div>
                    
                    <div class="download-item">
                        <h3>
                            <i class="fas fa-desktop"></i>
                            نسخه ویندوز
                        </h3>
                        <div class="download-meta">
                            <div class="meta-item"><i class="fas fa-code-branch"></i> نسخه 6.27</div>
                            <div class="meta-item"><i class="fas fa-calendar-alt"></i> 1402/04/28</div>
                        </div>
                        <p>نرم‌افزار v2rayN برای سیستم‌عامل ویندوز. پشتیبانی از ویندوز 7 به بالا با قابلیت‌های مدیریت چند کانفیگ.</p>
                        <a href="#" class="download-btn" onclick="showNotification('لینک دانلود به زودی اضافه خواهد شد')">
                            دانلود (45MB)
                            <i class="fas fa-download"></i>
                        </a>
                    </div>
                    
                    <div class="download-item">
                        <h3>
                            <i class="fas fa-mobile"></i>
                            نسخه iOS
                        </h3>
                        <div class="download-meta">
                            <div class="meta-item"><i class="fas fa-code-branch"></i> نسخه 2.1.1</div>
                            <div class="meta-item"><i class="fas fa-calendar-alt"></i> 1402/03/15</div>
                        </div>
                        <p>نرم‌افزار Shadowrocket برای دستگاه‌های iOS. بهترین انتخاب برای کاربران آیفون و آیپد با رابط کاربری ساده.</p>
                        <a href="#" class="download-btn" onclick="showNotification('لینک اپ استور به زودی اضافه خواهد شد')">
                            دانلود از اپ استور
                            <i class="fas fa-download"></i>
                        </a>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- مودال استوری -->
        <div id="storyModal" class="story-modal">
            <div class="story-header">
                <div class="story-progress">
                    <div class="progress-bar">
                        <div class="progress-fill" id="progressFill1"></div>
                    </div>
                    <div class="progress-bar">
                        <div class="progress-fill" id="progressFill2"></div>
                    </div>
                </div>
                <div class="close-story" onclick="closeStory()">×</div>
            </div>
            <div class="story-content" id="storyContent">
                <!-- محتوای استوری در اینجا نمایش داده می‌شود -->
                <div class="nav-area left" onclick="prevStoryStep()"></div>
                <div class="nav-area right" onclick="nextStoryStep()"></div>
            </div>
        </div>
        
        <!-- مودال سفارش -->
        <div id="orderModal" class="modal">
            <div class="modal-content">
                <div class="modal-header" id="modalHeader">
                    <span class="close-modal" onclick="closeModal()">×</span>
                    <h2 id="modalCountryName"><span>آمریکا</span> 🇺🇸</h2>
                </div>
                <div class="modal-body">
                    <div class="modal-tabs" id="modalTabs"></div>
                    
                    <div id="volumeTab" class="modal-tab-content active">
                        <div class="slider-container">
                            <div class="slider-header">
                                <span>حجم کانفیگ:</span>
                                <span class="slider-value" id="volumeValue">10 گیگ</span>
                            </div>
                            <input type="range" min="10" max="300" value="10" class="slider" id="volumeSlider" oninput="updateVolume(this.value)">
                        </div>
                        <div class="price-info" id="volumePriceInfo">
                            قیمت هر گیگ: <span id="volumePriceText">1,390 تومان</span>
                        </div>
                        <div class="modal-footer">
                            <button class="btn btn-secondary" onclick="closeModal()">
                                انصراف
                            </button>
                            <button class="btn btn-primary" id="volumeNextButton" onclick="showModalTab('days')">
                                بعدی
                            </button>
                        </div>
                    </div>
                    
                    <div id="daysTab" class="modal-tab-content">
                        <div class="slider-container">
                            <div class="slider-header">
                                <span>تعداد روز:</span>
                                <span class="slider-value" id="daysValue">5 روز</span>
                            </div>
                            <input type="range" min="5" max="140" value="5" class="slider" id="daysSlider" oninput="updateDays(this.value)">
                        </div>
                        <div class="price-info" id="dayPriceInfo">
                            قیمت هر روز: <span id="dayPriceText">298 تومان</span>
                        </div>
                        <div class="modal-footer">
                            <button class="btn btn-secondary" onclick="showModalTab('volume')">
                                قبلی
                            </button>
                            <button class="btn btn-primary" id="daysNextButton">
                                بعدی
                            </button>
                        </div>
                    </div>
                    
                    <div id="countTab" class="modal-tab-content">
                        <div class="slider-container">
                            <div class="slider-header">
                                <span>تعداد کانفیگ:</span>
                                <span class="slider-value" id="countValue">3 عدد</span>
                            </div>
                            <input type="range" min="3" max="15" value="3" class="slider" id="countSlider" oninput="updateCount(this.value)">
                        </div>
                        <div class="price-info">
                            تعداد کانفیگ‌های مورد نیاز خود را انتخاب کنید
                        </div>
                        <div class="modal-footer">
                            <button class="btn btn-secondary" onclick="showModalTab('days')">
                                قبلی
                            </button>
                            <button class="btn btn-primary" onclick="showModalTab('final')">
                                بعدی
                            </button>
                        </div>
                    </div>
                    
                    <div id="finalTab" class="modal-tab-content">
                        <div class="final-price" id="finalPriceContainer">
                            قیمت نهایی: <span id="finalPrice">0</span> تومان
                        </div>
                        <div class="order-summary" id="orderSummary">
                            <p>
                                <span>کشور:</span>
                                <span class="value" id="finalCountry">آمریکا</span>
                            </p>
                            <p>
                                <span>حجم:</span>
                                <span class="value" id="finalVolume">10 گیگ</span>
                            </p>
                            <p>
                                <span>مدت:</span>
                                <span class="value" id="finalDays">5 روز</span>
                            </p>
                            <p id="finalCountContainer" style="display: none;">
                                <span>تعداد:</span>
                                <span class="value" id="finalCount">3 عدد</span>
                            </p>
                        </div>
                        <div class="modal-footer">
                            <button class="btn btn-secondary" id="finalPreviousButton">
                                قبلی
                            </button>
                            <button class="btn btn-primary" id="submitOrderButton" onclick="submitOrder()">
                                سفارش
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- صفحه درباره ما -->
        <div id="aboutPage" class="about-page">
            <div class="about-content">
                <div class="about-header">
                    <span class="close-about" onclick="closeAbout()">×</span>
                    <h2>درباره ما</h2>
                    <p>XRO VPN - ارائه کانفیگ سرورهای پایدار و پرسرعت</p>
                </div>
                
                <div class="about-text">
                    <p>XRO VPN ارائه دهنده کانفیگ سرورهای پایدار و پرسرعت در کشورهای مختلف می‌باشد. ما با استفاده از بهترین سرورها و فناوری‌های روز، اتصالی پایدار و با کیفیت را برای شما فراهم می‌کنیم.</p>
                    
                    <p>تیم ما متشکل از متخصصان شبکه است که سال‌ها تجربه در زمینه ارائه سرویس‌های اینترنتی دارند. ما از آخرین فناوری‌ها برای ارائه بهترین کیفیت استفاده می‌کنیم و همواره در حال به‌روزرسانی سرورها و بهبود خدمات خود هستیم.</p>
                </div>
                
                <h3 style="text-align: center; margin: 2rem 0 1.5rem; color: var(--primary);">تیم ما</h3>
                <div class="team-members">
                    <div class="team-member">
                        <div class="member-avatar">X</div>
                        <div class="member-name">آقای ایکسرو</div>
                        <div class="member-role">مدیر فنی و بنیان‌گذار</div>
                    </div>
                </div>
                
                <div class="social-links">
                    <a href="https://t.me/xrovpn" class="social-link telegram" target="_blank">
                        <i class="fab fa-telegram"></i>
                    </a>
                    <a href="#" class="social-link instagram" onclick="showNotification('صفحه اینستاگرام به زودی راه‌اندازی می‌شود')">
                        <i class="fab fa-instagram"></i>
                    </a>
                </div>
            </div>
        </div>
        
        <!-- اعلان -->
        <div class="notification" id="notification">
            این سرویس در حال حاضر غیرفعال می‌باشد
        </div>
        
        <!-- منوی شناور -->
        <button id="floatingBtn" aria-label="منوی اصلی">
            <i class="fas fa-bars"></i>
        </button>
        
        <div id="menuContainer">
            <div id="menuBackdrop"></div>
            <div id="menuItems">
                <div class="menu-item" onclick="closeMenu()">
                    <i class="fas fa-arrow-right"></i>
                    <span>بازگشت</span>
                </div>
                <div class="menu-item" onclick="showNotification('تست سرعت در نسخه بعدی اضافه خواهد شد')">
                    <i class="fas fa-tachometer-alt"></i>
                    <span>تست سرعت</span>
                </div>
                <div class="menu-item" onclick="showNotification('پشتیبانی تلگرام در نسخه بعدی فعال خواهد شد')">
                    <i class="fab fa-telegram"></i>
                    <span>پشتیبانی تلگرام</span>
                </div>
                <div class="menu-item" onclick="showAbout()">
                    <i class="fas fa-info-circle"></i>
                    <span>درباره ما</span>
                </div>
            </div>
        </div>
    </div>

    <script>
        // تنظیمات اولیه
        let currentOrder = {
            country: '',
            volume: 10,
            days: 5,
            count: 3,
            volumePrice: 1390,
            dayPrice: 298,
            isAffiliate: false,
            minVolume: 10,
            maxVolume: 300,
            minDays: 5,
            maxDays: 140,
            isWar: false
        };
        
        // داده‌های استوری
        const stories = {
            you: {
                title: "نظرات کاربران",
                steps: [
                    {
                        text: "این تنها بخشی از نظرات صدها کاربر راضی XRO VPN است",
                        duration: 3000,
                        image: "https://via.placeholder.com/300x300/FF6B35/FFFFFF?text=XRO+VPN",
                        comments: [
                            {
                                name: "زهرا",
                                text: "من تازه با این تیم آشنا شدم امیدوارم همینجوری باقی بمونه. سرعت فوق‌العاده‌ای داره!",
                                position: "right"
                            },
                            {
                                name: "محمد",
                                text: "بهترین سرویسی که تا حالا استفاده کردم. واقعا راضیم و به همه توصیه می‌کنم",
                                position: "left"
                            }
                        ]
                    }
                ]
            },
            security: {
                title: "امنیت",
                steps: [
                    {
                        text: "امنیت و حریم خصوصی شما اولویت اصلی ماست",
                        duration: 3000,
                        image: "https://via.placeholder.com/300x300/4361EE/FFFFFF?text=امنیت"
                    },
                    {
                        text: "ما از سال ۱۳۹۸ تا همین الان درحال خدمت رسانی به مردم هستیم و از هرگونه مشکل و رفتن اطلاعات به دست غریبه ها جلوگیری میکنیم پس نگران نباش",
                        duration: 5000,
                        image: "https://via.placeholder.com/300x300/FF6B35/FFFFFF?text=حفاظت"
                    }
                ]
            },
            guide: {
                title: "راهنمای خرید",
                steps: [
                    {
                        text: "راهنمای خرید از XRO VPN",
                        duration: 3000,
                        image: "https://via.placeholder.com/300x300/4361EE/FFFFFF?text=راهنما"
                    },
                    {
                        text: "مراحل خرید از XRO VPN:\n1. وارد بخش 'برای خودم' شوید\n2. کشور مورد نظر خود را انتخاب کنید\n3. حجم و مدت زمان مورد نیاز را تنظیم کنید\n4. روی دکمه 'سفارش' کلیک کنید",
                        duration: 8000,
                        image: "https://via.placeholder.com/300x300/FF6B35/FFFFFF?text=مراحل+خرید"
                    }
                ]
            }
        };
        
        let currentStory = null;
        let currentStep = 0;
        let storyInterval = null;
        let progressInterval = null;
        
        // شمارنده حجم کل
        let totalVolume = 1700346912;
        let volumeInterval = null;
        
        // اعلانات
        const days = ['یکشنبه', 'دوشنبه', 'سه‌شنبه', 'چهارشنبه', 'پنجشنبه', 'جمعه', 'شنبه'];
        const today = new Date().getDay();
        const todayName = days[today];
        
        const announcements = [
            "سرویس جدید جنگی اضافه شده",
            "آقای ایکسرو حامی ایرانیان است",
            "ویتوری هم اکنون در مایکت!"
        ];
        
        // نمایش تب‌های اصلی
        function showMainTab(tabName) {
            const tabs = document.querySelectorAll('.main-tab');
            const tabContents = document.querySelectorAll('.main-tab-content');
            
            tabs.forEach(tab => tab.classList.remove('active'));
            tabContents.forEach(content => content.classList.remove('active'));
            
            document.getElementById(`${tabName}-tab`).classList.add('active');
            document.querySelector(`.main-tab[onclick="showMainTab('${tabName}')"]`).classList.add('active');
            
            closeMenu();
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
        
        // نمایش صفحه درباره ما
        function showAbout() {
            document.getElementById('aboutPage').style.display = 'block';
            document.body.style.overflow = 'hidden';
            closeMenu();
        }
        
        function closeAbout() {
            document.getElementById('aboutPage').style.display = 'none';
            document.body.style.overflow = 'auto';
        }
        
        // باز کردن مودال سفارش
        function openModal(country, volumePrice, dayPrice, isAffiliate) {
            const isWar = country === 'شرایط جنگی';
            
            currentOrder = {
                country: country,
                volume: isAffiliate ? 15 : 10,
                days: isAffiliate ? 10 : 5,
                count: 3,
                volumePrice: volumePrice,
                dayPrice: dayPrice,
                isAffiliate: isAffiliate,
                minVolume: isAffiliate ? 15 : 10,
                maxVolume: isAffiliate ? 1000 : 300,
                minDays: isAffiliate ? 10 : 5,
                maxDays: isAffiliate ? 365 : 140,
                isWar: isWar
            };
            
            // تنظیم استایل‌های مربوط به شرایط جنگی
            const modalHeader = document.getElementById('modalHeader');
            const modalTabs = document.getElementById('modalTabs');
            const volumeValue = document.getElementById('volumeValue');
            const daysValue = document.getElementById('daysValue');
            const volumeSlider = document.getElementById('volumeSlider');
            const daysSlider = document.getElementById('daysSlider');
            const volumePriceInfo = document.getElementById('volumePriceInfo');
            const dayPriceInfo = document.getElementById('dayPriceInfo');
            const finalPriceContainer = document.getElementById('finalPriceContainer');
            const orderSummary = document.getElementById('orderSummary');
            const volumeNextButton = document.getElementById('volumeNextButton');
            const daysNextButton = document.getElementById('daysNextButton');
            const submitOrderButton = document.getElementById('submitOrderButton');
            
            if (isWar) {
                modalHeader.className = 'modal-header war';
                volumeValue.className = 'slider-value war';
                daysValue.className = 'slider-value war';
                volumeSlider.className = 'slider war';
                daysSlider.className = 'slider war';
                volumePriceInfo.className = 'price-info war';
                dayPriceInfo.className = 'price-info war';
                finalPriceContainer.className = 'final-price war';
                orderSummary.className = 'order-summary war';
                volumeNextButton.className = 'btn btn-war';
                daysNextButton.className = 'btn btn-war';
                submitOrderButton.className = 'btn btn-war';
            } else {
                modalHeader.className = 'modal-header';
                volumeValue.className = 'slider-value';
                daysValue.className = 'slider-value';
                volumeSlider.className = 'slider';
                daysSlider.className = 'slider';
                volumePriceInfo.className = 'price-info';
                dayPriceInfo.className = 'price-info';
                finalPriceContainer.className = 'final-price';
                orderSummary.className = 'order-summary';
                volumeNextButton.className = 'btn btn-primary';
                daysNextButton.className = 'btn btn-primary';
                submitOrderButton.className = 'btn btn-primary';
            }
            
            document.getElementById('modalCountryName').innerHTML = `<span>${country}</span> ${getCountryFlag(country)}`;
            document.getElementById('finalCountry').textContent = country;
            document.getElementById('volumePriceText').textContent = volumePrice.toLocaleString('fa-IR') + ' تومان';
            document.getElementById('dayPriceText').textContent = dayPrice.toLocaleString('fa-IR') + ' تومان';
            
            volumeSlider.min = currentOrder.minVolume;
            volumeSlider.max = currentOrder.maxVolume;
            volumeSlider.value = currentOrder.volume;
            
            daysSlider.min = currentOrder.minDays;
            daysSlider.max = currentOrder.maxDays;
            daysSlider.value = currentOrder.days;
            
            setupModalTabs(isAffiliate);
            document.getElementById('orderModal').style.display = 'block';
            document.body.style.overflow = 'hidden';
            
            updateVolume(currentOrder.volume);
            updateDays(currentOrder.days);
            updateCount(currentOrder.count);
            showModalTab('volume');
        }
        
        // دریافت پرچم کشور
        function getCountryFlag(country) {
            const flags = {
                'آمریکا': '🇺🇸',
                'انگلیس': '🇬🇧',
                'ترکیه': '🇹🇷',
                'هلند': '🇳🇱',
                'فرانسه': '🇫🇷',
                'آلمان': '🇩🇪',
                'لهستان': '🇵🇱',
                'هند': '🇮🇳',
                'برزیل': '🇧🇷',
                'عربستان': '🇸🇦',
                'عراق': '🇮🇶',
                'شرایط جنگی': '🇮🇷 ⚔️ 🇮🇱'
            };
            return flags[country] || '';
        }
        
        // تنظیم تب‌های مودال
        function setupModalTabs(isAffiliate) {
            const modalTabs = document.getElementById('modalTabs');
            modalTabs.innerHTML = `
                <div class="modal-tab ${currentOrder.isWar ? 'war' : ''} active" onclick="showModalTab('volume')">حجم</div>
                <div class="modal-tab ${currentOrder.isWar ? 'war' : ''}" onclick="showModalTab('days')">روز</div>
                ${isAffiliate ? `<div class="modal-tab ${currentOrder.isWar ? 'war' : ''}" onclick="showModalTab('count')">تعداد</div>` : ''}
                <div class="modal-tab ${currentOrder.isWar ? 'war' : ''}" onclick="showModalTab('final')">نهایی</div>
            `;
            
            document.getElementById('finalCountContainer').style.display = isAffiliate ? 'flex' : 'none';
            document.getElementById('daysNextButton').onclick = isAffiliate ? () => showModalTab('count') : () => showModalTab('final');
            document.getElementById('finalPreviousButton').onclick = isAffiliate ? () => showModalTab('count') : () => showModalTab('days');
        }
        
        // نمایش تب‌های مودال
        function showModalTab(tabName) {
            const modalTabs = document.querySelectorAll('.modal-tab');
            const modalTabContents = document.querySelectorAll('.modal-tab-content');
            
            modalTabs.forEach(tab => tab.classList.remove('active'));
            modalTabContents.forEach(content => content.classList.remove('active'));
            
            document.getElementById(`${tabName}Tab`).classList.add('active');
            document.querySelector(`.modal-tab[onclick="showModalTab('${tabName}')"]`).classList.add('active');
            
            updatePrice();
        }
        
        // به‌روزرسانی حجم
        function updateVolume(value) {
            currentOrder.volume = parseInt(value);
            document.getElementById('volumeValue').textContent = `${currentOrder.volume} گیگ`;
            document.getElementById('finalVolume').textContent = `${currentOrder.volume} گیگ`;
            updatePrice();
        }
        
        // به‌روزرسانی روزها
        function updateDays(value) {
            currentOrder.days = parseInt(value);
            document.getElementById('daysValue').textContent = `${currentOrder.days} روز`;
            document.getElementById('finalDays').textContent = `${currentOrder.days} روز`;
            updatePrice();
        }
        
        // به‌روزرسانی تعداد
        function updateCount(value) {
            currentOrder.count = parseInt(value);
            document.getElementById('countValue').textContent = `${currentOrder.count} عدد`;
            document.getElementById('finalCount').textContent = `${currentOrder.count} عدد`;
            updatePrice();
        }
        
        // محاسبه قیمت نهایی
        function updatePrice() {
            const totalPrice = (currentOrder.volume * currentOrder.volumePrice + currentOrder.days * currentOrder.dayPrice) * (currentOrder.isAffiliate ? currentOrder.count : 1);
            document.getElementById('finalPrice').textContent = totalPrice.toLocaleString('fa-IR');
        }
        
        // بستن مودال
        function closeModal() {
            document.getElementById('orderModal').style.display = 'none';
            document.body.style.overflow = 'auto';
        }
        
        // ارسال سفارش
        function submitOrder() {
            const totalPrice = (currentOrder.volume * currentOrder.volumePrice + currentOrder.days * currentOrder.dayPrice) * (currentOrder.isAffiliate ? currentOrder.count : 1);
            const message = `سفارش جدید برای XRO VPN:\nکشور: ${currentOrder.country}\nحجم: ${currentOrder.volume} گیگ\nمدت: ${currentOrder.days} روز${currentOrder.isAffiliate ? `\nتعداد: ${currentOrder.count} عدد` : ''}\nقیمت نهایی: ${totalPrice.toLocaleString('fa-IR')} تومان`;
            window.open(`https://t.me/u0v0n?text=${encodeURIComponent(message)}`, '_blank');
            closeModal();
        }
        
        // توابع مربوط به استوری
        function openStory(storyKey) {
            currentStory = stories[storyKey];
            currentStep = 0;
            document.getElementById('storyModal').style.display = 'block';
            document.body.style.overflow = 'hidden';
            showStoryStep();
        }
        
        function closeStory() {
            clearInterval(storyInterval);
            clearInterval(progressInterval);
            document.getElementById('storyModal').style.display = 'none';
            document.body.style.overflow = 'auto';
            currentStory = null;
            currentStep = 0;
        }
        
        function showStoryStep() {
            const storyContent = document.getElementById('storyContent');
            const step = currentStory.steps[currentStep];
            
            // پاک کردن محتوای قبلی
            storyContent.innerHTML = '';
            
            // ایجاد عناصر جدید
            if (step.image) {
                const imageElement = document.createElement('img');
                imageElement.className = 'story-image';
                imageElement.src = step.image;
                imageElement.alt = step.text.substring(0, 20) + '...';
                storyContent.appendChild(imageElement);
                
                setTimeout(() => {
                    imageElement.classList.add('show');
                }, 100);
            }
            
            const textElement = document.createElement('div');
            textElement.className = 'story-text';
            textElement.textContent = step.text;
            
            storyContent.appendChild(textElement);
            
            // نمایش انیمیشن متن
            setTimeout(() => {
                textElement.classList.add('show');
            }, 100);
            
            // اضافه کردن نظرات اگر وجود دارد
            if (step.comments) {
                const commentsContainer = document.createElement('div');
                commentsContainer.className = 'story-comments';
                storyContent.appendChild(commentsContainer);
                
                // نمایش نظرات با تاخیر
                step.comments.forEach((comment, index) => {
                    setTimeout(() => {
                        const commentElement = document.createElement('div');
                        commentElement.className = `comment ${comment.position}`;
                        
                        const avatar = document.createElement('div');
                        avatar.className = 'comment-avatar';
                        avatar.textContent = comment.name.charAt(0);
                        
                        const text = document.createElement('div');
                        text.className = 'comment-text';
                        text.textContent = comment.text;
                        
                        commentElement.appendChild(avatar);
                        commentElement.appendChild(text);
                        commentsContainer.appendChild(commentElement);
                        
                        setTimeout(() => {
                            commentElement.classList.add('show');
                        }, 100);
                    }, index * 1000);
                });
            }
            
            // اضافه کردن ناحیه‌های ناوبری
            const navLeft = document.createElement('div');
            navLeft.className = 'nav-area left';
            navLeft.onclick = prevStoryStep;
            
            const navRight = document.createElement('div');
            navRight.className = 'nav-area right';
            navRight.onclick = nextStoryStep;
            
            storyContent.appendChild(navLeft);
            storyContent.appendChild(navRight);
            
            // شروع پیشرفت بار
            startProgressBars(step.duration);
            
            // تنظیم تایمر برای مرحله بعدی
            storyInterval = setTimeout(() => {
                nextStoryStep();
            }, step.duration);
        }
        
        function prevStoryStep() {
            clearInterval(storyInterval);
            clearInterval(progressInterval);
            
            if (currentStep > 0) {
                currentStep--;
                showStoryStep();
            } else {
                closeStory();
            }
        }
        
        function nextStoryStep() {
            clearInterval(storyInterval);
            clearInterval(progressInterval);
            
            currentStep++;
            if (currentStep < currentStory.steps.length) {
                showStoryStep();
            } else {
                closeStory();
            }
        }
        
        function startProgressBars(duration) {
            const progressBars = document.querySelectorAll('.progress-fill');
            progressBars.forEach(bar => bar.style.width = '0%');
            
            clearInterval(progressInterval);
            
            const progressFill = document.getElementById(`progressFill${currentStep + 1}`);
            let width = 0;
            const increment = 100 / (duration / 50);
            
            progressInterval = setInterval(() => {
                if (width >= 100) {
                    clearInterval(progressInterval);
                } else {
                    width += increment;
                    progressFill.style.width = `${width}%`;
                }
            }, 50);
        }
        
        // منوی شناور
        const floatingBtn = document.getElementById('floatingBtn');
        const menuContainer = document.getElementById('menuContainer');
        
        function toggleMenu() {
            menuContainer.classList.toggle('active');
        }
        
        function closeMenu() {
            menuContainer.classList.remove('active');
        }
        
        floatingBtn.addEventListener('click', function(e) {
            e.stopPropagation();
            toggleMenu();
        });
        
        document.getElementById('menuBackdrop').addEventListener('click', function() {
            closeMenu();
        });
        
        // شمارنده حجم کل
        function updateVolumeCounter() {
            // ذخیره مقدار فعلی در localStorage
            const savedVolume = localStorage.getItem('totalVolume');
            if (savedVolume) {
                totalVolume = parseInt(savedVolume);
            }
            
            // نمایش مقدار اولیه
            document.getElementById('totalVolume').textContent = totalVolume.toLocaleString('fa-IR');
            
            // افزایش خودکار هر ثانیه
            volumeInterval = setInterval(() => {
                totalVolume += Math.floor(Math.random() * 1000) + 500;
                document.getElementById('totalVolume').textContent = totalVolume.toLocaleString('fa-IR');
                
                // ذخیره مقدار جدید در localStorage
                localStorage.setItem('totalVolume', totalVolume.toString());
            }, 1000);
        }
        
        // نمایش اعلان تایپی
        function typeAnnouncement() {
            const typingText = document.getElementById('typingText');
            let currentAnnouncement = 0;
            let i = 0;
            let isDeleting = false;
            const speed = 50; // سرعت تایپ (میلی‌ثانیه)
            
            function typeWriter() {
                const announcement = announcements[currentAnnouncement];
                
                if (isDeleting) {
                    typingText.textContent = announcement.substring(0, i-1);
                    i--;
                } else {
                    typingText.textContent = announcement.substring(0, i+1);
                    i++;
                }
                
                if (!isDeleting && i === announcement.length) {
                    isDeleting = true;
                    setTimeout(typeWriter, 2000);
                } else if (isDeleting && i === 0) {
                    isDeleting = false;
                    currentAnnouncement = (currentAnnouncement + 1) % announcements.length;
                    setTimeout(typeWriter, 500);
                } else {
                    setTimeout(typeWriter, speed);
                }
            }
            
            typeWriter();
        }
        
        // کپی DNS
        function copyToClipboard(id) {
            const text = document.getElementById(id).textContent;
            navigator.clipboard.writeText(text).then(() => {
                showNotification('DNS با موفقیت کپی شد');
            }).catch(err => {
                console.error('خطا در کپی کردن متن: ', err);
                showNotification('خطا در کپی کردن DNS');
            });
        }
        
        // بستن با کلید ESC
        document.addEventListener('keydown', function(e) {
            if (e.key === 'Escape') {
                if (menuContainer.classList.contains('active')) {
                    closeMenu();
                } else if (document.getElementById('orderModal').style.display === 'block') {
                    closeModal();
                } else if (document.getElementById('aboutPage').style.display === 'block') {
                    closeAbout();
                } else if (document.getElementById('storyModal').style.display === 'block') {
                    closeStory();
                }
            }
        });
        
        // شمارنده و تغییر صفحه
        const loadingScreen = document.getElementById('loadingScreen');
        const mainScreen = document.getElementById('mainScreen');
        const loadingBar = document.getElementById('loadingBar');
        const counter = document.getElementById('counter');
        const mrText = document.querySelector('.mr');
        const xeroText = document.querySelector('.xero');
        const loadingFooter = document.querySelector('.loading-footer');
        
        let count = 0;
        const interval = setInterval(() => {
            if (count < 100) {
                count++;
                loadingBar.style.width = `${count}%`;
                counter.textContent = `${count}%`;
                
                const glowIntensity = count/3;
                loadingBar.style.boxShadow = `0 0 ${glowIntensity}px rgba(255, 215, 0, 0.7)`;
            } else {
                clearInterval(interval);
                
                // انیمیشن خروج بخش پایین
                loadingFooter.style.animation = 'slideDown 0.8s forwards';
                
                // تاخیر قبل از انیمیشن خروج متن
                setTimeout(() => {
                    // انیمیشن خروج متن‌ها به جهت مخالف
                    mrText.style.animation = 'slideOutRight 0.8s forwards';
                    xeroText.style.animation = 'slideOutLeft 0.8s forwards';
                    
                    // نمایش صفحه اصلی پس از اتمام انیمیشن‌ها
                    setTimeout(() => {
                        loadingScreen.style.display = 'none';
                        mainScreen.style.display = 'block';
                        mainScreen.style.opacity = '1';
                        
                        // مقداردهی اولیه تب‌ها
                        showMainTab('home');
                        typeAnnouncement();
                    }, 800);
                }, 300);
            }
        }, 40);
    </script>
</body>
</html>
