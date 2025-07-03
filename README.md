<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>xroVPN</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Vazirmatn:wght@400;500;700&display=swap');
        
        :root {
            --primary-color: #6e8efb;
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
            --transition-theme: all 0.8s cubic-bezier(0.65, 0.05, 0.36, 1);
        }
        
        .dark-mode {
            --primary-color: #7d9eff;
            --secondary-color: #5cb85c;
            --danger-color: #ff6b6b;
            --warning-color: #ffbe76;
            --text-color: #ecf0f1;
            --text-light: #bdc3c7;
            --bg-color: #2c3e50;
            --card-bg: #34495e;
            --border-color: #4a5a6a;
            --shadow-color: rgba(0,0,0,0.3);
            --overlay-color: rgba(0,0,0,0.5);
        }
        
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            transition: background-color 0.3s, color 0.3s;
        }
        
        body {
            font-family: 'Vazirmatn', sans-serif;
            background-color: var(--bg-color);
            height: 100vh;
            overflow: hidden;
            color: var(--text-color);
            -webkit-user-select: none;
            user-select: none;
            touch-action: manipulation;
            transition: var(--transition-theme);
        }
        
        .top-bar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 20px;
            background: var(--card-bg);
            border-bottom: 1px solid var(--border-color);
            box-shadow: 0 1px 3px var(--shadow-color);
            transition: var(--transition-theme);
        }
        
        .logo {
            font-size: 22px;
            font-weight: 700;
            color: var(--primary-color);
            transition: var(--transition-theme);
        }
        
        .menu-btn {
            width: 24px;
            height: 24px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            cursor: pointer;
        }
        
        .menu-line {
            width: 100%;
            height: 3px;
            background-color: var(--text-color);
            border-radius: 2px;
            transition: var(--transition-theme);
        }
        
        .content {
            height: calc(100vh - 60px);
            display: flex;
            flex-direction: column;
            padding: 20px;
            position: relative;
            overflow-y: auto;
            transition: var(--transition-theme);
        }
        
        .welcome-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            flex: 1;
            transition: opacity 0.3s;
        }
        
        .emoji-container {
            width: 120px;
            height: 120px;
            background: var(--card-bg);
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            margin-bottom: 20px;
            box-shadow: 0 4px 12px var(--shadow-color);
            border: 1px solid var(--border-color);
            transition: var(--transition-theme);
            overflow: hidden;
        }
        
        .emoji {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .creator {
            font-size: 16px;
            color: var(--text-light);
            margin-top: 10px;
            text-align: center;
            transition: var(--transition-theme);
        }
        
        .floating-btn {
            position: fixed;
            bottom: 20px;
            left: 20px;
            width: 60px;
            height: 60px;
            background: var(--primary-color);
            border-radius: 15px;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 30px;
            color: white;
            box-shadow: 0 4px 12px var(--shadow-color);
            cursor: pointer;
            z-index: 100;
            border: none;
            outline: none;
            transition: var(--transition-theme);
        }
        
        /* منوی اصلی (بزرگ) */
        .main-menu {
            position: fixed;
            top: -100%;
            right: 0;
            width: 100%;
            height: auto;
            max-height: 70%;
            background: var(--card-bg);
            z-index: 1000;
            transition: top 0.3s ease-out;
            overflow-y: auto;
            border-radius: 0 0 15px 15px;
            box-shadow: 0 5px 15px var(--shadow-color);
            transition: var(--transition-theme);
        }
        
        .main-menu.open {
            top: 0;
        }
        
        .menu-header {
            padding: 15px 20px;
            display: flex;
            justify-content: flex-end;
            border-bottom: 1px solid var(--border-color);
        }
        
        .close-btn {
            font-size: 24px;
            cursor: pointer;
            color: var(--text-color);
            transition: var(--transition-theme);
        }
        
        .menu-items {
            padding: 15px;
        }
        
        .menu-item {
            padding: 15px;
            margin-bottom: 10px;
            background: var(--bg-color);
            border-radius: 10px;
            cursor: pointer;
            transition: var(--transition-theme);
        }
        
        .menu-item-title {
            font-weight: 700;
            margin-bottom: 5px;
            color: var(--text-color);
            transition: var(--transition-theme);
        }
        
        .menu-item-desc {
            font-size: 13px;
            color: var(--text-light);
            transition: var(--transition-theme);
        }
        
        /* منوی سریع (کوچک) */
        .quick-menu {
            position: fixed;
            bottom: -50%;
            left: 0;
            width: 100%;
            height: auto;
            max-height: 60%;
            background: var(--card-bg);
            border-radius: 15px 15px 0 0;
            z-index: 1001;
            transition: bottom 0.3s ease-out;
            box-shadow: 0 -5px 15px var(--shadow-color);
            transition: var(--transition-theme);
        }
        
        .quick-menu.open {
            bottom: 0;
        }
        
        .quick-menu-items {
            padding: 15px;
        }
        
        /* منوی فروشگاه */
        .shop-menu {
            position: fixed;
            bottom: -100%;
            left: 0;
            width: 100%;
            height: 60%;
            max-height: 400px;
            background: var(--card-bg);
            border-radius: 15px 15px 0 0;
            z-index: 1002;
            transition: bottom 0.3s ease-out;
            padding: 20px;
            transition: var(--transition-theme);
        }
        
        .shop-menu.open {
            bottom: 0;
        }
        
        /* overlay */
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
        }
        
        .overlay.open {
            opacity: 1;
            visibility: visible;
        }
        
        /* پنجره فروشگاه */
        .shop-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 15px;
            padding-bottom: 10px;
            border-bottom: 1px solid var(--border-color);
        }
        
        .shop-title {
            font-weight: 700;
            color: var(--text-color);
            transition: var(--transition-theme);
        }
        
        .shop-close {
            cursor: pointer;
            font-size: 20px;
            color: var(--text-color);
            transition: var(--transition-theme);
        }
        
        .shop-content {
            height: calc(100% - 50px);
            overflow-y: auto;
        }
        
        .subscription-option {
            padding: 15px;
            margin-bottom: 10px;
            background: var(--bg-color);
            border-radius: 10px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            transition: var(--transition-theme);
        }
        
        .subscription-info {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .subscription-icon {
            font-size: 24px;
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 8px;
        }
        
        .month1 { background: linear-gradient(135deg, #ff7675, #d63031); color: white; }
        .month2 { background: linear-gradient(135deg, #74b9ff, #0984e3); color: white; }
        .month3 { background: linear-gradient(135deg, #55efc4, #00b894); color: white; }
        .month4 { background: linear-gradient(135deg, #a29bfe, #6c5ce7); color: white; }
        .month5 { background: linear-gradient(135deg, #ffeaa7, #fdcb6e); color: #2c3e50; }
        .month6 { background: linear-gradient(135deg, #fab1a0, #e17055); color: white; }
        
        .subscription-name {
            font-weight: 500;
            color: var(--text-color);
            transition: var(--transition-theme);
        }
        
        .subscription-price {
            font-weight: 700;
            color: var(--primary-color);
            font-size: 14px;
            transition: var(--transition-theme);
        }
        
        .order-btn {
            background: var(--primary-color);
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 8px;
            cursor: pointer;
            font-family: 'Vazirmatn', sans-serif;
            transition: var(--transition-theme);
        }
        
        /* پنجره راهنما */
        .help-window {
            position: fixed;
            bottom: -100%;
            left: 0;
            width: 100%;
            height: 60%;
            max-height: 500px;
            background: var(--card-bg);
            border-radius: 15px 15px 0 0;
            z-index: 1003;
            transition: bottom 0.3s ease-out;
            padding: 20px;
            display: flex;
            flex-direction: column;
            transition: var(--transition-theme);
        }
        
        .help-window.open {
            bottom: 0;
        }
        
        .help-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 15px;
            padding-bottom: 10px;
            border-bottom: 1px solid var(--border-color);
        }
        
        .help-title {
            font-weight: 700;
            color: var(--text-color);
            transition: var(--transition-theme);
        }
        
        .help-close {
            cursor: pointer;
            font-size: 20px;
            color: var(--text-color);
            transition: var(--transition-theme);
        }
        
        .help-content {
            flex: 1;
            overflow-y: auto;
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
        }
        
        .help-emoji {
            font-size: 60px;
            margin: 20px 0;
        }
        
        .help-items {
            width: 100%;
        }
        
        .help-item {
            padding: 15px;
            margin-bottom: 10px;
            background: var(--bg-color);
            border-radius: 10px;
            cursor: pointer;
            text-align: right;
            color: var(--text-color);
            transition: var(--transition-theme);
        }
        
        /* پنجره راهنمای جزئیات */
        .guide-window {
            position: fixed;
            bottom: -100%;
            left: 0;
            width: 100%;
            height: 60%;
            max-height: 500px;
            background: var(--card-bg);
            border-radius: 15px 15px 0 0;
            z-index: 1005;
            transition: bottom 0.3s ease-out;
            padding: 20px;
            display: flex;
            flex-direction: column;
            transition: var(--transition-theme);
        }
        
        .guide-window.open {
            bottom: 0;
        }
        
        .guide-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 15px;
            padding-bottom: 10px;
            border-bottom: 1px solid var(--border-color);
        }
        
        .guide-title {
            font-weight: 700;
            color: var(--text-color);
            transition: var(--transition-theme);
        }
        
        .guide-close {
            cursor: pointer;
            font-size: 20px;
            color: var(--text-color);
            transition: var(--transition-theme);
        }
        
        .guide-content {
            flex: 1;
            overflow-y: auto;
            color: var(--text-color);
            line-height: 1.6;
        }
        
        /* پنجره ساخت دفترچه تونل */
        .notebook-window {
            position: fixed;
            bottom: -100%;
            left: 0;
            width: 100%;
            height: 50%;
            max-height: 500px;
            background: var(--card-bg);
            border-radius: 15px 15px 0 0;
            z-index: 1004;
            transition: bottom 0.3s ease-out;
            padding: 20px;
            display: flex;
            flex-direction: column;
            transition: var(--transition-theme);
        }
        
        .notebook-window.open {
            bottom: 0;
        }
        
        .notebook-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 15px;
            padding-bottom: 10px;
            border-bottom: 1px solid var(--border-color);
        }
        
        .notebook-title {
            font-weight: 700;
            color: var(--text-color);
            transition: var(--transition-theme);
        }
        
        .notebook-close {
            cursor: pointer;
            font-size: 20px;
            color: var(--text-color);
            transition: var(--transition-theme);
        }
        
        .notebook-content {
            flex: 1;
            overflow-y: auto;
            display: flex;
            flex-direction: column;
        }
        
        .notebook-step {
            display: none;
            flex-direction: column;
            gap: 15px;
        }
        
        .notebook-step.active {
            display: flex;
        }
        
        .input-group {
            display: flex;
            flex-direction: column;
            gap: 5px;
        }
        
        .input-label {
            font-size: 14px;
            color: var(--text-light);
            transition: var(--transition-theme);
        }
        
        .input-field {
            padding: 12px 15px;
            border: 1px solid var(--border-color);
            border-radius: 8px;
            font-family: 'Vazirmatn', sans-serif;
            background: var(--bg-color);
            color: var(--text-color);
            transition: var(--transition-theme);
        }
        
        textarea.input-field {
            resize: none;
        }
        
        .duration-options {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 10px;
            margin-top: 10px;
        }
        
        .duration-option {
            padding: 15px;
            background: var(--bg-color);
            border-radius: 8px;
            text-align: center;
            cursor: pointer;
            transition: all 0.2s;
            color: var(--text-color);
            transition: var(--transition-theme);
        }
        
        .duration-option:hover {
            background: var(--border-color);
        }
        
        .duration-option.selected {
            background: var(--primary-color);
            color: white;
        }
        
        .action-buttons {
            display: flex;
            justify-content: space-between;
            margin-top: 20px;
        }
        
        .btn {
            padding: 12px 20px;
            border: none;
            border-radius: 8px;
            font-family: 'Vazirmatn', sans-serif;
            cursor: pointer;
            font-weight: 500;
            transition: var(--transition-theme);
        }
        
        .btn-next {
            background: var(--primary-color);
            color: white;
        }
        
        .btn-prev {
            background: var(--bg-color);
            color: var(--text-color);
        }
        
        .btn-submit {
            background: var(--secondary-color);
            color: white;
            width: 100%;
        }
        
        /* کارت نمایش دفترچه */
        .notebook-card {
            width: 100%;
            background: var(--card-bg);
            border-radius: 10px;
            padding: 15px;
            box-shadow: 0 4px 12px var(--shadow-color);
            margin-bottom: 15px;
            position: relative;
            transition: all 0.3s;
            transition: var(--transition-theme);
        }
        
        .notebook-card.expanded {
            padding-bottom: 30px;
        }
        
        .notebook-card-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
        }
        
        .notebook-card-title {
            font-weight: 700;
            color: var(--text-color);
            transition: var(--transition-theme);
        }
        
        .edit-btn {
            color: var(--primary-color);
            cursor: pointer;
            transition: var(--transition-theme);
        }
        
        .notebook-card-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 10px;
        }
        
        .notebook-info {
            display: flex;
            flex-direction: column;
        }
        
        .notebook-label {
            color: var(--text-light);
            font-size: 12px;
            margin-bottom: 3px;
            transition: var(--transition-theme);
        }
        
        .notebook-value {
            font-size: 14px;
            font-weight: 500;
            color: var(--text-color);
            transition: var(--transition-theme);
        }
        
        .copy-code {
            display: flex;
            align-items: center;
            gap: 5px;
            cursor: pointer;
        }
        
        .copy-icon {
            font-size: 14px;
            color: var(--primary-color);
        }
        
        .notebook-index {
            position: absolute;
            left: 10px;
            top: 10px;
            background: var(--primary-color);
            color: white;
            width: 25px;
            height: 25px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 12px;
            transition: var(--transition-theme);
        }
        
        /* بخش توضیحات و دکمه‌های کارت */
        .notebook-details {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.3s ease-out;
            margin-top: 10px;
            border-top: 1px solid var(--border-color);
            padding-top: 10px;
        }
        
        .notebook-card.expanded .notebook-details {
            max-height: 300px;
        }
        
        .notebook-actions {
            display: flex;
            justify-content: space-between;
            margin-top: 15px;
            padding-top: 10px;
            border-top: 1px solid var(--border-color);
        }
        
        .action-btn {
            padding: 8px 15px;
            border-radius: 8px;
            font-size: 14px;
            cursor: pointer;
            border: none;
            font-family: 'Vazirmatn', sans-serif;
            display: flex;
            align-items: center;
            gap: 5px;
            transition: var(--transition-theme);
        }
        
        .edit-action {
            background-color: var(--warning-color);
            color: white;
        }
        
        .delete-action {
            background-color: var(--danger-color);
            color: white;
        }
        
        /* پنجره گزارش فعالیت */
        .report-window {
            position: fixed;
            top: -100%;
            left: 0;
            width: 100%;
            height: 60%;
            max-height: 500px;
            background: var(--card-bg);
            border-radius: 0 0 15px 15px;
            z-index: 1006;
            transition: top 0.3s ease-out;
            padding: 20px;
            display: flex;
            flex-direction: column;
            transition: var(--transition-theme);
        }
        
        .report-window.open {
            top: 0;
        }
        
        .report-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 15px;
            padding-bottom: 10px;
            border-bottom: 1px solid var(--border-color);
        }
        
        .report-title {
            font-weight: 700;
            color: var(--text-color);
            transition: var(--transition-theme);
        }
        
        .report-close {
            cursor: pointer;
            font-size: 20px;
            color: var(--text-color);
            transition: var(--transition-theme);
        }
        
        .report-content {
            flex: 1;
            overflow-y: auto;
        }
        
        .report-item {
            padding: 15px;
            margin-bottom: 10px;
            background: var(--bg-color);
            border-radius: 10px;
            transition: var(--transition-theme);
        }
        
        .report-item-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 5px;
        }
        
        .report-item-title {
            font-weight: 500;
            color: var(--text-color);
            transition: var(--transition-theme);
        }
        
        .report-item-date {
            font-size: 12px;
            color: var(--text-light);
            transition: var(--transition-theme);
        }
        
        .report-item-desc {
            font-size: 14px;
            color: var(--text-color);
            transition: var(--transition-theme);
        }
        
        /* پنجره بکاپ */
        .backup-window {
            position: fixed;
            top: -100%;
            left: 0;
            width: 100%;
            height: 60%;
            max-height: 500px;
            background: var(--card-bg);
            border-radius: 0 0 15px 15px;
            z-index: 1007;
            transition: top 0.3s ease-out;
            padding: 20px;
            display: flex;
            flex-direction: column;
            transition: var(--transition-theme);
        }
        
        .backup-window.open {
            top: 0;
        }
        
        .backup-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 15px;
            padding-bottom: 10px;
            border-bottom: 1px solid var(--border-color);
        }
        
        .backup-title {
            font-weight: 700;
            color: var(--text-color);
            transition: var(--transition-theme);
        }
        
        .backup-close {
            cursor: pointer;
            font-size: 20px;
            color: var(--text-color);
            transition: var(--transition-theme);
        }
        
        .backup-content {
            flex: 1;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            gap: 20px;
        }
        
        .backup-btn {
            width: 100%;
            padding: 15px;
            border-radius: 10px;
            background: var(--primary-color);
            color: white;
            border: none;
            font-family: 'Vazirmatn', sans-serif;
            font-size: 16px;
            cursor: pointer;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 10px;
            transition: var(--transition-theme);
        }
        
        .backup-btn i {
            font-size: 20px;
        }
        
        .restore-btn {
            width: 100%;
            padding: 15px;
            border-radius: 10px;
            background: var(--secondary-color);
            color: white;
            border: none;
            font-family: 'Vazirmatn', sans-serif;
            font-size: 16px;
            cursor: pointer;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 10px;
            transition: var(--transition-theme);
        }
        
        .restore-btn i {
            font-size: 20px;
        }
        
        /* پنجره تایید حذف */
        .confirm-window {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%) scale(0.9);
            width: 90%;
            max-width: 350px;
            background: var(--card-bg);
            border-radius: 15px;
            padding: 20px;
            z-index: 1008;
            opacity: 0;
            visibility: hidden;
            transition: all 0.3s;
            box-shadow: 0 5px 15px var(--shadow-color);
            text-align: center;
        }
        
        .confirm-window.open {
            transform: translate(-50%, -50%) scale(1);
            opacity: 1;
            visibility: visible;
        }
        
        .confirm-title {
            font-weight: 700;
            margin-bottom: 15px;
            color: var(--text-color);
        }
        
        .confirm-message {
            margin-bottom: 20px;
            color: var(--text-light);
        }
        
        .confirm-buttons {
            display: flex;
            justify-content: center;
            gap: 15px;
        }
        
        .confirm-btn {
            padding: 10px 20px;
            border-radius: 8px;
            font-family: 'Vazirmatn', sans-serif;
            cursor: pointer;
            border: none;
            font-weight: 500;
        }
        
        .confirm-yes {
            background: var(--danger-color);
            color: white;
        }
        
        .confirm-no {
            background: var(--bg-color);
            color: var(--text-color);
        }
        
        /* نوتیفیکیشن */
        .notification {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: var(--card-bg);
            border-radius: 10px;
            padding: 15px 20px;
            box-shadow: 0 4px 12px var(--shadow-color);
            z-index: 1100;
            transform: translateY(100px);
            opacity: 0;
            transition: all 0.3s ease-out;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .notification.show {
            transform: translateY(0);
            opacity: 1;
        }
        
        .notification-icon {
            font-size: 20px;
        }
        
        .notification-success {
            color: var(--secondary-color);
        }
        
        .notification-info {
            color: var(--primary-color);
        }
        
        .notification-error {
            color: var(--danger-color);
        }
        
        .notification-message {
            font-size: 14px;
        }
        
        .hidden {
            opacity: 0;
            pointer-events: none;
        }
        
        /* انیمیشن‌ها */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        @keyframes slideIn {
            from { transform: translateY(-20px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }
        
        .fade-in {
            animation: fadeIn 0.3s ease-out;
        }
        
        .slide-in {
            animation: slideIn 0.3s ease-out;
        }
    </style>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
</head>
<body>
    <div class="top-bar">
        <div class="logo">xroVPN</div>
        <div class="menu-btn" id="mainMenuBtn">
            <div class="menu-line"></div>
            <div class="menu-line"></div>
            <div class="menu-line"></div>
        </div>
    </div>
    
    <div class="content">
        <div class="welcome-container" id="welcomeContainer">
            <div class="emoji-container">
                <img src="https://uploadkon.ir/uploads/78d303_25InShot-۲۰۲۵۰۷۰۳-۰۹۲۶۱۸۶۷۵.png" class="emoji" alt="Logo">
            </div>
            <div class="creator" id="todayDate">امروز درحال انجام سفارشات هستیم</div>
        </div>
        
        <!-- لیست دفترچه‌های تونل -->
        <div id="notebooksList"></div>
    </div>
    
    <button class="floating-btn" id="quickMenuBtn">
        <i class="fas fa-plus"></i>
    </button>
    
    <!-- منوی اصلی (بزرگ) -->
    <div class="main-menu" id="mainMenu">
        <div class="menu-header">
            <div class="close-btn" id="closeMainMenu">×</div>
        </div>
        <div class="menu-items">
            <div class="menu-item" id="reportItem">
                <div class="menu-item-title">گزارش فعالیت</div>
                <div class="menu-item-desc">می‌تونید ببینید چه کارهایی انجام دادید</div>
            </div>
            <div class="menu-item" id="backupItem">
                <div class="menu-item-title">بکاپ تونل‌ها</div>
                <div class="menu-item-desc">ذخیره و بازیابی اطلاعات</div>
            </div>
            <div class="menu-item" id="themeItem">
                <div class="menu-item-title">حالت روز شب</div>
                <div class="menu-item-desc">می‌تونید رنگ سایت رو تغییر بدید</div>
            </div>
        </div>
    </div>
    
    <!-- منوی سریع (کوچک) -->
    <div class="quick-menu" id="quickMenu">
        <div class="quick-menu-items">
            <div class="menu-item" id="quickShopItem">
                <div class="menu-item-title">فروشگاه خرید تونل</div>
                <div class="menu-item-desc">می‌تونید اشتراک وایرکارد خریداری کنید</div>
            </div>
            <div class="menu-item" id="quickNotebookItem">
                <div class="menu-item-title">دفترچه تونل جدید</div>
                <div class="menu-item-desc">میتونی اشتراک هات مدیریت کنی</div>
            </div>
            <div class="menu-item" id="quickHelpItem">
                <div class="menu-item-title">راهنما استفاده از سایت</div>
                <div class="menu-item-desc">می‌تونید صفر تا صد سایت رو یاد بگیرید</div>
            </div>
        </div>
    </div>
    
    <!-- پنجره فروشگاه -->
    <div class="shop-menu" id="shopWindow">
        <div class="shop-header">
            <div class="shop-title">فروشگاه خرید تونل</div>
            <div class="shop-close" id="closeShop">×</div>
        </div>
        <div class="shop-content">
            <div class="subscription-option">
                <div class="subscription-info">
                    <div class="subscription-icon month1"><i class="fas fa-crown"></i></div>
                    <div>
                        <div class="subscription-name">اشتراک 1 ماهه</div>
                        <div class="subscription-price">نامحدود - ۲۶۴.۰۰۰ تومان</div>
                    </div>
                </div>
                <button class="order-btn" onclick="orderSubscription(1)">سفارش اشتراک
 </button>
            </div>
            <div class="subscription-option">
                <div class="subscription-info">
                    <div class="subscription-icon month2"><i class="fas fa-medal"></i></div>
                    <div>
                        <div class="subscription-name">اشتراک 2 ماهه</div>
                        <div class="subscription-price">نامحدود - ۴۸۹.۰۰۰ تومان</div>
                    </div>
                </div>
                <button class="order-btn" onclick="orderSubscription(2)">سفارش اشتراک</button>
            </div>
            <div class="subscription-option">
                <div class="subscription-info">
                    <div class="subscription-icon month3"><i class="fas fa-gem"></i></div>
                    <div>
                        <div class="subscription-name">اشتراک 3 ماهه</div>
                        <div class="subscription-price">نامحدود - ۶۹۹.۰۰۰ تومان</div>
                    </div>
                </div>
                <button class="order-btn" onclick="orderSubscription(3)">سفارش اشتراک</button>
            </div>
            <div class="subscription-option">
                <div class="subscription-info">
                    <div class="subscription-icon month4"><i class="fas fa-trophy"></i></div>
                    <div>
                        <div class="subscription-name">اشتراک 4 ماهه</div>
                        <div class="subscription-price">نامحدود - ۸۹۹.۰۰۰ تومان</div>
                    </div>
                </div>
                <button class="order-btn" onclick="orderSubscription(4)">سفارش اشتراک</button>
            </div>
            <div class="subscription-option">
                <div class="subscription-info">
                    <div class="subscription-icon month5"><i class="fas fa-star"></i></div>
                    <div>
                        <div class="subscription-name">اشتراک 5 ماهه</div>
                        <div class="subscription-price">نامحدود - ۱.۰۹۹.۰۰۰ تومان</div>
                    </div>
                </div>
                <button class="order-btn" onclick="orderSubscription(5)">سفارش اشتراک</button>
            </div>
            <div class="subscription-option">
                <div class="subscription-info">
                    <div class="subscription-icon month6"><i class="fas fa-award"></i></div>
                    <div>
                        <div class="subscription-name">اشتراک 6 ماهه</div>
                        <div class="subscription-price">نامحدود - ۱.۲۰.۰۰۰ تومان</div>
                    </div>
                </div>
                <button class="order-btn" onclick="orderSubscription(6)">سفارش اشتراک</button>
            </div>
        </div>
    </div>
    
    <!-- پنجره راهنما -->
    <div class="help-window" id="helpWindow">
        <div class="help-header">
            <div class="help-title">راهنما استفاده از سایت</div>
            <div class="help-close" id="closeHelp">×</div>
        </div>
        <div class="help-content">
            <div class="help-emoji">🤖</div>
            <div class="help-items">
                <div class="help-item" id="helpShop">راهنمایی فروشگاه</div>
                <div class="help-item" id="helpSettings">راهنمای تنظیمات</div>
                <div class="help-item" id="helpNotebook">راهنمای ساخت دفترچه تونل</div>
                <div class="help-item" id="helpReport">راهنمای گزارش فعالیت</div>
                <div class="help-item" id="helpBackup">راهنمای بکاپ گیری تونل</div>
                <div class="help-item" id="helpInvite">راهنمای دعوت از دوستان</div>
            </div>
        </div>
    </div>
    
    <!-- پنجره راهنمای جزئیات -->
    <div class="guide-window" id="guideWindow">
        <div class="guide-header">
            <div class="guide-title" id="guideTitle">راهنمای استفاده</div>
            <div class="guide-close" id="closeGuide">×</div>
        </div>
        <div class="guide-content" id="guideContent">
            <!-- محتوای راهنما به صورت دینامیک پر می‌شود -->
        </div>
    </div>
    
    <!-- پنجره ساخت دفترچه تونل -->
    <div class="notebook-window" id="notebookWindow">
        <div class="notebook-header">
            <div class="notebook-title" id="notebookFormTitle">دفترچه تونل جدید</div>
            <div class="notebook-close" id="closeNotebook">×</div>
        </div>
        <div class="notebook-content">
            <!-- مرحله 1: وارد کردن کد اشتراک -->
            <div class="notebook-step active" id="step1">
                <div class="input-group">
                    <label class="input-label">کد اشتراک خود را وارد کنید</label>
                    <input type="text" class="input-field" id="subscriptionCode" placeholder="مثال: XRO_u7272u">
                </div>
                <div class="action-buttons">
                    <button class="btn btn-next" id="nextToStep2">بعدی</button>
                </div>
            </div>
            
            <!-- مرحله 2: انتخاب مدت زمان -->
            <div class="notebook-step" id="step2">
                <div class="input-group">
                    <label class="input-label">مدت زمان اشتراک را انتخاب کنید</label>
                    <div class="duration-options">
                        <div class="duration-option" data-months="1">1 ماهه</div>
                        <div class="duration-option" data-months="2">2 ماهه</div>
                        <div class="duration-option" data-months="3">3 ماهه</div>
                        <div class="duration-option" data-months="4">4 ماهه</div>
                        <div class="duration-option" data-months="5">5 ماهه</div>
                        <div class="duration-option" data-months="6">6 ماهه</div>
                    </div>
                </div>
                <div class="action-buttons">
                    <button class="btn btn-prev" id="backToStep1">قبلی</button>
                    <button class="btn btn-next" id="nextToStep3">بعدی</button>
                </div>
            </div>
            
            <!-- مرحله 3: اطلاعات کاربر -->
            <div class="notebook-step" id="step3">
                <div class="input-group">
                    <label class="input-label">نام کامل شما</label>
                    <input type="text" class="input-field" id="username" placeholder="نام و نام خانوادگی">
                </div>
                <div class="input-group">
                    <label class="input-label">آیدی تلگرام یا شماره تماس</label>
                    <input type="text" class="input-field" id="userContact" placeholder="@username یا 09123456789">
                </div>
                <div class="input-group">
                    <label class="input-label">توضیحات (اختیاری)</label>
                    <textarea class="input-field" id="userNotes" rows="3" placeholder="توضیحات اضافی..."></textarea>
                </div>
                <div class="action-buttons">
                    <button class="btn btn-prev" id="backToStep2">قبلی</button>
                    <button class="btn btn-submit" id="submitNotebook">ثبت درخواست</button>
                </div>
            </div>
        </div>
    </div>
    
    <!-- پنجره گزارش فعالیت -->
    <div class="report-window" id="reportWindow">
        <div class="report-header">
            <div class="report-title">گزارش فعالیت</div>
            <div class="report-close" id="closeReport">×</div>
        </div>
        <div class="report-content" id="reportContent">
            <!-- محتوای گزارش فعالیت به صورت دینامیک تولید می‌شود -->
        </div>
    </div>
    
    <!-- پنجره بکاپ -->
    <div class="backup-window" id="backupWindow">
        <div class="backup-header">
            <div class="backup-title">مدیریت بکاپ تونل‌ها</div>
            <div class="backup-close" id="closeBackup">×</div>
        </div>
        <div class="backup-content">
            <button class="backup-btn" id="exportBackup">
                <i class="fas fa-file-export"></i>
                گرفتن بکاپ از تونل‌ها
            </button>
            <button class="restore-btn" id="importBackup">
                <i class="fas fa-file-import"></i>
                بازیابی تونل‌ها از فایل
            </button>
            <input type="file" id="backupFileInput" accept=".json" style="display: none;">
        </div>
    </div>
    
    <!-- پنجره تایید حذف -->
    <div class="confirm-window" id="confirmWindow">
        <div class="confirm-title">تایید حذف</div>
        <div class="confirm-message">آیا از حذف این تونل مطمئن هستید؟</div>
        <div class="confirm-buttons">
            <button class="confirm-btn confirm-no" id="confirmNo">خیر</button>
            <button class="confirm-btn confirm-yes" id="confirmYes">بله</button>
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
        // عناصر DOM
        const mainMenuBtn = document.getElementById('mainMenuBtn');
        const quickMenuBtn = document.getElementById('quickMenuBtn');
        const mainMenu = document.getElementById('mainMenu');
        const quickMenu = document.getElementById('quickMenu');
        const shopWindow = document.getElementById('shopWindow');
        const helpWindow = document.getElementById('helpWindow');
        const guideWindow = document.getElementById('guideWindow');
        const notebookWindow = document.getElementById('notebookWindow');
        const reportWindow = document.getElementById('reportWindow');
        const backupWindow = document.getElementById('backupWindow');
        const confirmWindow = document.getElementById('confirmWindow');
        const notification = document.getElementById('notification');
        const overlay = document.getElementById('overlay');
        const closeMainMenu = document.getElementById('closeMainMenu');
        const closeShop = document.getElementById('closeShop');
        const closeHelp = document.getElementById('closeHelp');
        const closeGuide = document.getElementById('closeGuide');
        const closeNotebook = document.getElementById('closeNotebook');
        const closeReport = document.getElementById('closeReport');
        const closeBackup = document.getElementById('closeBackup');
        const confirmNo = document.getElementById('confirmNo');
        const confirmYes = document.getElementById('confirmYes');
        const todayDate = document.getElementById('todayDate');
        
        // آیتم‌های منو
        const reportItem = document.getElementById('reportItem');
        const backupItem = document.getElementById('backupItem');
        const themeItem = document.getElementById('themeItem');
        const quickShopItem = document.getElementById('quickShopItem');
        const quickNotebookItem = document.getElementById('quickNotebookItem');
        const quickHelpItem = document.getElementById('quickHelpItem');
        
        // آیتم‌های راهنما
        const helpShop = document.getElementById('helpShop');
        const helpSettings = document.getElementById('helpSettings');
        const helpNotebook = document.getElementById('helpNotebook');
        const helpReport = document.getElementById('helpReport');
        const helpBackup = document.getElementById('helpBackup');
        const helpInvite = document.getElementById('helpInvite');
        
        // مراحل ساخت دفترچه
        const step1 = document.getElementById('step1');
        const step2 = document.getElementById('step2');
        const step3 = document.getElementById('step3');
        const nextToStep2 = document.getElementById('nextToStep2');
        const nextToStep3 = document.getElementById('nextToStep3');
        const backToStep1 = document.getElementById('backToStep1');
        const backToStep2 = document.getElementById('backToStep2');
        const submitNotebook = document.getElementById('submitNotebook');
        
        // فیلدهای فرم
        const subscriptionCode = document.getElementById('subscriptionCode');
        const durationOptions = document.querySelectorAll('.duration-option');
        const username = document.getElementById('username');
        const userContact = document.getElementById('userContact');
        const userNotes = document.getElementById('userNotes');
        
        // عناصر صفحه اصلی
        const welcomeContainer = document.getElementById('welcomeContainer');
        const notebooksList = document.getElementById('notebooksList');
        
        // عناصر بکاپ
        const exportBackup = document.getElementById('exportBackup');
        const importBackup = document.getElementById('importBackup');
        const backupFileInput = document.getElementById('backupFileInput');
        
        // عناصر راهنما
        const guideTitle = document.getElementById('guideTitle');
        const guideContent = document.getElementById('guideContent');
        
        // نوتیفیکیشن
        const notificationIcon = document.getElementById('notificationIcon');
        const notificationMessage = document.getElementById('notificationMessage');
        
        // متغیرهای حالت
        let currentStep = 1;
        let selectedDuration = 0;
        let notebooks = JSON.parse(localStorage.getItem('notebooks')) || [];
        let currentEditingNotebook = null;
        let notebookToDelete = null;
        let activityLogs = JSON.parse(localStorage.getItem('activityLogs')) || [
            {
                title: 'ورود به سیستم',
                date: 'امروز - 14:30',
                desc: 'شما با موفقیت وارد حساب کاربری خود شدید.'
            },
            {
                title: 'ایجاد تونل جدید',
                date: 'دیروز - 09:45',
                desc: 'تونل جدید با کد اشتراک XRO_u7272u ایجاد شد.'
            },
            {
                title: 'ویرایش اطلاعات',
                date: 'سه شنبه - 16:20',
                desc: 'اطلاعات تماس تونل XRO_u7272u به روزرسانی شد.'
            },
            {
                title: 'خروج از سیستم',
                date: 'دوشنبه - 22:10',
                desc: 'شما با موفقیت از حساب کاربری خود خارج شدید.'
            }
        ];
        let darkMode = localStorage.getItem('darkMode') === 'true';

        // نمایش تاریخ امروز
        function showTodayDate() {
            const days = ['یکشنبه', 'دوشنبه', 'سه شنبه', 'چهارشنبه', 'پنجشنبه', 'جمعه', 'شنبه'];
            const today = new Date();
            const dayName = days[today.getDay()];
            todayDate.textContent = `${dayName}... درحال انجام سفارشات هستیم`;
        }

        // اعمال حالت شب/روز
        function applyTheme() {
            if (darkMode) {
                document.body.classList.add('dark-mode');
                showNotification('حالت شب فعال شد', 'info');
            } else {
                document.body.classList.remove('dark-mode');
                showNotification('حالت روز فعال شد', 'info');
            }
        }

        // تغییر حالت شب/روز
        function toggleTheme() {
            darkMode = !darkMode;
            localStorage.setItem('darkMode', darkMode);
            applyTheme();
            
            addActivityLog(
                'تغییر تم',
                darkMode ? 'حالت شب فعال شد' : 'حالت روز فعال شد'
            );
        }

        // نمایش نوتیفیکیشن
        function showNotification(message, type) {
            notification.className = 'notification';
            notificationIcon.className = 'notification-icon';
            
            notificationMessage.textContent = message;
            
            if (type === 'success') {
                notificationIcon.classList.add('notification-success');
                notificationIcon.innerHTML = '<i class="fas fa-check-circle"></i>';
            } else if (type === 'info') {
                notificationIcon.classList.add('notification-info');
                notificationIcon.innerHTML = '<i class="fas fa-info-circle"></i>';
            } else if (type === 'error') {
                notificationIcon.classList.add('notification-error');
                notificationIcon.innerHTML = '<i class="fas fa-exclamation-circle"></i>';
            }
            
            notification.classList.add('show');
            
            setTimeout(() => {
                notification.classList.remove('show');
            }, 3000);
        }

        // باز کردن منوی اصلی
        function openMainMenu() {
            mainMenu.classList.add('open');
            overlay.classList.add('open');
            document.body.style.overflow = 'hidden';
        }
        
        // باز کردن منوی سریع
        function openQuickMenu() {
            quickMenu.classList.add('open');
            overlay.classList.add('open');
            document.body.style.overflow = 'hidden';
        }
        
        // باز کردن پنجره فروشگاه
        function openShopWindow() {
            shopWindow.classList.add('open');
            overlay.classList.add('open');
            document.body.style.overflow = 'hidden';
        }
        
        // باز کردن پنجره راهنما
        function openHelpWindow() {
            helpWindow.classList.add('open');
            overlay.classList.add('open');
            document.body.style.overflow = 'hidden';
        }
        
        // باز کردن پنجره راهنمای جزئیات
        function openGuideWindow(title, content) {
            guideTitle.textContent = title;
            guideContent.innerHTML = content;
            guideWindow.classList.add('open');
            overlay.classList.add('open');
            document.body.style.overflow = 'hidden';
        }
        
        // باز کردن پنجره ساخت دفترچه
        function openNotebookWindow(notebook = null) {
            notebookWindow.classList.add('open');
            overlay.classList.add('open');
            document.body.style.overflow = 'hidden';
            
            if (notebook) {
                // حالت ویرایش
                document.getElementById('notebookFormTitle').textContent = 'ویرایش دفترچه تونل';
                subscriptionCode.value = notebook.subscriptionCode;
                username.value = notebook.username;
                userContact.value = notebook.userContact;
                userNotes.value = notebook.userNotes || '';
                selectedDuration = notebook.duration;
                
                // انتخاب مدت زمان در حالت ویرایش
                document.querySelectorAll('.duration-option').forEach(option => {
                    option.classList.remove('selected');
                    if (parseInt(option.dataset.months) === notebook.duration) {
                        option.classList.add('selected');
                    }
                });
                
                // مخفی کردن مراحل 1 و 2
                step1.classList.remove('active');
                step2.classList.remove('active');
                step3.classList.add('active');
                currentStep = 3;
                
                // تغییر دکمه ثبت به بروزرسانی
                submitNotebook.textContent = 'بروزرسانی اطلاعات';
                submitNotebook.onclick = function() {
                    updateNotebook(notebook.id);
                };
            } else {
                // حالت ایجاد جدید
                document.getElementById('notebookFormTitle').textContent = 'دفترچه تونل جدید';
                resetNotebookForm();
                submitNotebook.textContent = 'ثبت درخواست';
                submitNotebook.onclick = saveNotebook;
            }
        }
        
        // باز کردن پنجره گزارش فعالیت
        function openReportWindow() {
            reportWindow.classList.add('open');
            overlay.classList.add('open');
            document.body.style.overflow = 'hidden';
        }
        
        // باز کردن پنجره بکاپ
        function openBackupWindow() {
            backupWindow.classList.add('open');
            overlay.classList.add('open');
            document.body.style.overflow = 'hidden';
        }
        
        // باز کردن پنجره تایید حذف
        function openConfirmWindow(notebookId) {
            notebookToDelete = notebookId;
            confirmWindow.classList.add('open');
            overlay.classList.add('open');
        }
        
        // بستن همه پنجره‌ها
        function closeAllWindows() {
            mainMenu.classList.remove('open');
            quickMenu.classList.remove('open');
            shopWindow.classList.remove('open');
            helpWindow.classList.remove('open');
            guideWindow.classList.remove('open');
            notebookWindow.classList.remove('open');
            reportWindow.classList.remove('open');
            backupWindow.classList.remove('open');
            confirmWindow.classList.remove('open');
            overlay.classList.remove('open');
            document.body.style.overflow = 'auto';
        }
        
        // ریست فرم ساخت دفترچه
        function resetNotebookForm() {
            currentStep = 1;
            selectedDuration = 0;
            subscriptionCode.value = '';
            username.value = '';
            userContact.value = '';
            userNotes.value = '';
            
            step1.classList.add('active');
            step2.classList.remove('active');
            step3.classList.remove('active');
            
            durationOptions.forEach(option => {
                option.classList.remove('selected');
            });
        }
        
        // تغییر مرحله ساخت دفترچه
        function goToStep(step) {
            // اعتبارسنجی مرحله فعلی قبل از رفتن به مرحله بعد
            if (currentStep === 1 && step === 2) {
                if (!subscriptionCode.value) {
                    showNotification('لطفا کد اشتراک را وارد کنید', 'error');
                    return false;
                }
                
                if (!isValidSubscriptionCode(subscriptionCode.value)) {
                    showNotification('فرمت کد اشتراک نامعتبر است (مثال: XRO_u7272u)', 'error');
                    return false;
                }
            } else if (currentStep === 2 && step === 3) {
                if (selectedDuration === 0) {
                    showNotification('لطفا مدت زمان اشتراک را انتخاب کنید', 'error');
                    return false;
                }
            }
            
            // مخفی کردن تمام مراحل
            step1.classList.remove('active');
            step2.classList.remove('active');
            step3.classList.remove('active');
            
            // نمایش مرحله مورد نظر
            if (step === 1) {
                step1.classList.add('active');
            } else if (step === 2) {
                step2.classList.add('active');
            } else if (step === 3) {
                step3.classList.add('active');
            }
            
            currentStep = step;
            return true;
        }
        
        // اعتبارسنجی کد اشتراک
        function isValidSubscriptionCode(code) {
            const codeRegex = /^XRO_[a-zA-Z0-9]{6}$/;
            return codeRegex.test(code);
        }
        
        // اعتبارسنجی اطلاعات تماس
        function isValidContact(contact) {
            // بررسی آیدی تلگرام (شروع با @ و حداقل 5 کاراکتر)
            if (contact.startsWith('@') && contact.length >= 5) return true;
            
            // بررسی شماره تماس (11 رقم و شروع با 09)
            const phoneRegex = /^09\d{9}$/;
            if (phoneRegex.test(contact)) return true;
            
            return false;
        }
        
        // ثبت دفترچه تونل
        function saveNotebook() {
            if (!username.value || !userContact.value) {
                showNotification('لطفا اطلاعات کاربر را کامل کنید', 'error');
                return;
            }
            
            if (!isValidContact(userContact.value)) {
                showNotification('لطفا آیدی تلگرام یا شماره تماس معتبر وارد کنید', 'error');
                return;
            }
            
            const notebookData = {
                id: Date.now(),
                subscriptionCode: subscriptionCode.value,
                duration: selectedDuration,
                username: username.value,
                userContact: userContact.value,
                userNotes: userNotes.value,
                createdAt: new Date()
            };
            
            notebooks.push(notebookData);
            saveNotebooksToLocalStorage();
            
            addActivityLog(
                'ایجاد تونل جدید',
                `تونل جدید با کد اشتراک ${subscriptionCode.value} ایجاد شد.`
            );
            
            renderNotebooks();
            welcomeContainer.classList.add('hidden');
            closeAllWindows();
            showNotification('تونل با موفقیت ایجاد شد', 'success');
            resetNotebookForm();
        }
        
        // بروزرسانی دفترچه تونل
        function updateNotebook(id) {
            if (!username.value || !userContact.value) {
                showNotification('لطفا اطلاعات کاربر را کامل کنید', 'error');
                return;
            }
            
            if (!isValidContact(userContact.value)) {
                showNotification('لطفا آیدی تلگرام یا شماره تماس معتبر وارد کنید', 'error');
                return;
            }
            
            const notebookIndex = notebooks.findIndex(n => n.id === id);
            if (notebookIndex !== -1) {
                notebooks[notebookIndex].subscriptionCode = subscriptionCode.value;
                notebooks[notebookIndex].duration = selectedDuration;
                notebooks[notebookIndex].username = username.value;
                notebooks[notebookIndex].userContact = userContact.value;
                notebooks[notebookIndex].userNotes = userNotes.value;
                
                saveNotebooksToLocalStorage();
                
                addActivityLog(
                    'ویرایش اطلاعات تونل',
                    `اطلاعات تونل ${subscriptionCode.value} به روزرسانی شد.`
                );
                
                renderNotebooks();
                closeAllWindows();
                showNotification('تغییرات با موفقیت ذخیره شد', 'success');
            }
        }
        
        // ذخیره دفترچه‌ها در localStorage
        function saveNotebooksToLocalStorage() {
            localStorage.setItem('notebooks', JSON.stringify(notebooks));
        }
        
        // ذخیره گزارش فعالیت در localStorage
        function saveActivityLogsToLocalStorage() {
            localStorage.setItem('activityLogs', JSON.stringify(activityLogs));
        }
        
        // افزودن رویداد به گزارش فعالیت
        function addActivityLog(title, desc) {
            const now = new Date();
            const days = ['یکشنبه', 'دوشنبه', 'سه شنبه', 'چهارشنبه', 'پنجشنبه', 'جمعه', 'شنبه'];
            const months = ['فروردین', 'اردیبهشت', 'خرداد', 'تیر', 'مرداد', 'شهریور', 'مهر', 'آبان', 'آذر', 'دی', 'بهمن', 'اسفند'];
            
            const day = now.getDate();
            const month = now.getMonth() + 1;
            const year = now.getFullYear();
            const hours = now.getHours();
            const minutes = now.getMinutes();
            
            let dateStr = `امروز - ${hours}:${minutes < 10 ? '0' + minutes : minutes}`;
            
            activityLogs.unshift({
                title: title,
                date: dateStr,
                desc: desc
            });
            
            if (activityLogs.length > 50) {
                activityLogs = activityLogs.slice(0, 50);
            }
            
            saveActivityLogsToLocalStorage();
            renderActivityLogs();
        }
        
        // رندر گزارش فعالیت
        function renderActivityLogs() {
            const reportContent = document.getElementById('reportContent');
            reportContent.innerHTML = '';
            
            activityLogs.forEach(log => {
                const logItem = document.createElement('div');
                logItem.className = 'report-item fade-in';
                logItem.innerHTML = `
                    <div class="report-item-header">
                        <div class="report-item-title">${log.title}</div>
                        <div class="report-item-date">${log.date}</div>
                    </div>
                    <div class="report-item-desc">${log.desc}</div>
                `;
                reportContent.appendChild(logItem);
            });
        }
        
        // رندر لیست دفترچه‌ها
        function renderNotebooks() {
            notebooksList.innerHTML = '';
            
            if (notebooks.length === 0) {
                welcomeContainer.classList.remove('hidden');
                return;
            }
            
            const sortedNotebooks = [...notebooks].sort((a, b) => b.id - a.id);
            
            sortedNotebooks.forEach((notebook, index) => {
                const notebookCard = document.createElement('div');
                notebookCard.className = 'notebook-card slide-in';
                notebookCard.dataset.id = notebook.id;
                
                const endDate = new Date(notebook.createdAt);
                endDate.setMonth(endDate.getMonth() + notebook.duration);
                const today = new Date();
                const diffTime = endDate - today;
                
                const remainingTime = formatRemainingTime(diffTime);
                
                notebookCard.innerHTML = `
                    <div class="notebook-index">${index + 1}</div>
                    <div class="notebook-card-header">
                        <div class="notebook-card-title">کاربر: ${notebook.username}</div>
                        <div class="edit-btn" data-id="${notebook.id}"><i class="fas fa-pencil-alt"></i></div>
                    </div>
                    <div class="notebook-card-content">
                        <div class="notebook-info">
                            <span class="notebook-label">کد اشتراک:</span>
                            <span class="notebook-value">
                                <span class="copy-code" data-code="${notebook.subscriptionCode}">
                                    ${notebook.subscriptionCode}
                                    <i class="fas fa-copy copy-icon"></i>
                                </span>
                            </span>
                        </div>
                        <div class="notebook-info">
                            <span class="notebook-label">مدت زمان:</span>
                            <span class="notebook-value">${notebook.duration} ماهه</span>
                        </div>
                        <div class="notebook-info">
                            <span class="notebook-label">اتمام اشتراک:</span>
                            <span class="notebook-value">${remainingTime}</span>
                        </div>
                        <div class="notebook-info">
                            <span class="notebook-label">آیدی/شماره:</span>
                            <span class="notebook-value">${notebook.userContact}</span>
                        </div>
                    </div>
                    <div class="notebook-details">
                        <div class="notebook-info" style="margin-top: 10px;">
                            <span class="notebook-label">توضیحات:</span>
                            <span class="notebook-value">${notebook.userNotes || 'بدون توضیحات'}</span>
                        </div>
                        <div class="notebook-actions">
                            <button class="action-btn edit-action" data-id="${notebook.id}">
                                <i class="fas fa-edit"></i> ویرایش
                            </button>
                            <button class="action-btn delete-action" data-id="${notebook.id}">
                                <i class="fas fa-trash"></i> حذف
                            </button>
                        </div>
                    </div>
                `;
                
                notebooksList.appendChild(notebookCard);
                
                notebookCard.addEventListener('click', function(e) {
                    if (e.target.closest('.edit-btn') || e.target.closest('.action-btn') || e.target.closest('.copy-code')) {
                        return;
                    }
                    
                    document.querySelectorAll('.notebook-card.expanded').forEach(card => {
                        if (card !== this) {
                            card.classList.remove('expanded');
                        }
                    });
                    
                    this.classList.toggle('expanded');
                });
            });
            
            document.querySelectorAll('.edit-btn').forEach(btn => {
                btn.addEventListener('click', (e) => {
                    e.stopPropagation();
                    const notebookId = parseInt(btn.dataset.id);
                    const notebook = notebooks.find(n => n.id === notebookId);
                    if (notebook) {
                        openNotebookWindow(notebook);
                    }
                });
            });
            
            document.querySelectorAll('.edit-action').forEach(btn => {
                btn.addEventListener('click', (e) => {
                    e.stopPropagation();
                    const notebookId = parseInt(btn.dataset.id);
                    const notebook = notebooks.find(n => n.id === notebookId);
                    if (notebook) {
                        openNotebookWindow(notebook);
                    }
                });
            });
            
            document.querySelectorAll('.delete-action').forEach(btn => {
                btn.addEventListener('click', (e) => {
                    e.stopPropagation();
                    const notebookId = parseInt(btn.dataset.id);
                    openConfirmWindow(notebookId);
                });
            });
            
            document.querySelectorAll('.copy-code').forEach(btn => {
                btn.addEventListener('click', (e) => {
                    e.stopPropagation();
                    const code = btn.dataset.code;
                    navigator.clipboard.writeText(code);
                    showNotification('کد اشتراک کپی شد', 'success');
                });
            });
        }
        
        // حذف دفترچه تونل
        function deleteNotebook() {
            const notebookIndex = notebooks.findIndex(n => n.id === notebookToDelete);
            if (notebookIndex !== -1) {
                const deletedCode = notebooks[notebookIndex].subscriptionCode;
                notebooks = notebooks.filter(notebook => notebook.id !== notebookToDelete);
                saveNotebooksToLocalStorage();
                
                addActivityLog(
                    'حذف تونل',
                    `تونل با کد اشتراک ${deletedCode} حذف شد.`
                );
                
                renderNotebooks();
                closeAllWindows();
                showNotification('تونل با موفقیت حذف شد', 'success');
                
                if (notebooks.length === 0) {
                    welcomeContainer.classList.remove('hidden');
                }
            }
        }
        
        // فرمت زمان باقی‌مانده
        function formatRemainingTime(milliseconds) {
            if (milliseconds <= 0) {
                return 'منقضی شده';
            }
            
            const endDate = new Date(Date.now() + milliseconds);
            const day = endDate.getDate();
            const month = endDate.getMonth() + 1;
            const year = endDate.getFullYear();
            
            return `${year}/${month < 10 ? '0' + month : month}/${day < 10 ? '0' + day : day}`;
        }
        
        // گرفتن بکاپ از تونل‌ها
        function exportNotebooks() {
            const dataStr = JSON.stringify(notebooks);
            const dataUri = 'data:application/json;charset=utf-8,'+ encodeURIComponent(dataStr);
            
            const exportFileDefaultName = `xrovpn-backup-${new Date().toISOString().slice(0,10)}.json`;
            
            const linkElement = document.createElement('a');
            linkElement.setAttribute('href', dataUri);
            linkElement.setAttribute('download', exportFileDefaultName);
            linkElement.click();
            
            addActivityLog(
                'گرفتن بکاپ',
                'یک بکاپ از تمام تونل‌های شما گرفته شد.'
            );
            
            showNotification('بکاپ با موفقیت گرفته شد', 'success');
        }
        
        // بازیابی تونل‌ها از فایل بکاپ
        function importNotebooks(file) {
            const reader = new FileReader();
            
            reader.onload = function(e) {
                try {
                    const importedNotebooks = JSON.parse(e.target.result);
                    
                    if (!Array.isArray(importedNotebooks)) {
                        throw new Error('فرمت فایل نامعتبر است');
                    }
                    
                    const isValid = importedNotebooks.every(notebook => {
                        return notebook.id && notebook.subscriptionCode && notebook.duration && 
                               notebook.username && notebook.userContact && notebook.createdAt;
                    });
                    
                    if (!isValid) {
                        throw new Error('داده‌های فایل بکاپ معتبر نیستند');
                    }
                    
                    notebooks = importedNotebooks;
                    saveNotebooksToLocalStorage();
                    
                    addActivityLog(
                        'بازیابی بکاپ',
                        `تونل‌ها از فایل بکاپ بازیابی شدند (${importedNotebooks.length} تونل).`
                    );
                    
                    renderNotebooks();
                    closeAllWindows();
                    showNotification(`بکاپ با موفقیت بازیابی شد! ${importedNotebooks.length} تونل اضافه شد`, 'success');
                } catch (error) {
                    showNotification(`خطا در بازیابی بکاپ: ${error.message}`, 'error');
                }
            };
            
            reader.readAsText(file);
        }
        
        // سفارش اشتراک
        function orderSubscription(months) {
            const price = getSubscriptionPrice(months);
            const message = `درود آقای ایکسرو!\n\nپروتکل سرویس: وایرگارد\nحجم سرویس: نامحدود\nتعداد کاربر سرویس: 1\nانقضا سرویس: ${months} ماه\n\nقیمت نهایی: ${price} تومان\n\nاطلاعات لازم همراه شماره کارت برای بنده ارسال کنید ، باتشکر`;
            
            window.open(`https://t.me/u0v0n?text=${encodeURIComponent(message)}`, '_blank');
            closeAllWindows();
            
            addActivityLog(
                'درخواست اشتراک',
                `درخواست اشتراک ${months} ماهه ارسال شد`
            );
        }
        
        // دریافت قیمت اشتراک بر اساس تعداد ماه
        function getSubscriptionPrice(months) {
            const prices = {
                1: '264,000',
                2: '489,000',
                3: '699,000',
                4: '899,000',
                5: '1,099,000',
                6: '1,299,000'
            };
            
            return prices[months] || 'نامشخص';
        }
        
        // نمایش راهنمای جزئیات
        function showGuide(title) {
            let content = '';
            
            switch(title) {
                case 'راهنمایی فروشگاه':
                    content = `
                        <h3>راهنمای سفارش اشتراک</h3>
                        <p>1. روی گزینه "سفارش اشتراک" کلیک کنید</p>
                        <p>2. مدت زمان مورد نظر خود را انتخاب کنید</p>
                        <p>3. پیام پیشفرض به تلگرام ارسال می‌شود</p>
                        <p>4. اطلاعات پرداخت را از ادمین دریافت کنید</p>
                        <p>5. پس از پرداخت، کد اشتراک برای شما ارسال می‌شود</p>
                    `;
                    break;
                    
                case 'راهنمای تنظیمات':
                    content = `
                        <h3>راهنمای تنظیمات</h3>
                        <p>1. می‌توانید بین حالت روز و شب جابجا شوید</p>
                        <p>2. امکان بکاپ گیری از تونل‌ها وجود دارد</p>
                        <p>3. می‌توانید گزارش فعالیت را مشاهده کنید</p>
                    `;
                    break;
                    
                case 'راهنمای ساخت دفترچه تونل':
                    content = `
                        <h3>راهنمای ساخت تونل</h3>
                        <p>1. کد اشتراک خود را وارد کنید (مثال: XRO_u7272u)</p>
                        <p>2. مدت زمان اشتراک را انتخاب کنید</p>
                        <p>3. اطلاعات شخصی خود را وارد کنید</p>
                        <p>4. روی دکمه ثبت درخواست کلیک کنید</p>
                        <p>5. تونل شما در لیست نمایش داده می‌شود</p>
                    `;
                    break;
                    
                case 'راهنمای گزارش فعالیت':
                    content = `
                        <h3>راهنمای گزارش فعالیت</h3>
                        <p>در این بخش می‌توانید تاریخچه فعالیت‌های خود را مشاهده کنید:</p>
                        <p>- ایجاد تونل‌های جدید</p>
                        <p>- ویرایش اطلاعات تونل‌ها</p>
                        <p>- حذف تونل‌ها</p>
                        <p>- تغییرات تنظیمات</p>
                    `;
                    break;
                    
                case 'راهنمای بکاپ گیری تونل':
                    content = `
                        <h3>راهنمای بکاپ</h3>
                        <p>1. برای گرفتن بکاپ روی دکمه "گرفتن بکاپ" کلیک کنید</p>
                        <p>2. یک فایل JSON دانلود می‌شود</p>
                        <p>3. برای بازیابی، روی دکمه "بازیابی" کلیک کنید</p>
                        <p>4. فایل بکاپ قبلی را انتخاب کنید</p>
                        <p>5. تمام تونل‌های شما بازیابی می‌شوند</p>
                    `;
                    break;
                    
                case 'راهنمای دعوت از دوستان':
                    content = `
                        <h3>دعوت از دوستان</h3>
                        <p>1. می‌توانید این برنامه را با دوستان خود به اشتراک بگذارید</p>
                        <p>2. برای سفارش اشتراک به آیدی @u0v0n پیام دهید</p>
                        <p>3. کدهای اشتراک شما با فرمت XRO_xxxxxx می‌باشد</p>
                    `;
                    break;
                    
                default:
                    content = '<p>راهنمای مورد نظر یافت نشد</p>';
            }
            
            openGuideWindow(title, content);
        }
        
        // رویدادهای کلیک
        mainMenuBtn.addEventListener('click', openMainMenu);
        quickMenuBtn.addEventListener('click', openQuickMenu);
        closeMainMenu.addEventListener('click', closeAllWindows);
        overlay.addEventListener('click', closeAllWindows);
        confirmNo.addEventListener('click', closeAllWindows);
        confirmYes.addEventListener('click', deleteNotebook);
        
        // رویدادهای منو
        reportItem.addEventListener('click', openReportWindow);
        backupItem.addEventListener('click', openBackupWindow);
        themeItem.addEventListener('click', toggleTheme);
        quickShopItem.addEventListener('click', openShopWindow);
        quickNotebookItem.addEventListener('click', () => {
            resetNotebookForm();
            openNotebookWindow();
        });
        quickHelpItem.addEventListener('click', openHelpWindow);
        
        // رویدادهای راهنما
        helpShop.addEventListener('click', () => showGuide('راهنمایی فروشگاه'));
        helpSettings.addEventListener('click', () => showGuide('راهنمای تنظیمات'));
        helpNotebook.addEventListener('click', () => showGuide('راهنمای ساخت دفترچه تونل'));
        helpReport.addEventListener('click', () => showGuide('راهنمای گزارش فعالیت'));
        helpBackup.addEventListener('click', () => showGuide('راهنمای بکاپ گیری تونل'));
        helpInvite.addEventListener('click', () => showGuide('راهنمای دعوت از دوستان'));
        closeGuide.addEventListener('click', closeAllWindows);
        
        // رویدادهای پنجره فروشگاه
        closeShop.addEventListener('click', closeAllWindows);
        
        // رویدادهای پنجره راهنما
        closeHelp.addEventListener('click', closeAllWindows);
        
        // رویدادهای پنجره دفترچه تونل
        closeNotebook.addEventListener('click', closeAllWindows);
        
        // رویدادهای پنجره گزارش فعالیت
        closeReport.addEventListener('click', closeAllWindows);
        
        // رویدادهای پنجره بکاپ
        closeBackup.addEventListener('click', closeAllWindows);
        exportBackup.addEventListener('click', exportNotebooks);
        importBackup.addEventListener('click', () => backupFileInput.click());
        backupFileInput.addEventListener('change', (e) => {
            if (e.target.files.length > 0) {
                importNotebooks(e.target.files[0]);
            }
        });
        
        // مدیریت مراحل ساخت دفترچه
        nextToStep2.addEventListener('click', () => goToStep(2));
        nextToStep3.addEventListener('click', () => goToStep(3));
        backToStep1.addEventListener('click', () => goToStep(1));
        backToStep2.addEventListener('click', () => goToStep(2));
        
        // انتخاب مدت زمان
        durationOptions.forEach(option => {
            option.addEventListener('click', function() {
                durationOptions.forEach(opt => opt.classList.remove('selected'));
                this.classList.add('selected');
                selectedDuration = parseInt(this.dataset.months);
            });
        });
        
        // بستن با کلید ESC
        document.addEventListener('keydown', (e) => {
            if (e.key === 'Escape') {
                closeAllWindows();
            }
        });
        
        // بارگذاری اولیه
        document.addEventListener('DOMContentLoaded', () => {
            showTodayDate();
            applyTheme();
            renderNotebooks();
            renderActivityLogs();
            
            setInterval(() => {
                if (notebooks.length > 0) {
                    renderNotebooks();
                }
            }, 60000);
            
            addActivityLog(
                'ورود به سیستم',
                'شما با موفقیت وارد حساب کاربری خود شدید.'
            );
        });
    </script>
</body>
</html>
