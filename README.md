<html lang="fa" dir="rtl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width,initial-scale=1,maximum-scale=1,user-scalable=no">
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
      --text-color: #E1F5FE;
      --text-light: #FFF59D;
      --bg-color: #0A1A2F;
      --card-bg: #1E2A44;
      --card-hover: #2A3B5B;
      --border-color: rgba(129,212,250,0.3);
      --shadow-color: rgba(2,136,209,0.4);
      --glass-effect: linear-gradient(135deg, rgba(129,212,250,0.2), rgba(171,71,188,0.2));
      --glass-border: 1px solid rgba(129,212,250,0.15);
      --glass-shadow: 0 8px 24px rgba(2,136,209,0.3);
      --transition: all .3s cubic-bezier(.4,0,.2,1);
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
      font-family: 'Vazirmatn', 'Segoe UI', system-ui, sans-serif;
      background: var(--bg-color) var(--bg-image) center/cover fixed;
      background-blend-mode: overlay;
      color: var(--text-color);
      height: 100vh;
      overflow: hidden;
      user-select: none;
      touch-action: manipulation;
      position: relative;
    }
    body::after {
      content: '';
      position: fixed;
      inset: 0;
      background: var(--overlay-image) center/cover no-repeat;
      opacity: 0;
      animation: fadeInOut 5s ease-in-out infinite;
      z-index: -2;
    }
    @keyframes fadeInOut {
      0%, 100% { opacity: 0; }
      50% { opacity: 0.4; }
    }
    .particles {
      position: fixed;
      inset: 0;
      z-index: -1;
      overflow: hidden;
    }
    .particle {
      position: absolute;
      background: var(--primary-light);
      border-radius: 50%;
      pointer-events: none;
      animation: floatParticle linear infinite;
    }
    @keyframes floatParticle {
      0% { transform: translateY(0); opacity: 0; }
      10%, 90% { opacity: 0.6; }
      100% { transform: translateY(-100vh) translateX(20px); opacity: 0; }
    }
    #contentWindow {
      position: fixed;
      inset: 0;
      z-index: 10;
      display: none;
      overflow: hidden;
    }
    .top-bar {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 16px 20px;
      background: var(--glass-effect);
      border-bottom: var(--glass-border);
      box-shadow: var(--glass-shadow);
      -webkit-backdrop-filter: blur(12px);
      backdrop-filter: blur(12px);
      z-index: 100;
    }
    .logo {
      font-size: 1.2rem;
      font-weight: 700;
      padding: 10px 15px;
      border-radius: 10px;
      cursor: pointer;
      background: rgba(129,212,250,0.15);
      display: flex;
      align-items: center;
      gap: 10px;
      transition: var(--transition);
      border: 1px solid var(--border-color);
    }
    .logo:hover {
      background: rgba(129,212,250,0.25);
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
      background: rgba(129,212,250,0.1);
      border: 1px solid var(--border-color);
      cursor: pointer;
    }
    .menu-btn:hover {
      background: rgba(129,212,250,0.2);
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
      background: var(--card-bg);
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
      animation: slideInRight 0.5s ease-out 0.2s forwards;
    }
    .info-box:nth-child(2) {
      animation: slideInLeft 0.5s ease-out 0.4s forwards;
    }
    .info-box:nth-child(3) {
      animation: slideInRight 0.5s ease-out 0.6s forwards;
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
      font-size: 1.1rem;
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
      -webkit-backdrop-filter: blur(15px);
      backdrop-filter: blur(15px);
      border-radius: 16px;
      display: flex;
      flex-direction: column;
    }
    .main-menu, .settings-panel {
      top: -100%;
      right: 0;
      width: 100%;
      max-height: 65%;
      border-radius: 0 0 16px 16px;
    }
    .main-menu.open, .settings-panel.open {
      top: 0;
    }
    .config-select-menu, .private-shop-menu, .public-shop-menu {
      bottom: -100%;
      left: 0;
      width: 100%;
      max-height: 80%;
      border-radius: 16px 16px 0 0;
    }
    .config-select-menu.open, .private-shop-menu.open, .public-shop-menu.open {
      bottom: 0;
    }
    .modal-overlay {
      position: fixed;
      inset: 0;
      background: rgba(10,26,47,0.5);
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
    .modal-title {
      font-weight: 700;
      font-size: 1.2rem;
      color: var(--text-color);
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
      background: rgba(129,212,250,0.15);
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
    .subscription-wizard {
      display: flex;
      flex-direction: column;
      height: 100%;
      overflow: hidden;
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
      font-size: 2rem;
      font-weight: 700;
      text-align: center;
      margin: 25px 0;
      color: var(--primary-color);
      display: flex;
      justify-content: center;
      align-items: baseline;
    }
    .unit {
      font-size: 1.1rem;
      color: var(--text-light);
      margin-right: 10px;
    }
    .slider-container {
      margin: 25px 0;
    }
    .slider {
      -webkit-appearance: none;
      width: 100%;
      height: 10px;
      border-radius: 5px;
      background: rgba(129,212,250,0.2);
      outline: none;
      transition: var(--transition);
    }
    .slider:hover {
      height: 12px;
    }
    .slider::-webkit-slider-thumb {
      -webkit-appearance: none;
      width: 24px;
      height: 24px;
      border-radius: 50%;
      background: linear-gradient(135deg, var(--primary-light), var(--primary-dark));
      cursor: pointer;
      box-shadow: 0 3px 8px var(--shadow-color);
      border: 2px solid var(--text-color);
      transition: var(--transition);
    }
    .slider::-webkit-slider-thumb:hover {
      transform: scale(1.1);
    }
    .slider::-moz-range-thumb {
      width: 24px;
      height: 24px;
      border-radius: 50%;
      background: linear-gradient(135deg, var(--primary-light), var(--primary-dark));
      cursor: pointer;
      box-shadow: 0 3px 8px var(--shadow-color);
      border: 2px solid var(--text-color);
    }
    .range-info {
      display: flex;
      justify-content: space-between;
      margin-top: 20px;
      color: var(--text-light);
      font-size: 0.95rem;
    }
    .price-summary {
      background: var(--card-bg);
      border-radius: 16px;
      padding: 14px;
      margin: 20px 0;
      border: var(--glass-border);
      font-size: 0.9rem;
    }
    .price-row {
      display: flex;
      justify-content: space-between;
      margin-bottom: 10px;
      padding: 6px 0;
      color: var(--text-light);
    }
    .total-price {
      font-size: 1.1rem;
      color: var(--yellow-color);
      margin-top: 15px;
      padding-top: 15px;
      border-top: var(--glass-border);
      text-align: center;
      font-weight: 700;
    }
    .nav-buttons {
      display: flex;
      justify-content: space-between;
      margin-top: 20px;
      gap: 12px;
    }
    .nav-btn {
      padding: 12px;
      border-radius: 10px;
      font-weight: 700;
      cursor: pointer;
      border: none;
      flex: 1;
      font-size: 0.95rem;
      transition: var(--transition);
    }
    .nav-btn:hover {
      transform: translateY(-2px);
      box-shadow: 0 4px 12px var(--shadow-color);
    }
    .btn-prev {
      background: rgba(129,212,250,0.15);
      color: var(--primary-color);
      border: var(--glass-border);
    }
    .btn-next, .btn-submit {
      background: linear-gradient(135deg, var(--primary-light), var(--primary-dark));
      color: var(--text-color);
    }
    .btn-submit {
      background: linear-gradient(135deg, var(--purple-color), #7B1FA2);
      width: 100%;
    }
    .btn {
      padding: 10px 20px;
      border-radius: 10px;
      font-family: inherit;
      cursor: pointer;
      font-weight: 700;
      font-size: 0.9rem;
      transition: var(--transition);
      display: flex;
      align-items: center;
      gap: 8px;
      justify-content: center;
      border: none;
    }
    .btn-primary {
      background: linear-gradient(135deg, var(--primary-light), var(--primary-dark));
      color: var(--text-color);
      box-shadow: 0 5px 15px var(--shadow-color);
    }
    .btn-primary:hover {
      transform: translateY(-2px);
      box-shadow: 0 8px 20px var(--shadow-color);
    }
    .btn-secondary {
      background: linear-gradient(135deg, var(--yellow-color), #FBC02D);
      color: var(--bg-color);
      box-shadow: 0 5px 15px rgba(255,235,59,0.4);
    }
    .btn-secondary:hover {
      transform: translateY(-2px);
      box-shadow: 0 8px 20px rgba(255,235,59,0.5);
    }
    .btn-large {
      padding: 14px;
      font-size: 1rem;
      width: 100%;
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
      -webkit-backdrop-filter: blur(10px);
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
      background: rgba(171,71,188,0.15);
      color: var(--purple-color);
      border: 1px solid rgba(171,71,188,0.3);
    }
    .notification-info {
      background: rgba(129,212,250,0.15);
      color: var(--primary-color);
      border: 1px solid var(--border-color);
    }
    .notification-error {
      background: rgba(244,67,54,0.15);
      color: var(--red-color);
      border: 1px solid rgba(244,67,54,0.3);
    }
    .notification-message {
      font-size: 0.85rem;
      font-weight: 500;
      flex: 1;
      color: var(--text-color);
    }
    .language-switcher {
      background: rgba(129,212,250,0.1);
      border-radius: 16px;
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
      transition: var(--transition);
      border: none;
      background: transparent;
      color: var(--text-light);
    }
    .language-btn.active {
      background: linear-gradient(135deg, var(--primary-light), var(--primary-dark));
      color: var(--text-color);
      box-shadow: 0 4px 12px var(--shadow-color);
    }
    .configs-container {
      display: flex;
      gap: 12px;
      overflow-x: auto;
      padding: 15px;
      direction: rtl;
      -webkit-overflow-scrolling: touch;
      scrollbar-width: none;
      -ms-overflow-style: none;
    }
    .configs-container::-webkit-scrollbar {
      display: none;
    }
    .config-box {
      background: var(--card-bg);
      border-radius: 14px;
      padding: 14px;
      width: 170px;
      height: 190px;
      border: var(--glass-border);
      box-shadow: 0 6px 20px var(--shadow-color);
      transition: var(--transition);
      cursor: pointer;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: space-between;
      text-align: center;
      flex-shrink: 0;
      opacity: 0;
      position: relative;
    }
    .config-box:hover {
      transform: translateY(-4px);
      box-shadow: 0 10px 24px var(--shadow-color);
      border-color: var(--primary-light);
    }
    .config-logo {
      width: 50px;
      height: 50px;
      margin-bottom: 8px;
      transition: var(--transition);
      position: relative;
      z-index: 0;
    }
    .config-box:hover .config-logo {
      transform: scale(1.1);
    }
    .config-frame {
      width: 60px;
      height: 60px;
      background: url('https://biaupload.com/do.php?imgf=org-14607935dcc21.png') center/contain no-repeat;
      position: absolute;
      top: 28px;
      left: 50%;
      transform: translateX(-50%);
      z-index: 1;
    }
    .ping-result {
      font-size: 0.95rem;
      display: flex;
      align-items: center;
      gap: 6px;
      width: 100%;
      justify-content: center;
      font-weight: 600;
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
      background: rgba(244,67,54,0.15);
      color: var(--red-color);
      border: 1px solid rgba(244,67,54,0.3);
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
      box-shadow: 0 4px 12px rgba(255,235,59,0.3);
    }
    .copy-btn:hover {
      background: #FBC02D;
      transform: translateY(-2px);
      box-shadow: 0 6px 16px rgba(255,235,59,0.4);
    }
    .filter-container {
      display: flex;
      gap: 10px;
      margin-bottom: 15px;
      overflow-x: auto;
      padding: 10px;
      scrollbar-width: none;
      -ms-overflow-style: none;
    }
    .filter-container::-webkit-scrollbar {
      display: none;
    }
    .filter-btn {
      padding: 8px 16px;
      border-radius: 10px;
      background: rgba(129,212,250,0.1);
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
    @media (max-width: 768px) {
      .news-container { max-width: 90%; padding: 12px; }
      .modal-window { max-height: 80vh; }
      .modal-content { padding: 12px; }
      .floating-btn { width: 60px; height: 60px; font-size: 24px; bottom: 15px; left: 15px; }
      .value-display { font-size: 1.8rem; margin: 20px 0; }
      .nav-btn { padding: 10px; font-size: 0.9rem; }
      .loading-content { bottom: 20px; }
      .loading-messages { font-size: 1rem; height: 25px; }
      .loading-spinner { width: 40px; height: 40px; }
      .loading-frame { width: 50px; height: 50px; }
      .loading-footer { font-size: 1rem; }
      .configs-container { padding: 10px; gap: 10px; }
      .config-box { width: 140px; height: 160px; padding: 12px; }
      .config-logo { width: 45px; height: 45px; margin-bottom: 8px; }
      .config-frame { width: 50px; height: 50px; top: 24px; }
      .ping-result { font-size: 0.85rem; }
      .copy-btn { font-size: 0.85rem; padding: 8px; }
      .loading-dot { width: 8px; height: 8px; }
      .filter-btn { padding: 6px 12px; font-size: 0.8rem; }
    }
    @keyframes slideInUp {
      from { opacity: 0; transform: translateY(50px); }
      to { opacity: 1; transform: translateY(0); }
    }
    .fade-in {
      animation: fadeIn .5s ease-out;
    }
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }
  </style>
  <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@400;500;700&display=swap"/>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css"/>
</head>
<body class="theme-default">
  <div class="particles" id="particles"></div>
  <audio id="bgMusic" loop>
    <source src="https://uploadkon.ir/uploads/833c07_25shervin-nahal-online-audio-converter-com-.mp3" type="audio/mpeg"/>
  </audio>
  <div class="loading-window" id="loadingWindow">
    <div class="loading-content">
      <div class="loading-messages">
        <span>چند لحظه صبر کنید</span>
      </div>
      <div class="loading-spinner">
        <div class="loading-frame"></div>
      </div>
      <div class="loading-footer">آقای ایکسرو</div>
    </div>
  </div>
  <div id="contentWindow">
    <div class="top-bar">
      <div class="logo">
        <i class="fas fa-shield-alt"></i>
        <span>گزارش مشکل</span>
      </div>
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
              <div class="info-icon"><i class="fas fa-desktop"></i></div>
              <div class="info-text">سیستم:</div>
              <div class="info-value" id="device">--</div>
            </div>
            <div class="info-box">
              <div class="info-icon"><i class="fas fa-globe"></i></div>
              <div class="info-text">آیپی:</div>
              <div class="info-value" id="ip">--</div>
            </div>
            <div class="info-box">
              <div class="info-icon"><i class="fas fa-signal"></i></div>
              <div class="info-text">پینگ:</div>
              <div class="info-value" id="ping">-- م‌ب</div>
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
          <div class="menu-item-title">
            <i class="fas fa-cog"></i>
            <span>تنظیمات</span>
          </div>
          <div class="menu-item-desc">تغییر تنظیمات برنامه</div>
        </div>
        <div class="menu-item" id="aboutItem">
          <div class="menu-item-title">
            <i class="fas fa-info-circle"></i>
            <span>درباره ما</span>
          </div>
          <div class="menu-item-desc">اطلاعات بیشتر درباره ایکسرو</div>
        </div>
      </div>
    </div>
    <div class="modal-overlay" id="configSelectOverlay"></div>
    <div class="modal-window config-select-menu" id="configSelectMenu">
      <div class="modal-header">
        <div class="modal-title">انتخاب نوع سرویس</div>
        <div class="home-btn" id="closeConfigSelectMenu">
          <img src="https://biaupload.com/do.php?imgf=org-19fb842c16fb1.png" alt="Close">
        </div>
      </div>
      <div class="modal-content">
        <div class="menu-item" id="privateConfigItem">
          <div class="menu-item-title">
            <i class="fas fa-lock"></i>
            <span>استفاده از سرویس‌های شخصی</span>
          </div>
          <div class="menu-item-desc">میتونی با خرید یک کانفیگ شخصی داشه باشی</div>
        </div>
        <div class="menu-item" id="publicConfigItem">
          <div class="menu-item-title">
            <i class="fas fa-globe"></i>
            <span>استفاده از کانفیگ‌های عمومی</span>
          </div>
          <div class="menu-item-desc">میتونی از کانفیگ‌های رایگان استفاده کنی</div>
        </div>
      </div>
    </div>
    <div class="modal-window private-shop-menu" id="privateShopMenu">
      <div class="modal-header">
        <div class="modal-title">سرویس‌های شخصی</div>
        <div class="home-btn" id="closePrivateShopMenu">
          <img src="https://biaupload.com/do.php?imgf=org-19fb842c16fb1.png" alt="Close">
        </div>
      </div>
      <div class="modal-content">
        <div class="subscription-wizard">
          <div class="wizard-step active" id="step1">
            <div class="value-display">
              <span class="unit">گیگابایت</span>
              <span id="dataValue">3</span>
            </div>
            <div class="slider-container">
              <input type="range" min="3" max="8000" value="3" class="slider" id="dataSlider"/>
              <div class="range-info">
                <span>3 گیگابایت</span>
                <span>8000 گیگابایت</span>
              </div>
            </div>
            <div class="nav-buttons">
              <button class="nav-btn btn-prev" disabled><i class="fas fa-arrow-right"></i>قبلی</button>
              <button class="nav-btn btn-next" id="nextToStep2">بعدی<i class="fas fa-arrow-left"></i></button>
            </div>
          </div>
          <div class="wizard-step" id="step2">
            <div class="value-display">
              <span class="unit">روز</span>
              <span id="daysValue">30</span>
            </div>
            <div class="slider-container">
              <input type="range" min="7" max="365" value="30" class="slider" id="daysSlider"/>
              <div class="range-info">
                <span>7 روز</span>
                <span>365 روز</span>
              </div>
            </div>
            <div class="nav-buttons">
              <button class="nav-btn btn-prev" id="backToStep1"><i class="fas fa-arrow-right"></i>قبلی</button>
              <button class="nav-btn btn-next" id="nextToStep3">بعدی<i class="fas fa-arrow-left"></i></button>
            </div>
          </div>
          <div class="wizard-step" id="step3">
            <div class="value-display">
              <span class="unit">کاربر</span>
              <span id="usersValue">1</span>
            </div>
            <div class="slider-container">
              <input type="range" min="1" max="10" value="1" class="slider" id="usersSlider"/>
              <div class="range-info">
                <span>1 کاربر</span>
                <span>10 کاربر</span>
              </div>
            </div>
            <div class="nav-buttons">
              <button class="nav-btn btn-prev" id="backToStep2"><i class="fas fa-arrow-right"></i>قبلی</button>
              <button class="nav-btn btn-next" id="nextToStep4">بعدی<i class="fas fa-arrow-left"></i></button>
            </div>
          </div>
          <div class="wizard-step" id="step4">
            <div class="price-summary">
              <div class="price-row">
                <span>حجم انتخابی:</span>
                <span id="finalSelectedData">3 گیگابایت</span>
              </div>
              <div class="price-row">
                <span>مدت اعتبار:</span>
                <span id="finalDays">30 روز</span>
              </div>
              <div class="price-row">
                <span>تعداد کاربران:</span>
                <span id="finalUsers">1 نفر</span>
              </div>
              <div class="price-row">
                <span>قیمت سرویس:</span>
                <span id="servicePrice">5,670 تومان</span>
              </div>
              <div class="price-row">
                <span>مالیات:</span>
                <span id="taxPrice">0 تومان</span>
              </div>
              <div class="total-price">
                مبلغ کل: <span id="totalPrice">5,670 تومان</span>
              </div>
            </div>
            <div class="nav-buttons">
              <button class="nav-btn btn-prev" id="backToStep3"><i class="fas fa-arrow-right"></i>قبلی</button>
              <button class="nav-btn btn-submit" id="submitPayment">ثبت درخواست<i class="fas fa-check-circle"></i></button>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="modal-window public-shop-menu" id="publicShopMenu">
      <div class="modal-header">
        <div class="modal-title">کانفیگ‌های عمومی</div>
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
          </div>
        </div>
      </div>
    </div>
    <div class="modal-window settings-panel" id="settingsPanel">
      <div class="modal-header">
        <div class="modal-title">تنظیمات</div>
        <div class="home-btn" id="closeSettingsPanel">
          <img src="https://biaupload.com/do.php?imgf=org-19fb842c16fb1.png" alt="Close">
        </div>
      </div>
      <div class="modal-content">
        <div class="language-switcher">
          <button class="language-btn active">فارسی</button>
          <button class="language-btn">English</button>
        </div>
      </div>
    </div>
    <div class="notification" id="notification">
      <div class="notification-icon" id="notificationIcon"><i class="fas fa-check-circle"></i></div>
      <div class="notification-message" id="notificationMessage">عملیات با موفقیت انجام شد</div>
    </div>
  </div>
  <script>
    if (!window.atob || !window.btoa) {
      window.atob = function(s) {
        try { return Buffer.from(s, 'base64').toString('binary'); } catch(e) { return null; }
      };
      window.btoa = function(s) {
        try { return Buffer.from(s, 'binary').toString('base64'); } catch(e) { return null; }
      };
    }
    document.addEventListener('DOMContentLoaded', () => {
      const e = {
        contentWindow: document.getElementById('contentWindow'),
        loadingWindow: document.getElementById('loadingWindow'),
        mainMenuBtn: document.getElementById('mainMenuBtn'),
        mainMenu: document.getElementById('mainMenu'),
        mainMenuOverlay: document.getElementById('mainMenuOverlay'),
        configSelectBtn: document.getElementById('configSelectBtn'),
        configSelectMenu: document.getElementById('configSelectMenu'),
        configSelectOverlay: document.getElementById('configSelectOverlay'),
        privateConfigItem: document.getElementById('privateConfigItem'),
        publicConfigItem: document.getElementById('publicConfigItem'),
        privateShopMenu: document.getElementById('privateShopMenu'),
        publicShopMenu: document.getElementById('publicShopMenu'),
        settingsItem: document.getElementById('settingsItem'),
        settingsPanel: document.getElementById('settingsPanel'),
        dataSlider: document.getElementById('dataSlider'),
        daysSlider: document.getElementById('daysSlider'),
        usersSlider: document.getElementById('usersSlider'),
        dataValue: document.getElementById('dataValue'),
        daysValue: document.getElementById('daysValue'),
        usersValue: document.getElementById('usersValue'),
        finalSelectedData: document.getElementById('finalSelectedData'),
        finalDays: document.getElementById('finalDays'),
        finalUsers: document.getElementById('finalUsers'),
        servicePrice: document.getElementById('servicePrice'),
        taxPrice: document.getElementById('taxPrice'),
        totalPrice: document.getElementById('totalPrice'),
        notification: document.getElementById('notification'),
        notificationIcon: document.getElementById('notificationIcon'),
        notificationMessage: document.getElementById('notificationMessage'),
        bgMusic: document.getElementById('bgMusic'),
        particles: document.getElementById('particles'),
        configsContainer: document.getElementById('configsContainer'),
        filterContainer: document.getElementById('filterContainer'),
        device: document.getElementById('device'),
        ip: document.getElementById('ip'),
        ping: document.getElementById('ping')
      };
      const toggleModal = (modalId, state, overlayId, single = false) => {
        if (single) {
          Object.values(e).forEach(el => {
            if (el.classList && el.classList.contains('open')) el.classList.remove('open');
            if (el.classList && el.classList.contains('show')) el.classList.remove('show');
          });
          e[modalId].classList.add('open');
          if (overlayId) {
            e[overlayId].classList.add('show');
            e[overlayId].classList.remove('hidden');
          }
        } else {
          e[modalId].classList.toggle('open', state);
          if (overlayId) {
            e[overlayId].classList.toggle('show', state);
            e[overlayId].classList.toggle('hidden', !state);
          }
        }
        if (!Object.values(e).some(el => el.classList && el.classList.contains('open'))) {
          e.contentWindow.style.overflow = 'auto';
          e.mainMenuOverlay.classList.remove('show');
          e.mainMenuOverlay.classList.add('hidden');
          e.configSelectOverlay.classList.remove('show');
          e.configSelectOverlay.classList.add('hidden');
        } else {
          e.contentWindow.style.overflow = 'hidden';
        }
      };
      const showNotification = (message, type = 'success') => {
        e.notification.className = 'notification';
        e.notificationIcon.className = 'notification-icon';
        const icons = {
          success: '<i class="fas fa-check-circle"></i>',
          error: '<i class="fas fa-times-circle"></i>',
          info: '<i class="fas fa-info-circle"></i>'
        };
        e.notification.classList.add(`notification-${type}`);
        e.notificationIcon.innerHTML = icons[type];
        e.notificationMessage.textContent = message;
        e.notification.classList.add('show');
        setTimeout(() => e.notification.classList.remove('show'), 3000);
      };
      const createParticles = () => {
        for (let i = 0; i < 50; i++) {
          const particle = document.createElement('div');
          particle.className = 'particle';
          particle.style.width = particle.style.height = Math.random() * 5 + 2 + 'px';
          particle.style.left = Math.random() * 100 + '%';
          particle.style.top = Math.random() * 100 + '%';
          particle.style.animationDuration = (Math.random() * 10 + 5) + 's';
          particle.style.opacity = Math.random() * 0.5 + 0.2;
          e.particles.appendChild(particle);
        }
      };
      const updatePrice = () => {
        const [data, days, users] = [parseInt(e.dataSlider.value), parseInt(e.daysSlider.value), parseInt(e.usersSlider.value)];
        const [dataPrice, daysPrice, usersPrice] = [1890, 340, 4800];
        const serviceCost = data * dataPrice + days * daysPrice + users * usersPrice;
        const tax = Math.round(0.02 * serviceCost);
        const total = serviceCost + tax;
        ['dataValue', 'daysValue', 'usersValue'].forEach((id, idx) => {
          e[id].textContent = [data, days, users][idx].toLocaleString('fa-IR');
        });
        e.finalSelectedData.textContent = `${data.toLocaleString('fa-IR')} گیگابایت`;
        e.finalDays.textContent = `${days.toLocaleString('fa-IR')} روز`;
        e.finalUsers.textContent = `${users.toLocaleString('fa-IR')} نفر`;
        e.servicePrice.textContent = `${serviceCost.toLocaleString('fa-IR')} تومان`;
        e.taxPrice.textContent = `${tax.toLocaleString('fa-IR')} تومان`;
        e.totalPrice.textContent = `${total.toLocaleString('fa-IR')} تومان`;
      };
      const submitOrder = () => {
        const [data, days, users] = [parseInt(e.dataSlider.value), parseInt(e.daysSlider.value), parseInt(e.usersSlider.value)];
        const [dataPrice, daysPrice, usersPrice] = [1890, 340, 4800];
        const serviceCost = data * dataPrice + days * daysPrice + users * usersPrice;
        const tax = Math.round(0.02 * serviceCost);
        const message = `درخواست سفارش سرویس xroVPN:\nحجم: ${data.toLocaleString('fa-IR')} گیگ\nمدت: ${days.toLocaleString('fa-IR')} روز\nکاربران: ${users.toLocaleString('fa-IR')} نفر\nمالیات: ${tax.toLocaleString('fa-IR')} تومان\nمبلغ کل: ${(serviceCost + tax).toLocaleString('fa-IR')} تومان`;
        window.open(`https://t.me/u0v0n?text=${encodeURIComponent(message)}`, '_blank');
      };
      const toPersianDigits = str => str.replace(/[0-9]/g, d => '۰۱۲۳۴۵۶۷۸۹'[parseInt(d)]);
      const updateIP = () => {
        fetch('https://api.ipify.org?format=json')
          .then(res => res.json())
          .then(data => { e.ip.textContent = toPersianDigits(data.ip); })
          .catch(() => { e.ip.textContent = 'نامشخص'; });
      };
      const refreshIP = () => {
        updateIP();
        setTimeout(refreshIP, 5000);
      };
      const updatePing = () => {
        const start = performance.now();
        fetch('https://www.google.com', { method: 'HEAD', mode: 'no-cors', cache: 'no-store' })
          .then(() => {
            e.ping.textContent = toPersianDigits(Math.round(performance.now() - start).toString()) + ' م‌ب';
          })
          .catch(() => { e.ping.textContent = 'نامشخص'; });
      };
      const refreshPing = () => {
        updatePing();
        setTimeout(refreshPing, 1000);
      };
      const parseConfig = config => {
        try {
          const [, protocol, rest] = config.match(/^(hysteria2|vless|trojan|ss|vmess):\/\/(.+)/i) || [];
          if (!protocol) return null;
          if (protocol.toLowerCase() === 'vmess') {
            const data = JSON.parse(window.atob(rest.split('#')[0]));
            return data.add ? { host: data.add, protocol } : null;
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
            const data = JSON.parse(window.atob(base));
            data.ps = 'telegram ☜☞ v2xro';
            return `vmess://${window.btoa(JSON.stringify(data))}${comment.length ? '#' + comment.join('#') : ''}`;
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
        const timeout = setTimeout(() => controller.abort(), 7000);
        fetch(`https://${host}/generate_204`, {
          method: 'HEAD',
          mode: 'no-cors',
          signal: controller.signal,
          cache: 'no-store'
        })
          .then(() => {
            clearTimeout(timeout);
            resolve({ success: true, ping: Math.round(performance.now() - start) });
          })
          .catch(err => {
            clearTimeout(timeout);
            resolve({ success: false, error: err.name === 'AbortError' ? 'تایم‌اوت' : 'عدم اتصال' });
          });
      });
      const extractConfigs = async () => {
        try {
          const url = 'https://gist.githubusercontent.com/xroVPN/12a0c02781cfed451da84e9b802c0912/raw';
          const response = await fetch(url, { mode: 'cors', cache: 'no-store' });
          if (!response.ok) throw new Error(`خطا در دریافت فایل: ${response.status}`);
          const configs = (await response.text()).split('\n').filter(c => c.trim());
          if (!configs.length) {
            e.configsContainer.innerHTML = '<p class="error">متاسفانه موجود نیست</p>';
            showNotification('هیچ کانفیگی در فایل یافت نشد.', 'error');
            return;
          }
          const loading = document.createElement('div');
          loading.className = 'loading-container';
          loading.innerHTML = '<div class="loading-dots"><div class="loading-dot"></div><div class="loading-dot"></div><div class="loading-dot"></div></div>';
          e.configsContainer.innerHTML = '';
          e.configsContainer.appendChild(loading);
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
                return pingResult.success ? { config: formattedConfig, ping: pingResult.ping, protocol: parsed.protocol } : null;
              } catch (err) {
                console.error(`خطا در پردازش کانفیگ: ${err.message}`);
                return null;
              }
            }));
            validConfigs.push(...results.filter(c => c));
            renderConfigs(validConfigs, false);
          }
          loading.remove();
          if (!validConfigs.length) {
            e.configsContainer.innerHTML = '<p class="error">متاسفانه موجود نیست</p>';
            showNotification('هیچ کانفیگ معتبری یافت نشد.', 'error');
          }
        } catch (err) {
          e.configsContainer.innerHTML = `<p class="error">خطا در استخراج کانفیگ‌ها: ${err.message}</p>`;
          console.error('خطای کلی:', err);
          showNotification(`خطا در استخراج کانفیگ‌ها: ${err.message}`, 'error');
        }
      };
      const renderConfigs = (configs, clear = true) => {
        const fragment = document.createDocumentFragment();
        const activeProtocol = e.filterContainer.querySelector('.filter-btn.active')?.dataset.protocol || 'all';
        const filteredConfigs = configs.filter(c => activeProtocol === 'all' || c.protocol.toLowerCase() === activeProtocol);
        if (!filteredConfigs.length) {
          e.configsContainer.innerHTML = '<p class="error">متاسفانه موجود نیست</p>';
          return;
        }
        filteredConfigs.sort((a, b) => a.ping - b.ping).forEach(({ config, ping, protocol }) => {
          const box = document.createElement('div');
          box.className = 'config-box';
          box.dataset.protocol = protocol.toLowerCase();
          const pingClass = ping < 300 ? 'fast' : ping < 600 ? 'medium' : 'slow';
          box.innerHTML = `
            <div class="config-logo-container">
              <img src="https://biaupload.com/do.php?imgf=org-7a7eb985bb052.png" class="config-logo" alt="Config Logo">
              <div class="config-frame"></div>
            </div>
            <div class="ping-result ${pingClass}"><i class="fas fa-signal"></i> ${toPersianDigits(ping.toString())} م‌ب</div>
            <button class="copy-btn"><i class="fas fa-copy"></i> کپی</button>
          `;
          box.querySelector('.copy-btn').addEventListener('click', () => {
            if (navigator.clipboard) {
              navigator.clipboard.writeText(config)
                .then(() => showNotification('کانفیگ با موفقیت کپی شد!', 'success'))
                .catch(() => showNotification('خطا در کپی کردن کانفیگ!', 'error'));
            } else {
              const textarea = document.createElement('textarea');
              textarea.value = config;
              document.body.appendChild(textarea);
              textarea.select();
              try {
                document.execCommand('copy');
                showNotification('کانفیگ با موفقیت کپی شد!', 'success');
              } catch {
                showNotification('خطا در کپی کردن کانفیگ!', 'error');
              }
              document.body.removeChild(textarea);
            }
          });
          fragment.appendChild(box);
        });
        if (clear) e.configsContainer.innerHTML = '';
        e.configsContainer.appendChild(fragment);
        const configBoxes = e.configsContainer.querySelectorAll('.config-box');
        configBoxes.forEach((box, index) => {
          box.style.animation = `slideInUp 0.5s ease-out ${index * 0.2}s forwards`;
        });
      };
      const setupFilters = () => {
        e.filterContainer.querySelectorAll('.filter-btn').forEach(btn => {
          btn.addEventListener('click', () => {
            e.filterContainer.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
            btn.classList.add('active');
            extractConfigs();
          });
        });
      };
      e.device.textContent = /Mobile|Android|iPhone|iPad/i.test(navigator.userAgent) ? 'موبایل' : 'دسکتاپ';
      createParticles();
      updatePrice();
      refreshIP();
      refreshPing();
      setupFilters();
      setTimeout(() => {
        e.loadingWindow.classList.add('hidden');
        e.contentWindow.style.display = 'block';
        setTimeout(() => showNotification('به ایکسرو خوش آمدید! از خدمات ما لذت ببرید.', 'success'), 500);
      }, 10000);
      e.bgMusic.play().catch(() => showNotification('برای پخش موسیقی، ابتدا با صفحه تعامل کنید.', 'info'));
      ['dataSlider', 'daysSlider', 'usersSlider'].forEach(id => e[id].addEventListener('input', updatePrice));
      e.mainMenuBtn.addEventListener('click', () => toggleModal('mainMenu', true, 'mainMenuOverlay'));
      e.configSelectBtn.addEventListener('click', () => toggleModal('configSelectMenu', true, 'configSelectOverlay'));
      e.privateConfigItem.addEventListener('click', () => {
        toggleModal('configSelectMenu', false, 'configSelectOverlay');
        setTimeout(() => toggleModal('privateShopMenu', true), 300);
      });
      e.publicConfigItem.addEventListener('click', () => {
        toggleModal('configSelectMenu', false, 'configSelectOverlay');
        setTimeout(() => {
          toggleModal('publicShopMenu', true);
          extractConfigs();
        }, 300);
      });
      document.getElementById('closeMainMenu').addEventListener('click', () => toggleModal('mainMenu', false, 'mainMenuOverlay'));
      document.getElementById('closeConfigSelectMenu').addEventListener('click', () => toggleModal('configSelectMenu', false, 'configSelectOverlay'));
      document.getElementById('closePrivateShopMenu').addEventListener('click', () => toggleModal('privateShopMenu', false));
      document.getElementById('closePublicShopMenu').addEventListener('click', () => {
        toggleModal('publicShopMenu', false);
        extractConfigs();
      });
      document.getElementById('closeSettingsPanel').addEventListener('click', () => toggleModal('settingsPanel', false));
      document.getElementById('nextToStep2').addEventListener('click', () => {
        const step1 = document.getElementById('step1');
        const step2 = document.getElementById('step2');
        const prevButtons = document.querySelectorAll('.btn-prev');
        step1.classList.remove('active');
        step2.classList.add('active');
        prevButtons.forEach(btn => btn.disabled = step2.id === 'step1');
      });
      document.getElementById('nextToStep3').addEventListener('click', () => {
        const step2 = document.getElementById('step2');
        const step3 = document.getElementById('step3');
        const prevButtons = document.querySelectorAll('.btn-prev');
        step2.classList.remove('active');
        step3.classList.add('active');
        prevButtons.forEach(btn => btn.disabled = step3.id === 'step1');
      });
      document.getElementById('nextToStep4').addEventListener('click', () => {
        const step3 = document.getElementById('step3');
        const step4 = document.getElementById('step4');
        const prevButtons = document.querySelectorAll('.btn-prev');
        step3.classList.remove('active');
        step4.classList.add('active');
        prevButtons.forEach(btn => btn.disabled = step4.id === 'step1');
      });
      document.getElementById('backToStep1').addEventListener('click', () => {
        const step2 = document.getElementById('step2');
        const step1 = document.getElementById('step1');
        const prevButtons = document.querySelectorAll('.btn-prev');
        step2.classList.remove('active');
        step1.classList.add('active');
        prevButtons.forEach(btn => btn.disabled = step1.id === 'step1');
      });
      document.getElementById('backToStep2').addEventListener('click', () => {
        const step3 = document.getElementById('step3');
        const step2 = document.getElementById('step2');
        const prevButtons = document.querySelectorAll('.btn-prev');
        step3.classList.remove('active');
        step2.classList.add('active');
        prevButtons.forEach(btn => btn.disabled = step2.id === 'step1');
      });
      document.getElementById('backToStep3').addEventListener('click', () => {
        const step4 = document.getElementById('step4');
        const step3 = document.getElementById('step3');
        const prevButtons = document.querySelectorAll('.btn-prev');
        step4.classList.remove('active');
        step3.classList.add('active');
        prevButtons.forEach(btn => btn.disabled = step3.id === 'step1');
      });
      document.getElementById('submitPayment').addEventListener('click', () => {
        submitOrder();
        showNotification('درخواست شما با موفقیت ثبت شد!', 'success');
      });
      e.settingsItem.addEventListener('click', () => {
        toggleModal('mainMenu', false, 'mainMenuOverlay');
        setTimeout(() => toggleModal('settingsPanel', true), 300);
      });
    });
  </script>
</body>
</html>
