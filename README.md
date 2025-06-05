<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>XRO VPN | امنیت، سرعت، پایداری</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css">
    <style>
        @font-face {
            font-family: 'Vazir';
            src: url('https://cdn.jsdelivr.net/gh/rastikerdar/vazir-font@v30.1.0/dist/Vazir.woff2') format('woff2');
            font-display: swap;
        }
        
        :root {
            --primary: #FF6B35;
            --primary-dark: #EF5621;
            --primary-light: rgba(255, 107, 53, 0.15);
            --secondary: #4361EE;
            --secondary-dark: #3A56D4;
            --success: #4CAF50;
            --danger: #F44336;
            --gray: #9E9E9E;
            --dark: #0F0F0F;
            --dark-light: #1A1A1A;
            --darker: #121212;
            --light: rgba(255, 255, 255, 0.95);
            --lighter: rgba(255, 255, 255, 0.7);
            --border-radius: 16px;
            --border-radius-sm: 10px;
            --box-shadow: 0 12px 40px rgba(0, 0, 0, 0.35);
            --transition: all 0.4s cubic-bezier(0.25, 0.8, 0.25, 1);
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            -webkit-tap-highlight-color: transparent;
            user-select: none;
            -webkit-user-select: none;
        }
        
        body {
            font-family: 'Vazir', sans-serif;
            background: var(--darker);
            color: var(--light);
            min-height: 100vh;
            line-height: 1.8;
            padding-bottom: 90px;
            overflow-x: hidden;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* هدر جدید */
        .app-header {
            padding: 2rem 0 1.5rem;
            text-align: center;
            position: relative;
            margin-bottom: 1rem;
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
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-left: 12px;
            box-shadow: 0 8px 20px rgba(67, 97, 238, 0.3);
            animation: pulse 3s infinite;
        }
        
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }
        
        .logo-icon svg {
            width: 28px;
            height: 28px;
            fill: white;
        }
        
        .logo-text {
            font-size: 1.8rem;
            font-weight: 800;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
        }
        
        .tagline {
            display: flex;
            justify-content: center;
            margin-bottom: 1.5rem;
            flex-wrap: wrap;
        }
        
        .tagline-item {
            margin: 0.5rem;
            padding: 0.5rem 1.2rem;
            border-radius: 50px;
            font-weight: 700;
            font-size: 0.95rem;
            position: relative;
            overflow: hidden;
            animation: wave 6s infinite;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
        }
        
        @keyframes wave {
            0% { transform: translateY(0); }
            50% { transform: translateY(-5px); }
            100% { transform: translateY(0); }
        }
        
        .tagline-item:nth-child(1) {
            background: linear-gradient(135deg, var(--primary), #FF8A65);
            animation-delay: 0s;
        }
        
        .tagline-item:nth-child(2) {
            background: linear-gradient(135deg, var(--secondary), #64B5F6);
            animation-delay: 0.5s;
        }
        
        .tagline-item:nth-child(3) {
            background: linear-gradient(135deg, #4CAF50, #81C784);
            animation-delay: 1s;
        }
        
        .app-description {
            font-size: 0.95rem;
            color: var(--gray);
            max-width: 700px;
            margin: 0 auto;
            line-height: 1.8;
        }
        
        /* تب‌های اصلی */
        .tabs {
            display: flex;
            margin: 2rem 0;
            background: var(--dark-light);
            border-radius: 50px;
            overflow: hidden;
            max-width: 500px;
            margin-left: auto;
            margin-right: auto;
            border: 1px solid rgba(255,255,255,0.1);
            box-shadow: var(--box-shadow);
        }
        
        .tab-button {
            flex: 1;
            padding: 1rem;
            background: transparent;
            border: none;
            cursor: pointer;
            font-size: 0.95rem;
            font-weight: 600;
            color: var(--gray);
            position: relative;
            overflow: hidden;
            transition: var(--transition);
        }
        
        .tab-button.active {
            color: white;
            background: linear-gradient(135deg, var(--primary), var(--primary-dark));
            box-shadow: 0 4px 15px rgba(255, 107, 53, 0.4);
        }
        
        .tab-button:not(.active):hover {
            background: rgba(255,255,255,0.05);
            color: var(--light);
        }
        
        /* محتوای تب‌ها */
        .tab-content {
            margin: 2rem 0;
            padding: 1.5rem;
            background: var(--dark-light);
            border-radius: var(--border-radius);
            min-height: 300px;
            border: 1px solid rgba(255,255,255,0.1);
            box-shadow: var(--box-shadow);
            animation: fadeIn 0.5s ease;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        /* باکس پیام */
        .message {
            background: rgba(67, 97, 238, 0.1);
            margin: 1.5rem auto;
            padding: 1rem 1.5rem;
            border-radius: var(--border-radius);
            text-align: right;
            font-size: 0.85rem;
            color: var(--light);
            border: 1px solid rgba(67, 97, 238, 0.2);
            display: flex;
            align-items: center;
            justify-content: right;
            animation: fadeIn 0.6s ease;
        }
        
        .notice-label {
            background: var(--secondary);
            color: white;
            padding: 0.3rem 0.8rem;
            border-radius: 50px;
            font-weight: 700;
            font-size: 0.8rem;
            margin-left: 12px;
            white-space: nowrap;
        }
        
        /* گرید کشورها */
        .flag-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
            gap: 1.2rem;
            padding: 0.5rem 0;
        }
        
        .flag-item {
            background: var(--dark);
            padding: 1.2rem 0.5rem;
            text-align: center;
            border-radius: var(--border-radius);
            cursor: pointer;
            border: 1px solid rgba(255,255,255,0.1);
            transition: var(--transition);
            position: relative;
            overflow: hidden;
        }
        
        .flag-item.active {
            border-color: var(--success);
        }
        
        .flag-item.inactive {
            opacity: 0.7;
            filter: grayscale(0.8);
            cursor: not-allowed;
        }
        
        .flag-item:hover:not(.inactive) {
            background: rgba(40, 40, 40, 0.8);
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
            border-color: rgba(255,255,255,0.2);
        }
        
        .flag-item:before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(255,107,53,0.1) 0%, rgba(67,97,238,0.1) 100%);
            z-index: -1;
            opacity: 0;
            transition: var(--transition);
        }
        
        .flag-item:hover:not(.inactive):before {
            opacity: 1;
        }
        
        .flag-item span {
            font-size: 2.8rem;
            display: block;
            margin-bottom: 0.5rem;
            transition: var(--transition);
        }
        
        .flag-item:hover:not(.inactive) span {
            transform: scale(1.1);
        }
        
        .flag-item p {
            margin: 0;
            font-size: 0.9rem;
            color: var(--light);
            font-weight: 500;
        }
        
        .status-badge {
            position: absolute;
            top: 10px;
            left: 10px;
            font-size: 0.7rem;
            padding: 0.2rem 0.5rem;
            border-radius: 50px;
            font-weight: 700;
        }
        
        .status-badge.active {
            background: rgba(76, 175, 80, 0.2);
            color: var(--success);
            border: 1px solid var(--success);
        }
        
        .status-badge.inactive {
            background: rgba(158, 158, 158, 0.2);
            color: var(--gray);
            border: 1px solid var(--gray);
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
            border-radius: var(--border-radius);
            max-width: 500px;
            width: 95%;
            margin: 5% auto;
            overflow: hidden;
            border: 1px solid rgba(255,255,255,0.1);
            box-shadow: var(--box-shadow);
            animation: modalFadeIn 0.5s ease;
        }
        
        @keyframes modalFadeIn {
            from { opacity: 0; transform: translateY(40px) scale(0.95); }
            to { opacity: 1; transform: translateY(0) scale(1); }
        }
        
        .modal-header {
            padding: 1.5rem;
            background: linear-gradient(90deg, var(--primary), var(--primary-dark));
            color: white;
            text-align: center;
            position: relative;
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
            transition: var(--transition);
        }
        
        .close-modal:hover {
            transform: rotate(90deg);
        }
        
        .modal-body {
            padding: 1.5rem;
            color: var(--light);
        }
        
        /* تب‌های مودال */
        .modal-tabs {
            display: flex;
            border-bottom: 1px solid rgba(255,255,255,0.1);
            margin-bottom: 1.5rem;
        }
        
        .modal-tab {
            padding: 0.8rem 1.2rem;
            cursor: pointer;
            font-weight: 600;
            color: var(--gray);
            font-size: 0.9rem;
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
            border-radius: 3px 3px 0 0;
        }
        
        .modal-tab.active {
            color: var(--primary);
        }
        
        .modal-tab.active:after {
            width: 100%;
        }
        
        .modal-tab:hover {
            color: var(--light);
        }
        
        .modal-tab-content {
            display: none;
            animation: fadeIn 0.4s ease;
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
            font-size: 0.95rem;
        }
        
        .slider-value {
            font-weight: 700;
            color: var(--primary);
        }
        
        .slider {
            -webkit-appearance: none;
            width: 100%;
            height: 8px;
            border-radius: 4px;
            background: var(--dark);
            outline: none;
            margin: 1rem 0;
            transition: var(--transition);
        }
        
        .slider:hover {
            opacity: 0.9;
        }
        
        .slider::-webkit-slider-thumb {
            -webkit-appearance: none;
            width: 24px;
            height: 24px;
            border-radius: 50%;
            background: var(--primary);
            cursor: pointer;
            border: 3px solid white;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3);
            transition: var(--transition);
        }
        
        .slider::-webkit-slider-thumb:hover {
            transform: scale(1.1);
        }
        
        /* اطلاعات قیمت */
        .price-info {
            background: rgba(255, 107, 53, 0.1);
            padding: 1rem;
            border-radius: var(--border-radius-sm);
            margin-top: 1.5rem;
            text-align: center;
            font-size: 0.9rem;
            border: 1px solid rgba(255,255,255,0.1);
        }
        
        .price-info span {
            color: var(--primary);
            font-weight: 600;
        }
        
        /* قیمت نهایی */
        .final-price {
            text-align: center;
            margin: 2rem 0;
            font-size: 1.2rem;
            animation: pulse 2s infinite;
        }
        
        .final-price span {
            color: var(--primary);
            font-weight: 800;
            font-size: 1.8rem;
        }
        
        .order-summary {
            background: rgba(30, 30, 30, 0.7);
            padding: 1.5rem;
            border-radius: var(--border-radius-sm);
            margin: 2rem 0;
            border-left: 4px solid var(--primary);
        }
        
        .order-summary p {
            margin-bottom: 0.8rem;
            font-size: 0.95rem;
            display: flex;
            justify-content: space-between;
        }
        
        .order-summary p:last-child {
            margin-bottom: 0;
        }
        
        .order-summary span {
            color: var(--light);
            font-weight: 500;
        }
        
        /* فوتر مودال */
        .modal-footer {
            display: flex;
            justify-content: space-between;
            padding: 1.5rem;
            border-top: 1px solid rgba(255,255,255,0.1);
        }
        
        /* دکمه‌ها */
        .btn {
            padding: 0.9rem 1.8rem;
            border-radius: 50px;
            font-family: inherit;
            font-size: 0.95rem;
            font-weight: 600;
            cursor: pointer;
            border: none;
            transition: var(--transition);
            display: inline-flex;
            align-items: center;
            justify-content: center;
        }
        
        .btn svg {
            width: 20px;
            height: 20px;
            margin-left: 10px;
        }
        
        .btn-primary {
            background: linear-gradient(135deg, var(--primary), var(--primary-dark));
            color: white;
            box-shadow: 0 6px 20px rgba(255, 107, 53, 0.3);
        }
        
        .btn-primary:hover {
            background: linear-gradient(135deg, var(--primary-dark), var(--primary));
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(255, 107, 53, 0.4);
        }
        
        .btn-secondary {
            background: var(--dark);
            color: var(--light);
            border: 1px solid rgba(255,255,255,0.1);
        }
        
        .btn-secondary:hover {
            background: rgba(255,255,255,0.05);
            transform: translateY(-3px);
        }
        
        /* صفحه دانلود */
        .download-page {
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
        
        .download-content {
            max-width: 600px;
            margin: 2rem auto;
            background: var(--dark-light);
            padding: 2rem;
            border-radius: var(--border-radius);
            border: 1px solid rgba(255,255,255,0.1);
            position: relative;
            box-shadow: var(--box-shadow);
            animation: fadeIn 0.5s ease;
        }
        
        .download-header {
            text-align: center;
            margin-bottom: 2rem;
            position: relative;
        }
        
        .download-header h2 {
            color: var(--primary);
            font-size: 1.8rem;
            margin-bottom: 1rem;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .download-header p {
            color: var(--gray);
            font-size: 1rem;
        }
        
        .close-download {
            position: absolute;
            top: 0;
            left: 0;
            font-size: 2rem;
            cursor: pointer;
            color: var(--gray);
            padding: 0.5rem;
            transition: var(--transition);
        }
        
        .close-download:hover {
            color: var(--primary);
            transform: rotate(90deg);
        }
        
        /* محتوای دانلود */
        .download-items {
            display: grid;
            gap: 1.5rem;
        }
        
        .download-item {
            background: rgba(30, 30, 30, 0.7);
            padding: 1.5rem;
            border-radius: var(--border-radius-sm);
            border-left: 4px solid var(--primary);
            transition: var(--transition);
            position: relative;
            overflow: hidden;
        }
        
        .download-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
        }
        
        .download-item h3 {
            color: var(--primary);
            margin-bottom: 1rem;
            font-size: 1.3rem;
            display: flex;
            align-items: center;
        }
        
        .download-item h3 svg {
            width: 24px;
            height: 24px;
            margin-left: 10px;
            fill: currentColor;
        }
        
        .download-item p {
            font-size: 0.95rem;
            color: var(--lighter);
            margin-bottom: 1.5rem;
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
            box-shadow: 0 4px 15px rgba(67, 97, 238, 0.3);
        }
        
        .download-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(67, 97, 238, 0.4);
        }
        
        .download-btn svg {
            width: 20px;
            height: 20px;
            margin-left: 8px;
            fill: white;
        }
        
        /* صفحه درباره ما */
        .about-page {
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
        
        .about-content {
            max-width: 600px;
            margin: 2rem auto;
            background: var(--dark-light);
            padding: 2rem;
            border-radius: var(--border-radius);
            border: 1px solid rgba(255,255,255,0.1);
            position: relative;
            box-shadow: var(--box-shadow);
            animation: fadeIn 0.5s ease;
            text-align: center;
        }
        
        .about-header {
            margin-bottom: 2rem;
            position: relative;
        }
        
        .about-header h2 {
            color: var(--primary);
            font-size: 1.8rem;
            margin-bottom: 1rem;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .about-header p {
            color: var(--gray);
            font-size: 1rem;
        }
        
        .close-about {
            position: absolute;
            top: 0;
            left: 0;
            font-size: 2rem;
            cursor: pointer;
            color: var(--gray);
            padding: 0.5rem;
            transition: var(--transition);
        }
        
        .close-about:hover {
            color: var(--primary);
            transform: rotate(90deg);
        }
        
        .about-text {
            line-height: 1.9;
            margin-bottom: 2rem;
            font-size: 1rem;
            color: var(--lighter);
            text-align: justify;
        }
        
        /* لینک‌های اجتماعی */
        .social-links {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin-top: 2rem;
            flex-wrap: wrap;
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
            position: relative;
            overflow: hidden;
        }
        
        .social-link svg {
            width: 28px;
            height: 28px;
            fill: white;
            transition: var(--transition);
        }
        
        .social-link:hover {
            transform: translateY(-5px) scale(1.1);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
        }
        
        .social-link:hover svg {
            transform: scale(1.2);
        }
        
        .telegram {
            background: #0088CC;
        }
        
        .virasty {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
        }
        
        .instagram {
            background: linear-gradient(45deg, #405DE6, #5851DB, #833AB4, #C13584, #E1306C, #FD1D1D);
        }
        
        /* نوتیفیکیشن */
        .notification {
            position: fixed;
            bottom: 100px;
            right: 50%;
            transform: translateX(50%);
            background: var(--secondary);
            color: white;
            padding: 1rem 1.8rem;
            border-radius: 50px;
            font-size: 0.9rem;
            z-index: 100;
            box-shadow: 0 10px 30px rgba(67, 97, 238, 0.3);
            animation: slideUp 0.5s ease, fadeOut 0.5s ease 2.5s forwards;
            display: none;
            max-width: 90%;
            text-align: center;
        }
        
        @keyframes slideUp {
            from { bottom: 70px; opacity: 0; }
            to { bottom: 100px; opacity: 1; }
        }
        
        @keyframes fadeOut {
            from { opacity: 1; }
            to { opacity: 0; }
        }
        
        /* نویگیشن پایین */
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
            box-shadow: 0 -8px 25px rgba(0, 0, 0, 0.3);
            backdrop-filter: blur(10px);
        }
        
        .bottom-nav-btn {
            flex: 1;
            max-width: 220px;
            margin: 0 0.5rem;
            padding: 1rem;
            border-radius: 50px;
            background: var(--dark);
            color: var(--light);
            border: none;
            font-family: inherit;
            font-size: 0.95rem;
            cursor: pointer;
            border: 1px solid rgba(255,255,255,0.1);
            display: flex;
            align-items: center;
            justify-content: center;
            transition: var(--transition);
        }
        
        .bottom-nav-btn:hover {
            background: rgba(255,255,255,0.05);
            transform: translateY(-5px);
        }
        
        .bottom-nav-btn svg {
            width: 22px;
            height: 22px;
            margin-left: 10px;
            fill: currentColor;
        }
        
        #aboutBtn {
            color: var(--primary);
        }
        
        #downloadBtn {
            color: var(--secondary);
        }
        
        /* ریسپانسیو */
        @media (max-width: 768px) {
            .flag-grid {
                grid-template-columns: 1fr 1fr;
            }
            
            .flag-item span {
                font-size: 2.5rem;
            }
            
            .download-content, .about-content, .modal-content {
                padding: 1.5rem;
            }
            
            .download-item, .guide-step {
                padding: 1.2rem;
            }
            
            .download-item h3, .guide-step h3 {
                font-size: 1.2rem;
            }
            
            .bottom-nav-btn {
                font-size: 0.85rem;
                padding: 0.8rem;
            }
        }
        
        @media (max-width: 480px) {
            .flag-grid {
                grid-template-columns: 1fr 1fr;
                gap: 1rem;
            }
            
            .flag-item {
                padding: 1rem 0.5rem;
            }
            
            .flag-item span {
                font-size: 2.2rem;
            }
            
            .tab-button {
                padding: 0.8rem;
                font-size: 0.85rem;
            }
            
            .modal-tab {
                padding: 0.7rem 1rem;
                font-size: 0.85rem;
            }
            
            .btn {
                padding: 0.8rem 1.5rem;
                font-size: 0.85rem;
            }
            
            .social-link {
                width: 50px;
                height: 50px;
                font-size: 1.3rem;
            }
            
            .tagline-item {
                font-size: 0.85rem;
                padding: 0.4rem 1rem;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- هدر جدید -->
        <header class="app-header">
            <div class="logo">
                <div class="logo-icon">
                    <svg viewBox="0 0 24 24">
                        <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 18c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8zm-1-13h2v6h-2zm0 8h2v2h-2z"/>
                    </svg>
                </div>
                <div class="logo-text">XRO VPN</div>
            </div>
            
            <div class="tagline">
                <div class="tagline-item">امنیت</div>
                <div class="tagline-item">سرعت</div>
                <div class="tagline-item">پایداری</div>
            </div>
            
            <p class="app-description">ارائه بهترین سرویس‌های VPN با بالاترین سطح امنیت و سرعت برای دسترسی آزاد به اینترنت</p>
        </header>

        <!-- تب‌های اصلی -->
        <div class="tabs">
            <button class="tab-button active" onclick="showTab('country')">برای خودم</button>
            <button class="tab-button" onclick="showTab('affiliate')">برای همکاری</button>
        </div>

        <!-- تب استفاده شخصی -->
        <div id="country-tab" class="tab-content">
            <div class="message">
                <span id="typingText1"></span>
                <span class="notice-label">توجه</span>
            </div>

            <div class="flag-grid">
                <div class="flag-item active" onclick="openModal('آمریکا', 1350, 327, false)">
                    <span>🇺🇸</span>
                    <p>آمریکا</p>
                    <div class="status-badge active">سرویس فعال</div>
                </div>
                <div class="flag-item active" onclick="openModal('انگلیس', 1350, 327, false)">
                    <span>🇬🇧</span>
                    <p>انگلیس</p>
                    <div class="status-badge active">سرویس فعال</div>
                </div>
                <div class="flag-item active" onclick="openModal('ترکیه', 1350, 327, false)">
                    <span>🇹🇷</span>
                    <p>ترکیه</p>
                    <div class="status-badge active">سرویس فعال</div>
                </div>
                <div class="flag-item active" onclick="openModal('هلند', 1350, 327, false)">
                    <span>🇳🇱</span>
                    <p>هلند</p>
                    <div class="status-badge active">سرویس فعال</div>
                </div>
                <div class="flag-item active" onclick="openModal('فرانسه', 1350, 327, false)">
                    <span>🇫🇷</span>
                    <p>فرانسه</p>
                    <div class="status-badge active">سرویس فعال</div>
                </div>
                <div class="flag-item active" onclick="openModal('فنلاند', 1350, 327, false)">
                    <span>🇫🇮</span>
                    <p>فنلاند</p>
                    <div class="status-badge active">سرویس فعال</div>
                </div>
                <div class="flag-item inactive" onclick="showNotification()">
                    <span>🇮🇳</span>
                    <p>هند</p>
                    <div class="status-badge inactive">غیرفعال</div>
                </div>
                <div class="flag-item inactive" onclick="showNotification()">
                    <span>🇨🇳</span>
                    <p>چین</p>
                    <div class="status-badge inactive">غیرفعال</div>
                </div>
            </div>
        </div>

        <!-- تب همکاری -->
        <div id="affiliate-tab" class="tab-content" style="display: none;">
            <div class="message">
                <span id="typingText2"></span>
                <span class="notice-label">توجه</span>
            </div>

            <div class="flag-grid">
                <div class="flag-item active" onclick="openModal('آمریکا', 1010, 240, true)">
                    <span>🇺🇸</span>
                    <p>آمریکا</p>
                    <div class="status-badge active">سرویس فعال</div>
                </div>
                <div class="flag-item active" onclick="openModal('انگلیس', 1010, 240, true)">
                    <span>🇬🇧</span>
                    <p>انگلیس</p>
                    <div class="status-badge active">سرویس فعال</div>
                </div>
                <div class="flag-item active" onclick="openModal('ترکیه', 1010, 240, true)">
                    <span>🇹🇷</span>
                    <p>ترکیه</p>
                    <div class="status-badge active">سرویس فعال</div>
                </div>
                <div class="flag-item active" onclick="openModal('هلند', 1010, 240, true)">
                    <span>🇳🇱</span>
                    <p>هلند</p>
                    <div class="status-badge active">سرویس فعال</div>
                </div>
                <div class="flag-item active" onclick="openModal('فرانسه', 1010, 240, true)">
                    <span>🇫🇷</span>
                    <p>فرانسه</p>
                    <div class="status-badge active">سرویس فعال</div>
                </div>
                <div class="flag-item active" onclick="openModal('فنلاند', 1010, 240, true)">
                    <span>🇫🇮</span>
                    <p>فنلاند</p>
                    <div class="status-badge active">سرویس فعال</div>
                </div>
                <div class="flag-item inactive" onclick="showNotification()">
                    <span>🇮🇳</span>
                    <p>هند</p>
                    <div class="status-badge inactive">غیرفعال</div>
                </div>
                <div class="flag-item inactive" onclick="showNotification()">
                    <span>🇨🇳</span>
                    <p>چین</p>
                    <div class="status-badge inactive">غیرفعال</div>
                </div>
            </div>
        </div>
    </div>

    <!-- مودال سفارش -->
    <div id="orderModal" class="modal">
        <div class="modal-content">
            <div class="modal-header">
                <span class="close-modal" onclick="closeModal()">&times;</span>
                <h2 id="modalCountryName"><span>آمریکا</span> 🇺🇸</h2>
            </div>
            <div class="modal-body">
                <div class="modal-tabs" id="modalTabs"></div>
                
                <!-- تب حجم -->
                <div id="volumeTab" class="modal-tab-content active">
                    <div class="slider-container">
                        <div class="slider-header">
                            <span>حجم کانفیگ:</span>
                            <span class="slider-value" id="volumeValue">10 گیگ</span>
                        </div>
                        <input type="range" min="10" max="300" value="10" class="slider" id="volumeSlider" oninput="updateVolume(this.value)">
                    </div>
                    <div class="price-info">
                        قیمت هر گیگ: <span id="volumePriceText">1,350 تومان</span>
                    </div>
                    <div class="modal-footer">
                        <button class="btn btn-secondary" onclick="closeModal()">
                            <svg viewBox="0 0 24 24">
                                <path d="M19 6.41L17.59 5 12 10.59 6.41 5 5 6.41 10.59 12 5 17.59 6.41 19 12 13.41 17.59 19 19 17.59 13.41 12z"/>
                            </svg>
                            انصراف
                        </button>
                        <button class="btn btn-primary" onclick="showModalTab('days')">
                            <svg viewBox="0 0 24 24">
                                <path d="M10 6L8.59 7.41 13.17 12l-4.58 4.59L10 18l6-6z"/>
                            </svg>
                            بعدی
                        </button>
                    </div>
                </div>
                
                <!-- تب روز -->
                <div id="daysTab" class="modal-tab-content">
                    <div class="slider-container">
                        <div class="slider-header">
                            <span>تعداد روز:</span>
                            <span class="slider-value" id="daysValue">5 روز</span>
                        </div>
                        <input type="range" min="5" max="140" value="5" class="slider" id="daysSlider" oninput="updateDays(this.value)">
                    </div>
                    <div class="price-info">
                        قیمت هر روز: <span id="dayPriceText">327 تومان</span>
                    </div>
                    <div class="modal-footer">
                        <button class="btn btn-secondary" onclick="showModalTab('volume')">
                            <svg viewBox="0 0 24 24">
                                <path d="M15.41 7.41L14 6l-6 6 6 6 1.41-1.41L10.83 12z"/>
                            </svg>
                            قبلی
                        </button>
                        <button class="btn btn-primary" id="daysNextButton">
                            <svg viewBox="0 0 24 24">
                                <path d="M10 6L8.59 7.41 13.17 12l-4.58 4.59L10 18l6-6z"/>
                            </svg>
                            بعدی
                        </button>
                    </div>
                </div>
                
                <!-- تب تعداد -->
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
                            <svg viewBox="0 0 24 24">
                                <path d="M15.41 7.41L14 6l-6 6 6 6 1.41-1.41L10.83 12z"/>
                            </svg>
                            قبلی
                        </button>
                        <button class="btn btn-primary" onclick="showModalTab('final')">
                            <svg viewBox="0 0 24 24">
                                <path d="M10 6L8.59 7.41 13.17 12l-4.58 4.59L10 18l6-6z"/>
                            </svg>
                            بعدی
                        </button>
                    </div>
                </div>
                
                <!-- تب نهایی -->
                <div id="finalTab" class="modal-tab-content">
                    <div class="final-price">
                        قیمت نهایی: <span id="finalPrice">0</span> تومان
                    </div>
                    
                    <div class="order-summary">
                        <p>
                            <span>کشور:</span>
                            <span id="finalCountry">آمریکا</span>
                        </p>
                        <p>
                            <span>حجم:</span>
                            <span id="finalVolume">10 گیگ</span>
                        </p>
                        <p>
                            <span>مدت:</span>
                            <span id="finalDays">5 روز</span>
                        </p>
                        <p id="finalCountContainer" style="display: none;">
                            <span>تعداد:</span>
                            <span id="finalCount">3 عدد</span>
                        </p>
                    </div>
                    
                    <div class="modal-footer">
                        <button class="btn btn-secondary" id="finalPreviousButton">
                            <svg viewBox="0 0 24 24">
                                <path d="M15.41 7.41L14 6l-6 6 6 6 1.41-1.41L10.83 12z"/>
                            </svg>
                            قبلی
                        </button>
                        <button class="btn btn-primary" onclick="submitOrder()">
                            <svg viewBox="0 0 24 24">
                                <path d="M9 16.17L4.83 12l-1.42 1.41L9 19 21 7l-1.41-1.41z"/>
                            </svg>
                            ثبت درخواست
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- صفحه دانلود -->
    <div id="downloadPage" class="download-page">
        <div class="download-content">
            <div class="download-header">
                <span class="close-download" onclick="closeDownload()">&times;</span>
                <h2>دانلود نرم‌افزار</h2>
                <p>نسخه‌های مختلف برای دستگاه‌های مختلف</p>
            </div>
            <div class="download-items">
                <div class="download-item">
                    <h3>
                        <svg viewBox="0 0 24 24">
                            <path d="M17.6 9.48l1.84-3.18c.16-.31.04-.69-.26-.85-.3-.15-.68-.04-.85.26l-1.85 3.2c-2.86-1.21-6.08-1.21-8.94 0L5.65 5.71c-.18-.3-.55-.41-.85-.26-.3.16-.42.54-.26.85L6.4 9.48C3.3 11.25 1.28 14.44 1 18h22c-.28-3.56-2.3-6.75-5.4-8.52zM7 15.25c-.69 0-1.25-.56-1.25-1.25s.56-1.25 1.25-1.25 1.25.56 1.25 1.25-.56 1.25-1.25 1.25zm10 0c-.69 0-1.25-.56-1.25-1.25s.56-1.25 1.25-1.25 1.25.56 1.25 1.25-.56 1.25-1.25 1.25z"/>
                        </svg>
                        نسخه اندروید
                    </h3>
                    <p>نرم‌افزار v2rayNG برای دستگاه‌های اندروید</p>
                    <a href="https://github.com/2dust/v2rayNG/releases/download/1.8.5/v2rayNG_1.8.5.apk" class="download-btn" target="_blank">
                        دانلود
                        <svg viewBox="0 0 24 24">
                            <path d="M19 9h-4V3H9v6H5l7 7 7-7zM5 18v2h14v-2H5z"/>
                        </svg>
                    </a>
                </div>
                
                <div class="download-item">
                    <h3>
                        <svg viewBox="0 0 24 24">
                            <path d="M20 18c1.1 0 1.99-.9 1.99-2L22 6c0-1.1-.9-2-2-2H4c-1.1 0-2 .9-2 2v10c0 1.1.9 2 2 2H0v2h24v-2h-4zM4 6h16v10H4V6z"/>
                        </svg>
                        نسخه ویندوز
                    </h3>
                    <p>نرم‌افزار v2rayN برای سیستم‌عامل ویندوز</p>
                    <a href="https://github.com/2dust/v2rayN/releases/download/6.27/zz_v2rayN-With-Core-SelfContained.7z" class="download-btn" target="_blank">
                        دانلود
                        <svg viewBox="0 0 24 24">
                            <path d="M19 9h-4V3H9v6H5l7 7 7-7zM5 18v2h14v-2H5z"/>
                        </svg>
                    </a>
                </div>
                
                <div class="download-item">
                    <h3>
                        <svg viewBox="0 0 24 24">
                            <path d="M18.71 19.5c-.83 1.24-1.71 2.45-3.05 2.47-1.34.03-1.77-.79-3.29-.79-1.53 0-2 .77-3.27.82-1.31.05-2.3-1.32-3.14-2.53C4.25 17 2.94 12.45 4.7 9.39c.87-1.52 2.43-2.48 4.12-2.51 1.28-.02 2.5.87 3.29.87.78 0 2.26-1.07 3.81-.91.65.03 2.47.26 3.64 1.98-.09.06-2.17 1.28-2.15 3.81.03 3.02 2.65 4.03 2.68 4.04-.03.07-.42 1.44-1.38 2.83M13 3.5c.73-.83 1.94-1.46 2.94-1.5.13 1.17-.34 2.35-.96 3.07-.69.84-1.8 1.5-2.95 1.42-.15-1.15.41-2.35.97-2.99z"/>
                        </svg>
                        نسخه آیفون
                    </h3>
                    <p>نرم‌افزار Foxray برای دستگاه‌های iOS</p>
                    <a href="https://apps.apple.com/ca/app/foxray/id6448898396?platform=iphone" class="download-btn" target="_blank">
                        دانلود
                        <svg viewBox="0 0 24 24">
                            <path d="M19 9h-4V3H9v6H5l7 7 7-7zM5 18v2h14v-2H5z"/>
                        </svg>
                    </a>
                </div>
            </div>
        </div>
    </div>

    <!-- صفحه درباره ما -->
    <div id="aboutPage" class="about-page">
        <div class="about-content">
            <div class="about-header">
                <span class="close-about" onclick="closeAbout()">&times;</span>
                <h2>درباره ما</h2>
                <p>XRO VPN - حامی آزادی اینترنت</p>
            </div>
            <div class="about-text">
                <p>XRO VPN یک سرویس پیشرفته VPN است که با هدف ارائه دسترسی آزاد و امن به اینترنت تأسیس شده است. ما باور داریم که هر فردی حق دسترسی به اطلاعات را دارد، فارغ از محدودیت‌های جغرافیایی.</p>
                
                <p>تیم ما متشکل از متخصصان امنیت سایبری و شبکه است که سال‌ها تجربه در زمینه فناوری اطلاعات دارند. ما از آخرین فناوری‌های رمزنگاری و پروتکل‌های امنیتی استفاده می‌کنیم تا حریم خصوصی و امنیت کاربران را تضمین کنیم.</p>
                
                <p>سرورهای ما در بهترین دیتاسنترهای جهان قرار دارند و با بالاترین استانداردهای فنی پیکربندی شده‌اند تا بهترین تجربه کاربری را ارائه دهند. ما به طور مداوم در حال بهبود سرویس‌های خود هستیم تا نیازهای کاربران را به بهترین شکل برآورده کنیم.</p>
            </div>
            <div class="social-links">
                <a href="https://t.me/xrovpn" class="social-link telegram" target="_blank">
                    <svg viewBox="0 0 24 24">
                        <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm4.64 6.8c-.15 1.58-.8 5.42-1.13 7.19-.14.75-.42 1-.68 1.03-.58.05-1.02-.38-1.58-.75-.88-.58-1.38-.94-2.23-1.5-.99-.65-.35-1.01.22-1.59.15-.15 2.71-2.48 2.76-2.69.03-.1.06-.22-.06-.34-.1-.12-.26-.08-.4-.05-.17.05-2.79 1.86-3.15 2.1-.59.4-1.13.38-1.64-.12-.52-.51-.2-1.44.41-2.14 2.83-2.63 6.22-5.51 6.35-5.57.14-.07.27-.06.38.04.09.09.12.22.12.32-.01.06-.01.11-.02.17z"/>
                    </svg>
                </a>
                <a href="https://virasty.com/xroVPN" class="social-link virasty" target="_blank">
                    <svg viewBox="0 0 24 24">
                        <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 18c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8zm-1-13h2v6h-2zm0 8h2v2h-2z"/>
                    </svg>
                </a>
                <a href="#" class="social-link instagram" onclick="showNotification()">
                    <svg viewBox="0 0 24 24">
                        <path d="M12 2.16c3.2 0 3.58.01 4.85.07 3.12.14 4.53 1.56 4.66 4.66.06 1.27.07 1.65.07 4.85s-.01 3.58-.07 4.85c-.14 3.12-1.56 4.53-4.66 4.66-1.27.06-1.65.07-4.85.07s-3.58-.01-4.85-.07c-3.12-.14-4.53-1.56-4.66-4.66-.06-1.27-.07-1.65-.07-4.85s.01-3.58.07-4.85c.14-3.12 1.56-4.53 4.66-4.66 1.27-.06 1.65-.07 4.85-.07zm0-2.16c-3.21 0-3.62.01-4.9.07-3.88.18-5.55 1.85-5.73 5.73-.06 1.28-.07 1.69-.07 4.9s.01 3.62.07 4.9c.18 3.88 1.85 5.55 5.73 5.73 1.28.06 1.69.07 4.9.07s3.62-.01 4.9-.07c3.88-.18 5.55-1.85 5.73-5.73.06-1.28.07-1.69.07-4.9s-.01-3.62-.07-4.9c-.18-3.88-1.85-5.55-5.73-5.73-1.28-.06-1.69-.07-4.9-.07zm0 5.51c-2.49 0-4.51 2.02-4.51 4.51s2.02 4.51 4.51 4.51 4.51-2.02 4.51-4.51-2.02-4.51-4.51-4.51zm0 7.43c-1.61 0-2.92-1.31-2.92-2.92s1.31-2.92 2.92-2.92 2.92 1.31 2.92 2.92-1.31 2.92-2.92 2.92zm5.54-7.83c-.6 0-1.08-.48-1.08-1.08s.48-1.08 1.08-1.08 1.08.48 1.08 1.08-.48 1.08-1.08 1.08z"/>
                    </svg>
                </a>
            </div>
        </div>
    </div>

    <!-- نوتیفیکیشن -->
    <div class="notification" id="notification">
        این سرویس در حال حاضر غیرفعال می‌باشد
    </div>

    <!-- نویگیشن پایین -->
    <div class="bottom-nav">
        <button class="bottom-nav-btn" id="aboutBtn" onclick="showAbout()">
            <svg viewBox="0 0 24 24">
                <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm1 15h-2v-6h2v6zm0-8h-2V7h2v2z"/>
            </svg>
            درباره ما
        </button>
        <button class="bottom-nav-btn" id="downloadBtn" onclick="showDownload()">
            <svg viewBox="0 0 24 24">
                <path d="M19 9h-4V3H9v6H5l7 7 7-7zM5 18v2h14v-2H5z"/>
            </svg>
            دانلود نرم‌افزار
        </button>
    </div>

    <script>
        // متغیرهای سفارش
        let currentOrder = {
            country: '',
            volume: 10,
            days: 5,
            count: 3,
            volumePrice: 1350,
            dayPrice: 327,
            isAffiliate: false,
            minVolume: 10,
            maxVolume: 300,
            minDays: 5,
            maxDays: 140
        };
        
        // متن‌های تایپی
        const typingTexts = {
            personal: "این بخش مخصوص سفارش کانفیگ برای استفاده شخصی می‌باشد. حداقل حجم 10 گیگ و حداقل مدت 5 روز می‌باشد.",
            affiliate: "این بخش ویژه همکاران و کسب و کارها می‌باشد. حداقل حجم 15 گیگ و حداقل مدت 10 روز است."
        };
        
        // نمایش تب‌های اصلی
        function showTab(tabName) {
            const tabs = document.querySelectorAll('.tab-button');
            const tabContents = document.querySelectorAll('.tab-content');

            tabs.forEach(tab => tab.classList.remove('active'));
            tabContents.forEach(content => content.style.display = 'none');

            document.getElementById(`${tabName}-tab`).style.display = 'block';
            event.currentTarget.classList.add('active');
            
            // تنظیم محدودیت‌ها بر اساس نوع سفارش
            if (tabName === 'affiliate') {
                currentOrder.minVolume = 15;
                currentOrder.maxVolume = 1000;
                currentOrder.minDays = 10;
                currentOrder.maxDays = 365;
                typeText('typingText2', typingTexts.affiliate);
            } else {
                currentOrder.minVolume = 10;
                currentOrder.maxVolume = 300;
                currentOrder.minDays = 5;
                currentOrder.maxDays = 140;
                typeText('typingText1', typingTexts.personal);
            }
        }

        // تایپ متن
        function typeText(elementId, text) {
            const element = document.getElementById(elementId);
            element.textContent = '';
            let i = 0;
            const speed = 20;
            
            function typeWriter() {
                if (i < text.length) {
                    element.textContent += text.charAt(i);
                    i++;
                    setTimeout(typeWriter, speed);
                }
            }
            
            typeWriter();
        }

        // نمایش نوتیفیکیشن
        function showNotification() {
            const notification = document.getElementById('notification');
            notification.style.display = 'block';
            setTimeout(() => {
                notification.style.display = 'none';
            }, 2500);
            return false;
        }

        // نمایش صفحه درباره ما
        function showAbout() {
            document.getElementById('aboutPage').style.display = 'block';
            document.body.style.overflow = 'hidden';
        }

        // بستن صفحه درباره ما
        function closeAbout() {
            document.getElementById('aboutPage').style.display = 'none';
            document.body.style.overflow = 'auto';
        }

        // نمایش صفحه دانلود
        function showDownload() {
            document.getElementById('downloadPage').style.display = 'block';
            document.body.style.overflow = 'hidden';
        }

        // بستن صفحه دانلود
        function closeDownload() {
            document.getElementById('downloadPage').style.display = 'none';
            document.body.style.overflow = 'auto';
        }

        // باز کردن مودال سفارش
        function openModal(country, volumePrice, dayPrice, isAffiliate) {
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
                maxDays: isAffiliate ? 365 : 140
            };
            
            document.getElementById('modalCountryName').innerHTML = `<span>${country}</span> ${getCountryFlag(country)}`;
            document.getElementById('finalCountry').textContent = country;
            document.getElementById('volumePriceText').textContent = volumePrice.toLocaleString('fa-IR') + ' تومان';
            document.getElementById('dayPriceText').textContent = dayPrice.toLocaleString('fa-IR') + ' تومان';
            
            // تنظیم محدودیت‌های اسلایدرها
            const volumeSlider = document.getElementById('volumeSlider');
            volumeSlider.min = currentOrder.minVolume;
            volumeSlider.max = currentOrder.maxVolume;
            volumeSlider.value = currentOrder.volume;
            
            const daysSlider = document.getElementById('daysSlider');
            daysSlider.min = currentOrder.minDays;
            daysSlider.max = currentOrder.maxDays;
            daysSlider.value = currentOrder.days;
            
            // تنظیم تب‌های مودال بر اساس نوع سفارش
            setupModalTabs(isAffiliate);
            
            document.getElementById('orderModal').style.display = 'block';
            document.body.style.overflow = 'hidden';
            
            // به‌روزرسانی مقادیر اولیه
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
                'فنلاند': '🇫🇮',
                'هند': '🇮🇳',
                'چین': '🇨🇳'
            };
            return flags[country] || '🌐';
        }

        // تنظیم تب‌های مودال
        function setupModalTabs(isAffiliate) {
            const modalTabs = document.getElementById('modalTabs');
            modalTabs.innerHTML = '';
            
            // تب حجم
            const volumeTab = document.createElement('div');
            volumeTab.className = 'modal-tab active';
            volumeTab.textContent = 'حجم';
            volumeTab.onclick = () => showModalTab('volume');
            modalTabs.appendChild(volumeTab);
            
            // تب روز
            const daysTab = document.createElement('div');
            daysTab.className = 'modal-tab';
            daysTab.textContent = 'روز';
            daysTab.onclick = () => showModalTab('days');
            modalTabs.appendChild(daysTab);
            
            // تب تعداد (فقط برای همکاران)
            if (isAffiliate) {
                const countTab = document.createElement('div');
                countTab.className = 'modal-tab';
                countTab.textContent = 'تعداد';
                countTab.onclick = () => showModalTab('count');
                modalTabs.appendChild(countTab);
                
                document.getElementById('daysNextButton').onclick = () => showModalTab('count');
                document.getElementById('finalPreviousButton').onclick = () => showModalTab('count');
                document.getElementById('finalCountContainer').style.display = 'block';
            } else {
                document.getElementById('daysNextButton').onclick = () => showModalTab('final');
                document.getElementById('finalPreviousButton').onclick = () => showModalTab('days');
                document.getElementById('finalCountContainer').style.display = 'none';
            }
            
            // تب نهایی
            const finalTab = document.createElement('div');
            finalTab.className = 'modal-tab';
            finalTab.textContent = 'نهایی';
            finalTab.onclick = () => showModalTab('final');
            modalTabs.appendChild(finalTab);
        }

        // بستن مودال
        function closeModal() {
            document.getElementById('orderModal').style.display = 'none';
            document.body.style.overflow = 'auto';
        }

        // نمایش تب‌های مودال
        function showModalTab(tabName) {
            const tabs = document.querySelectorAll('.modal-tab');
            const tabContents = document.querySelectorAll('.modal-tab-content');

            tabs.forEach(tab => tab.classList.remove('active'));
            tabContents.forEach(content => content.classList.remove('active'));

            const targetTab = document.querySelector(`.modal-tab[onclick*="${tabName}"]`);
            if (targetTab) targetTab.classList.add('active');
            
            document.getElementById(`${tabName}Tab`).classList.add('active');
            
            if (tabName === 'final') {
                calculateFinalPrice();
            }
        }

        // به‌روزرسانی حجم
        function updateVolume(value) {
            currentOrder.volume = parseInt(value);
            document.getElementById('volumeValue').textContent = `${value} گیگ`;
            document.getElementById('finalVolume').textContent = `${value} گیگ`;
        }

        // به‌روزرسانی روزها
        function updateDays(value) {
            currentOrder.days = parseInt(value);
            document.getElementById('daysValue').textContent = `${value} روز`;
            document.getElementById('finalDays').textContent = `${value} روز`;
        }

        // به‌روزرسانی تعداد
        function updateCount(value) {
            currentOrder.count = parseInt(value);
            document.getElementById('countValue').textContent = `${value} عدد`;
            document.getElementById('finalCount').textContent = `${value} عدد`;
        }

        // محاسبه قیمت نهایی
        function calculateFinalPrice() {
            let totalPrice;
            if (currentOrder.isAffiliate) {
                totalPrice = (currentOrder.volume * currentOrder.volumePrice + currentOrder.days * currentOrder.dayPrice) * currentOrder.count;
            } else {
                totalPrice = (currentOrder.volume * currentOrder.volumePrice + currentOrder.days * currentOrder.dayPrice);
            }
            document.getElementById('finalPrice').textContent = totalPrice.toLocaleString('fa-IR');
            return totalPrice;
        }

        // ارسال سفارش
        function submitOrder() {
            const totalPrice = calculateFinalPrice();
            let orderText = `سفارش جدید:\n\nکشور: ${currentOrder.country}\nحجم: ${currentOrder.volume} گیگ\nمدت: ${currentOrder.days} روز`;

            if (currentOrder.isAffiliate) {
                orderText += `\nتعداد: ${currentOrder.count} عدد`;
            }

            orderText += `\n\nقیمت نهایی: ${totalPrice.toLocaleString('fa-IR')} تومان\n\nشماره کارت و اطلاعات لازم را ارسال کنید.`;

            const telegramUrl = `https://t.me/u0v0n?text=${encodeURIComponent(orderText)}`;
            window.open(telegramUrl, '_blank');
            
            closeModal();
        }

        // فعال کردن تب کشور به صورت پیش‌فرض
        document.addEventListener('DOMContentLoaded', function() {
            document.getElementById('country-tab').style.display = 'block';
            typeText('typingText1', typingTexts.personal);
        });

        // بستن مودال با کلیک خارج از آن
        window.addEventListener('click', function(event) {
            if (event.target === document.getElementById('orderModal')) {
                closeModal();
            }
            if (event.target === document.getElementById('downloadPage')) {
                closeDownload();
            }
            if (event.target === document.getElementById('aboutPage')) {
                closeAbout();
            }
        });
    </script>
</body>
</html>
