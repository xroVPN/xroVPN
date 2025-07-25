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
            background-image: 
                radial-gradient(circle at 20% 30%, rgba(110, 69, 226, 0.15) 0%, transparent 50%),
                radial-gradient(circle at 80% 70%, rgba(61, 200, 213, 0.15) 0%, transparent 50%),
                linear-gradient(to bottom, rgba(10, 14, 26, 0.9), rgba(15, 20, 40, 0.95));
            background-attachment: fixed;
            background-size: 200% 200%;
            animation: gradientAnimation 15s ease infinite;
        }

        @keyframes gradientAnimation {
            0% { background-position: 0% 0%; }
            50% { background-position: 100% 100%; }
            100% { background-position: 0% 0%; }
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

        /* Biometric Auth Screen */
        .biometric-auth {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 2000;
            background: radial-gradient(ellipse at center, rgba(10, 14, 26, 0.95), rgba(5, 7, 15, 0.98));
            backdrop-filter: blur(5px);
            transition: var(--transition-slow);
        }

        .scanner-container {
            position: relative;
            width: 280px;
            height: 280px;
            display: flex;
            justify-content: center;
            align-items: center;
            perspective: 1000px;
        }

        .scanner-border {
            position: absolute;
            width: 100%;
            height: 100%;
            border-radius: 50%;
            border: 2px solid rgba(110, 69, 226, 0.3);
            box-shadow: 
                0 0 30px rgba(110, 69, 226, 0.3),
                inset 0 0 20px rgba(110, 69, 226, 0.2);
            animation: borderPulse 4s infinite ease-in-out;
        }

        @keyframes borderPulse {
            0%, 100% { 
                box-shadow: 
                    0 0 30px rgba(110, 69, 226, 0.3),
                    inset 0 0 20px rgba(110, 69, 226, 0.2);
                border-color: rgba(110, 69, 226, 0.3);
            }
            50% { 
                box-shadow: 
                    0 0 50px rgba(110, 69, 226, 0.5),
                    inset 0 0 30px rgba(110, 69, 226, 0.3);
                border-color: rgba(110, 69, 226, 0.6);
            }
        }

        .scanner-surface {
            position: relative;
            width: 80%;
            height: 80%;
            border-radius: 50%;
            background: linear-gradient(145deg, rgba(21, 26, 45, 0.8), rgba(15, 20, 40, 0.9));
            box-shadow: 
                inset 0 0 30px rgba(0, 0, 0, 0.8),
                0 10px 50px rgba(110, 69, 226, 0.4);
            display: flex;
            justify-content: center;
            align-items: center;
            cursor: pointer;
            overflow: hidden;
            transition: var(--transition-medium);
            transform-style: preserve-3d;
            backdrop-filter: blur(5px);
        }

        .scanner-surface.active {
            box-shadow: 
                inset 0 0 40px rgba(0, 0, 0, 0.9),
                0 15px 70px rgba(110, 69, 226, 0.7);
            transform: translateZ(20px) scale(1.05);
        }

        .fingerprint-icon {
            font-size: 120px;
            color: rgba(110, 69, 226, 0.8);
            transition: var(--transition-medium);
            position: relative;
            z-index: 2;
            text-shadow: 0 0 20px rgba(110, 69, 226, 0.5);
        }

        .scanner-surface.active .fingerprint-icon {
            color: rgba(255, 255, 255, 0.95);
            filter: drop-shadow(0 0 20px rgba(110, 69, 226, 0.9));
            animation: iconPulse 1.5s infinite ease-in-out;
        }

        @keyframes iconPulse {
            0%, 100% { transform: scale(1); opacity: 1; }
            50% { transform: scale(1.1); opacity: 0.9; }
        }

        .progress-ring {
            position: absolute;
            width: 110%;
            height: 110%;
        }

        .progress-ring-circle {
            stroke: rgba(110, 69, 226, 0.2);
            stroke-width: 4;
            fill: transparent;
        }

        .progress-ring-fill {
            stroke: var(--primary-color);
            stroke-width: 4;
            fill: transparent;
            stroke-dasharray: 283;
            stroke-dashoffset: 283;
            transform-origin: center;
            transform: rotate(-90deg);
            transition: stroke-dashoffset 0.1s linear;
            filter: drop-shadow(0 0 5px rgba(110, 69, 226, 0.7));
        }

        .success-check {
            position: absolute;
            width: 100%;
            height: 100%;
            display: flex;
            justify-content: center;
            align-items: center;
            opacity: 0;
            transform: scale(0.5);
            transition: var(--transition-medium);
            z-index: 3;
        }

        .success-check.show {
            opacity: 1;
            transform: scale(1);
        }

        .check-icon {
            font-size: 120px;
            color: var(--success-color);
            filter: drop-shadow(0 0 20px rgba(76, 225, 182, 0.8));
            animation: checkPulse 2s infinite ease-in-out;
        }

        @keyframes checkPulse {
            0%, 100% { transform: scale(1); opacity: 1; }
            50% { transform: scale(1.1); opacity: 0.9; }
        }

        /* Content Window */
        #contentWindow {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1000;
            display: none;
            opacity: 0;
            transform: translateY(20px);
            transition: var(--transition-medium);
            overflow: hidden;
        }

        #contentWindow.show {
            opacity: 1;
            transform: translateY(0);
            display: block;
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

        .wireguard-window {
            bottom: -100%;
            left: 0;
            width: 100%;
            height: 75%;
            max-height: 750px;
            border-radius: 18px 18px 0 0;
            transform: translateY(100%);
            transition: transform 0.4s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .wireguard-window.open {
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

        /* Subscription Options */
        .subscription-option {
            padding: 18px;
            margin-bottom: 15px;
            background: rgba(21, 26, 45, 0.6);
            border-radius: 14px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            transition: var(--transition-medium);
            border: var(--glass-border);
            box-shadow: var(--glass-shadow);
            flex-wrap: wrap;
            gap: 12px;
        }

        .subscription-option:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.4);
            border-color: var(--primary-color);
            background: var(--card-hover);
        }

        .subscription-info {
            display: flex;
            align-items: center;
            gap: 12px;
            flex: 1;
            min-width: 220px;
        }

        .subscription-icon {
            font-size: 1.6rem;
            width: 55px;
            height: 55px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 14px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            color: white;
        }

        .volumetric1 { background: var(--gradient-primary); }
        .volumetric2 { background: var(--gradient-primary); }
        .volumetric3 { background: var(--gradient-primary); }
        .volumetric4 { background: var(--gradient-primary); }
        .volumetric5 { background: var(--gradient-primary); }
        .volumetric6 { background: var(--gradient-primary); }

        .unlimited1 { background: var(--gradient-secondary); }
        .unlimited2 { background: var(--gradient-secondary); }
        .unlimited3 { background: var(--gradient-secondary); }
        .unlimited4 { background: var(--gradient-secondary); }
        .unlimited5 { background: var(--gradient-secondary); }
        .unlimited6 { background: var(--gradient-secondary); }

        .free1 { background: var(--gradient-warning); }
        .free2 { background: var(--gradient-warning); }
        .free3 { background: var(--gradient-warning); }
        .free4 { background: var(--gradient-warning); }
        .free5 { background: var(--gradient-warning); }
        .free6 { background: var(--gradient-warning); }

        .subscription-details {
            display: flex;
            flex-direction: column;
            gap: 6px;
            flex: 1;
        }

        .subscription-name {
            font-weight: 700;
            color: var(--text-color);
            font-size: 1rem;
        }

        .subscription-features {
            font-size: 0.8rem;
            color: var(--text-light);
            display: flex;
            gap: 12px;
            flex-wrap: wrap;
        }

        .subscription-features span {
            display: flex;
            align-items: center;
            gap: 4px;
        }

        .subscription-features i {
            color: var(--primary-color);
        }

        .subscription-price {
            font-weight: 800;
            color: var(--primary-color);
            font-size: 1.2rem;
            white-space: nowrap;
            margin-left: 12px;
        }

        .volume-buttons {
            display: flex;
            gap: 8px;
            margin-top: 12px;
            width: 100%;
        }

        .volume-btn {
            flex: 1;
            padding: 8px;
            border-radius: 8px;
            background: rgba(110, 69, 226, 0.1);
            border: 1px solid rgba(110, 69, 226, 0.2);
            color: var(--text-color);
            font-size: 0.8rem;
            text-align: center;
            cursor: pointer;
            transition: var(--transition-fast);
        }

        .volume-btn:hover {
            background: rgba(110, 69, 226, 0.2);
        }

        .volume-btn.active {
            background: var(--gradient-primary);
            color: white;
            box-shadow: 0 3px 10px rgba(110, 69, 226, 0.3);
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
            .scanner-container {
                width: 240px;
                height: 240px;
            }
            
            .fingerprint-icon {
                font-size: 100px;
            }
            
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
        }
    </style>
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="" />
    <link href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@400;500;700&display=swap" rel="stylesheet" />
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" />
</head>
<body>
    <!-- Particle Background -->
    <div class="particles" id="particles"></div>
    
    <!-- Audio Element for Background Music -->
    <audio id="bgMusic" loop>
        <source src="https://musicviral.musitraf.com/Music/03-05/Ghol%20Bede%20Hamin%20Emshab%20Hoomaan.mp3" type="audio/mpeg" />
    </audio>
    
    <!-- Biometric Auth Screen -->
    <div class="biometric-auth" id="authContainer">
        <div class="scanner-container">
            <svg class="progress-ring" viewBox="0 0 100 100">
                <circle class="progress-ring-circle" cx="50" cy="50" r="45" />
                <circle class="progress-ring-fill" cx="50" cy="50" r="45" />
            </svg>
            
            <div class="scanner-border"></div>
            
            <div class="scanner-surface" id="scannerSurface">
                <i class="fas fa-fingerprint fingerprint-icon" id="fingerprintIcon"></i>
                <div class="scan-animation" id="scanAnimation"></div>
                
                <div class="success-check" id="successCheck">
                    <i class="fas fa-check-circle check-icon"></i>
                </div>
            </div>
        </div>
    </div>
    
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
                <div class="creator" id="todayDate"></div>
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
                        <div class="theme-option" data-theme="dark" style="background: linear-gradient(135deg, #2c3e50, #34495e);">
                            <div class="theme-name">تیره</div>
                        </div>
                        <div class="theme-option" data-theme="ocean" style="background: linear-gradient(135deg, #4ca1af, #2c3e50);">
                            <div class="theme-name">اقیانوسی</div>
                        </div>
                        <div class="theme-option" data-theme="sunset" style="background: linear-gradient(135deg, #ff7e5f, #feb47b);">
                            <div class="theme-name">غروب</div>
                        </div>
                        <div class="theme-option" data-theme="forest" style="background: linear-gradient(135deg, #5a8f3d, #3a6b1f);">
                            <div class="theme-name">جنگلی</div>
                        </div>
                        <div class="theme-option" data-theme="midnight" style="background: linear-gradient(135deg, #0f2027, #203a43, #2c5364);">
                            <div class="theme-name">نیمه شب</div>
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
                        <li>فایل را در برنامه WireGuard وارد کنید</li>
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
                <div class="menu-item" id="quickWireguardItem">
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
            <div class="tabs">
                <div class="tab active" data-tab="volumetric">
                    <span>حجمی</span>
                </div>
                <div class="tab" data-tab="unlimited">
                    <span>نامحدود</span>
                </div>
            </div>
            <div class="modal-content">
                <div class="tab-content active" id="volumetric-tab">
                    <div class="subscription-option">
                        <div class="subscription-info">
                            <div class="subscription-icon volumetric1"><i class="fas fa-database"></i></div>
                            <div class="subscription-details">
                                <div class="subscription-name">اشتراک ۱ ماهه وایرگارد</div>
                                <div class="subscription-features">
                                    <span><i class="fas fa-user"></i> ۱ کاربر</span>
                                    <span><i class="fas fa-bolt"></i> سرعت بالا</span>
                                    <span><i class="fas fa-headset"></i> دارای پشتیبان</span>
                                </div>
                            </div>
                        </div>
                        <div class="volume-buttons">
                            <div class="volume-btn active" data-volume="30" data-price="98000">30 گیگ</div>
                            <div class="volume-btn" data-volume="50" data-price="147000">50 گیگ</div>
                            <div class="volume-btn" data-volume="100" data-price="235000">100 گیگ</div>
                            <div class="volume-btn" data-volume="200" data-price="471000">200 گیگ</div>
                        </div>
                        <div class="subscription-price">۹۸,۰۰۰ تومان</div>
                        <button class="btn btn-primary" onclick="orderVolumetricSubscription(1, 30)">
                            <i class="fas fa-shopping-cart"></i>
                            <span>برای سفارش کلیک کنید</span>
                        </button>
                    </div>
                    
                    <div class="subscription-option">
                        <div class="subscription-info">
                            <div class="subscription-icon volumetric2"><i class="fas fa-database"></i></div>
                            <div class="subscription-details">
                                <div class="subscription-name">اشتراک ۲ ماهه وایرگارد</div>
                                <div class="subscription-features">
                                    <span><i class="fas fa-user"></i> ۱ کاربر</span>
                                    <span><i class="fas fa-bolt"></i> سرعت بالا</span>
                                    <span><i class="fas fa-headset"></i> دارای پشتیبان</span>
                                </div>
                            </div>
                        </div>
                        <div class="volume-buttons">
                            <div class="volume-btn active" data-volume="30" data-price="116000">30 گیگ</div>
                            <div class="volume-btn" data-volume="50" data-price="171000">50 گیگ</div>
                            <div class="volume-btn" data-volume="100" data-price="266000">100 گیگ</div>
                            <div class="volume-btn" data-volume="200" data-price="519000">200 گیگ</div>
                        </div>
                        <div class="subscription-price">۱۱۶,۰۰۰ تومان</div>
                        <button class="btn btn-primary" onclick="orderVolumetricSubscription(2, 30)">
                            <i class="fas fa-shopping-cart"></i>
                            <span>برای سفارش کلیک کنید</span>
                        </button>
                    </div>
                    
                    <div class="subscription-option">
                        <div class="subscription-info">
                            <div class="subscription-icon volumetric3"><i class="fas fa-database"></i></div>
                            <div class="subscription-details">
                                <div class="subscription-name">اشتراک ۳ ماهه وایرگارد</div>
                                <div class="subscription-features">
                                    <span><i class="fas fa-user"></i> ۱ کاربر</span>
                                    <span><i class="fas fa-bolt"></i> سرعت بالا</span>
                                    <span><i class="fas fa-headset"></i> دارای پشتیبان</span>
                                </div>
                            </div>
                        </div>
                        <div class="volume-buttons">
                            <div class="volume-btn active" data-volume="30" data-price="134000">30 گیگ</div>
                            <div class="volume-btn" data-volume="50" data-price="195000">50 گیگ</div>
                            <div class="volume-btn" data-volume="100" data-price="297000">100 گیگ</div>
                            <div class="volume-btn" data-volume="200" data-price="567000">200 گیگ</div>
                        </div>
                        <div class="subscription-price">۱۳۴,۰۰۰ تومان</div>
                        <button class="btn btn-primary" onclick="orderVolumetricSubscription(3, 30)">
                            <i class="fas fa-shopping-cart"></i>
                            <span>برای سفارش کلیک کنید</span>
                        </button>
                    </div>
                    
                    <div class="subscription-option">
                        <div class="subscription-info">
                            <div class="subscription-icon volumetric4"><i class="fas fa-database"></i></div>
                            <div class="subscription-details">
                                <div class="subscription-name">اشتراک ۴ ماهه وایرگارد</div>
                                <div class="subscription-features">
                                    <span><i class="fas fa-user"></i> ۱ کاربر</span>
                                    <span><i class="fas fa-bolt"></i> سرعت بالا</span>
                                    <span><i class="fas fa-headset"></i> دارای پشتیبان</span>
                                </div>
                            </div>
                        </div>
                        <div class="volume-buttons">
                            <div class="volume-btn active" data-volume="30" data-price="152000">30 گیگ</div>
                            <div class="volume-btn" data-volume="50" data-price="219000">50 گیگ</div>
                            <div class="volume-btn" data-volume="100" data-price="328000">100 گیگ</div>
                            <div class="volume-btn" data-volume="200" data-price="615000">200 گیگ</div>
                        </div>
                        <div class="subscription-price">۱۵۲,۰۰۰ تومان</div>
                        <button class="btn btn-primary" onclick="orderVolumetricSubscription(4, 30)">
                            <i class="fas fa-shopping-cart"></i>
                            <span>برای سفارش کلیک کنید</span>
                        </button>
                    </div>
                    
                    <div class="subscription-option">
                        <div class="subscription-info">
                            <div class="subscription-icon volumetric5"><i class="fas fa-database"></i></div>
                            <div class="subscription-details">
                                <div class="subscription-name">اشتراک ۵ ماهه وایرگارد</div>
                                <div class="subscription-features">
                                    <span><i class="fas fa-user"></i> ۱ کاربر</span>
                                    <span><i class="fas fa-bolt"></i> سرعت بالا</span>
                                    <span><i class="fas fa-headset"></i> دارای پشتیبان</span>
                                </div>
                            </div>
                        </div>
                        <div class="volume-buttons">
                            <div class="volume-btn active" data-volume="30" data-price="170000">30 گیگ</div>
                            <div class="volume-btn" data-volume="50" data-price="243000">50 گیگ</div>
                            <div class="volume-btn" data-volume="100" data-price="359000">100 گیگ</div>
                            <div class="volume-btn" data-volume="200" data-price="663000">200 گیگ</div>
                        </div>
                        <div class="subscription-price">۱۷۰,۰۰۰ تومان</div>
                        <button class="btn btn-primary" onclick="orderVolumetricSubscription(5, 30)">
                            <i class="fas fa-shopping-cart"></i>
                            <span>برای سفارش کلیک کنید</span>
                        </button>
                    </div>
                    
                    <div class="subscription-option">
                        <div class="subscription-info">
                            <div class="subscription-icon volumetric6"><i class="fas fa-database"></i></div>
                            <div class="subscription-details">
                                <div class="subscription-name">اشتراک ۶ ماهه وایرگارد</div>
                                <div class="subscription-features">
                                    <span><i class="fas fa-user"></i> ۱ کاربر</span>
                                    <span><i class="fas fa-bolt"></i> سرعت بالا</span>
                                    <span><i class="fas fa-headset"></i> دارای پشتیبان</span>
                                </div>
                            </div>
                        </div>
                        <div class="volume-buttons">
                            <div class="volume-btn active" data-volume="30" data-price="188000">30 گیگ</div>
                            <div class="volume-btn" data-volume="50" data-price="267000">50 گیگ</div>
                            <div class="volume-btn" data-volume="100" data-price="390000">100 گیگ</div>
                            <div class="volume-btn" data-volume="200" data-price="711000">200 گیگ</div>
                        </div>
                        <div class="subscription-price">۱۸۸,۰۰۰ تومان</div>
                        <button class="btn btn-primary" onclick="orderVolumetricSubscription(6, 30)">
                            <i class="fas fa-shopping-cart"></i>
                            <span>برای سفارش کلیک کنید</span>
                        </button>
                    </div>
                </div>
                
                <div class="tab-content" id="unlimited-tab">
                    <div class="subscription-option">
                        <div class="subscription-info">
                            <div class="subscription-icon unlimited1"><i class="fas fa-infinity"></i></div>
                            <div class="subscription-details">
                                <div class="subscription-name">اشتراک ۱ ماهه نامحدود</div>
                                <div class="subscription-features">
                                    <span><i class="fas fa-infinity"></i> حجم نامحدود</span>
                                    <span><i class="fas fa-bolt"></i> سرعت بالا</span>
                                    <span><i class="fas fa-user"></i> ۱ کاربر</span>
                                </div>
                            </div>
                        </div>
                        <div class="subscription-price">۳۴۸,۰۰۰ تومان</div>
                        <button class="btn btn-primary" onclick="orderUnlimitedSubscription(1)">
                            <i class="fas fa-shopping-cart"></i>
                            <span>برای سفارش کلیک کنید</span>
                        </button>
                    </div>
                    
                    <div class="subscription-option">
                        <div class="subscription-info">
                            <div class="subscription-icon unlimited2"><i class="fas fa-infinity"></i></div>
                            <div class="subscription-details">
                                <div class="subscription-name">اشتراک ۲ ماهه نامحدود</div>
                                <div class="subscription-features">
                                    <span><i class="fas fa-infinity"></i> حجم نامحدود</span>
                                    <span><i class="fas fa-bolt"></i> سرعت بالا</span>
                                    <span><i class="fas fa-user"></i> ۱ کاربر</span>
                                </div>
                            </div>
                        </div>
                        <div class="subscription-price">۶۹۱,۰۰۰ تومان</div>
                        <button class="btn btn-primary" onclick="orderUnlimitedSubscription(2)">
                            <i class="fas fa-shopping-cart"></i>
                            <span>برای سفارش کلیک کنید</span>
                        </button>
                    </div>
                    
                    <div class="subscription-option">
                        <div class="subscription-info">
                            <div class="subscription-icon unlimited3"><i class="fas fa-infinity"></i></div>
                            <div class="subscription-details">
                                <div class="subscription-name">اشتراک ۳ ماهه نامحدود</div>
                                <div class="subscription-features">
                                    <span><i class="fas fa-infinity"></i> حجم نامحدود</span>
                                    <span><i class="fas fa-bolt"></i> سرعت بالا</span>
                                    <span><i class="fas fa-user"></i> ۱ کاربر</span>
                                </div>
                            </div>
                        </div>
                        <div class="subscription-price">۱,۰۳۴,۰۰۰ تومان</div>
                        <button class="btn btn-primary" onclick="orderUnlimitedSubscription(3)">
                            <i class="fas fa-shopping-cart"></i>
                            <span>برای سفارش کلیک کنید</span>
                        </button>
                    </div>
                    
                    <div class="subscription-option">
                        <div class="subscription-info">
                            <div class="subscription-icon unlimited4"><i class="fas fa-infinity"></i></div>
                            <div class="subscription-details">
                                <div class="subscription-name">اشتراک ۴ ماهه نامحدود</div>
                                <div class="subscription-features">
                                    <span><i class="fas fa-infinity"></i> حجم نامحدود</span>
                                    <span><i class="fas fa-bolt"></i> سرعت بالا</span>
                                    <span><i class="fas fa-user"></i> ۱ کاربر</span>
                                </div>
                            </div>
                        </div>
                        <div class="subscription-price">۱,۳۷۷,۰۰۰ تومان</div>
                        <button class="btn btn-primary" onclick="orderUnlimitedSubscription(4)">
                            <i class="fas fa-shopping-cart"></i>
                            <span>برای سفارش کلیک کنید</span>
                        </button>
                    </div>
                    
                    <div class="subscription-option">
                        <div class="subscription-info">
                            <div class="subscription-icon unlimited5"><i class="fas fa-infinity"></i></div>
                            <div class="subscription-details">
                                <div class="subscription-name">اشتراک ۵ ماهه نامحدود</div>
                                <div class="subscription-features">
                                    <span><i class="fas fa-infinity"></i> حجم نامحدود</span>
                                    <span><i class="fas fa-bolt"></i> سرعت بالا</span>
                                    <span><i class="fas fa-user"></i> ۱ کاربر</span>
                                </div>
                            </div>
                        </div>
                        <div class="subscription-price">۱,۷۲۰,۰۰۰ تومان</div>
                        <button class="btn btn-primary" onclick="orderUnlimitedSubscription(5)">
                            <i class="fas fa-shopping-cart"></i>
                            <span>برای سفارش کلیک کنید</span>
                        </button>
                    </div>
                    
                    <div class="subscription-option">
                        <div class="subscription-info">
                            <div class="subscription-icon unlimited6"><i class="fas fa-infinity"></i></div>
                            <div class="subscription-details">
                                <div class="subscription-name">اشتراک ۶ ماهه نامحدود</div>
                                <div class="subscription-features">
                                    <span><i class="fas fa-infinity"></i> حجم نامحدود</span>
                                    <span><i class="fas fa-bolt"></i> سرعت بالا</span>
                                    <span><i class="fas fa-user"></i> ۱ کاربر</span>
                                </div>
                            </div>
                        </div>
                        <div class="subscription-price">۲,۰۶۳,۰۰۰ تومان</div>
                        <button class="btn btn-primary" onclick="orderUnlimitedSubscription(6)">
                            <i class="fas fa-shopping-cart"></i>
                            <span>برای سفارش کلیک کنید</span>
                        </button>
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
        
        <!-- WireGuard Download Window -->
        <div class="modal-window wireguard-window" id="wireguardWindow">
            <div class="modal-header">
                <div class="modal-title">دانلود اپلیکیشن رسمی</div>
                <div class="close-btn" id="closeWireguard"><span>×</span></div>
            </div>
            <div class="modal-content">
                <div class="download-buttons">
                    <div class="download-card" onclick="downloadWireguard('windows')">
                        <i class="fab fa-windows download-icon"></i>
                        <div class="download-title">ویندوز</div>
                        <div class="download-desc">نسخه 64 بیتی - سازگار با ویندوز 10 و 11</div>
                        <button class="btn btn-primary">
                            <i class="fas fa-download"></i>
                            <span>دانلود (25MB)</span>
                        </button>
                    </div>
                    
                    <div class="download-card" onclick="downloadWireguard('mac')">
                        <i class="fab fa-apple download-icon"></i>
                        <div class="download-title">مک</div>
                        <div class="download-desc">نسخه اپل سیلیکون و اینتل - مک اواس 11+</div>
                        <button class="btn btn-primary">
                            <i class="fas fa-download"></i>
                            <span>دانلود (18MB)</span>
                        </button>
                    </div>
                    
                    <div class="download-card" onclick="downloadWireguard('ios')">
                        <i class="fab fa-apple download-icon"></i>
                        <div class="download-title">iOS</div>
                        <div class="download-desc">آیفون و آیپد - iOS 12.2 و بالاتر</div>
                        <button class="btn btn-primary">
                            <i class="fas fa-external-link-alt"></i>
                            <span>رفتن به اپ استور</span>
                        </button>
                    </div>
                    
                    <div class="download-card" onclick="downloadWireguard('android')">
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
                        <li>فایل را در برنامه وارد کنید (از طریق دکمه Import یا کشیدن و رها کردن)</li>
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
            isAuthenticated: false,
            authState: {
                isScanning: false,
                scanStartTime: 0,
                scanTimer: null,
                progressInterval: null,
                progress: 0,
                scanDuration: 4000,
                lastScanTime: 0,
                cooldown: 1000
            },
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
            authContainer: document.getElementById('authContainer'),
            scannerSurface: document.getElementById('scannerSurface'),
            fingerprintIcon: document.getElementById('fingerprintIcon'),
            scanAnimation: document.getElementById('scanAnimation'),
            successCheck: document.getElementById('successCheck'),
            progressRing: document.querySelector('.progress-ring-fill'),
            contentWindow: document.getElementById('contentWindow'),
            mainContent: document.getElementById('mainContent'),
            mainMenuBtn: document.getElementById('mainMenuBtn'),
            quickMenuBtn: document.getElementById('quickMenuBtn'),
            mainMenu: document.getElementById('mainMenu'),
            quickMenu: document.getElementById('quickMenu'),
            shopWindow: document.getElementById('shopWindow'),
            aboutWindow: document.getElementById('aboutWindow'),
            wireguardWindow: document.getElementById('wireguardWindow'),
            inviteWindow: document.getElementById('inviteWindow'),
            confirmWindow: document.getElementById('confirmWindow'),
            settingsPanel: document.getElementById('settingsPanel'),
            helpWindow: document.getElementById('helpWindow'),
            notification: document.getElementById('notification'),
            overlay: document.getElementById('overlay'),
            todayDate: document.getElementById('todayDate'),
            publishTime: document.getElementById('publishTime'),
            bgMusic: document.getElementById('bgMusic'),
            inviteFriendsItem: document.getElementById('inviteFriendsItem'),
            smsInvite: document.getElementById('smsInvite'),
            socialInvite: document.getElementById('socialInvite'),
            copyInvite: document.getElementById('copyInvite'),
            closeInvite: document.getElementById('closeInvite'),
            aboutItem: document.getElementById('aboutItem'),
            closeAbout: document.getElementById('closeAbout')
        };

        // Initialize the app
        function init() {
            createParticles();
            setupEventListeners();
            applyTheme(state.theme);
            setInterval(checkForDayChange, 60000);
            checkForDayChange();
            
            // Set current time
            const now = new Date();
            const hours = now.getHours();
            const minutes = now.getMinutes();
            elements.publishTime.textContent = `زمان ورود: ${hours}:${minutes < 10 ? '0' + minutes : minutes}`;
            
            // Setup volume buttons
            setupVolumeButtons();
        }

        // Setup event listeners
        function setupEventListeners() {
            // Main menu buttons
            elements.mainMenuBtn.addEventListener('click', () => toggleModal(elements.mainMenu));
            elements.quickMenuBtn.addEventListener('click', () => toggleModal(elements.quickMenu));
            elements.overlay.addEventListener('click', closeAllModals);
            
            // Fingerprint scanner events
            elements.scannerSurface.addEventListener('mousedown', startFingerprintScan);
            elements.scannerSurface.addEventListener('touchstart', startFingerprintScan, { passive: true });
            elements.scannerSurface.addEventListener('mouseup', cancelFingerprintScan);
            elements.scannerSurface.addEventListener('mouseleave', cancelFingerprintScan);
            elements.scannerSurface.addEventListener('touchend', cancelFingerprintScan);
            elements.scannerSurface.addEventListener('touchcancel', cancelFingerprintScan);
            
            // Menu items
            document.getElementById('helpBtn').addEventListener('click', () => toggleModal(elements.helpWindow));
            elements.aboutItem.addEventListener('click', () => toggleModal(elements.aboutWindow));
            elements.inviteFriendsItem.addEventListener('click', () => toggleModal(elements.inviteWindow));
            document.getElementById('settingsItem').addEventListener('click', () => toggleModal(elements.settingsPanel));
            document.getElementById('quickShopItem').addEventListener('click', () => toggleModal(elements.shopWindow));
            document.getElementById('quickWireguardItem').addEventListener('click', () => toggleModal(elements.wireguardWindow));
            
            // Close buttons
            document.querySelectorAll('.close-btn').forEach(btn => {
                btn.addEventListener('click', closeAllModals);
            });
            
            // Tabs
            document.querySelectorAll('.tab').forEach(tab => {
                tab.addEventListener('click', () => {
                    const tabId = tab.dataset.tab;
                    const tabType = tab.closest('.tabs').parentElement.id.includes('shop') ? 'shop' : 'wireguard';
                    changeTab(tabId, tabType);
                });
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

        // Setup volume buttons
        function setupVolumeButtons() {
            document.querySelectorAll('.volume-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    const parent = this.closest('.subscription-option');
                    const priceElement = parent.querySelector('.subscription-price');
                    const orderButton = parent.querySelector('.btn-primary');
                    
                    // Remove active class from all buttons in this group
                    parent.querySelectorAll('.volume-btn').forEach(b => {
                        b.classList.remove('active');
                    });
                    
                    // Add active class to clicked button
                    this.classList.add('active');
                    
                    // Update price
                    const price = this.dataset.price;
                    priceElement.textContent = `${Number(price).toLocaleString('fa-IR')} تومان`;
                    
                    // Update order button
                    const months = parent.querySelector('.subscription-name').textContent.match(/(\d+)/)[0];
                    const volume = this.dataset.volume;
                    orderButton.setAttribute('onclick', `orderVolumetricSubscription(${months}, ${volume})`);
                });
            });
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
            
            document.querySelectorAll('.theme-option').forEach(btn => {
                if (btn.dataset.theme === theme) {
                    btn.classList.add('active');
                } else {
                    btn.classList.remove('active');
                }
            });
            
            // Apply theme-specific styles
            const root = document.documentElement;
            
            switch(theme) {
                case 'dark':
                    root.style.setProperty('--primary-color', '#2c3e50');
                    root.style.setProperty('--primary-light', '#34495e');
                    root.style.setProperty('--primary-dark', '#1a252f');
                    root.style.setProperty('--bg-color', '#121212');
                    root.style.setProperty('--card-bg', '#1e1e1e');
                    break;
                case 'ocean':
                    root.style.setProperty('--primary-color', '#4ca1af');
                    root.style.setProperty('--primary-light', '#2c3e50');
                    root.style.setProperty('--primary-dark', '#2c3e50');
                    root.style.setProperty('--bg-color', '#0f2027');
                    root.style.setProperty('--card-bg', '#203a43');
                    break;
                case 'sunset':
                    root.style.setProperty('--primary-color', '#ff7e5f');
                    root.style.setProperty('--primary-light', '#feb47b');
                    root.style.setProperty('--primary-dark', '#ff6b6b');
                    root.style.setProperty('--bg-color', '#2c3e50');
                    root.style.setProperty('--card-bg', '#34495e');
                    break;
                case 'forest':
                    root.style.setProperty('--primary-color', '#5a8f3d');
                    root.style.setProperty('--primary-light', '#3a6b1f');
                    root.style.setProperty('--primary-dark', '#2c5e1a');
                    root.style.setProperty('--bg-color', '#0a1f0a');
                    root.style.setProperty('--card-bg', '#1a3a1a');
                    break;
                case 'midnight':
                    root.style.setProperty('--primary-color', '#0f2027');
                    root.style.setProperty('--primary-light', '#203a43');
                    root.style.setProperty('--primary-dark', '#2c5364');
                    root.style.setProperty('--bg-color', '#000000');
                    root.style.setProperty('--card-bg', '#0a0e1a');
                    break;
                default: // default theme
                    root.style.setProperty('--primary-color', '#6e45e2');
                    root.style.setProperty('--primary-light', '#9c64ff');
                    root.style.setProperty('--primary-dark', '#4a1fb8');
                    root.style.setProperty('--bg-color', '#0a0e1a');
                    root.style.setProperty('--card-bg', '#151a2d');
            }
            
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

        // Fingerprint scanner functions
        function startFingerprintScan(event) {
            const now = Date.now();
            if (now - state.authState.lastScanTime < state.authState.cooldown) {
                return;
            }
            
            if (state.authState.isScanning) return;
            
            state.authState.isScanning = true;
            state.authState.scanStartTime = now;
            state.authState.lastScanTime = now;
            state.authState.progress = 0;
            
            elements.scannerSurface.classList.add('active');
            elements.fingerprintIcon.style.transform = 'scale(1.1)';
            elements.scanAnimation.classList.add('active');
            
            updateProgress();
            state.authState.progressInterval = setInterval(updateProgress, 50);
            
            state.authState.scanTimeout = setTimeout(() => {
                completeFingerprintScan();
            }, state.authState.scanDuration);
        }

        function updateProgress() {
            const elapsed = Date.now() - state.authState.scanStartTime;
            state.authState.progress = Math.min(elapsed / state.authState.scanDuration * 100, 100);
            
            const circumference = 2 * Math.PI * 45;
            const offset = circumference - (state.authState.progress / 100 * circumference);
            elements.progressRing.style.strokeDashoffset = offset;
            
            if (state.authState.progress >= 100) {
                clearInterval(state.authState.progressInterval);
            }
        }

        function completeFingerprintScan() {
            if (!state.authState.isScanning) return;
            
            clearInterval(state.authState.progressInterval);
            clearTimeout(state.authState.scanTimeout);
            
            elements.fingerprintIcon.style.opacity = '0';
            elements.successCheck.classList.add('show');
            
            showNotification(
                'احراز هویت موفق',
                'هویت شما با موفقیت تایید شد',
                'success'
            );
            
            // Play background music
            elements.bgMusic.play().catch(e => console.log('Autoplay prevented:', e));
            
            setTimeout(() => {
                elements.authContainer.style.opacity = '0';
                setTimeout(() => {
                    elements.authContainer.style.display = 'none';
                    elements.contentWindow.classList.add('show');
                    state.isAuthenticated = true;
                    
                    startTypingAnimation();
                }, 500);
            }, 1500);
        }

        function cancelFingerprintScan() {
            if (!state.authState.isScanning) return;
            
            clearInterval(state.authState.progressInterval);
            clearTimeout(state.authState.scanTimeout);
            state.authState.isScanning = false;
            
            elements.progressRing.style.strokeDashoffset = 283;
            
            elements.scannerSurface.classList.remove('active');
            elements.fingerprintIcon.style.transform = 'scale(1)';
            elements.fingerprintIcon.style.opacity = '1';
            elements.successCheck.classList.remove('show');
            
            if (state.authState.progress < 90) {
                showNotification(
                    'اسکن ناتمام',
                    'لطفا انگشت خود را تا پایان اسکن نگه دارید',
                    'error'
                );
            }
            
            elements.scanAnimation.classList.remove('active');
            setTimeout(() => {
                elements.scanAnimation.style.animation = 'none';
                setTimeout(() => {
                    elements.scanAnimation.style.animation = '';
                }, 10);
            }, 300);
        }

        // Tab functions
        function changeTab(tabId, tabType) {
            const prefix = tabType === 'shop' ? 'shop' : 'wireguard';
            
            document.querySelectorAll(`.${prefix}-menu .tab`).forEach(tab => {
                tab.classList.remove('active');
            });
            
            document.querySelectorAll(`.${prefix}-menu .tab-content`).forEach(content => {
                content.classList.remove('active');
            });
            
            document.querySelector(`.${prefix}-menu .tab[data-tab="${tabId}"]`).classList.add('active');
            document.getElementById(`${tabId}-tab`).classList.add('active');
            
            addActivityLog(
                `تغییر تب ${tabType === 'shop' ? 'فروشگاه' : 'دانلود'}`,
                `تب ${tabId === 'volumetric' ? 'حجمی' : tabId === 'unlimited' ? 'نامحدود' : 'رایگان'} انتخاب شد`
            );
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

        // Subscription functions
        function orderVolumetricSubscription(months, volume) {
            let price;
            
            if (volume === 30) {
                price = getVolumetricSubscriptionPrice(months, 30);
            } else if (volume === 50) {
                price = getVolumetricSubscriptionPrice(months, 50);
            } else if (volume === 100) {
                price = getVolumetricSubscriptionPrice(months, 100);
            } else if (volume === 200) {
                price = getVolumetricSubscriptionPrice(months, 200);
            }
            
            const message = `درود آقای ایکسرو!\n\nپروتکل سرویس: حجمی\nحجم سرویس: ${volume} گیگ\nتعداد کاربر سرویس: 1\nانقضا سرویس: ${months} ماه\n\nقیمت نهایی: ${price} تومان\n\nاطلاعات لازم همراه شماره کارت برای بنده ارسال کنید ، باتشکر`;
            
            window.open(`https://t.me/u0v0n?text=${encodeURIComponent(message)}`, '_blank');
            closeAllModals();
            
            addActivityLog(
                'درخواست اشتراک',
                `درخواست اشتراک ${months} ماهه حجمی (${volume} گیگ) ارسال شد`
            );
            
            showNotification(
                `درخواست اشتراک ${months} ماهه با موفقیت ارسال شد`,
                'success'
            );
        }

        function orderUnlimitedSubscription(months) {
            const price = getUnlimitedSubscriptionPrice(months);
            
            const message = `درود آقای ایکسرو!\n\nپروتکل سرویس: نامحدود\nحجم سرویس: نامحدود\nتعداد کاربر سرویس: 1\nانقضا سرویس: ${months} ماه\n\nقیمت نهایی: ${price} تومان\n\nاطلاعات لازم همراه شماره کارت برای بنده ارسال کنید ، باتشکر`;
            
            window.open(`https://t.me/u0v0n?text=${encodeURIComponent(message)}`, '_blank');
            closeAllModals();
            
            addActivityLog(
                'درخواست اشتراک',
                `درخواست اشتراک ${months} ماهه نامحدود ارسال شد`
            );
            
            showNotification(
                `درخواست اشتراک ${months} ماهه با موفقیت ارسال شد`,
                'success'
            );
        }

        function getVolumetricSubscriptionPrice(months, volume) {
            // Base prices for 1 month
            const basePrices = {
                30: 98000,
                50: 147000,
                100: 235000,
                200: 471000
            };
            
            // Additional price per month
            const monthlyAdditions = {
                30: 18000,
                50: 24000,
                100: 31000,
                200: 48000
            };
            
            const basePrice = basePrices[volume];
            const addition = monthlyAdditions[volume] * (months - 1);
            
            return basePrice + addition;
        }
        
        function getUnlimitedSubscriptionPrice(months) {
            // Base price for 1 month
            const basePrice = 348000;
            
            // Additional price per month
            const monthlyAddition = 343000;
            
            return basePrice + (monthlyAddition * (months - 1));
        }

        // WireGuard download
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
                case 'linux':
                    downloadUrl = 'https://www.wireguard.com/install/';
                    fileName = 'wireguard-linux-install.html';
                    break;
                case 'router':
                    downloadUrl = 'https://www.wireguard.com/install/';
                    fileName = 'wireguard-router-install.html';
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
                `دانلود کلاینت برای ${platform} آغاز شد`
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

        // Typing animation
        function startTypingAnimation() {
            
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

        // Initialize the app when DOM is loaded
        document.addEventListener('DOMContentLoaded', init);
    </script>
</body>
</html>
