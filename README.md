<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=yes">
    <title>Для тебя ❤️</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Times New Roman', Times, serif;
        }

        body {
            background: linear-gradient(135deg, #ffd9e8 0%, #ffb6c1 100%);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 10px;
            position: relative;
            overflow-x: hidden;
        }

        .heart-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
        }

        .heart-bg i {
            position: absolute;
            color: rgba(255, 105, 180, 0.2);
            animation: float 8s ease-in-out infinite;
            font-size: 20px;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0) rotate(0deg); }
            50% { transform: translateY(-30px) rotate(8deg); }
        }

        .container {
            width: 1200px;
            max-width: 100%;
            background: rgba(255, 245, 250, 0.97);
            backdrop-filter: blur(8px);
            border-radius: 40px;
            box-shadow: 0 30px 60px rgba(255, 105, 180, 0.25);
            overflow: hidden;
            position: relative;
            z-index: 1;
            animation: fadeIn 1.2s ease;
            border: 1px solid rgba(255, 182, 193, 0.5);
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: scale(0.92); }
            to { opacity: 1; transform: scale(1); }
        }

        .youtube-button {
            position: absolute;
            top: 10px;
            right: 10px;
            z-index: 10;
            background: #ff69b4;
            padding: 8px 16px;
            border-radius: 30px;
            box-shadow: 0 8px 20px rgba(255, 105, 180, 0.25);
            display: flex;
            align-items: center;
            gap: 8px;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            color: #fff0f5;
            font-weight: 500;
            letter-spacing: 0.5px;
            border: 1px solid rgba(255, 240, 245, 0.3);
            font-size: 14px;
        }

        @media (min-width: 768px) {
            .youtube-button {
                top: 20px;
                right: 20px;
                padding: 12px 28px;
                font-size: 16px;
                gap: 12px;
            }
        }

        .youtube-button:hover {
            transform: scale(1.05);
            box-shadow: 0 12px 30px rgba(255, 105, 180, 0.35);
            background: #ff1493;
        }

        .youtube-button i {
            font-size: 18px;
            color: #fff0f5;
        }

        @media (min-width: 768px) {
            .youtube-button i {
                font-size: 22px;
            }
        }

        .tabs {
            display: flex;
            background: linear-gradient(135deg, #ffc0cb 0%, #ffb6c1 100%);
            padding: 15px 15px 0 15px;
            gap: 8px;
            flex-wrap: wrap;
            justify-content: center;
        }

        @media (min-width: 768px) {
            .tabs {
                padding: 25px 25px 0 25px;
                gap: 12px;
            }
        }

        .tab {
            padding: 10px 16px;
            background: rgba(255, 240, 245, 0.3);
            border-radius: 25px 25px 0 0;
            color: #8b3a62;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 6px;
            border: none;
            font-size: 14px;
            backdrop-filter: blur(4px);
            letter-spacing: 0.5px;
            border-bottom: 2px solid transparent;
            white-space: nowrap;
        }

        @media (min-width: 768px) {
            .tab {
                padding: 16px 32px;
                font-size: 17px;
                gap: 10px;
                letter-spacing: 0.7px;
            }
        }

        .tab i {
            font-size: 14px;
            color: #b24b73;
        }

        @media (min-width: 768px) {
            .tab i {
                font-size: 18px;
            }
        }

        .tab:hover {
            background: rgba(255, 240, 245, 0.5);
            transform: translateY(-3px);
            border-bottom-color: #ff8da1;
        }

        .tab.active {
            background: #fff0f5;
            color: #b24b73;
            box-shadow: 0 -8px 20px rgba(255, 105, 180, 0.1);
            border-bottom: 2px solid #ff8da1;
        }

        .tab.active i {
            color: #ff69b4;
        }

        .tab-content {
            padding: 20px;
            min-height: 450px;
            background: #fff0f5;
        }

        @media (min-width: 768px) {
            .tab-content {
                padding: 35px;
                min-height: 550px;
            }
        }

        .tab-pane {
            display: none;
            animation: slideIn 0.5s ease;
        }

        .tab-pane.active {
            display: block;
        }

        @keyframes slideIn {
            from { opacity: 0; transform: translateX(15px); }
            to { opacity: 1; transform: translateX(0); }
        }

        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(140px, 1fr));
            gap: 15px;
            margin-top: 15px;
        }

        @media (min-width: 768px) {
            .gallery-grid {
                grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
                gap: 25px;
                margin-top: 25px;
            }
        }

        .gallery-item {
            position: relative;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 12px 25px rgba(255, 105, 180, 0.2);
            transition: all 0.3s ease;
            cursor: pointer;
            aspect-ratio: 1 / 1;
            border: 2px solid #ffe4ec;
        }

        @media (min-width: 768px) {
            .gallery-item {
                border-radius: 28px;
                border: 3px solid #ffe4ec;
            }
        }

        .gallery-item:hover {
            transform: scale(1.02);
            box-shadow: 0 18px 35px rgba(255, 105, 180, 0.3);
            border-color: #ffb6c1;
        }

        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
        }

        .gallery-item .overlay {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: linear-gradient(to top, rgba(255, 105, 180, 0.85), transparent);
            color: #fff0f5;
            padding: 10px;
            transform: translateY(100%);
            transition: transform 0.3s ease;
            font-size: 16px;
            font-weight: 500;
            text-align: center;
            letter-spacing: 0.5px;
            backdrop-filter: blur(2px);
        }

        @media (min-width: 768px) {
            .gallery-item .overlay {
                padding: 20px;
                font-size: 22px;
                letter-spacing: 1px;
            }
        }

        .gallery-item:hover .overlay {
            transform: translateY(0);
        }

        .love-notes {
            display: grid;
            grid-template-columns: 1fr;
            gap: 15px;
        }

        @media (min-width: 768px) {
            .love-notes {
                grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
                gap: 25px;
            }
        }

        .note-card {
            background: linear-gradient(135deg, #ffe4ec 0%, #ffd9e8 100%);
            padding: 20px;
            border-radius: 25px;
            box-shadow: 0 10px 25px rgba(255, 105, 180, 0.15);
            position: relative;
            transition: all 0.3s ease;
            border: 2px solid rgba(255, 182, 193, 0.3);
            cursor: pointer;
            text-align: center;
        }

        @media (min-width: 768px) {
            .note-card {
                padding: 28px;
                border-radius: 35px;
            }
        }

        .note-card:hover {
            transform: translateY(-6px);
            box-shadow: 0 15px 35px rgba(255, 105, 180, 0.25);
            border-color: #ffb6c1;
        }

        .note-card i {
            font-size: 30px;
            color: #ff69b4;
            margin-bottom: 12px;
        }

        @media (min-width: 768px) {
            .note-card i {
                font-size: 38px;
                margin-bottom: 18px;
            }
        }

        .note-card p {
            font-size: 16px;
            line-height: 1.5;
            color: #8b3a62;
            margin-bottom: 12px;
            font-weight: 500;
        }

        @media (min-width: 768px) {
            .note-card p {
                font-size: 19px;
                line-height: 1.6;
                margin-bottom: 18px;
            }
        }

        .note-card .emoji-row {
            font-size: 24px;
            letter-spacing: 4px;
        }

        @media (min-width: 768px) {
            .note-card .emoji-row {
                font-size: 30px;
                letter-spacing: 8px;
            }
        }

        .message-section {
            text-align: center;
            padding: 25px;
            background: linear-gradient(135deg, #ffe4ec 0%, #ffd9e8 100%);
            border-radius: 30px;
            margin-top: 15px;
            border: 2px solid #ffe4ec;
        }

        @media (min-width: 768px) {
            .message-section {
                padding: 45px;
                border-radius: 50px;
                margin-top: 20px;
            }
        }

        .message-section h2 {
            font-size: 28px;
            color: #b24b73;
            margin-bottom: 15px;
            font-weight: 600;
            letter-spacing: 0.5px;
        }

        @media (min-width: 768px) {
            .message-section h2 {
                font-size: 44px;
                margin-bottom: 30px;
                letter-spacing: 1px;
            }
        }

        .message-section p {
            font-size: 16px;
            color: #8b3a62;
            margin: 15px 0;
            line-height: 1.6;
        }

        @media (min-width: 768px) {
            .message-section p {
                font-size: 22px;
                margin: 22px 0;
                line-height: 1.8;
            }
        }

        .big-emoji {
            font-size: 40px;
            margin: 20px 0;
            animation: bounce 2.2s infinite;
        }

        @media (min-width: 768px) {
            .big-emoji {
                font-size: 65px;
                margin: 35px 0;
            }
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-18px); }
        }

        .surprise-button {
            background: linear-gradient(135deg, #ffb6c1 0%, #ff9eb5 100%);
            color: #fff0f5;
            border: none;
            padding: 12px 30px;
            font-size: 18px;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            margin: 20px 0 15px;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            font-weight: 500;
            box-shadow: 0 15px 30px rgba(255, 105, 180, 0.25);
            letter-spacing: 0.5px;
            border: 2px solid rgba(255, 240, 245, 0.4);
        }

        @media (min-width: 768px) {
            .surprise-button {
                padding: 18px 48px;
                font-size: 24px;
                border-radius: 70px;
                margin: 30px 0 20px;
                gap: 15px;
                letter-spacing: 1px;
            }
        }

        .surprise-button:hover {
            transform: scale(1.08);
            box-shadow: 0 20px 40px rgba(255, 105, 180, 0.35);
            background: linear-gradient(135deg, #ff9eb5 0%, #ff8da1 100%);
        }

        .floating-hearts {
            position: relative;
            height: 60px;
            margin: 10px 0;
        }

        @media (min-width: 768px) {
            .floating-hearts {
                height: 100px;
                margin: 20px 0;
            }
        }

        .floating-hearts i {
            position: absolute;
            color: #ff69b4;
            animation: floatHeart 3.5s ease-in-out infinite;
            font-size: 18px;
        }

        @media (min-width: 768px) {
            .floating-hearts i {
                font-size: 24px;
            }
        }

        @keyframes floatHeart {
            0% { transform: translateY(0) scale(1); opacity: 0.8; }
            100% { transform: translateY(-60px) scale(1.3); opacity: 0; }
        }

        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(255, 182, 193, 0.3);
            z-index: 1000;
            justify-content: center;
            align-items: center;
            padding: 15px;
        }

        .modal.active {
            display: flex;
        }

        .modal-content {
            background: #fff0f5;
            padding: 25px;
            border-radius: 40px;
            text-align: center;
            max-width: 90%;
            animation: modalPop 0.35s ease;
            box-shadow: 0 30px 50px rgba(255, 105, 180, 0.25);
            border: 3px solid #ffe4ec;
        }

        @media (min-width: 768px) {
            .modal-content {
                padding: 45px;
                border-radius: 60px;
                max-width: 450px;
            }
        }

        @keyframes modalPop {
            from { transform: scale(0.85); opacity: 0; }
            to { transform: scale(1); opacity: 1; }
        }

        .modal-content i {
            font-size: 50px;
            color: #ff69b4;
            margin: 10px 0;
        }

        @media (min-width: 768px) {
            .modal-content i {
                font-size: 75px;
                margin: 20px 0;
            }
        }

        .modal-content h2 {
            font-size: 28px;
            color: #b24b73;
            margin: 10px 0;
            font-weight: 600;
        }

        @media (min-width: 768px) {
            .modal-content h2 {
                font-size: 38px;
                margin: 20px 0;
            }
        }

        .modal-content p {
            font-size: 18px;
            color: #8b3a62;
            line-height: 1.5;
        }

        @media (min-width: 768px) {
            .modal-content p {
                font-size: 24px;
                line-height: 1.6;
            }
        }

        .close-modal {
            background: #ffb6c1;
            color: #fff0f5;
            border: none;
            padding: 10px 25px;
            border-radius: 30px;
            font-size: 16px;
            cursor: pointer;
            margin-top: 15px;
            transition: all 0.3s ease;
            border: 2px solid rgba(255, 240, 245, 0.4);
            letter-spacing: 0.5px;
        }

        @media (min-width: 768px) {
            .close-modal {
                padding: 14px 40px;
                border-radius: 40px;
                font-size: 19px;
                margin-top: 25px;
                letter-spacing: 0.7px;
            }
        }

        .close-modal:hover {
            background: #ff9eb5;
            transform: scale(1.05);
        }

        h2 i {
            margin-right: 8px;
        }

        @media (max-width: 480px) {
            .tab {
                padding: 8px 12px;
                font-size: 13px;
            }
            
            .gallery-grid {
                grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
                gap: 10px;
            }
            
            .gallery-item .overlay {
                font-size: 14px;
                padding: 8px;
            }
        }
    </style>
</head>
<body>
    <div class="heart-bg" id="heartBg"></div>

    <div class="container">
        <a href="https://youtu.be/oeLvR-JtDRE?si=L6-DldGyUg0auVVZ" target="_blank" class="youtube-button">
            <i class="fab fa-youtube"></i>
            <span>🎵 нажми</span>
        </a>

        <div class="tabs">
            <button class="tab active" onclick="switchTab('gallery')">
                <i class="fas fa-camera-retro"></i> Наши моменты
            </button>
            <button class="tab" onclick="switchTab('love')">
                <i class="fas fa-heart"></i> Признания
            </button>
            <button class="tab" onclick="switchTab('messages')">
                <i class="fas fa-envelope"></i> Письмо
            </button>
            <button class="tab" onclick="switchTab('surprise')">
                <i class="fas fa-gift"></i> Сюрприз
            </button>
        </div>

        <div class="tab-content">
            <div class="tab-pane active" id="gallery">
                <h2 style="color: #b24b73; margin-bottom: 15px; text-align: center; font-size: 24px;">
                    <i class="fas fa-camera"></i> Наши особенные кадры
                </h2>
                <div class="gallery-grid">
                    <div class="gallery-item">
                        <img src="3.jpg" alt="Именниник">
                        <div class="overlay">
                            <i class="fas fa-heart"></i> Именниник
                        </div>
                    </div>
                    <div class="gallery-item">
                        <img src="5.jpg" alt="Вместе">
                        <div class="overlay">
                            <i class="fas fa-heart"></i> Вместе
                        </div>
                    </div>
                    <div class="gallery-item">
                        <img src="8.jpg" alt="Моя лабубушечка">
                        <div class="overlay">
                            <i class="fas fa-heart"></i> Моя лабубушечка
                        </div>
                    </div>
                    <div class="gallery-item">
                        <img src="7.jpg" alt="Наше место">
                        <div class="overlay">
                            <i class="fas fa-heart"></i> Наше место
                        </div>
                    </div>
                    <div class="gallery-item">
                        <img src="4.jpg" alt="Крайняя">
                        <div class="overlay">
                            <i class="fas fa-heart"></i> Крайняя
                        </div>
                    </div>
                    <div class="gallery-item">
                        <img src="1.jpg" alt="Чемпион">
                        <div class="overlay">
                            <i class="fas fa-heart"></i> Чемпион
                        </div>
                    </div>
                    <div class="gallery-item">
                        <img src="9.jpg" alt="Счастливы">
                        <div class="overlay">
                            <i class="fas fa-heart"></i> Счастливы
                        </div>
                    </div>
                    <div class="gallery-item">
                        <img src="2.jpg" alt="Поцелуй">
                        <div class="overlay">
                            <i class="fas fa-heart"></i> Поцелуй
                        </div>
                    </div>
                    <div class="gallery-item">
                        <img src="6.jpg" alt="Мой милашка">
                        <div class="overlay">
                            <i class="fas fa-heart"></i> Мой милашка
                        </div>
                    </div>
                </div>
            </div>

            <div class="tab-pane" id="love">
                <h2 style="color: #b24b73; margin-bottom: 15px; text-align: center; font-size: 24px;">
                    <i class="fas fa-heartbeat"></i> Нажми на послания ❤️
                </h2>
                <div class="love-notes">
                    <div class="note-card" onclick="openLoveModal('Ты — моё счастье! ✨')">
                        <i class="fas fa-heart"></i>
                        <p>Ты делаешь мою жизнь волшебной</p>
                        <div class="emoji-row">💕 💗 💓</div>
                    </div>
                    <div class="note-card" onclick="openLoveModal('Ты — мой свет! ⭐')">
                        <i class="fas fa-star"></i>
                        <p>С тобой каждый день особенный</p>
                        <div class="emoji-row">🌟 ✨ 💫</div>
                    </div>
                    <div class="note-card" onclick="openLoveModal('Ты согреваешь меня! ☀️')">
                        <i class="fas fa-sun"></i>
                        <p>Твоё тепло чувствую всегда</p>
                        <div class="emoji-row">🌞 💛 🥰</div>
                    </div>
                    <div class="note-card" onclick="openLoveModal('Ты мой герой! 👑')">
                        <i class="fas fa-crown"></i>
                        <p>Для меня ты лучший</p>
                        <div class="emoji-row">💖 👑 💘</div>
                    </div>
                    <div class="note-card" onclick="openLoveModal('Всегда с тобой! ♾️')">
                        <i class="fas fa-infinity"></i>
                        <p>Наша любовь бесконечна</p>
                        <div class="emoji-row">💞 🌌 💫</div>
                    </div>
                    <div class="note-card" onclick="openLoveModal('Ты — моя радость! 😊')">
                        <i class="fas fa-hand-holding-heart"></i>
                        <p>Твоя улыбка - мой любимый момент</p>
                        <div class="emoji-row">🥰 💕 😘</div>
                    </div>
                </div>
            </div>

            <div class="tab-pane" id="messages">
                <div class="message-section">
                    <h2>💌 Моему любимому 💌</h2>
                    <i class="fas fa-heart" style="font-size: 40px; color: #ff69b4; margin: 15px;"></i>
                    <p>Владислав,</p>
                    <p>Каждый день с тобой — это особенное чудо. Ты делаешь мой мир ярче, теплее и счастливее. Спасибо тебе за твою заботу, нежность и бесконечную любовь.</p>
                    <p>Ты — самый удивительный человек в моей жизни, и я бесконечно благодарна судьбе за нашу встречу. Рядом с тобой я чувствую себя любимой и защищенной.</p>
                    <p>Помни: ты самый важный человек для меня. Твои мечты — это и мои мечты. Мы вместе преодолеем всё, потому что наша любовь сильнее всего.</p>
                    
                    <div class="big-emoji">
                        💖 🥰 💕 😘 💗
                    </div>
                    <p>С днём рождения, мой любименький! 🎉</p>
                    <p style="font-size: 24px;">Навсегда с тобой ❤️</p>
                </div>
            </div>

            <div class="tab-pane" id="surprise">
                <div class="message-section" style="background: linear-gradient(135deg, #ffd9e8 0%, #ffc0cb 100%);">
                    <h2>🎉 СЮРПРИЗ! 🎉</h2>
                    <div class="floating-hearts" id="floatingHearts"></div>
                    <div class="big-emoji">
                        🎈 💝 🎁 💖 🎈
                    </div>
                    <p style="font-size: 20px;">Ты — самый лучший парень на свете!</p>
                    <p style="font-size: 18px; font-style: italic; color: #b24b73;">Я приготовила для тебя особенное послание:</p>
                    <p style="font-size: 22px; font-weight: 600; color: #b24b73; margin: 20px; background: white; padding: 15px; border-radius: 40px; border: 2px solid #ffb6c1;">
                        "Спасибо, что ты есть у меня!"
                    </p>
                    <button class="surprise-button" onclick="createRainbowHearts()">
                        <i class="fas fa-heart"></i> Нажми на удачу
                    </button>
                    <div class="floating-hearts" id="surpriseHearts"></div>
                </div>
            </div>
        </div>
    </div>

    <div class="modal" id="loveModal">
        <div class="modal-content">
            <i class="fas fa-heart"></i>
            <h2>Я ТЕБЯ ЛЮБЛЮ</h2>
            <p id="modalMessage">❤️</p>
            <div style="font-size: 35px; margin: 15px 0;">
                💖 💗 💓 💕 💘
            </div>
            <button class="close-modal" onclick="closeLoveModal()">Закрыть</button>
        </div>
    </div>

    <script>
        function createHearts() {
            const heartBg = document.getElementById('heartBg');
            for (let i = 0; i < 35; i++) {
                const heart = document.createElement('i');
                heart.className = 'fas fa-heart';
                heart.style.left = Math.random() * 100 + '%';
                heart.style.top = Math.random() * 100 + '%';
                heart.style.animationDelay = Math.random() * 6 + 's';
                heart.style.fontSize = (Math.random() * 25 + 15) + 'px';
                heartBg.appendChild(heart);
            }
        }

        function switchTab(tabId) {
            document.querySelectorAll('.tab-pane').forEach(pane => {
                pane.classList.remove('active');
            });
            document.querySelectorAll('.tab').forEach(tab => {
                tab.classList.remove('active');
            });
            document.getElementById(tabId).classList.add('active');
            event.target.closest('.tab').classList.add('active');
        }

        function openLoveModal(message) {
            document.getElementById('loveModal').classList.add('active');
            document.getElementById('modalMessage').innerHTML = message + '<br>❤️';
            
            for (let i = 0; i < 20; i++) {
                setTimeout(() => {
                    createFloatingHeart();
                }, i * 70);
            }
        }

        function closeLoveModal() {
            document.getElementById('loveModal').classList.remove('active');
        }

        function createFloatingHeart() {
            const heart = document.createElement('i');
            heart.className = 'fas fa-heart';
            heart.style.position = 'fixed';
            heart.style.left = Math.random() * 100 + '%';
            heart.style.top = '50%';
            heart.style.color = '#ff69b4';
            heart.style.fontSize = (Math.random() * 35 + 20) + 'px';
            heart.style.zIndex = '1001';
            heart.style.animation = 'floatHeart 2.2s ease-out forwards';
            document.body.appendChild(heart);
            
            setTimeout(() => {
                heart.remove();
            }, 2200);
        }

        function createRainbowHearts() {
            const colors = ['#ff69b4', '#ffb6c1', '#ff9eb5', '#ff8da1', '#ff7b9c'];
            for (let i = 0; i < 25; i++) {
                setTimeout(() => {
                    const heart = document.createElement('i');
                    heart.className = 'fas fa-heart';
                    heart.style.position = 'fixed';
                    heart.style.left = Math.random() * 100 + '%';
                    heart.style.bottom = '0';
                    heart.style.color = colors[Math.floor(Math.random() * colors.length)];
                    heart.style.fontSize = (Math.random() * 45 + 25) + 'px';
                    heart.style.zIndex = '1001';
                    heart.style.animation = 'floatHeart 2.8s ease-out forwards';
                    document.body.appendChild(heart);
                    
                    setTimeout(() => {
                        heart.remove();
                    }, 2800);
                }, i * 100);
            }
            
            alert('💖 Ты — мой самый любимый, милый, добрый, красивый, очаровательный человек! Спасибо, что ты у меня есть 💖');
        }

        window.onload = function() {
            createHearts();
            
            const galleryItems = document.querySelectorAll('.gallery-item');
            galleryItems.forEach((item, index) => {
                item.addEventListener('click', function() {
                    const overlay = this.querySelector('.overlay').textContent;
                    alert('❤️ ' + overlay + ' ❤️\nЭто наш особенный момент!');
                });
            });
        };

        document.getElementById('loveModal').addEventListener('click', function(e) {
            if (e.target === this) {
                closeLoveModal();
            }
        });
    </script>
</body>
</html>
