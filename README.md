<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>XRO VPN | امنیت، سرعت، پایداری</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
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
            --warning: #FFC107;
            --info: #17A2B8;
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
            --card-shadow: 0 8px 30px rgba(0, 0, 0, 0.2);
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
            padding-bottom: 80px;
            overflow-x: hidden;
            font-size: 14px;
            background-image: radial-gradient(circle at 10% 20%, rgba(67, 97, 238, 0.1) 0%, transparent 20%),
                            radial-gradient(circle at 90% 80%, rgba(255, 107, 53, 0.1) 0%, transparent 20%);
        }
        
        .container {
            max-width: 100%;
            margin: 0 auto;
            padding: 0 15px;
            width: 100%;
            overflow-x: hidden;
        }
        
        .app-header {
            padding: 1.5rem 0;
            text-align: center;
            position: relative;
            margin-bottom: 1rem;
        }
        
        .logo {
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 1.5rem;
            position: relative;
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
            box-shadow: 0 10px 25px rgba(67, 97, 238, 0.4);
            animation: pulse 3s infinite, float 6s ease-in-out infinite;
            position: relative;
            z-index: 1;
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
            animation: pulse 3s infinite 0.5s;
        }
        
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }
        
        @keyframes float {
            0% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
            100% { transform: translateY(0); }
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
            text-shadow: 0 4px 15px rgba(0, 0, 0, 0.3);
            position: relative;
        }
        
        .logo-text:after {
            content: 'PREMIUM';
            position: absolute;
            top: -10px;
            left: 0;
            font-size: 0.6rem;
            background: var(--warning);
            color: var(--dark);
            padding: 2px 8px;
            border-radius: 50px;
            font-weight: 700;
        }
        
        .tagline {
            display: flex;
            justify-content: center;
            margin-bottom: 1.5rem;
            flex-wrap: wrap;
            gap: 10px;
        }
        
        .tagline-item {
            margin: 0.4rem;
            padding: 0.6rem 1.2rem;
            border-radius: 50px;
            font-weight: 700;
            font-size: 0.85rem;
            position: relative;
            overflow: hidden;
            animation: wave 6s infinite;
            box-shadow: var(--card-shadow);
            display: flex;
            align-items: center;
        }
        
        .tagline-item i {
            margin-left: 6px;
            font-size: 1rem;
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
            color: var(--lighter);
            max-width: 90%;
            margin: 0 auto;
            line-height: 1.7;
            text-align: center;
            background: rgba(255,255,255,0.05);
            padding: 1rem;
            border-radius: var(--border-radius);
            border: 1px solid rgba(255,255,255,0.1);
            backdrop-filter: blur(5px);
        }
        
        .tabs {
            display: flex;
            margin: 2rem 0;
            background: var(--dark-light);
            border-radius: 50px;
            overflow: hidden;
            max-width: 100%;
            margin-left: auto;
            margin-right: auto;
            border: 1px solid rgba(255,255,255,0.1);
            box-shadow: var(--box-shadow);
            position: relative;
        }
        
        .tabs:before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(255,107,53,0.1), rgba(67,97,238,0.1));
            z-index: 0;
            opacity: 0;
            transition: var(--transition);
        }
        
        .tabs:hover:before {
            opacity: 1;
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
            z-index: 1;
        }
        
        .tab-button.active {
            color: white;
            background: linear-gradient(135deg, var(--primary), var(--primary-dark));
            box-shadow: 0 4px 15px rgba(255, 107, 53, 0.4);
        }
        
        .tab-button:not(.active):hover {
            color: var(--light);
            transform: translateY(-2px);
        }
        
        .tab-content {
            margin: 1.5rem 0;
            padding: 1.5rem;
            background: var(--dark-light);
            border-radius: var(--border-radius);
            min-height: 250px;
            border: 1px solid rgba(255,255,255,0.1);
            box-shadow: var(--box-shadow);
            animation: fadeIn 0.5s ease;
            backdrop-filter: blur(5px);
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(15px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .message {
            background: rgba(67, 97, 238, 0.1);
            margin: 1rem auto;
            padding: 1rem;
            border-radius: var(--border-radius);
            text-align: right;
            font-size: 0.85rem;
            color: var(--light);
            border: 1px solid rgba(67, 97, 238, 0.2);
            display: flex;
            align-items: center;
            justify-content: right;
            animation: fadeIn 0.6s ease;
            max-width: 95%;
            backdrop-filter: blur(5px);
        }
        
        .notice-label {
            background: var(--secondary);
            color: white;
            padding: 0.3rem 0.8rem;
            border-radius: 50px;
            font-weight: 700;
            font-size: 0.8rem;
            margin-left: 10px;
            white-space: nowrap;
            box-shadow: 0 3px 10px rgba(67, 97, 238, 0.3);
        }
        
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
            border-radius: var(--border-radius);
            cursor: pointer;
            border: 1px solid rgba(255,255,255,0.1);
            transition: var(--transition);
            position: relative;
            overflow: hidden;
            box-shadow: var(--card-shadow);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 120px;
            aspect-ratio: 1/1;
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
        
        .flag-item.active {
            border-color: var(--success);
        }
        
        .flag-item.inactive {
            opacity: 0.7;
            filter: grayscale(0.8);
            cursor: not-allowed;
        }
        
        .flag-item:hover:not(.inactive) {
            transform: translateY(-8px) scale(1.03);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.4);
            border-color: rgba(255,255,255,0.2);
        }
        
        .flag-item:hover:not(.inactive):before {
            opacity: 1;
        }
        
        .flag-item span {
            font-size: 2.5rem;
            display: block;
            margin-bottom: 0.5rem;
            transition: var(--transition);
            text-shadow: 0 5px 15px rgba(0,0,0,0.3);
        }
        
        .flag-item:hover:not(.inactive) span {
            transform: scale(1.2);
        }
        
        .flag-item p {
            margin: 0;
            font-size: 0.95rem;
            color: var(--light);
            font-weight: 600;
        }
        
        .flag-item .country-info {
            font-size: 0.8rem;
            color: var(--lighter);
            margin-top: 0.5rem;
            opacity: 0;
            max-height: 0;
            overflow: hidden;
            transition: var(--transition);
        }
        
        .flag-item:hover:not(.inactive) .country-info {
            opacity: 1;
            max-height: 100px;
            margin-top: 0.8rem;
        }
        
        .status-badge {
            position: absolute;
            top: 10px;
            left: 10px;
            font-size: 0.7rem;
            padding: 0.3rem 0.6rem;
            border-radius: 50px;
            font-weight: 700;
            box-shadow: 0 3px 8px rgba(0,0,0,0.2);
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
        
        .server-stats {
            display: none;
        }
        
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
            backdrop-filter: blur(5px);
        }
        
        .modal-content {
            background: var(--dark-light);
            border-radius: var(--border-radius);
            max-width: 95%;
            width: 100%;
            margin: 5% auto;
            overflow: hidden;
            border: 1px solid rgba(255,255,255,0.1);
            box-shadow: var(--box-shadow);
            animation: modalFadeIn 0.5s ease;
            transform-origin: center;
            position: relative;
            overflow: hidden;
        }
        
        .modal-content:before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,107,53,0.1) 0%, transparent 70%);
            z-index: -1;
            animation: rotate 20s linear infinite;
        }
        
        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }
        
        @keyframes modalFadeIn {
            from { opacity: 0; transform: translateY(30px) scale(0.95); }
            to { opacity: 1; transform: translateY(0) scale(1); }
        }
        
        .modal-header {
            padding: 1.5rem;
            background: linear-gradient(90deg, var(--primary), var(--primary-dark));
            color: white;
            text-align: center;
            position: relative;
            box-shadow: 0 5px 15px rgba(255, 107, 53, 0.3);
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
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
        }
        
        .close-modal:hover {
            transform: rotate(90deg);
            background: rgba(255,255,255,0.2);
        }
        
        .modal-body {
            padding: 1.5rem;
            color: var(--light);
        }
        
        .modal-tabs {
            display: flex;
            border-bottom: 1px solid rgba(255,255,255,0.1);
            margin-bottom: 1.5rem;
            overflow-x: auto;
            white-space: nowrap;
            position: relative;
        }
        
        .modal-tabs:after {
            content: '';
            position: absolute;
            bottom: -1px;
            left: 0;
            width: 100%;
            height: 1px;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            opacity: 0.3;
        }
        
        .modal-tab {
            padding: 0.8rem 1.2rem;
            cursor: pointer;
            font-weight: 600;
            color: var(--gray);
            font-size: 0.9rem;
            position: relative;
            transition: var(--transition);
            flex: 1;
            text-align: center;
            min-width: 80px;
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
        
        .slider-container {
            margin: 1.5rem 0;
            position: relative;
        }
        
        .slider-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 1rem;
            font-size: 0.95rem;
            align-items: center;
        }
        
        .slider-value {
            font-weight: 700;
            color: var(--primary);
            background: rgba(255,107,53,0.1);
            padding: 0.4rem 0.8rem;
            border-radius: 50px;
            min-width: 80px;
            text-align: center;
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
            position: relative;
            z-index: 1;
        }
        
        .slider:before {
            content: '';
            position: absolute;
            top: -5px;
            left: -5px;
            right: -5px;
            bottom: -5px;
            background: linear-gradient(135deg, rgba(255,107,53,0.1), rgba(67,97,238,0.1));
            border-radius: 8px;
            z-index: -1;
            opacity: 0;
            transition: var(--transition);
        }
        
        .slider:hover:before {
            opacity: 1;
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
            box-shadow: 0 6px 15px rgba(0, 0, 0, 0.4);
        }
        
        .price-info {
            background: rgba(255, 107, 53, 0.1);
            padding: 1rem;
            border-radius: var(--border-radius-sm);
            margin-top: 1.5rem;
            text-align: center;
            font-size: 0.9rem;
            border: 1px solid rgba(255,255,255,0.1);
            backdrop-filter: blur(5px);
        }
        
        .price-info span {
            color: var(--primary);
            font-weight: 700;
        }
        
        .final-price {
            text-align: center;
            margin: 2rem 0;
            font-size: 1.3rem;
            animation: pulse 2s infinite;
            position: relative;
        }
        
        .final-price:before {
            content: '';
            position: absolute;
            top: -10px;
            left: 0;
            right: 0;
            height: 1px;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
        }
        
        .final-price:after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            right: 0;
            height: 1px;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
        }
        
        .final-price span {
            color: var(--primary);
            font-weight: 800;
            font-size: 1.8rem;
            text-shadow: 0 3px 10px rgba(255, 107, 53, 0.3);
        }
        
        .order-summary {
            background: rgba(30, 30, 30, 0.7);
            padding: 1.5rem;
            border-radius: var(--border-radius-sm);
            margin: 2rem 0;
            border-left: 3px solid var(--primary);
            backdrop-filter: blur(5px);
            box-shadow: var(--card-shadow);
        }
        
        .order-summary p {
            margin-bottom: 0.8rem;
            font-size: 0.95rem;
            display: flex;
            justify-content: space-between;
            padding: 0.4rem 0;
            border-bottom: 1px dashed rgba(255,255,255,0.1);
        }
        
        .order-summary p:last-child {
            margin-bottom: 0;
            border-bottom: none;
        }
        
        .order-summary span {
            color: var(--light);
            font-weight: 500;
        }
        
        .order-summary .value {
            color: var(--primary);
            font-weight: 600;
        }
        
        .modal-footer {
            display: flex;
            justify-content: space-between;
            padding: 1.5rem;
            border-top: 1px solid rgba(255,255,255,0.1);
            gap: 15px;
        }
        
        .btn {
            padding: 1rem 1.8rem;
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
            flex: 1;
            position: relative;
            overflow: hidden;
            z-index: 1;
        }
        
        .btn:before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(255,255,255,0.1), transparent);
            z-index: -1;
            opacity: 0;
            transition: var(--transition);
        }
        
        .btn:hover:before {
            opacity: 1;
        }
        
        .btn svg {
            width: 20px;
            height: 20px;
            margin-left: 10px;
            transition: var(--transition);
        }
        
        .btn-primary {
            background: linear-gradient(135deg, var(--primary), var(--primary-dark));
            color: white;
            box-shadow: 0 8px 20px rgba(255, 107, 53, 0.3);
        }
        
        .btn-primary:hover {
            background: linear-gradient(135deg, var(--primary-dark), var(--primary));
            transform: translateY(-3px);
            box-shadow: 0 12px 25px rgba(255, 107, 53, 0.4);
        }
        
        .btn-primary:hover svg {
            transform: translateX(3px);
        }
        
        .btn-secondary {
            background: var(--dark);
            color: var(--light);
            border: 1px solid rgba(255,255,255,0.1);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        
        .btn-secondary:hover {
            background: rgba(255,255,255,0.05);
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
        }
        
        .btn-secondary:hover svg {
            transform: translateX(-3px);
        }
        
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
            backdrop-filter: blur(5px);
        }
        
        .download-content, .about-content {
            max-width: 95%;
            margin: 2rem auto;
            background: var(--dark-light);
            padding: 2rem;
            border-radius: var(--border-radius);
            border: 1px solid rgba(255,255,255,0.1);
            position: relative;
            box-shadow: var(--box-shadow);
            animation: fadeIn 0.5s ease;
            transform-origin: center;
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
            text-shadow: 0 4px 15px rgba(0, 0, 0, 0.3);
        }
        
        .download-header p, .about-header p {
            color: var(--gray);
            font-size: 1rem;
            max-width: 80%;
            margin: 0 auto;
        }
        
        .close-download, .close-about {
            position: absolute;
            top: 0;
            left: 0;
            font-size: 2rem;
            cursor: pointer;
            color: var(--gray);
            padding: 0.5rem;
            transition: var(--transition);
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
        }
        
        .close-download:hover, .close-about:hover {
            color: var(--primary);
            transform: rotate(90deg);
            background: rgba(255,255,255,0.1);
        }
        
        .download-items {
            display: grid;
            gap: 1.5rem;
        }
        
        .download-item {
            background: rgba(30, 30, 30, 0.7);
            padding: 1.5rem;
            border-radius: var(--border-radius-sm);
            border-left: 3px solid var(--primary);
            transition: var(--transition);
            position: relative;
            overflow: hidden;
            backdrop-filter: blur(5px);
            box-shadow: var(--card-shadow);
        }
        
        .download-item:before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(67,97,238,0.1), transparent);
            z-index: -1;
            opacity: 0;
            transition: var(--transition);
        }
        
        .download-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.4);
        }
        
        .download-item:hover:before {
            opacity: 1;
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
            line-height: 1.7;
        }
        
        .download-meta {
            display: flex;
            justify-content: space-between;
            margin-bottom: 1.5rem;
            font-size: 0.85rem;
            color: var(--gray);
        }
        
        .meta-item {
            display: flex;
            align-items: center;
        }
        
        .meta-item i {
            margin-left: 6px;
            color: var(--primary);
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
            box-shadow: 0 5px 15px rgba(67, 97, 238, 0.3);
        }
        
        .download-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(67, 97, 238, 0.4);
            background: linear-gradient(135deg, var(--secondary-dark), var(--secondary));
        }
        
        .download-btn svg {
            width: 20px;
            height: 20px;
            margin-left: 8px;
            fill: white;
        }
        
        .about-text {
            line-height: 1.8;
            margin-bottom: 2rem;
            font-size: 0.95rem;
            color: var(--lighter);
            text-align: justify;
        }
        
        .team-members {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 1.5rem;
            margin: 2rem 0;
        }
        
        .team-member {
            background: rgba(30, 30, 30, 0.7);
            padding: 1.5rem;
            border-radius: var(--border-radius-sm);
            text-align: center;
            border: 1px solid rgba(255,255,255,0.1);
            transition: var(--transition);
            box-shadow: var(--card-shadow);
        }
        
        .team-member:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
            border-color: var(--primary);
        }
        
        .member-avatar {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            margin: 0 auto 1rem;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 2rem;
            font-weight: 700;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }
        
        .member-name {
            font-weight: 700;
            margin-bottom: 0.5rem;
            color: var(--light);
        }
        
        .member-role {
            font-size: 0.85rem;
            color: var(--primary);
        }
        
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 1.5rem;
            margin: 2rem 0;
        }
        
        .stat-card {
            background: rgba(30, 30, 30, 0.7);
            padding: 1.5rem;
            border-radius: var(--border-radius-sm);
            text-align: center;
            border: 1px solid rgba(255,255,255,0.1);
            transition: var(--transition);
            box-shadow: var(--card-shadow);
        }
        
        .stat-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
        }
        
        .stat-value {
            font-size: 2rem;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 0.5rem;
        }
        
        .stat-label {
            font-size: 0.85rem;
            color: var(--lighter);
        }
        
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
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
        }
        
        .social-link:before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(255,255,255,0.1), transparent);
            z-index: -1;
            opacity: 0;
            transition: var(--transition);
        }
        
        .social-link:hover:before {
            opacity: 1;
        }
        
        .social-link:hover {
            transform: translateY(-5px) scale(1.1);
            box-shadow: 0 12px 25px rgba(0, 0, 0, 0.4);
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
        
        .notification {
            position: fixed;
            bottom: 70px;
            right: 50%;
            transform: translateX(50%);
            background: var(--secondary);
            color: white;
            padding: 1rem 1.8rem;
            border-radius: 50px;
            font-size: 0.9rem;
            z-index: 100;
            box-shadow: 0 10px 30px rgba(67, 97, 238, 0.4);
            animation: slideUp 0.5s ease, fadeOut 0.5s ease 2.5s forwards;
            display: none;
            max-width: 90%;
            text-align: center;
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255,255,255,0.2);
        }
        
        @keyframes slideUp {
            from { bottom: 50px; opacity: 0; }
            to { bottom: 70px; opacity: 1; }
        }
        
        @keyframes fadeOut {
            from { opacity: 1; }
            to { opacity: 0; }
        }
        
        .bottom-nav {
            position: fixed;
            bottom: 0;
            left: 0;
            right: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            background: var(--dark-light);
            padding: 1rem;
            border-top: 1px solid rgba(255,255,255,0.1);
            z-index: 99;
            box-shadow: 0 -8px 25px rgba(0, 0, 0, 0.3);
            backdrop-filter: blur(8px);
            width: 100%;
            max-width: 100%;
            overflow-x: hidden;
            gap: 15px;
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
            font-size: 0.95rem;
            cursor: pointer;
            border: 1px solid rgba(255,255,255,0.1);
            display: flex;
            align-items: center;
            justify-content: center;
            transition: var(--transition);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            position: relative;
            overflow: hidden;
        }
        
        .bottom-nav-btn:before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(255,255,255,0.05), transparent);
            z-index: -1;
            opacity: 0;
            transition: var(--transition);
        }
        
        .bottom-nav-btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
        }
        
        .bottom-nav-btn:hover:before {
            opacity: 1;
        }
        
        .bottom-nav-btn svg {
            width: 22px;
            height: 22px;
            margin-left: 10px;
            fill: currentColor;
            transition: var(--transition);
        }
        
        .bottom-nav-btn:hover svg {
            transform: scale(1.1);
        }
        
        #aboutBtn {
            color: var(--primary);
        }
        
        #downloadBtn {
            color: var(--secondary);
        }
        
        @media (min-width: 768px) {
            body { font-size: 16px; padding-bottom: 100px; }
            .container { max-width: 1200px; padding: 0 25px; }
            .app-header { padding: 3rem 0 2rem; }
            .logo-icon { width: 60px; height: 60px; }
            .logo-icon svg { width: 32px; height: 32px; }
            .logo-text { font-size: 2rem; }
            .logo-text:after { font-size: 0.7rem; padding: 3px 10px; top: -12px; }
            .app-description { font-size: 1rem; max-width: 800px; padding: 1.2rem; }
            .tabs { max-width: 550px; }
            .tab-button { padding: 1.2rem; font-size: 1rem; }
            .tab-content { padding: 2rem; min-height: 350px; }
            .message { padding: 1.2rem 1.8rem; font-size: 0.9rem; max-width: 90%; }
            .notice-label { padding: 0.4rem 1rem; font-size: 0.85rem; }
            .flag-grid { grid-template-columns: repeat(auto-fit, minmax(150px, 1fr)); gap: 2rem; }
            .flag-item { padding: 1.5rem; min-height: 150px; }
            .flag-item span { font-size: 3rem; }
            .flag-item p { font-size: 1.1rem; }
            .status-badge { font-size: 0.8rem; padding: 0.3rem 0.8rem; top: 15px; left: 15px; }
            .modal-content { max-width: 550px; margin: 3% auto; }
            .modal-header { padding: 2rem; }
            .modal-header h2 { font-size: 1.5rem; }
            .modal-header h2 span { font-size: 2rem; }
            .close-modal { font-size: 2rem; top: 1.5rem; left: 2rem; }
            .modal-body { padding: 2rem; }
            .modal-tab { padding: 1rem 1.5rem; font-size: 1rem; }
            .slider-container { margin: 2rem 0; }
            .slider-header { font-size: 1rem; }
            .slider { height: 10px; margin: 1.2rem 0; }
            .slider::-webkit-slider-thumb { width: 28px; height: 28px; border: 4px solid white; }
            .price-info { padding: 1.2rem; font-size: 1rem; }
            .final-price { font-size: 1.5rem; margin: 2.5rem 0; }
            .final-price span { font-size: 2.2rem; }
            .order-summary { padding: 2rem; }
            .order-summary p { font-size: 1rem; }
            .modal-footer { padding: 2rem; }
            .btn { padding: 1.2rem 2rem; font-size: 1rem; }
            .btn svg { width: 22px; height: 22px; margin-left: 12px; }
            .download-content, .about-content { max-width: 700px; padding: 3rem; }
            .download-header h2, .about-header h2 { font-size: 2.2rem; }
            .download-header p, .about-header p { font-size: 1.1rem; }
            .close-download, .close-about { font-size: 2.2rem; }
            .download-item { padding: 2rem; }
            .download-item h3 { font-size: 1.5rem; }
            .download-item h3 svg { width: 28px; height: 28px; }
            .download-item p { font-size: 1rem; }
            .download-btn { padding: 1rem 1.8rem; font-size: 1rem; }
            .download-btn svg { width: 22px; height: 22px; margin-left: 10px; }
            .about-text { font-size: 1.1rem; line-height: 2; }
            .team-members { grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 2rem; }
            .member-avatar { width: 100px; height: 100px; font-size: 2.5rem; }
            .member-name { font-size: 1.1rem; }
            .member-role { font-size: 0.9rem; }
            .stats-grid { grid-template-columns: repeat(auto-fit, minmax(150px, 1fr)); gap: 2rem; }
            .stat-value { font-size: 2.5rem; }
            .stat-label { font-size: 0.95rem; }
            .social-links { gap: 2rem; }
            .social-link { width: 70px; height: 70px; font-size: 1.8rem; }
            .social-link svg { width: 32px; height: 32px; }
            .notification { padding: 1.2rem 2rem; font-size: 1rem; max-width: 500px; }
            .bottom-nav { padding: 1.2rem; }
            .bottom-nav-btn { max-width: 250px; padding: 1.2rem; font-size: 1rem; }
            .bottom-nav-btn svg { width: 24px; height: 24px; margin-left: 12px; }
        }
        
        @media (min-width: 480px) and (max-width: 767px) {
            .flag-grid { grid-template-columns: repeat(auto-fit, minmax(140px, 1fr)); gap: 1.8rem; }
            .flag-item span { font-size: 2.8rem; }
            .modal-content { max-width: 90%; }
            .bottom-nav-btn { font-size: 0.9rem; padding: 1rem; }
        }
        
        @media (max-width: 479px) {
            .flag-grid { grid-template-columns: 1fr 1fr; gap: 1rem; }
            .flag-item { padding: 1rem; min-height: 120px; }
            .flag-item span { font-size: 2.2rem; }
            .tab-button { padding: 0.8rem; font-size: 0.85rem; }
            .modal-tab { padding: 0.7rem 0.9rem; font-size: 0.85rem; min-width: 70px; }
            .btn { padding: 0.9rem 1.2rem; font-size: 0.85rem; }
            .social-link { width: 50px; height: 50px; font-size: 1.3rem; }
            .social-link svg { width: 24px; height: 24px; }
            .notification { padding: 0.9rem 1.5rem; font-size: 0.85rem; }
            .bottom-nav-btn { font-size: 0.85rem; padding: 0.9rem; }
            .bottom-nav-btn svg { width: 20px; height: 20px; }
        }
    </style>
