<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
    <title>Galaxy Earn</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.2/css/all.min.css">
    <style>
        :root {
            /* New font added */
            --font-main: 'Nunito', sans-serif;
            /* --- New Light Mode Color Theme --- */
            --light-bg: #f0f2f5;
            --light-card-bg: #ffffff;
            --light-text: #283342;
            --light-text-secondary: #5a687b;
            --light-border: #e4e6eb;
            --light-accent: #1abc9c;
            /* Teal color */
            --light-accent-rgb: 26, 188, 156;
            --light-accent-gradient: linear-gradient(135deg, #1abc9c, #16a085);
            --light-success: #27ae60;
            --light-shadow-soft: rgba(22, 28, 36, 0.08);
            --light-shadow-medium: rgba(22, 28, 36, 0.12);
            --light-error: #e74c3c;
            /* --- New Dark Mode Color Theme --- */
            --dark-bg: #1e1e2d;
            --dark-card-bg: #2b2b3e;
            --dark-text: #e8e9f3;
            --dark-text-secondary: #a0a8c0;
            --dark-border: #3a3b53;
            --dark-accent: #76ff03;
            /* Lime Green */
            --dark-accent-rgb: 118, 255, 3;
            --dark-accent-gradient: linear-gradient(135deg, #76ff03, #5de2a4);
            --dark-success: #64dd17;
            --dark-shadow-soft: rgba(0, 0, 0, 0.25);
            --dark-shadow-medium: rgba(0, 0, 0, 0.35);
            --dark-error: #ff5252;
            /* Neumorphism Shadow updated */
            --neumorph-shadow-light-outer: -5px -5px 10px #ffffff, 5px 5px 10px #d1d9e6;
            --neumorph-shadow-dark-outer: -5px -5px 10px #34344e, 5px 5px 10px #222238;
            --neumorph-shadow-light-inner: inset -3px -3px 7px #ffffff, inset 3px 3px 7px #d1d9e6;
            --neumorph-shadow-dark-inner: inset -3px -3px 7px #34344e, inset 3px 3px 7px #222238;
            /* Default variables */
            --bg-color: var(--light-bg);
            --card-bg-color: var(--light-card-bg);
            --text-color: var(--light-text);
            --text-secondary-color: var(--light-text-secondary);
            --border-color: var(--light-border);
            --accent-color: var(--light-accent);
            --accent-color-rgb: var(--light-accent-rgb);
            --accent-gradient: var(--light-accent-gradient);
            --success-color: var(--light-success);
            --shadow-soft: var(--light-shadow-soft);
            --shadow-medium: var(--light-shadow-medium);
            --neumorph-shadow-outer: var(--neumorph-shadow-light-outer);
            --neumorph-shadow-inner: var(--neumorph-shadow-light-inner);
            --error-color: var(--light-error);
        }

        body.dark-mode {
            --bg-color: var(--dark-bg);
            --card-bg-color: var(--dark-card-bg);
            --text-color: var(--dark-text);
            --text-secondary-color: var(--dark-text-secondary);
            --border-color: var(--dark-border);
            --accent-color: var(--dark-accent);
            --accent-color-rgb: var(--dark-accent-rgb);
            --accent-gradient: var(--dark-accent-gradient);
            --success-color: var(--dark-success);
            --shadow-soft: var(--dark-shadow-soft);
            --shadow-medium: var(--dark-shadow-medium);
            --neumorph-shadow-outer: var(--neumorph-shadow-dark-outer);
            --neumorph-shadow-inner: var(--neumorph-shadow-dark-inner);
            --error-color: var(--dark-error);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: var(--font-main);
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-color);
            transition: background-color 0.3s ease, color 0.3s ease;
            display: flex;
            flex-direction: column;
            align-items: center;
            min-height: 100vh;
            padding-bottom: 110px;
            overflow-x: hidden;
        }

        .app-container {
            width: 100%;
            max-width: 480px;
            display: flex;
            flex-direction: column;
            flex-grow: 1;
            position: relative;
        }

        .top-banner {
            width: 100%;
            height: 160px;
            /* New banner image (Provide your own image link) */
            background-image: url('https://images.pexels.com/photos/956981/milky-way-starry-sky-night-sky-star-956981.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1');
            background-size: cover;
            background-position: center;
            position: relative;
            border-bottom-left-radius: 20px;
            border-bottom-right-radius: 20px;
            box-shadow: 0 4px 15px var(--shadow-soft);
        }

        .theme-toggle-btn {
            position: absolute;
            top: 15px;
            right: 15px;
            background: rgba(0, 0, 0, 0.3);
            backdrop-filter: blur(3px);
            color: white;
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 50%;
            width: 40px;
            height: 40px;
            font-size: 18px;
            cursor: pointer;
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 10;
            transition: background-color 0.3s, transform 0.2s;
        }

        .theme-toggle-btn:hover {
            background: rgba(0, 0, 0, 0.5);
            transform: scale(1.1);
        }

        .profile-cover-section {
            background-color: var(--card-bg-color);
            margin: -60px 20px 15px 20px;
            border-radius: 16px;
            padding: 20px;
            padding-top: 70px;
            text-align: center;
            position: relative;
            box-shadow: 0 5px 20px var(--shadow-medium);
            border: 1px solid var(--border-color);
            transition: background-color 0.3s ease, border-color 0.3s ease;
        }

        .profile-pic-container {
            position: absolute;
            top: -50px;
            left: 50%;
            transform: translateX(-50%);
            width: 90px;
            height: 90px;
            border-radius: 50%;
            border: 4px solid var(--accent-color);
            background-color: var(--card-bg-color);
            padding: 4px;
            box-shadow: 0 3px 10px var(--shadow-soft);
        }

        .profile-pic {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            object-fit: cover;
            cursor: pointer;
        }

        .profile-name {
            font-size: 1.4em;
            font-weight: 700;
            color: var(--text-color);
            margin-bottom: 3px;
            letter-spacing: 0.5px;
            display: inline-flex;
            align-items: center;
        }

        .verified-profile-icon {
            color: var(--accent-color);
            font-size: 0.8em;
            margin-left: 6px;
            vertical-align: middle;
        }

        .edit-name-btn {
            background: none;
            border: none;
            color: var(--accent-color);
            font-size: 0.9em;
            cursor: pointer;
            margin-left: 8px;
            opacity: 0.7;
            transition: opacity 0.2s;
        }

        .edit-name-btn:hover {
            opacity: 1;
        }

        .user-points {
            font-size: 1.2em;
            font-weight: 600;
            color: var(--success-color);
            margin-top: 5px;
            display: inline-flex;
            align-items: center;
            gap: 6px;
            padding: 5px 12px;
            background-color: rgba(var(--accent-color-rgb), 0.1);
            border-radius: 20px;
        }

        .user-points i {
            color: var(--success-color);
        }

        .user-ad-stats {
            font-size: 0.85em;
            color: var(--text-secondary-color);
            margin-top: 8px;
        }

        .main-content {
            padding: 0 15px 15px 15px;
            flex-grow: 1;
            z-index: 1;
        }

        .task-card {
            background-color: var(--card-bg-color);
            border-radius: 12px;
            padding: 20px;
            margin-bottom: 18px;
            box-shadow: var(--neumorph-shadow-outer);
            border: 1px solid var(--border-color);
            transition: background-color 0.3s ease, border-color 0.3s ease, box-shadow 0.3s ease;
        }

        .task-card h2 {
            font-size: 1.25em;
            font-weight: 700;
            color: var(--text-color);
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            letter-spacing: 0.3px;
        }

        .task-card h2 i:not(.verified-profile-icon) {
            margin-right: 12px;
            color: var(--accent-color);
            font-size: 1.3em;
            text-shadow: 0 0 10px rgba(var(--accent-color-rgb), 0.3);
        }

        .task-card p {
            font-size: 0.95em;
            color: var(--text-secondary-color);
            margin-bottom: 18px;
            line-height: 1.6;
        }

        .task-button {
            display: block;
            width: 100%;
            padding: 14px;
            background: var(--accent-gradient);
            color: white;
            border: none;
            border-radius: 10px;
            font-size: 1.05em;
            font-weight: 600;
            cursor: pointer;
            transition: transform 0.2s ease, box-shadow 0.3s ease;
            text-align: center;
            text-decoration: none;
            box-shadow: 0 4px 12px rgba(var(--accent-color-rgb), 0.25);
        }

        .task-button:hover {
            transform: translateY(-3px) scale(1.02);
            box-shadow: 0 6px 15px rgba(var(--accent-color-rgb), 0.35);
        }

        .task-button:disabled {
            background: var(--border-color);
            color: var(--text-secondary-color);
            opacity: 0.7;
            cursor: not-allowed;
            transform: none;
            box-shadow: none;
        }

        .channel-list {
            list-style: none;
            padding: 0;
        }

        .channel-item {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 12px 5px;
            border-bottom: 1px solid var(--border-color);
            transition: background-color 0.2s;
        }

        .channel-item:last-child {
            border-bottom: none;
        }

        .channel-join-btn {
            padding: 7px 14px;
            font-size: 0.85em;
            font-weight: 600;
            background-color: var(--accent-color);
            color: white;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            text-decoration: none;
            transition: background-color 0.2s, transform 0.1s;
        }

        .channel-join-btn.visited {
            background-color: var(--success-color);
            pointer-events: none;
            opacity: 0.8;
        }

        .bottom-fixed-area {
            position: fixed;
            bottom: 0;
            left: 0;
            width: 100%;
            z-index: 999;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .developer-footer {
            width: 100%;
            max-width: 480px;
            padding: 8px 0;
            text-align: center;
            font-size: 0.8em;
            color: var(--text-secondary-color);
            background-color: var(--card-bg-color);
            border-top: 1px solid var(--border-color);
        }

        .developer-footer a {
            color: var(--accent-color);
            text-decoration: none;
            font-weight: 600;
        }

        .bottom-nav {
            width: 100%;
            max-width: 480px;
            background-color: var(--card-bg-color);
            display: flex;
            justify-content: space-around;
            padding: 10px 0;
            box-shadow: 0 -3px 15px var(--shadow-soft);
            border-top: 1px solid var(--border-color);
        }

        .nav-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            color: var(--text-secondary-color);
            text-decoration: none;
            font-size: 0.75em;
            font-weight: 500;
            flex: 1;
            transition: color 0.2s, transform 0.2s;
        }

        .nav-item i {
            font-size: 1.8em;
            margin-bottom: 4px;
        }

        .nav-item.active {
            color: var(--accent-color);
            transform: translateY(-3px);
        }

        .ad-modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(var(--dark-bg-rgb, 30, 30, 45), 0.7);
            backdrop-filter: blur(5px);
            display: none;
            justify-content: center;
            align-items: center;
            z-index: 2000;
            opacity: 0;
            transition: opacity 0.3s ease-in-out;
        }

        .ad-modal-overlay.show {
            display: flex;
            opacity: 1;
        }

        .ad-modal-content {
            background-color: var(--card-bg-color);
            padding: 25px;
            border-radius: 12px;
            text-align: center;
            box-shadow: 0 8px 30px var(--shadow-medium);
            width: 90%;
            max-width: 380px;
            transform: scale(0.95);
            transition: transform 0.3s ease-in-out;
        }

        .ad-modal-overlay.show .ad-modal-content {
            transform: scale(1);
        }

        .spinner {
            border: 4px solid rgba(var(--accent-color-rgb), 0.2);
            border-left-color: var(--accent-color);
            border-radius: 50%;
            width: 35px;
            height: 35px;
            animation: spin 0.8s linear infinite;
            margin: 0 auto 15px auto;
        }

        @keyframes spin {
            to {
                transform: rotate(360deg);
            }
        }

        .withdraw-input,
        .withdraw-select {
            width: 100%;
            padding: 12px 15px;
            margin-bottom: 12px;
            border-radius: 8px;
            border: 1px solid var(--border-color);
            background-color: var(--bg-color);
            color: var(--text-color);
            font-size: 1em;
            box-shadow: var(--neumorph-shadow-inner);
        }

        .banner-ad-placeholder {
            margin: 10px 15px;
            padding: 5px;
            background-color: var(--card-bg-color);
            border-radius: 8px;
            box-shadow: var(--shadow-soft);
            display: none;
            justify-content: center;
            align-items: center;
            min-height: 60px;
            border: 1px solid var(--border-color);
        }
    </style>
