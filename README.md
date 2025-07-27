<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>فروشگاه VPN - ایکسرو</title>
    <style>
        :root {
            --primary-color: #6e45e2;
            --primary-light: #9c64ff;
            --primary-dark: #4a1fb8;
            --secondary-color: #3dc8d5;
            --danger-color: #ff4e64;
            --success-color: #4ce1b6;
            --warning-color: #ffb54a;
            --text-color: #f0f4ff;
            --text-light: #c5d0e8;
            --bg-color: #0a0e1a;
            --card-bg: #151a2d;
            --card-hover: #1d2442;
            --border-color: rgba(110, 69, 226, 0.3);
            --shadow-color: rgba(0, 0, 0, 0.6);
            --overlay-color: rgba(0, 0, 0, 0.85);
            --gradient-primary: linear-gradient(135deg, var(--primary-light), var(--primary-color));
            --gradient-secondary: linear-gradient(135deg, var(--secondary-color), #2a9fd8);
            --gradient-danger: linear-gradient(135deg, var(--danger-color), #ff6b6b);
            --gradient-success: linear-gradient(135deg, var(--success-color), #3dcc91);
            --gradient-warning: linear-gradient(135deg, var(--warning-color), #ff8a3d);
            --glass-effect: linear-gradient(135deg, rgba(21, 26, 45, 0.8), rgba(33, 40, 70, 0.6));
            --glass-border: 1px solid rgba(255, 255, 255, 0.1);
            --glass-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.36);
            --transition-fast: all 0.2s cubic-bezier(0.4, 0, 0.2, 1);
            --transition-medium: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            --transition-slow: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
            --bg-image: url('https://fs.noorgram.ir/pic/2020/26/%D8%B9%DA%A9%D8%B3%20%D9%BE%D8%B3%20%D8%B2%D9%85%DB%8C%D9%86%D9%87%20%D8%AA%D9%84%DA%AF%D8%B1%D8%A7%D9%85%20(2).jpg');
        }

        /* Theme-specific styles */
        body.theme-default {
            --primary-color: #6e45e2;
            --primary-light: #9c64ff;
            --primary-dark: #4a1fb8;
            --secondary-color: #3dc8d5;
            --bg-color: #0a0e1a;
            --card-bg: #151a2d;
            --text-color: #f0f4ff;
            --text-light: #c5d0e8;
            --bg-image: url('https://fs.noorgram.ir/pic/2020/26/%D8%B9%DA%A9%D8%B3%20%D9%BE%D8%B3%20%D8%B2%D9%85%DB%8C%D9%86%D9%87%20%D8%AA%D9%84%DA%AF%D8%B1%D8%A7%D9%85%20(2).jpg');
        }

        body.theme-bomb {
            --primary-color: #ff0000;
            --primary-light: #ff6b6b;
            --primary-dark: #b80000;
            --secondary-color: #ffb54a;
            --bg-color: #1a0000;
            --card-bg: #2a0a0a;
            --text-color: #ffffff;
            --text-light: #e8c5c5;
            --bg-image: url('https://fs.noorgram.ir/pic/2020/26/%D8%B9%DA%A9%D8%B3%20%D8%B4%D8%A7%D8%AE%20%D8%A8%D8%B1%D8%A7%DB%8C%20%D9%BE%D8%B3%20%D8%B2%D9%85%DB%8C%D9%86%D9%87%20%D8%AA%D9%84%DA%AF%D8%B1%D8%A7%D9%85.jpg');
        }

        body.theme-space {
            --primary-color: #ffffff;
            --primary-light: #cccccc;
            --primary-dark: #999999;
            --secondary-color: #3dc8d5;
            --bg-color: #000000;
            --card-bg: #0a0a0a;
            --text-color: #ffffff;
            --text-light: #e0e0e0;
            --bg-image: url('https://fs.noorgram.ir/pic/2020/26/%D8%B9%DA%A9%D8%B3%20%D9%BE%D8%B3%20%D8%B2%D9%85%DB%8C%D9%86%D9%87%20%D8%AA%D9%84%DA%AF%D8%B1%D8%A7%D9%85%20(1).jpg');
        }

        /* Base Styles */
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            -webkit-tap-highlight-color: transparent;
        }

        body {
            font-family: 'Vazirmatn', 'Segoe UI', system-ui, sans-serif;
            background-color: var(--bg-color);
            color: var(--text-color);
            height: 100vh;
            overflow: hidden;
            user-select: none;
            touch-action: manipulation;
            background-image: var(--bg-image);
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            background-blend-mode: overlay;
            background-color: rgba(10, 14, 26, 0.9);
        }

        /* Particle Background */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            overflow: hidden;
        }

        .particle {
            position: absolute;
            background: rgba(255, 255, 255, 0.5);
            border-radius: 50%;
            pointer-events: none;
            animation: floatParticle linear infinite;
        }

        @keyframes floatParticle {
            0% { transform: translateY(0) translateX(0); opacity: 0; }
            10% { opacity: 1; }
            90% { opacity: 1; }
            100% { transform: translateY(-100vh) translateX(20px); opacity: 0; }
        }

        /* Content Window */
        #contentWindow {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1000;
            display: block;
            opacity: 1;
            transform: translateY(0);
            overflow: hidden;
        }

        .top-bar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 18px 25px;
            background: var(--glass-effect);
            border-bottom: var(--glass-border);
            box-shadow: var(--glass-shadow);
            position: relative;
            z-index: 100;
            backdrop-filter: blur(10px);
        }

        .logo {
            font-size: 1.1rem;
            font-weight: 700;
            color: var(--text-color);
            padding: 10px 15px;
            border-radius: 12px;
            cursor: pointer;
            background: rgba(110, 69, 226, 0.15);
            display: flex;
            align-items: center;
            gap: 10px;
            transition: var(--transition-medium);
            border: 1px solid rgba(110, 69, 226, 0.2);
        }

        .logo:hover {
            background: rgba(110, 69, 226, 0.25);
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(110, 69, 226, 0.3);
        }

        .menu-btn {
            width: 40px;
            height: 40px;
            display: flex;
            flex-direction: column;
            justify-content: space-around;
            align-items: center;
            cursor: pointer;
            padding: 8px;
            border-radius: 12px;
            transition: var(--transition-medium);
            background: rgba(110, 69, 226, 0.1);
            border: 1px solid rgba(110, 69, 226, 0.2);
        }

        .menu-btn:hover {
            background: rgba(110, 69, 226, 0.2);
            transform: rotate(90deg);
        }

        .menu-line {
            width: 100%;
            height: 3px;
            background-color: var(--text-color);
            border-radius: 2px;
            transition: var(--transition-medium);
        }

        .menu-btn:hover .menu-line {
            background-color: var(--primary-color);
        }

        .content {
            height: calc(100vh - 70px);
            display: flex;
            flex-direction: column;
            padding: 20px;
            position: relative;
            overflow-y: auto;
        }

        .welcome-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            flex: 1;
        }

        .news-container {
            width: 100%;
            max-width: 500px;
            margin: 0 auto;
            padding: 20px;
            background: var(--glass-effect);
            border-radius: 18px;
            border: var(--glass-border);
            box-shadow: var(--glass-shadow);
            backdrop-filter: blur(10px);
            text-align: center;
            line-height: 1.8;
        }

        .news-title {
            color: var(--primary-color);
            font-size: 1.2rem;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            font-weight: 700;
        }

        .news-content {
            color: var(--text-light);
            font-size: 0.95rem;
            margin-bottom: 12px;
            text-align: right;
        }

        .update-item {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 10px;
            padding: 10px;
            border-radius: 10px;
            background: rgba(21, 26, 45, 0.4);
        }

        .update-icon {
            font-size: 1.2rem;
            color: var(--primary-color);
            min-width: 30px;
        }

        .update-text {
            flex: 1;
            text-align: right;
        }

        .news-footer {
            display: flex;
            justify-content: space-between;
            margin-top: 15px;
            font-size: 0.85rem;
            color: var(--text-light);
        }

        .version-code {
            background: linear-gradient(90deg, #ff4e64, #feb47b, #6e45e2, #3dc8d5);
            background-size: 300% 300%;
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: gradientShift 5s ease infinite;
            font-weight: bold;
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .creator {
            font-size: 1.1rem;
            color: var(--text-light);
            margin-top: 20px;
            text-align: center;
            height: 25px;
            text-shadow: 0 0 10px rgba(110, 69, 226, 0.3);
        }

        /* Floating Action Button */
        .floating-btn {
            position: fixed;
            bottom: 25px;
            left: 25px;
            width: 75px;
            height: 75px;
            background: var(--gradient-primary);
            border-radius: 18px;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 28px;
            color: white;
            box-shadow: 0 10px 30px rgba(110, 69, 226, 0.5);
            cursor: pointer;
            z-index: 100;
            border: none;
            outline: none;
            transition: var(--transition-medium);
        }

        .floating-btn:hover {
            transform: translateY(-5px) scale(1.1);
            box-shadow: 0 15px 40px rgba(110, 69, 226, 0.7);
        }

        /* Modal Windows */
        .modal-window {
            position: fixed;
            background: var(--glass-effect);
            z-index: 1000;
            transition: var(--transition-medium);
            box-shadow: var(--glass-shadow);
            overflow: hidden;
            display: flex;
            flex-direction: column;
            border: var(--glass-border);
            backdrop-filter: blur(20px);
            border-radius: 18px;
        }

        .main-menu {
            top: -100%;
            right: 0;
            width: 100%;
            height: auto;
            max-height: 65%;
            border-radius: 0 0 18px 18px;
        }

        .main-menu.open {
            top: 0;
        }

        .quick-menu {
            bottom: -60%;
            left: 0;
            width: 100%;
            height: auto;
            max-height: 55%;
            border-radius: 18px 18px 0 0;
        }

        .quick-menu.open {
            bottom: 0;
        }

        .shop-menu {
            bottom: -100%;
            left: 0;
            width: 100%;
            height: 75%;
            max-height: 600px;
            border-radius: 18px 18px 0 0;
        }

        .shop-menu.open {
            bottom: 0;
        }

        .challenge-window {
            top: -100%;
            right: 0;
            width: 100%;
            height: 50%;
            max-height: 500px;
            border-radius: 0 0 18px 18px;
        }

        .challenge-window.open {
            top: 0;
        }

        .settings-panel {
            top: -100%;
            right: 0;
            width: 100%;
            height: 55%;
            border-radius: 0 0 18px 18px;
        }

        .settings-panel.open {
            top: 0;
        }

        .confirm-window {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%) scale(0.9);
            width: 90%;
            max-width: 350px;
            border-radius: 18px;
            padding: 20px;
            z-index: 1007;
            opacity: 0;
            visibility: hidden;
            border: var(--glass-border);
            background: var(--glass-effect);
            box-shadow: var(--glass-shadow);
            backdrop-filter: blur(20px);
        }

        .confirm-window.open {
            transform: translate(-50%, -50%) scale(1);
            opacity: 1;
            visibility: visible;
        }

        .help-window {
            top: -100%;
            right: 0;
            width: 100%;
            height: 70%;
            max-height: 700px;
            border-radius: 0 0 18px 18px;
        }

        .help-window.open {
            top: 0;
        }

        .hiddify-window {
            bottom: -100%;
            left: 0;
            width: 100%;
            height: 75%;
            max-height: 750px;
            border-radius: 18px 18px 0 0;
            transform: translateY(100%);
            transition: transform 0.4s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .hiddify-window.open {
            transform: translateY(0);
            bottom: 0;
        }

        .invite-window {
            top: -100%;
            right: 0;
            width: 100%;
            height: auto;
            max-height: 70%;
            border-radius: 0 0 18px 18px;
        }

        .invite-window.open {
            top: 0;
        }

        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
            padding: 18px;
            padding-bottom: 12px;
            border-bottom: var(--glass-border);
        }

        .modal-title {
            font-weight: 700;
            color: var(--text-color);
            font-size: 1.2rem;
        }

        .close-btn {
            cursor: pointer;
            font-size: 1.6rem;
            color: var(--text-color);
            transition: var(--transition-medium);
            width: 38px;
            height: 38px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            position: relative;
        }

        .close-btn:hover {
            background: rgba(110, 69, 226, 0.1);
            transform: rotate(90deg);
            color: var(--primary-color);
        }

        .close-btn::before {
            content: "";
            position: absolute;
            width: 20px;
            height: 20px;
            background: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24' fill='%23f0f4ff'%3E%3Cpath d='M12 2L10 0L6 4L2 0L0 2L4 6L0 10L2 12L6 8L10 12L12 10L8 6L12 2Z'/%3E%3C/svg%3E") no-repeat center;
            background-size: contain;
            transition: var(--transition-medium);
        }

        .close-btn:hover::before {
            transform: rotate(180deg);
        }

        .close-btn span {
            display: none;
        }

        .modal-content {
            flex: 1;
            overflow-y: auto;
            padding: 18px;
        }

        /* Menu Items */
        .menu-item {
            padding: 18px;
            margin-bottom: 12px;
            background: rgba(21, 26, 45, 0.6);
            border-radius: 14px;
            cursor: pointer;
            transition: var(--transition-medium);
            border: var(--glass-border);
            box-shadow: var(--glass-shadow);
        }

        .menu-item:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.4);
            border-color: var(--primary-color);
            background: var(--card-hover);
        }

        .menu-item-title {
            font-weight: 700;
            margin-bottom: 8px;
            color: var(--text-color);
            font-size: 1.1rem;
            display: flex;
            align-items: center;
            gap: 10px;
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

        /* Invite Methods */
        .invite-methods {
            display: flex;
            flex-direction: column;
            gap: 15px;
            margin-top: 10px;
        }

        .invite-method {
            display: flex;
            align-items: center;
            padding: 15px;
            background: rgba(21, 26, 45, 0.6);
            border-radius: 14px;
            cursor: pointer;
            transition: var(--transition-medium);
            border: var(--glass-border);
            box-shadow: var(--glass-shadow);
        }

        .invite-method:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.4);
            border-color: var(--primary-color);
            background: var(--card-hover);
        }

        .invite-icon {
            font-size: 1.8rem;
            width: 50px;
            height: 50px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            margin-left: 15px;
            color: white;
        }

        .sms-icon { background: var(--gradient-success); }
        .social-icon { background: var(--gradient-primary); }
        .copy-icon { background: var(--gradient-secondary); }

        .invite-details {
            flex: 1;
        }

        .invite-title {
            font-weight: 700;
            margin-bottom: 5px;
            font-size: 1rem;
        }

        .invite-desc {
            font-size: 0.85rem;
            color: var(--text-light);
        }

        /* Tabs */
        .tabs {
            display: flex;
            border-bottom: var(--glass-border);
            margin-bottom: 15px;
            gap: 5px;
            overflow-x: auto;
            padding: 0 18px;
        }

        .tab {
            padding: 10px 20px;
            cursor: pointer;
            border-bottom: 3px solid transparent;
            font-weight: 500;
            transition: var(--transition-medium);
            border-radius: 8px 8px 0 0;
            white-space: nowrap;
            font-size: 0.9rem;
        }

        .tab:hover {
            background: rgba(110, 69, 226, 0.1);
        }

        .tab.active {
            border-bottom: 3px solid var(--primary-color);
            color: var(--primary-color);
            font-weight: 700;
            background: rgba(110, 69, 226, 0.1);
        }

        .tab-content {
            display: none;
        }

        .tab-content.active {
            display: block;
        }

        /* Subscription Options - New Design */
        .subscription-wizard {
            display: flex;
            flex-direction: column;
            height: 100%;
        }

        .wizard-step {
            display: none;
            flex-direction: column;
            flex: 1;
        }

        .wizard-step.active {
            display: flex;
        }

        .value-display {
            font-size: 2.4rem;
            font-weight: 700;
            text-align: center;
            margin: 25px 0;
            color: var(--primary-color);
            display: flex;
            justify-content: center;
            align-items: baseline;
        }

        .unit {
            font-size: 1.3rem;
            color: var(--text-light);
            margin-right: 10px;
        }

        .price-text {
            text-align: center;
            font-size: 1.2rem;
            color: var(--text-light);
            margin-bottom: 20px;
        }

        .price-text span {
            color: var(--secondary-color);
            font-weight: 700;
        }

        .slider-container {
            width: 100%;
            margin: 25px 0;
            position: relative;
        }

        .slider {
            -webkit-appearance: none;
            width: 100%;
            height: 10px;
            border-radius: 5px;
            background: rgba(110, 69, 226, 0.2);
            outline: 0;
            transition: var(--transition-medium);
        }

        .slider:hover {
            height: 12px;
        }

        .slider::-webkit-slider-thumb {
            -webkit-appearance: none;
            appearance: none;
            width: 26px;
            height: 26px;
            border-radius: 50%;
            background: var(--gradient-primary);
            cursor: pointer;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.3);
            transition: var(--transition-medium);
            border: 2px solid var(--text-color);
        }

        .slider::-webkit-slider-thumb:hover {
            transform: scale(1.1);
        }

        .slider::-moz-range-thumb {
            width: 26px;
            height: 26px;
            border-radius: 50%;
            background: var(--gradient-primary);
            cursor: pointer;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.3);
            border: 2px solid var(--text-color);
        }

        .range-info {
            display: flex;
            justify-content: space-between;
            margin-top: 20px;
            color: var(--text-light);
            font-size: .95rem;
        }

        .price-summary {
            background: rgba(42, 58, 68, 0.7);
            border-radius: 18px;
            padding: 18px;
            margin: 25px 0;
            border: var(--glass-border);
            font-size: 1rem;
        }

        .price-row {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
            padding: 6px 0;
        }

        .total-price {
            font-size: 1.3rem;
            color: var(--secondary-color);
            margin-top: 15px;
            padding-top: 15px;
            border-top: var(--glass-border);
            text-align: center;
            font-weight: 700;
        }

        .nav-buttons {
            display: flex;
            justify-content: space-between;
            margin-top: 25px;
            gap: 12px;
        }

        .nav-btn {
            padding: 16px;
            border-radius: 10px;
            font-weight: 700;
            cursor: pointer;
            border: none;
            outline: 0;
            display: flex;
            align-items: center;
            justify-content: center;
            flex: 1;
            font-size: 1.05rem;
            transition: var(--transition-medium);
            will-change: transform;
        }

        .nav-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 12px rgba(0, 0, 0, 0.25);
        }

        .btn-prev {
            background: rgba(110, 69, 226, 0.15);
            color: var(--primary-color);
            border: var(--glass-border);
        }

        .btn-next, .btn-submit {
            background: var(--gradient-primary);
            color: var(--text-color);
        }

        .btn-submit {
            width: 100%;
            background: var(--gradient-success);
        }

        /* Buttons */
        .btn {
            padding: 10px 20px;
            border-radius: 10px;
            font-family: inherit;
            cursor: pointer;
            font-weight: 700;
            font-size: 0.9rem;
            transition: var(--transition-medium);
            display: flex;
            align-items: center;
            gap: 8px;
            justify-content: center;
            border: none;
            outline: none;
        }

        .btn-primary {
            background: var(--gradient-primary);
            color: white;
            box-shadow: 0 5px 15px rgba(110, 69, 226, 0.4);
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 20px rgba(110, 69, 226, 0.6);
            background: linear-gradient(135deg, var(--primary-color), var(--primary-light));
        }

        .btn-secondary {
            background: var(--gradient-success);
            color: white;
            box-shadow: 0 5px 15px rgba(76, 225, 182, 0.4);
        }

        .btn-secondary:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 20px rgba(76, 225, 182, 0.6);
            background: linear-gradient(135deg, #3dcc91, var(--success-color));
        }

        .btn-large {
            padding: 15px;
            font-size: 1rem;
            width: 100%;
        }

        /* Notification */
        .notification {
            position: fixed;
            bottom: 25px;
            right: 25px;
            background: var(--card-bg);
            border-radius: 14px;
            padding: 18px;
            box-shadow: 0 10px 30px var(--shadow-color);
            z-index: 1100;
            transform: translateY(100px);
            opacity: 0;
            transition: var(--transition-medium);
            display: flex;
            align-items: center;
            gap: 12px;
            border: var(--glass-border);
            max-width: 320px;
            backdrop-filter: blur(10px);
        }

        .notification.show {
            transform: translateY(0);
            opacity: 1;
        }

        .notification-icon {
            font-size: 1.6rem;
            width: 45px;
            height: 45px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
        }

        .notification-success {
            background: rgba(76, 225, 182, 0.1);
            color: var(--success-color);
            border: 1px solid rgba(76, 225, 182, 0.3);
        }

        .notification-info {
            background: rgba(110, 69, 226, 0.1);
            color: var(--primary-color);
            border: 1px solid rgba(110, 69, 226, 0.3);
        }

        .notification-error {
            background: rgba(255, 78, 100, 0.1);
            color: var(--danger-color);
            border: 1px solid rgba(255, 78, 100, 0.3);
        }

        .notification-message {
            font-size: 0.9rem;
            font-weight: 500;
            flex: 1;
        }

        /* Usage Guide */
        .usage-guide {
            font-size: 0.9rem;
            color: var(--text-light);
            line-height: 1.7;
            margin-top: 20px;
            padding: 18px;
            background: rgba(21, 26, 45, 0.6);
            border-radius: 14px;
            border: var(--glass-border);
            box-shadow: var(--glass-shadow);
        }

        .usage-guide h4 {
            color: var(--primary-color);
            margin-bottom: 12px;
            font-size: 1rem;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .usage-guide ol {
            padding-right: 18px;
            margin-bottom: 8px;
        }

        .usage-guide li {
            margin-bottom: 8px;
        }

        /* Language Switcher */
        .language-switcher {
            background: rgba(110, 69, 226, 0.1);
            border-radius: 18px;
            padding: 4px;
            display: flex;
            border: var(--glass-border);
            margin: 12px 0;
        }

        .language-btn {
            padding: 6px 18px;
            border-radius: 14px;
            cursor: pointer;
            font-size: 0.85rem;
            font-weight: 500;
            transition: var(--transition-medium);
            border: none;
            background: transparent;
            color: var(--text-light);
        }

        .language-btn.active {
            background: var(--gradient-primary);
            color: white;
            box-shadow: 0 5px 15px rgba(110, 69, 226, 0.3);
        }

        /* Download Buttons */
        .download-buttons {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 12px;
            margin-bottom: 20px;
        }

        .download-card {
            background: rgba(21, 26, 45, 0.6);
            border-radius: 14px;
            padding: 20px;
            border: var(--glass-border);
            box-shadow: var(--glass-shadow);
            transition: var(--transition-medium);
            text-align: center;
        }

        .download-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
        }

        .download-icon {
            font-size: 2.5rem;
            margin-bottom: 15px;
            color: var(--primary-color);
        }

        .download-title {
            font-weight: 700;
            margin-bottom: 10px;
            font-size: 1.1rem;
        }

        .download-desc {
            font-size: 0.85rem;
            color: var(--text-light);
            margin-bottom: 15px;
        }

        /* About Section */
        .about-content {
            padding: 18px;
            text-align: center;
        }
        
        .about-logo {
            width: 110px;
            height: 110px;
            margin: 0 auto 18px;
            background: var(--gradient-primary);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 15px 35px rgba(110, 69, 226, 0.5);
        }
        
        .about-logo i {
            font-size: 45px;
            color: white;
        }
        
        .about-text {
            margin-bottom: 18px;
            line-height: 1.7;
            color: var(--text-light);
        }
        
        .social-links {
            display: flex;
            justify-content: center;
            gap: 12px;
            margin-top: 25px;
        }
        
        .social-link {
            width: 42px;
            height: 42px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            background: rgba(21, 26, 45, 0.6);
            color: var(--text-color);
            transition: var(--transition-medium);
            box-shadow: var(--glass-shadow);
            border: var(--glass-border);
            font-size: 1.1rem;
        }
        
        .social-link:hover {
            transform: translateY(-3px);
            background: var(--gradient-primary);
            color: white;
            box-shadow: 0 10px 25px rgba(110, 69, 226, 0.4);
        }

        /* Important Notice */
        .important-notice {
            background: #000;
            color: white;
            padding: 15px;
            border-radius: 10px;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
            border-left: 4px solid var(--primary-color);
        }

        .important-notice i {
            color: var(--primary-color);
            font-size: 1.2rem;
        }

        /* Theme Options */
        .theme-options {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
            gap: 12px;
            margin: 15px 0;
        }

        .theme-option {
            padding: 15px;
            border-radius: 12px;
            cursor: pointer;
            transition: var(--transition-medium);
            border: var(--glass-border);
            position: relative;
            overflow: hidden;
        }

        .theme-option::after {
            content: "✓";
            position: absolute;
            top: 5px;
            left: 5px;
            width: 20px;
            height: 20px;
            background: var(--primary-color);
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.8rem;
            opacity: 0;
            transition: var(--transition-medium);
        }

        .theme-option.active::after {
            opacity: 1;
        }

        .theme-option:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
        }

        .theme-name {
            font-weight: 600;
            margin-top: 8px;
            font-size: 0.9rem;
            text-align: center;
        }

        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes slideIn {
            from { transform: translateY(-30px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        .fade-in {
            animation: fadeIn 0.5s ease-out forwards;
        }

        .slide-in {
            animation: slideIn 0.5s ease-out forwards;
        }

        /* Scrollbar */
        ::-webkit-scrollbar {
            width: 6px;
            height: 6px;
        }

        ::-webkit-scrollbar-track {
            background: transparent;
            border-radius: 8px;
        }

        ::-webkit-scrollbar-thumb {
            background: var(--primary-color);
            border-radius: 8px;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: var(--primary-light);
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .news-container {
                padding: 15px;
                max-width: 90%;
            }
            
            .modal-window {
                max-height: 75vh;
            }
            
            .subscription-option {
                flex-direction: column;
                align-items: stretch;
            }
            
            .subscription-price {
                margin-left: 0;
                margin-top: 8px;
            }
            
            .floating-btn {
                width: 65px;
                height: 65px;
                font-size: 24px;
                bottom: 15px;
                left: 15px;
            }
            
            .tabs {
                padding-bottom: 4px;
            }
            
            .tab {
                padding: 8px 12px;
                font-size: 0.85rem;
            }

            .download-buttons {
                grid-template-columns: 1fr;
            }

            .theme-options {
                grid-template-columns: repeat(3, 1fr);
            }
            
            .volume-buttons {
                flex-direction: column;
            }

            .value-display {
                font-size: 2.1rem;
                margin: 20px 0;
            }
            
            .nav-btn {
                padding: 14px;
                font-size: 1rem;
            }
        }
    </style>
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="" />
    <link href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@400;500;700&display=swap" rel="stylesheet" />
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" />
</head>
<body class="theme-default">
    <!-- Particle Background -->
    <div class="particles" id="particles"></div>
    
    <!-- Audio Element for Background Music -->
    <audio id="bgMusic" loop>
        <source src="https://musicviral.musitraf.com/Music/03-05/Ghol%20Bede%20Hamin%20Emshab%20Hoomaan.mp3" type="audio/mpeg" />
    </audio>
    
    <!-- Content Window -->
    <div id="contentWindow">
        <div class="top-bar">
            <div class="logo" id="helpBtn">
                <i class="fas fa-question-circle"></i>
                <span>راهنمای سایت</span>
            </div>
            <div class="menu-btn" id="mainMenuBtn">
                <div class="menu-line"></div>
                <div class="menu-line"></div>
                <div class="menu-line"></div>
            </div>
        </div>
        
        <div class="content" id="mainContent">
            <div class="welcome-container" id="welcomeContainer">
                <div class="news-container">
                    <div class="news-title">
                        <i class="fas fa-bullhorn"></i>
                        <span>اطلاعیه آپدیت</span>
                    </div>
                    <div class="news-content">
                        <div class="update-item">
                            <div class="update-icon"><i class="fas fa-music"></i></div>
                            <div class="update-text">اضافه شدن آهنگ پس زمینه</div>
                        </div>
                        <div class="update-item">
                            <div class="update-icon"><i class="fas fa-mobile-alt"></i></div>
                            <div class="update-text">سازگاری با دستگاه‌های قدیمی</div>
                        </div>
                        <div class="update-item">
                            <div class="update-icon"><i class="fas fa-shield-alt"></i></div>
                            <div class="update-text">ارتقاء سیستم امنیتی و حریم خصوصی</div>
                        </div>
                    </div>
                    <div class="news-footer">
                        <span>کد نسخه: <span class="version-code">12581</span></span>
                        <span id="publishTime">زمان ورود: 12:30</span>
                    </div>
                </div>
            </div>
        </div>
        
        <button class="floating-btn" id="quickMenuBtn">
            <i class="fas fa-pencil-alt"></i>
        </button>
        
        <!-- Main Menu -->
        <div class="modal-window main-menu" id="mainMenu">
            <div class="modal-header">
                <div class="modal-title">منوی اصلی</div>
                <div class="close-btn" id="closeMainMenu"><span>×</span></div>
            </div>
            <div class="modal-content">
                <div class="menu-item" id="settingsItem">
                    <div class="menu-item-title">
                        <i class="fas fa-cog"></i>
                        <span>تنظیمات</span>
                    </div>
                    <div class="menu-item-desc">تغییر تنظیمات برنامه</div>
                </div>
                <div class="menu-item" id="inviteFriendsItem">
                    <div class="menu-item-title">
                        <i class="fas fa-user-plus"></i>
                        <span>دعوت از دوستان</span>
                    </div>
                    <div class="menu-item-desc">دعوت دوستان و دریافت پاداش</div>
                </div>
                <div class="menu-item" id="aboutItem">
                    <div class="menu-item-title">
                        <i class="fas fa-info-circle"></i>
                        <span>درباره سازنده</span>
                    </div>
                    <div class="menu-item-desc">اطلاعات درباره تیم توسعه دهنده</div>
                </div>
            </div>
        </div>
        
        <!-- Invite Friends Window -->
        <div class="modal-window invite-window" id="inviteWindow">
            <div class="modal-header">
                <div class="modal-title">دعوت از دوستان</div>
                <div class="close-btn" id="closeInvite"><span>×</span></div>
            </div>
            <div class="modal-content">
                <div class="important-notice">
                    <i class="fas fa-gift"></i>
                    <span>با معرفی دوستان خود سرعت رو هدیه بدید</span>
                </div>
                
                <div class="invite-methods">
                    <div class="invite-method" id="smsInvite">
                        <div class="invite-icon sms-icon">
                            <i class="fas fa-sms"></i>
                        </div>
                        <div class="invite-details">
                            <div class="invite-title">دعوت پیامکی</div>
                            <div class="invite-desc">ارسال لینک دعوت از طریق پیامک</div>
                        </div>
                    </div>
                    
                    <div class="invite-method" id="socialInvite">
                        <div class="invite-icon social-icon">
                            <i class="fas fa-share-alt"></i>
                        </div>
                        <div class="invite-details">
                            <div class="invite-title">دعوت شبکه اجتماعی</div>
                            <div class="invite-desc">اشتراک گذاری در شبکه‌های اجتماعی</div>
                        </div>
                    </div>
                    
                    <div class="invite-method" id="copyInvite">
                        <div class="invite-icon copy-icon">
                            <i class="fas fa-copy"></i>
                        </div>
                        <div class="invite-details">
                            <div class="invite-title">کپی لینک دعوت</div>
                            <div class="invite-desc">کپی لینک برای ارسال در هر برنامه</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Settings Panel -->
        <div class="modal-window settings-panel" id="settingsPanel">
            <div class="modal-header">
                <div class="modal-title">تنظیمات کاربری</div>
                <div class="close-btn" id="closeSettings"><span>×</span></div>
            </div>
            <div class="modal-content">
                <div class="setting-item" style="margin-bottom: 20px;">
                    <div class="setting-label" style="margin-bottom: 12px; font-weight: 600;">تغییر زبان</div>
                    <div class="language-switcher">
                        <button class="language-btn active" data-lang="fa">فارسی</button>
                        <button class="language-btn" data-lang="en">English</button>
                    </div>
                </div>
                
                <div class="setting-item" style="margin-bottom: 20px;">
                    <div class="setting-label" style="margin-bottom: 12px; font-weight: 600;">تم سایت</div>
                    <div class="theme-options">
                        <div class="theme-option active" data-theme="default" style="background: var(--gradient-primary);">
                            <div class="theme-name">پیش فرض</div>
                        </div>
                        <div class="theme-option" data-theme="bomb" style="background: linear-gradient(135deg, #ff0000, #ff6b6b);">
                            <div class="theme-name">بمبک</div>
                        </div>
                        <div class="theme-option" data-theme="space" style="background: linear-gradient(135deg, #ffffff, #cccccc);">
                            <div class="theme-name">فضایی</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Help Window -->
        <div class="modal-window help-window" id="helpWindow">
            <div class="modal-header">
                <div class="modal-title">راهنمای جامع استفاده</div>
                <div class="close-btn" id="closeHelp"><span>×</span></div>
            </div>
            <div class="modal-content">
                <div class="important-notice">
                    <i class="fas fa-exclamation-circle"></i>
                    <span>راهنمای جامع شامل تمام جزئیات استفاده از سرویس</span>
                </div>
                
                <div class="usage-guide">
                    <h4><i class="fas fa-shopping-cart"></i> راهنمای خرید اشتراک</h4>
                    <ol>
                        <li>به بخش فروشگاه سرویس بروید</li>
                        <li>نوع اشتراک مورد نظر خود را انتخاب کنید</li>
                        <li>روی دکمه سفارش کلیک کنید</li>
                        <li>پیام پیش‌نویس شده را ارسال کنید</li>
                        <li>منتظر پاسخ پشتیبانی بمانید</li>
                        <li>پس از پرداخت، فایل پیکربندی را دریافت خواهید کرد</li>
                        <li>فایل را در برنامه Hiddify وارد کنید</li>
                    </ol>
                </div>
            </div>
        </div>
        
        <!-- Quick Menu -->
        <div class="modal-window quick-menu" id="quickMenu">
            <div class="modal-content">
                <div class="menu-item" id="quickShopItem">
                    <div class="menu-item-title">
                        <i class="fas fa-shopping-bag"></i>
                        <span>فروشگاه سرویس</span>
                    </div>
                    <div class="menu-item-desc">خرید اشتراک جدید یا تمدید اشتراک فعلی</div>
                </div>
                <div class="menu-item" id="quickHiddifyItem">
                    <div class="menu-item-title">
                        <i class="fas fa-download"></i>
                        <span>دانلود اپلیکیشن</span>
                    </div>
                    <div class="menu-item-desc">دانلود کلاینت رسمی برای دستگاه‌های مختلف</div>
                </div>
            </div>
        </div>
        
        <!-- Shop Window -->
        <div class="modal-window shop-menu" id="shopWindow">
            <div class="modal-header">
                <div class="modal-title">فروشگاه سرویس</div>
                <div class="close-btn" id="closeShop"><span>×</span></div>
            </div>
            <div class="modal-content">
                <div class="subscription-wizard">
                    <!-- Step 1: Volume Selection -->
                    <div class="wizard-step active" id="step-volume">
                        <div class="section-content">
                            <div class="value-display">
                                <span id="volume-value">4</span>
                                <span class="unit">گیگابایت</span>
                            </div>
                            <div class="price-text">قیمت: <span id="volume-price">11,920</span> تومان</div>
                            <div class="slider-container">
                                <input type="range" min="4" max="2000" value="4" class="slider" id="volume-slider">
                            </div>
                            <div class="range-info">
                                <span>حداقل: 4 گیگ</span>
                                <span>حداکثر: 2000 گیگ</span>
                            </div>
                        </div>
                        <div class="nav-buttons">
                            <button class="nav-btn btn-next" id="next-days" style="width:100%">
                                <span>بعدی</span>
                                <i class="fas fa-arrow-left" aria-hidden="true"></i>
                            </button>
                        </div>
                    </div>
                    
                    <!-- Step 2: Days Selection -->
                    <div class="wizard-step" id="step-days">
                        <div class="section-content">
                            <div class="value-display">
                                <span id="days-value">3</span>
                                <span class="unit">روز</span>
                            </div>
                            <div class="price-text">قیمت: <span id="days-price">1,380</span> تومان</div>
                            <div class="slider-container">
                                <input type="range" min="3" max="365" value="3" class="slider" id="days-slider">
                            </div>
                            <div class="range-info">
                                <span>حداقل: 3 روز</span>
                                <span>حداکثر: 365 روز</span>
                            </div>
                        </div>
                        <div class="nav-buttons">
                            <button class="nav-btn btn-prev" id="prev-volume">
                                <i class="fas fa-arrow-right" aria-hidden="true"></i>
                                <span>قبلی</span>
                            </button>
                            <button class="nav-btn btn-next" id="next-users">
                                <span>بعدی</span>
                                <i class="fas fa-arrow-left" aria-hidden="true"></i>
                            </button>
                        </div>
                    </div>
                    
                    <!-- Step 3: Users Selection -->
                    <div class="wizard-step" id="step-users">
                        <div class="section-content">
                            <div class="value-display">
                                <span id="users-value">1</span>
                                <span class="unit">کاربر</span>
                            </div>
                            <div class="price-text"><span id="users-price">رایگان</span></div>
                            <div class="slider-container">
                                <input type="range" min="1" max="7" value="1" class="slider" id="users-slider">
                            </div>
                            <div class="range-info">
                                <span>حداقل: 1 کاربر</span>
                                <span>حداکثر: 7 کاربر</span>
                            </div>
                        </div>
                        <div class="nav-buttons">
                            <button class="nav-btn btn-prev" id="prev-days">
                                <i class="fas fa-arrow-right" aria-hidden="true"></i>
                                <span>قبلی</span>
                            </button>
                            <button class="nav-btn btn-next" id="next-confirm">
                                <span>بعدی</span>
                                <i class="fas fa-arrow-left" aria-hidden="true"></i>
                            </button>
                        </div>
                    </div>
                    
                    <!-- Step 4: Confirmation -->
                    <div class="wizard-step" id="step-confirm">
                        <div class="final-section">
                            <div class="price-summary">
                                <div class="price-row">
                                    <span class="price-label">قیمت <span id="final-volume">4</span> گیگ</span>
                                    <span class="price-value" id="final-volume-price">11,920 تومان</span>
                                </div>
                                <div class="price-row">
                                    <span class="price-label">قیمت <span id="final-days">3</span> روز</span>
                                    <span class="price-value" id="final-days-price">1,380 تومان</span>
                                </div>
                                <div class="price-row">
                                    <span class="price-label">قیمت <span id="final-users">1</span> کاربر</span>
                                    <span class="price-value" id="final-users-price">رایگان</span>
                                </div>
                                <div class="total-price">
                                    <span>قابل پرداخت: </span>
                                    <span id="final-total">13,300 تومان</span>
                                </div>
                            </div>
                            <div class="nav-buttons">
                                <button class="nav-btn btn-prev" id="prev-users">
                                    <i class="fas fa-arrow-right" aria-hidden="true"></i>
                                    <span>قبلی</span>
                                </button>
                                <button class="nav-btn btn-submit" id="submit-order">
                                    <i class="fas fa-paper-plane" aria-hidden="true"></i>
                                    <span>ارسال سفارش</span>
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- About Window -->
        <div class="modal-window challenge-window" id="aboutWindow">
            <div class="modal-header">
                <div class="modal-title">درباره سازنده</div>
                <div class="close-btn" id="closeAbout"><span>×</span></div>
            </div>
            <div class="modal-content" style="display: flex; flex-direction: column; justify-content: center; align-items: center; text-align: center; padding: 35px;">
                <div class="about-logo">
                    <i class="fas fa-shield-alt"></i>
                </div>
                <h3 style="margin-bottom: 12px; font-size: 1.4rem;">تیم ایکسرو</h3>
                <p style="color: var(--text-light); margin-bottom: 25px; font-size: 0.95rem; max-width: 80%; line-height: 1.7;">
                    ما بیش از 5 سال است که در زمینه ارائه سرویس‌های VPN فعالیت داریم. اولویت اصلی ما امنیت و حریم خصوصی کاربران است. 
                    با استفاده از آخرین تکنولوژی‌های روز دنیا، سرویس‌هایی با بالاترین کیفیت و پایداری ارائه می‌دهیم.
                    تیم پشتیبانی ما 24 ساعته آماده پاسخگویی به سوالات و مشکلات شماست.
                </p>
                
                <div style="display: flex; gap: 15px; margin-top: 20px; width: 100%; justify-content: center;">
                    <a href="https://t.me/xroVPN" target="_blank" class="btn btn-primary" style="flex: 1; max-width: 200px;">
                        <i class="fab fa-telegram"></i>
                        <span>کانال تلگرام</span>
                    </a>
                    <a href="https://t.me/u0v0n" target="_blank" class="btn btn-secondary" style="flex: 1; max-width: 200px;">
                        <i class="fas fa-headset"></i>
                        <span>پشتیبانی</span>
                    </a>
                </div>
            </div>
        </div>
        
        <!-- Hiddify Download Window -->
        <div class="modal-window hiddify-window" id="hiddifyWindow">
            <div class="modal-header">
                <div class="modal-title">دانلود اپلیکیشن رسمی Hiddify</div>
                <div class="close-btn" id="closeHiddify"><span>×</span></div>
            </div>
            <div class="modal-content">
                <div class="download-buttons">
                    <div class="download-card" onclick="downloadHiddify('windows')">
                        <i class="fab fa-windows download-icon"></i>
                        <div class="download-title">ویندوز</div>
                        <div class="download-desc">نسخه 64 بیتی - سازگار با ویندوز 10 و 11</div>
                        <button class="btn btn-primary">
                            <i class="fas fa-download"></i>
                            <span>دانلود (25MB)</span>
                        </button>
                    </div>
                    
                    <div class="download-card" onclick="downloadHiddify('mac')">
                        <i class="fab fa-apple download-icon"></i>
                        <div class="download-title">مک</div>
                        <div class="download-desc">نسخه اپل سیلیکون و اینتل - مک اواس 11+</div>
                        <button class="btn btn-primary">
                            <i class="fas fa-download"></i>
                            <span>دانلود (18MB)</span>
                        </button>
                    </div>
                    
                    <div class="download-card" onclick="downloadHiddify('ios')">
                        <i class="fab fa-apple download-icon"></i>
                        <div class="download-title">iOS</div>
                        <div class="download-desc">آیفون و آیپد - iOS 12.2 و بالاتر</div>
                        <button class="btn btn-primary">
                            <i class="fas fa-external-link-alt"></i>
                            <span>رفتن به اپ استور</span>
                        </button>
                    </div>
                    
                    <div class="download-card" onclick="downloadHiddify('android')">
                        <i class="fab fa-android download-icon"></i>
                        <div class="download-title">اندروید</div>
                        <div class="download-desc">اندروید 5.0 و بالاتر - سازگار با تمام دستگاه‌ها</div>
                        <button class="btn btn-primary">
                            <i class="fas fa-external-link-alt"></i>
                            <span>رفتن به گوگل پلی</span>
                        </button>
                    </div>
                </div>
                
                <div class="usage-guide">
                    <h4>راهنمای نصب و استفاده:</h4>
                    <ol>
                        <li>فایل مربوط به سیستم عامل خود را دانلود کنید</li>
                        <li>برنامه را نصب و اجرا کنید (نیاز به دسترسی روت/ادمین ندارد)</li>
                        <li>فایل پیکربندی را از پشتیبانی دریافت کنید</li>
                        <li>فایل را در برنامه Hiddify وارد کنید (از طریق دکمه Import یا کشیدن و رها کردن)</li>
                        <li>اتصال را فعال کنید</li>
                        <li>برای اتصال خودکار، گزینه "اتصال هنگام راه‌اندازی" را فعال کنید</li>
                    </ol>
                </div>
            </div>
        </div>
        
        <!-- Confirm Window -->
        <div class="modal-window confirm-window" id="confirmWindow">
            <div class="modal-title">تایید عملیات</div>
            <div style="margin: 18px 0 25px; text-align: center;">آیا از انجام این عملیات مطمئن هستید؟ این عمل غیرقابل بازگشت است.</div>
            <div style="display: flex; justify-content: center; gap: 15px;">
                <button class="btn btn-primary" id="confirmYes" style="flex: 1; max-width: 140px;">تایید</button>
                <button class="btn" id="confirmNo" style="flex: 1; max-width: 140px; background: var(--card-bg); border: var(--glass-border); color: var(--text-color);">انصراف</button>
            </div>
        </div>
        
        <!-- Notification -->
        <div class="notification" id="notification">
            <div class="notification-icon" id="notificationIcon"></div>
            <div class="notification-message" id="notificationMessage"></div>
        </div>
        
        <!-- Overlay -->
        <div class="overlay" id="overlay"></div>
    </div>

    <script>
        // Particle System
        function createParticles() {
            const particlesContainer = document.getElementById('particles');
            const particleCount = window.innerWidth < 768 ? 30 : 50;
            
            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.classList.add('particle');
                
                // Random properties
                const size = Math.random() * 5 + 2;
                const posX = Math.random() * window.innerWidth;
                const duration = Math.random() * 20 + 10;
                const delay = Math.random() * 10;
                const opacity = Math.random() * 0.5 + 0.1;
                
                particle.style.width = `${size}px`;
                particle.style.height = `${size}px`;
                particle.style.left = `${posX}px`;
                particle.style.bottom = `-10px`;
                particle.style.animationDuration = `${duration}s`;
                particle.style.animationDelay = `${delay}s`;
                particle.style.opacity = opacity;
                
                particlesContainer.appendChild(particle);
            }
        }

        // App State
        const state = {
            language: 'fa',
            theme: 'default',
            activityLogs: [
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

        // DOM Elements
        const elements = {
            contentWindow: document.getElementById('contentWindow'),
            mainContent: document.getElementById('mainContent'),
            mainMenuBtn: document.getElementById('mainMenuBtn'),
            quickMenuBtn: document.getElementById('quickMenuBtn'),
            mainMenu: document.getElementById('mainMenu'),
            quickMenu: document.getElementById('quickMenu'),
            shopWindow: document.getElementById('shopWindow'),
            aboutWindow: document.getElementById('aboutWindow'),
            hiddifyWindow: document.getElementById('hiddifyWindow'),
            inviteWindow: document.getElementById('inviteWindow'),
            confirmWindow: document.getElementById('confirmWindow'),
            settingsPanel: document.getElementById('settingsPanel'),
            helpWindow: document.getElementById('helpWindow'),
            notification: document.getElementById('notification'),
            overlay: document.getElementById('overlay'),
            publishTime: document.getElementById('publishTime'),
            bgMusic: document.getElementById('bgMusic'),
            inviteFriendsItem: document.getElementById('inviteFriendsItem'),
            smsInvite: document.getElementById('smsInvite'),
            socialInvite: document.getElementById('socialInvite'),
            copyInvite: document.getElementById('copyInvite'),
            closeInvite: document.getElementById('closeInvite'),
            aboutItem: document.getElementById('aboutItem'),
            closeAbout: document.getElementById('closeAbout'),
            quickHiddifyItem: document.getElementById('quickHiddifyItem'),
            closeHiddify: document.getElementById('closeHiddify')
        };

        // Initialize the app
        function init() {
            createParticles();
            setupEventListeners();
            setInterval(checkForDayChange, 60000);
            checkForDayChange();
            
            // Set current time
            const now = new Date();
            const hours = now.getHours();
            const minutes = now.getMinutes();
            elements.publishTime.textContent = `زمان ورود: ${hours}:${minutes < 10 ? '0' + minutes : minutes}`;
            
            // Initialize shop wizard
            initShopWizard();
            
            // Play background music with user interaction workaround
            document.body.addEventListener('click', handleFirstUserInteraction, { once: true });
        }

        // Handle first user interaction to play music
        function handleFirstUserInteraction() {
            elements.bgMusic.play().catch(e => console.log('Autoplay prevented:', e));
            
            // Add touch event listener for mobile devices
            document.body.addEventListener('touchstart', () => {
                elements.bgMusic.play().catch(e => console.log('Autoplay prevented:', e));
            }, { once: true });
        }

        // Setup event listeners
        function setupEventListeners() {
            // Main menu buttons
            elements.mainMenuBtn.addEventListener('click', () => toggleModal(elements.mainMenu));
            elements.quickMenuBtn.addEventListener('click', () => toggleModal(elements.quickMenu));
            elements.overlay.addEventListener('click', closeAllModals);
            
            // Menu items
            document.getElementById('helpBtn').addEventListener('click', () => toggleModal(elements.helpWindow));
            elements.aboutItem.addEventListener('click', () => toggleModal(elements.aboutWindow));
            elements.inviteFriendsItem.addEventListener('click', () => toggleModal(elements.inviteWindow));
            document.getElementById('settingsItem').addEventListener('click', () => toggleModal(elements.settingsPanel));
            document.getElementById('quickShopItem').addEventListener('click', () => toggleModal(elements.shopWindow));
            elements.quickHiddifyItem.addEventListener('click', () => toggleModal(elements.hiddifyWindow));
            
            // Close buttons
            document.querySelectorAll('.close-btn').forEach(btn => {
                btn.addEventListener('click', closeAllModals);
            });
            
            // Language switcher
            document.querySelectorAll('.language-btn').forEach(btn => {
                btn.addEventListener('click', () => {
                    const lang = btn.dataset.lang;
                    changeLanguage(lang);
                });
            });
            
            // Theme switcher
            document.querySelectorAll('.theme-option').forEach(btn => {
                btn.addEventListener('click', () => {
                    const theme = btn.dataset.theme;
                    applyTheme(theme);
                });
            });
            
            // Confirm buttons
            document.getElementById('confirmYes').addEventListener('click', confirmAction);
            document.getElementById('confirmNo').addEventListener('click', closeConfirmWindow);
            
            // Invite methods
            elements.smsInvite.addEventListener('click', sendSMSInvite);
            elements.socialInvite.addEventListener('click', shareOnSocialMedia);
            elements.copyInvite.addEventListener('click', copyInviteLink);
            
            // Escape key to close modals
            document.addEventListener('keydown', (e) => {
                if (e.key === 'Escape') {
                    closeAllModals();
                }
            });
        }

        // Initialize shop wizard
        function initShopWizard() {
            // Constants
            const PRICE_PER_GB = 2980;
            const PRICE_PER_DAY = 460;
            const PRICE_PER_USER = 14000;
            
            // DOM Elements
            const wizardElements = {
                // Sliders
                volumeSlider: document.getElementById('volume-slider'),
                daysSlider: document.getElementById('days-slider'),
                usersSlider: document.getElementById('users-slider'),
                
                // Value displays
                volumeValue: document.getElementById('volume-value'),
                daysValue: document.getElementById('days-value'),
                usersValue: document.getElementById('users-value'),
                
                // Price displays
                volumePrice: document.getElementById('volume-price'),
                daysPrice: document.getElementById('days-price'),
                usersPrice: document.getElementById('users-price'),
                
                // Final price displays
                finalVolume: document.getElementById('final-volume'),
                finalDays: document.getElementById('final-days'),
                finalUsers: document.getElementById('final-users'),
                finalVolumePrice: document.getElementById('final-volume-price'),
                finalDaysPrice: document.getElementById('final-days-price'),
                finalUsersPrice: document.getElementById('final-users-price'),
                finalTotal: document.getElementById('final-total'),
                
                // Navigation buttons
                nextButtons: {
                    days: document.getElementById('next-days'),
                    users: document.getElementById('next-users'),
                    confirm: document.getElementById('next-confirm')
                },
                prevButtons: {
                    volume: document.getElementById('prev-volume'),
                    days: document.getElementById('prev-days'),
                    users: document.getElementById('prev-users')
                },
                submitButton: document.getElementById('submit-order'),
                
                // Steps
                steps: [
                    document.getElementById('step-volume'),
                    document.getElementById('step-days'),
                    document.getElementById('step-users'),
                    document.getElementById('step-confirm')
                ]
            };
            
            // Current step
            let currentStep = 0;
            
            // Update prices function
            function updatePrices() {
                const volume = parseInt(wizardElements.volumeSlider.value);
                const days = parseInt(wizardElements.daysSlider.value);
                const users = parseInt(wizardElements.usersSlider.value);
                
                // Calculate prices
                const volumePrice = volume * PRICE_PER_GB;
                const daysPrice = days * PRICE_PER_DAY;
                const usersPrice = (users - 1) * PRICE_PER_USER;
                
                // Update displays
                wizardElements.volumeValue.textContent = volume;
                wizardElements.daysValue.textContent = days;
                wizardElements.usersValue.textContent = users;
                
                wizardElements.volumePrice.textContent = volumePrice.toLocaleString('fa-IR');
                wizardElements.daysPrice.textContent = daysPrice.toLocaleString('fa-IR');
                wizardElements.usersPrice.textContent = users === 1 ? 
                    "رایگان" : `${usersPrice.toLocaleString('fa-IR')} تومان`;
                
                // Update final prices if on confirmation step
                if (currentStep === 3) {
                    updateFinalPrices();
                }
            }
            
            // Update final prices
            function updateFinalPrices() {
                const volume = parseInt(wizardElements.volumeSlider.value);
                const days = parseInt(wizardElements.daysSlider.value);
                const users = parseInt(wizardElements.usersSlider.value);
                
                const volumePrice = volume * PRICE_PER_GB;
                const daysPrice = days * PRICE_PER_DAY;
                const usersPrice = (users - 1) * PRICE_PER_USER;
                const totalPrice = volumePrice + daysPrice + usersPrice;
                
                wizardElements.finalVolume.textContent = volume;
                wizardElements.finalDays.textContent = days;
                wizardElements.finalUsers.textContent = users;
                wizardElements.finalVolumePrice.textContent = `${volumePrice.toLocaleString('fa-IR')} تومان`;
                wizardElements.finalDaysPrice.textContent = `${daysPrice.toLocaleString('fa-IR')} تومان`;
                wizardElements.finalUsersPrice.textContent = users === 1 ? 
                    "رایگان" : `${usersPrice.toLocaleString('fa-IR')} تومان`;
                wizardElements.finalTotal.textContent = `${totalPrice.toLocaleString('fa-IR')} تومان`;
            }
            
            // Navigate between steps
            function navigate(stepIndex) {
                // Hide current step
                wizardElements.steps[currentStep].classList.remove('active');
                
                // Update current step
                currentStep = stepIndex;
                
                // Show new step
                wizardElements.steps[stepIndex].classList.add('active');
                
                // Update final prices if on confirmation step
                if (stepIndex === 3) {
                    updateFinalPrices();
                }
            }
            
            // Place order
            function placeOrder() {
                const volume = parseInt(wizardElements.volumeSlider.value);
                const days = parseInt(wizardElements.daysSlider.value);
                const users = parseInt(wizardElements.usersSlider.value);
                
                const volumePrice = volume * PRICE_PER_GB;
                const daysPrice = days * PRICE_PER_DAY;
                const usersPrice = (users - 1) * PRICE_PER_USER;
                const totalPrice = volumePrice + daysPrice + usersPrice;
                
                const message = `درخواست سفارش سرویس XroVPN:\n\nحجم: ${volume.toLocaleString('fa-IR')} گیگ\nمدت: ${days.toLocaleString('fa-IR')} روز\nکاربران: ${users.toLocaleString('fa-IR')} نفر\nمبلغ: ${totalPrice.toLocaleString('fa-IR')} تومان`;
                
                window.open(`https://t.me/u0v0n?text=${encodeURIComponent(message)}`, '_blank');
                closeAllModals();
                
                addActivityLog(
                    'درخواست اشتراک',
                    `درخواست اشتراک ${days} روزه با حجم ${volume} گیگ برای ${users} کاربر ارسال شد`
                );
                
                showNotification(
                    `درخواست اشتراک با موفقیت ارسال شد`,
                    'success'
                );
            }
            
            // Setup event listeners
            wizardElements.volumeSlider.addEventListener('input', updatePrices);
            wizardElements.daysSlider.addEventListener('input', updatePrices);
            wizardElements.usersSlider.addEventListener('input', updatePrices);
            
            // Navigation buttons
            wizardElements.nextButtons.days.addEventListener('click', () => navigate(1));
            wizardElements.nextButtons.users.addEventListener('click', () => navigate(2));
            wizardElements.nextButtons.confirm.addEventListener('click', () => navigate(3));
            
            wizardElements.prevButtons.volume.addEventListener('click', () => navigate(0));
            wizardElements.prevButtons.days.addEventListener('click', () => navigate(1));
            wizardElements.prevButtons.users.addEventListener('click', () => navigate(2));
            
            // Submit button
            wizardElements.submitButton.addEventListener('click', placeOrder);
            
            // Initial update
            updatePrices();
        }

        // Helper functions
        function getFormattedTime() {
            const now = new Date();
            const hours = now.getHours();
            const minutes = now.getMinutes();
            return `امروز - ${hours}:${minutes < 10 ? '0' + minutes : minutes}`;
        }

        function changeLanguage(lang) {
            state.language = lang;
            
            document.querySelectorAll('.language-btn').forEach(btn => {
                if (btn.dataset.lang === lang) {
                    btn.classList.add('active');
                } else {
                    btn.classList.remove('active');
                }
            });
            
            showNotification(
                lang === 'fa' ? 'زبان به فارسی تغییر کرد' : 'Language changed to English',
                'info'
            );
        }

        function applyTheme(theme) {
            state.theme = theme;
            document.body.className = `theme-${theme}`;
            
            document.querySelectorAll('.theme-option').forEach(btn => {
                if (btn.dataset.theme === theme) {
                    btn.classList.add('active');
                } else {
                    btn.classList.remove('active');
                }
            });
            
            showNotification(
                'تم سایت تغییر کرد',
                'info'
            );
        }

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

        function closeConfirmWindow() {
            elements.confirmWindow.classList.remove('open');
            elements.overlay.classList.remove('open');
        }

        function confirmAction() {
            // Add your confirmation logic here
            closeConfirmWindow();
            showNotification(
                'عملیات با موفقیت انجام شد',
                'success'
            );
        }

        function showConfirmDialog() {
            elements.confirmWindow.classList.add('open');
            elements.overlay.classList.add('open');
        }

        // Notification system
        function showNotification(message, type, duration = 3000) {
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
            }, duration);
        }

        function showComingSoonNotification() {
            closeAllModals();
            showNotification(
                'در نسخه بعدی اضافه خواهد شد',
                'info'
            );
        }

        // Activity log
        function addActivityLog(title, desc) {
            state.activityLogs.unshift({
                title: title,
                date: getFormattedTime(),
                desc: desc
            });
            
            if (state.activityLogs.length > 50) {
                state.activityLogs = state.activityLogs.slice(0, 50);
            }
        }

        function checkForDayChange() {
            const now = new Date();
            const currentDay = now.getDate();
            
            if (currentDay !== state.lastDayChecked) {
                state.lastDayChecked = currentDay;
                state.activityLogs = [];
                
                addActivityLog(
                    'شروع روز جدید',
                    'گزارشات روز قبل پاک شد و روز جدید شروع شد.'
                );
            }
        }

        // Hiddify download functions
        function downloadHiddify(platform) {
            let downloadUrl = '';
            let fileName = '';
            
            switch (platform) {
                case 'windows':
                    downloadUrl = 'https://github.com/hiddify/hiddify-next/releases/latest/download/Hiddify.Windows.exe';
                    fileName = 'hiddify-windows-installer.exe';
                    break;
                case 'mac':
                    downloadUrl = 'https://github.com/hiddify/hiddify-next/releases/latest/download/Hiddify.Mac.dmg';
                    fileName = 'hiddify-macos.dmg';
                    break;
                case 'ios':
                    downloadUrl = 'https://apps.apple.com/us/app/hiddify/id6475881953';
                    break;
                case 'android':
                    downloadUrl = 'https://play.google.com/store/apps/details?id=com.hiddify.hiddify';
                    break;
                default:
                    showNotification(
                        'پلتفرم انتخاب شده نامعتبر است',
                        'error'
                    );
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
                `دانلود کلاینت Hiddify برای ${platform} آغاز شد`
            );
            
            showNotification(
                `دانلود برای ${platform} با موفقیت آغاز شد`,
                'success'
            );
        }

        // Invite friends functions
        function sendSMSInvite() {
            const inviteText = `سلام رفیق 👋\n\nاگه تو هم دنبال یه سرویس قوی VPN هستی پس وارد سایت آقای ایکسرو شو:\n\n🌐 آدرس سایت:\nhttp://xrovpn.github.io/xroVPN\n\n📢 کانال اطلاع رسانی:\nhttp://t.me/xroVPN\n\n💎 ویژگی‌ها:\n- سرعت بالا\n- اتصال پایدار\n- پشتیبانی 24 ساعته`;
            
            if (/Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent)) {
                window.open(`sms:?body=${encodeURIComponent(inviteText)}`, '_blank');
            } else {
                navigator.clipboard.writeText(inviteText).then(() => {
                    showNotification('متن دعوت کپی شد، می‌توانید در برنامه پیامک پیست کنید', 'success');
                }).catch(err => {
                    showNotification('خطا در کپی متن دعوت', 'error');
                    console.error('Could not copy text: ', err);
                });
            }
            
            closeAllModals();
            showNotification('دعوت پیامکی آماده ارسال شد', 'success');
        }

        function shareOnSocialMedia() {
            const inviteText = `سلام دوست عزیز 👋\n\nسرویس VPN ایکسرو با بهترین کیفیت و سرعت در دسترس شماست!\n\n🔗 لینک سایت:\nhttp://xrovpn.github.io/xroVPN\n\n📢 کانال تلگرام:\nhttp://t.me/xroVPN\n\n✨ ویژگی‌های منحصر به فرد:\n✅ سرعت فوق‌العاده\n✅ اتصال پایدار\n✅ پشتیبانی 24/7\n✅ سرورهای متعدد`;
            
            if (navigator.share) {
                navigator.share({
                    title: 'سرویس VPN ایکسرو',
                    text: inviteText,
                    url: 'http://xrovpn.github.io/xroVPN'
                }).then(() => {
                    showNotification('دعوت با موفقیت ارسال شد', 'success');
                }).catch(err => {
                    showNotification('خطا در ارسال دعوت', 'error');
                    console.error('Error sharing:', err);
                });
            } else if (/Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent)) {
                // For mobile devices without Web Share API
                window.open(`whatsapp://send?text=${encodeURIComponent(inviteText)}`, '_blank');
            } else {
                // For desktop browsers
                navigator.clipboard.writeText(inviteText).then(() => {
                    showNotification('متن دعوت کپی شد، می‌توانید در شبکه اجتماعی مورد نظر پیست کنید', 'success');
                }).catch(err => {
                    showNotification('خطا در کپی متن دعوت', 'error');
                    console.error('Could not copy text: ', err);
                });
            }
            
            closeAllModals();
        }

        function copyInviteLink() {
            const inviteText = `سلام 👋\n\nسرویس VPN ایکسرو رو بهت پیشنهاد می‌کنم:\n\n🌐 آدرس سایت:\nhttp://xrovpn.github.io/xroVPN\n\n📢 کانال تلگرام:\nhttp://t.me/xroVPN\n\n💎 امکانات:\n- سرعت بالا\n- اتصال پایدار\n- پشتیبانی 24 ساعته\n- سرورهای متعدد`;
            
            navigator.clipboard.writeText(inviteText).then(() => {
                showNotification('متن دعوت با موفقیت کپی شد', 'success');
            }).catch(err => {
                showNotification('خطا در کپی متن دعوت', 'error');
                console.error('Could not copy text: ', err);
            });
            
            closeAllModals();
        }

        // Initialize the app when DOM is loaded
        document.addEventListener('DOMContentLoaded', init);
    </script>
</body>
</html>