</head>
<body>
    <div class="container">
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
                <div class="tagline-item"><i class="fas fa-shield-alt"></i> امنیت</div>
                <div class="tagline-item"><i class="fas fa-bolt"></i> سرعت</div>
                <div class="tagline-item"><i class="fas fa-server"></i> پایداری</div>
            </div>
            <p class="app-description">یآ هَمِه یآ هیچ کَس</p>
        </header>
        <div class="tabs">
            <button class="tab-button active" onclick="showTab('country')">برای خودم</button>
            <button class="tab-button" onclick="showTab('affiliate')">برای همکاری</button>
        </div>
        <div id="country-tab" class="tab-content">
            <div class="message">
                <span id="typingText1">این بخش مخصوص سفارش کانفیگ برای استفاده شخصی است</span>
                <span class="notice-label">توجه</span>
            </div>
            <div class="flag-grid">
                <div class="flag-item active" onclick="openModal('آمریکا', 1350, 327, false)">
                    <span>🇺🇸</span>
                    <p>آمریکا</p>
                    <div class="country-info">سرورهای پرسرعت در نیویورک و لس آنجلس</div>
                    <div class="status-badge active">سرویس فعال</div>
                </div>
                <div class="flag-item active" onclick="openModal('انگلیس', 1350, 327, false)">
                    <span>🇬🇧</span>
                    <p>انگلیس</p>
                    <div class="country-info">سرورهای لندن با پهنای باند بالا</div>
                    <div class="status-badge active">سرویس فعال</div>
                </div>
                <div class="flag-item active" onclick="openModal('ترکیه', 1350, 327, false)">
                    <span>🇹🇷</span>
                    <p>ترکیه</p>
                    <div class="country-info">سرورهای استانبول با پینگ پایین</div>
                    <div class="status-badge active">سرویس فعال</div>
                </div>
                <div class="flag-item active" onclick="openModal('هلند', 1350, 327, false)">
                    <span>🇳🇱</span>
                    <p>هلند</p>
                    <div class="country-info">سرورهای آمستردام با اتصال پایدار</div>
                    <div class="status-badge active">سرویس فعال</div>
                </div>
                <div class="flag-item active" onclick="openModal('فرانسه', 1350, 327, false)">
                    <span>🇫🇷</span>
                    <p>فرانسه</p>
                    <div class="country-info">سرورهای پاریس با امنیت بالا</div>
                    <div class="status-badge active">سرویس فعال</div>
                </div>
                <div class="flag-item active" onclick="openModal('فنلاند', 1350, 327, false)">
                    <span>🇫🇮</span>
                    <p>فنلاند</p>
                    <div class="country-info">سرورهای هلسینکی با حریم خصوصی قوی</div>
                    <div class="status-badge active">سرویس فعال</div>
                </div>
                <div class="flag-item inactive" onclick="showNotification()">
                    <span>🇮🇳</span>
                    <p>هند</p>
                    <div class="country-info">به زودی فعال می‌شود</div>
                    <div class="status-badge inactive">غیرفعال</div>
                </div>
                <div class="flag-item inactive" onclick="showNotification()">
                    <span>🇨🇳</span>
                    <p>چین</p>
                    <div class="country-info">به زودی فعال می‌شود</div>
                    <div class="status-badge inactive">غیرفعال</div>
                </div>
            </div>
        </div>
        <div id="affiliate-tab" class="tab-content" style="display: none;">
            <div class="message">
                <span id="typingText2">این بخش مخصوص همکاران و فروشندگان وی پی ان می باشد</span>
                <span class="notice-label">توجه</span>
            </div>
            <div class="flag-grid">
                <div class="flag-item active" onclick="openModal('آمریکا', 1010, 240, true)">
                    <span>🇺🇸</span>
                    <p>آمریکا</p>
                    <div class="country-info">سرورهای پرسرعت در نیویورک و لس آنجلس</div>
                    <div class="status-badge active">سرویس فعال</div>
                </div>
                <div class="flag-item active" onclick="openModal('انگلیس', 1010, 240, true)">
                    <span>🇬🇧</span>
                    <p>انگلیس</p>
                    <div class="country-info">سرورهای لندن با پهنای باند بالا</div>
                    <div class="status-badge active">سرویس فعال</div>
                </div>
                <div class="flag-item active" onclick="openModal('ترکیه', 1010, 240, true)">
                    <span>🇹🇷</span>
                    <p>ترکیه</p>
                    <div class="country-info">سرورهای استانبول با پینگ پایین</div>
                    <div class="status-badge active">سرویس فعال</div>
                </div>
                <div class="flag-item active" onclick="openModal('هلند', 1010, 240, true)">
                    <span>🇳🇱</span>
                    <p>هلند</p>
                    <div class="country-info">سرورهای آمستردام با اتصال پایدار</div>
                    <div class="status-badge active">سرویس فعال</div>
                </div>
                <div class="flag-item active" onclick="openModal('فرانسه', 1010, 240, true)">
                    <span>🇫🇷</span>
                    <p>فرانسه</p>
                    <div class="country-info">سرورهای پاریس با امنیت بالا</div>
                    <div class="status-badge active">سرویس فعال</div>
                </div>
                <div class="flag-item active" onclick="openModal('فنلاند', 1010, 240, true)">
                    <span>🇫🇮</span>
                    <p>فنلاند</p>
                    <div class="country-info">سرورهای هلسینکی با حریم خصوصی قوی</div>
                    <div class="status-badge active">سرویس فعال</div>
                </div>
                <div class="flag-item inactive" onclick="showNotification()">
                    <span>🇮🇳</span>
                    <p>هند</p>
                    <div class="country-info">به زودی فعال می‌شود</div>
                    <div class="status-badge inactive">غیرفعال</div>
                </div>
                <div class="flag-item inactive" onclick="showNotification()">
                    <span>🇨🇳</span>
                    <p>چین</p>
                    <div class="country-info">به زودی فعال می‌شود</div>
                    <div class="status-badge inactive">غیرفعال</div>
                </div>
            </div>
        </div>
    </div>
    <div id="orderModal" class="modal">
        <div class="modal-content">
            <div class="modal-header">
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
                <div id="finalTab" class="modal-tab-content">
                    <div class="final-price">
                        قیمت نهایی: <span id="finalPrice">0</span> تومان
                    </div>
                    <div class="order-summary">
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
    <div id="downloadPage" class="download-page">
        <div class="download-content">
            <div class="download-header">
                <span class="close-download" onclick="closeDownload()">×</span>
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
                    <div class="download-meta">
                        <div class="meta-item"><i class="fas fa-code-branch"></i> نسخه 1.8.5</div>
                        <div class="meta-item"><i class="fas fa-calendar-alt"></i> 1402/05/12</div>
                    </div>
                    <p>نرم‌افزار v2rayNG برای دستگاه‌های اندروید. بهترین انتخاب برای کاربران اندروید با رابط کاربری ساده و امکانات پیشرفته.</p>
                    <a href="https://github.com/2dust/v2rayNG/releases/download/1.8.5/v2rayNG_1.8.5.apk" class="download-btn" target="_blank">
                        دانلود (12MB)
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
                    <div class="download-meta">
                        <div class="meta-item"><i class="fas fa-code-branch"></i> نسخه 6.27</div>
                        <div class="meta-item"><i class="fas fa-calendar-alt"></i> 1402/04/28</div>
                    </div>
                    <p>نرم‌افزار v2rayN برای سیستم‌عامل ویندوز. پشتیبانی از ویندوز 7 به بالا با قابلیت‌های مدیریت چند کانفیگ.</p>
                    <a href="https://github.com/2dust/v2rayN/releases/download/6.27/zz_v2rayN-With-Core-SelfContained.7z" class="download-btn" target="_blank">
                        دانلود (45MB)
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
                    <div class="download-meta">
                        <div class="meta-item"><i class="fas fa-code-branch"></i> نسخه 2.1.4</div>
                        <div class="meta-item"><i class="fas fa-calendar-alt"></i> 1402/05/05</div>
                    </div>
                    <p>نرم‌افزار Foxray برای دستگاه‌های iOS. سازگار با آیفون و آیپد با پشتیبانی از آخرین نسخه iOS.</p>
                    <a href="https://apps.apple.com/ca/app/foxray/id6448898396?platform=iphone" class="download-btn" target="_blank">
                        دانلود از اپ استور
                        <svg viewBox="0 0 24 24">
                            <path d="M19 9h-4V3H9v6H5l7 7 7-7zM5 18v2h14v-2H5z"/>
                        </svg>
                    </a>
                </div>
            </div>
        </div>
    </div>
    <div id="aboutPage" class="about-page">
        <div class="about-content">
            <div class="about-header">
                <span class="close-about" onclick="closeAbout()">×</span>
                <h2>درباره ما</h2>
                <p>XRO VPN - ارائه کانفیگ سرورهای پایدار</p>
            </div>
            <div class="about-text">
                <p>XRO VPN ارائه دهنده کانفیگ سرورهای پایدار و پرسرعت در کشورهای مختلف می‌باشد. ما با استفاده از بهترین سرورها و فناوری‌های روز، اتصالی پایدار و با کیفیت را برای شما فراهم می‌کنیم.</p>
                <p>تیم ما متشکل از متخصصان شبکه است که سال‌ها تجربه در زمینه ارائه سرویس‌های اینترنتی دارند. ما از آخرین فناوری‌ها برای ارائه بهترین کیفیت استفاده می‌کنیم.</p>
            </div>
            
            <div class="stats-grid">
                <div class="stat-card">
                    <div class="stat-value">50+</div>
                    <div class="stat-label">سرور در سراسر جهان</div>
                </div>
                <div class="stat-card">
                    <div class="stat-value">15</div>
                    <div class="stat-label">کشور مختلف</div>
                </div>
                <div class="stat-card">
                    <div class="stat-value">10K+</div>
                    <div class="stat-label">کاربر راضی</div>
                </div>
                <div class="stat-card">
                    <div class="stat-value">99.9%</div>
                    <div class="stat-label">آپتایم سرویس</div>
                </div>
            </div>
            
            <h3 style="text-align: center; margin: 2rem 0 1.5rem; color: var(--primary);">سازنده</h3>
            <div class="team-members">
                <div class="team-member">
                    <div class="member-avatar">X</div>
                    <div class="member-name">آقای ایکسرو</div>
                    <div class="member-role">سازنده</div>
                </div>
            </div>
            
            <div class="social-links">
                <a href="https://t.me/xrovpn" class="social-link telegram" target="_blank">
                    <i class="fab fa-telegram"></i>
                </a>
                <a href="https://virasty.com/xroVPN" class="social-link virasty" target="_blank">
                    <i class="fas fa-globe"></i>
                </a>
                <a href="#" class="social-link instagram" onclick="showNotification()">
                    <i class="fab fa-instagram"></i>
                </a>
            </div>
        </div>
    </div>
    <div class="notification" id="notification">
        این سرویس در حال حاضر غیرفعال می‌باشد
    </div>
    
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
        
        const typingTexts = {
            personal: "این بخش مخصوص سفارش کانفیگ برای استفاده شخصی است",
            affiliate: "این بخش مخصوص همکاران و فروشندگان وی پی ان می باشد"
        };
        
        function showTab(tabName) {
            const tabs = document.querySelectorAll('.tab-button');
            const tabContents = document.querySelectorAll('.tab-content');
            
            tabs.forEach(tab => tab.classList.remove('active'));
            tabContents.forEach(content => content.style.display = 'none');
            
            document.getElementById(`${tabName}-tab`).style.display = 'block';
            event.currentTarget.classList.add('active');
            
            if (tabName === 'affiliate') {
                currentOrder.minVolume = 15;
                currentOrder.maxVolume = 1000;
                currentOrder.minDays = 10;
                currentOrder.maxDays = 365;
                document.getElementById('typingText2').textContent = typingTexts.affiliate;
            } else {
                currentOrder.minVolume = 10;
                currentOrder.maxVolume = 300;
                currentOrder.minDays = 5;
                currentOrder.maxDays = 140;
                document.getElementById('typingText1').textContent = typingTexts.personal;
            }
        }
        
        function showNotification() {
            const notification = document.getElementById('notification');
            notification.style.display = 'block';
            
            setTimeout(() => {
                notification.style.display = 'none';
            }, 2500);
            
            return false;
        }
        
        function showAbout() {
            document.getElementById('aboutPage').style.display = 'block';
            document.body.style.overflow = 'hidden';
        }
        
        function closeAbout() {
            document.getElementById('aboutPage').style.display = 'none';
            document.body.style.overflow = 'auto';
        }
        
        function showDownload() {
            document.getElementById('downloadPage').style.display = 'block';
            document.body.style.overflow = 'hidden';
        }
        
        function closeDownload() {
            document.getElementById('downloadPage').style.display = 'none';
            document.body.style.overflow = 'auto';
        }
        
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
            
            const volumeSlider = document.getElementById('volumeSlider');
            volumeSlider.min = currentOrder.minVolume;
            volumeSlider.max = currentOrder.maxVolume;
            volumeSlider.value = currentOrder.volume;
            
            const daysSlider = document.getElementById('daysSlider');
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
            return flags[country] || '';
        }
        
        function setupModalTabs(isAffiliate) {
            const modalTabs = document.getElementById('modalTabs');
            modalTabs.innerHTML = `
                <div class="modal-tab active" onclick="showModalTab('volume')">حجم</div>
                <div class="modal-tab" onclick="showModalTab('days')">روز</div>
                ${isAffiliate ? '<div class="modal-tab" onclick="showModalTab(\'count\')">تعداد</div>' : ''}
                <div class="modal-tab" onclick="showModalTab('final')">نهایی</div>
            `;
            
            document.getElementById('finalCountContainer').style.display = isAffiliate ? 'flex' : 'none';
            document.getElementById('daysNextButton').onclick = isAffiliate ? () => showModalTab('count') : () => showModalTab('final');
            document.getElementById('finalPreviousButton').onclick = isAffiliate ? () => showModalTab('count') : () => showModalTab('days');
        }
        
        function showModalTab(tabName) {
            const modalTabs = document.querySelectorAll('.modal-tab');
            const modalTabContents = document.querySelectorAll('.modal-tab-content');
            
            modalTabs.forEach(tab => tab.classList.remove('active'));
            modalTabContents.forEach(content => content.style.display = 'none');
            
            document.getElementById(`${tabName}Tab`).style.display = 'block';
            document.querySelector(`.modal-tab[onclick="showModalTab('${tabName}')"]`).classList.add('active');
            
            updatePrice();
        }
        
        function updateVolume(value) {
            currentOrder.volume = parseInt(value);
            document.getElementById('volumeValue').textContent = `${currentOrder.volume} گیگ`;
            document.getElementById('finalVolume').textContent = `${currentOrder.volume} گیگ`;
            updatePrice();
        }
        
        function updateDays(value) {
            currentOrder.days = parseInt(value);
            document.getElementById('daysValue').textContent = `${currentOrder.days} روز`;
            document.getElementById('finalDays').textContent = `${currentOrder.days} روز`;
            updatePrice();
        }
        
        function updateCount(value) {
            currentOrder.count = parseInt(value);
            document.getElementById('countValue').textContent = `${currentOrder.count} عدد`;
            document.getElementById('finalCount').textContent = `${currentOrder.count} عدد`;
            updatePrice();
        }
        
        function updatePrice() {
            const totalPrice = (currentOrder.volume * currentOrder.volumePrice + currentOrder.days * currentOrder.dayPrice) * (currentOrder.isAffiliate ? currentOrder.count : 1);
            document.getElementById('finalPrice').textContent = totalPrice.toLocaleString('fa-IR');
        }
        
        function closeModal() {
            document.getElementById('orderModal').style.display = 'none';
            document.body.style.overflow = 'auto';
        }
        
        function submitOrder() {
            const message = `سفارش جدید برای u0v0n:\nکشور: ${currentOrder.country}\nحجم: ${currentOrder.volume} گیگ\nمدت: ${currentOrder.days} روز${currentOrder.isAffiliate ? `\nتعداد: ${currentOrder.count} عدد` : ''}\nقیمت نهایی: ${(currentOrder.volume * currentOrder.volumePrice + currentOrder.days * currentOrder.dayPrice) * (currentOrder.isAffiliate ? currentOrder.count : 1).toLocaleString('fa-IR')} تومان`;
            window.open(`https://t.me/u0v0n?text=${encodeURIComponent(message)}`, '_blank');
            closeModal();
        }
        
        window.onload = () => {
            document.getElementById('typingText1').textContent = typingTexts.personal;
            
            // Add animation to flag items
            const flagItems = document.querySelectorAll('.flag-item');
            flagItems.forEach((item, index) => {
                item.style.animationDelay = `${index * 0.1}s`;
            });
        };
    </script>
</body>
</html>