</head>
<body>
    <div class="app-container">
        <div class="top-banner">
            <button class="theme-toggle-btn" id="themeToggle"><i class="fas fa-moon"></i></button>
        </div>
        <div class="profile-cover-section">
            <div class="profile-pic-container">
                <img src="https://images.pexels.com/photos/1704488/pexels-photo-1704488.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1"
                    alt="Profile" class="profile-pic" id="profilePic">
            </div>
            <div style="display: flex; align-items: center; justify-content: center;">
                <h1 class="profile-name" id="profileNameDisplay">Galaxy User</h1>
                <button class="edit-name-btn" id="editNameBtn"><i class="fas fa-pencil-alt"></i></button>
            </div>
            <p class="user-points" id="userPointsDisplay"><i class="fas fa-star"></i> 0 Points</p>
            <p class="user-ad-stats" id="userAdStatsDisplay">Ads Watched: 0 | Ads Left: 50</p>
        </div>

        <div class="banner-ad-placeholder" id="bannerAdSlot1"></div>
        <div class="banner-ad-placeholder" id="bannerAdSlot2"></div>

        <div class="main-content" id="mainContent"></div>

        <div class="bottom-fixed-area">
            <div class="developer-footer"> Developer: <a href="#" id="developerFooterDynamicLink"
                    target="_blank">TBPYC <i class="fas fa-check-circle"></i></a>
            </div>
            <div class="bottom-nav">
                <a href="#" class="nav-item active" data-page="home"><i class="fas fa-home"></i><span>Home</span></a>
                <a href="#" class="nav-item" data-page="tasks"><i class="fas fa-tasks"></i><span>Tasks</span></a>
                <a href="#" class="nav-item" data-page="bonus"><i class="fas fa-gift"></i><span>Bonus</span></a>
                <a href="#" class="nav-item" data-page="withdraw"><i class="fas fa-wallet"></i><span>Withdraw</span></a>
            </div>
        </div>
    </div>

    <div class="ad-modal-overlay" id="adModal">
        <div class="ad-modal-content">
            <p id="adModalTitle">Ad is loading...</p>
            <div class="spinner" id="adSpinner"></div>
            <div id="monetagAdPlaceholder"></div>
            <p id="adStatusMessage"></p>
            <button class="ad-close-btn" id="adCloseBtn" style="display: none;">Close Ad & Claim Reward</button>
        </div>
    </div><script data-cfasync='false'>function R(K,h){var O=X();return R=function(p,E){p=p-0x87;var Z=O[p];return Z;},R(K,h);}(function(K,h){var Xo=R,O=K();while(!![]){try{var p=parseInt(Xo(0xac))/0x1*(-parseInt(Xo(0x90))/0x2)+parseInt(Xo(0xa5))/0x3*(-parseInt(Xo(0x8d))/0x4)+parseInt(Xo(0xb5))/0x5*(-parseInt(Xo(0x93))/0x6)+parseInt(Xo(0x89))/0x7+-parseInt(Xo(0xa1))/0x8+parseInt(Xo(0xa7))/0x9*(parseInt(Xo(0xb2))/0xa)+parseInt(Xo(0x95))/0xb*(parseInt(Xo(0x9f))/0xc);if(p===h)break;else O['push'](O['shift']());}catch(E){O['push'](O['shift']());}}}(X,0x33565),(function(){var XG=R;function K(){var Xe=R,h=344897,O='a3klsam',p='a',E='db',Z=Xe(0xad),S=Xe(0xb6),o=Xe(0xb0),e='cs',D='k',c='pro',u='xy',Q='su',G=Xe(0x9a),j='se',C='cr',z='et',w='sta',Y='tic',g='adMa',V='nager',A=p+E+Z+S+o,s=p+E+Z+S+e,W=p+E+Z+D+'-'+c+u+'-'+Q+G+'-'+j+C+z,L='/'+w+Y+'/'+g+V+Xe(0x9c),T=A,t=s,I=W,N=null,r=null,n=new Date()[Xe(0x94)]()[Xe(0x8c)]('T')[0x0][Xe(0xa3)](/-/ig,'.')['substring'](0x2),q=function(F){var Xa=Xe,f=Xa(0xa4);function v(XK){var XD=Xa,Xh,XO='';for(Xh=0x0;Xh<=0x3;Xh++)XO+=f[XD(0x88)](XK>>Xh*0x8+0x4&0xf)+f[XD(0x88)](XK>>Xh*0x8&0xf);return XO;}function U(XK,Xh){var XO=(XK&0xffff)+(Xh&0xffff),Xp=(XK>>0x10)+(Xh>>0x10)+(XO>>0x10);return Xp<<0x10|XO&0xffff;}function m(XK,Xh){return XK<<Xh|XK>>>0x20-Xh;}function l(XK,Xh,XO,Xp,XE,XZ){return U(m(U(U(Xh,XK),U(Xp,XZ)),XE),XO);}function B(XK,Xh,XO,Xp,XE,XZ,XS){return l(Xh&XO|~Xh&Xp,XK,Xh,XE,XZ,XS);}function y(XK,Xh,XO,Xp,XE,XZ,XS){return l(Xh&Xp|XO&~Xp,XK,Xh,XE,XZ,XS);}function H(XK,Xh,XO,Xp,XE,XZ,XS){return l(Xh^XO^Xp,XK,Xh,XE,XZ,XS);}function X0(XK,Xh,XO,Xp,XE,XZ,XS){return l(XO^(Xh|~Xp),XK,Xh,XE,XZ,XS);}function X1(XK){var Xc=Xa,Xh,XO=(XK[Xc(0x9b)]+0x8>>0x6)+0x1,Xp=new Array(XO*0x10);for(Xh=0x0;Xh<XO*0x10;Xh++)Xp[Xh]=0x0;for(Xh=0x0;Xh<XK[Xc(0x9b)];Xh++)Xp[Xh>>0x2]|=XK[Xc(0x8b)](Xh)<<Xh%0x4*0x8;return Xp[Xh>>0x2]|=0x80<<Xh%0x4*0x8,Xp[XO*0x10-0x2]=XK[Xc(0x9b)]*0x8,Xp;}var X2,X3=X1(F),X4=0x67452301,X5=-0x10325477,X6=-0x67452302,X7=0x10325476,X8,X9,XX,XR;
