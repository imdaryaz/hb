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
            color: rgba(255, 105, 180, 0.15);
            animation: float 8s ease-in-out infinite;
            font-size: 20px;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0) rotate(0deg); }
            50% { transform: translateY(-30px) rotate(8deg); }
        }

        .container {
            width: 100%;
            max-width: 500px;
            background: rgba(255, 245, 250, 0.98);
            backdrop-filter: blur(10px);
            border-radius: 35px;
            box-shadow: 0 25px 50px rgba(255, 105, 180, 0.3);
            overflow: hidden;
            position: relative;
            z-index: 1;
            animation: fadeIn 1s ease;
            border: 1px solid rgba(255, 255, 255, 0.3);
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: scale(0.95); }
            to { opacity: 1; transform: scale(1); }
        }

        .tabs {
            display: flex;
            background: linear-gradient(135deg, #ffb6c1 0%, #ff9eb5 100%);
            padding: 20px 15px 0 15px;
            gap: 5px;
            flex-wrap: wrap;
            justify-content: center;
        }

        .tab {
            padding: 10px 15px;
            background: rgba(255, 255, 255, 0.25);
            border-radius: 25px 25px 0 0;
            color: #8b3a62;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 5px;
            border: none;
            font-size: 14px;
            backdrop-filter: blur(5px);
            border-bottom: 2px solid transparent;
            flex: 1;
            justify-content: center;
            min-width: auto;
        }

        .tab i {
            font-size: 13px;
            color: #b24b73;
        }

        .tab.active {
            background: white;
            color: #b24b73;
            border-bottom: 2px solid #ff69b4;
            box-shadow: 0 -5px 15px rgba(255, 105, 180, 0.1);
        }

        .tab.active i {
            color: #ff69b4;
        }

        .tab-content {
            padding: 20px 15px;
            background: white;
        }

        .tab-pane {
            display: none;
            animation: fadeInPane 0.4s ease;
        }

        .tab-pane.active {
            display: block;
        }

        @keyframes fadeInPane {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .section-title {
            color: #b24b73;
            margin-bottom: 20px;
            text-align: center;
            font-size: 24px;
            font-weight: 600;
            letter-spacing: 0.5px;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }

        .section-title i {
            color: #ff69b4;
        }

        .gallery-grid {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        .gallery-item {
            position: relative;
            border-radius: 25px;
            overflow: hidden;
            box-shadow: 0 10px 25px rgba(255, 105, 180, 0.2);
            cursor: pointer;
            aspect-ratio: 1/1;
            border: 3px solid white;
            transition: all 0.3s ease;
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
            background: linear-gradient(to top, rgba(255, 105, 180, 0.9), rgba(255, 105, 180, 0.3));
            color: white;
            padding: 20px;
            font-size: 20px;
            font-weight: 500;
            text-align: center;
            backdrop-filter: blur(2px);
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }

        .love-notes {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .note-card {
            background: linear-gradient(135deg, #ffe4ec 0%, #ffd9e8 100%);
            padding: 25px;
            border-radius: 30px;
            box-shadow: 0 8px 20px rgba(255, 105, 180, 0.15);
            border: 2px solid rgba(255, 182, 193, 0.4);
            cursor: pointer;
            text-align: center;
            transition: all 0.3s ease;
        }

        .note-card:active {
            transform: scale(0.98);
            background: linear-gradient(135deg, #ffd9e8 0%, #ffc0cb 100%);
        }

        .note-card i {
            font-size: 35px;
            color: #ff69b4;
            margin-bottom: 12px;
        }

        .note-card p {
            font-size: 18px;
            line-height: 1.5;
            color: #8b3a62;
            margin-bottom: 12px;
            font-weight: 500;
        }

        .note-card .emoji-row {
            font-size: 28px;
            letter-spacing: 6px;
        }

        .message-section {
            text-align: center;
            padding: 25px 20px;
            background: linear-gradient(135deg, #ffe4ec 0%, #ffd9e8 100%);
            border-radius: 35px;
            border: 2px solid rgba(255, 182, 193, 0.4);
        }

        .message-section h2 {
            font-size: 26px;
            color: #b24b73;
            margin-bottom: 20px;
            font-weight: 600;
        }

        .message-section p {
            font-size: 17px;
            color: #8b3a62;
            margin: 15px 0;
            line-height: 1.7;
        }

        .big-emoji {
            font-size: 40px;
            margin: 20px 0;
            animation: bounce 2s infinite;
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-15px); }
        }

        .surprise-button {
            background: linear-gradient(135deg, #ff69b4 0%, #ff4d8c 100%);
            color: white;
            border: none;
            padding: 16px 35px;
            font-size: 20px;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            margin: 20px 0 10px;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            font-weight: 500;
            box-shadow: 0 15px 30px rgba(255, 105, 180, 0.3);
            border: 2px solid rgba(255, 255, 255, 0.3);
        }

        .surprise-button:active {
            transform: scale(0.95);
            box-shadow: 0 10px 20px rgba(255, 105, 180, 0.4);
        }

        .youtube-button {
            background: rgba(255, 255, 255, 0.3);
            backdrop-filter: blur(8px);
            padding: 12px 25px;
            border-radius: 40px;
            box-shadow: 0 4px 15px rgba(255, 105, 180, 0.2);
            display: inline-flex;
            align-items: center;
            gap: 8px;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            color: #b24b73;
            font-weight: 500;
            font-size: 16px;
            border: 1px solid rgba(255, 255, 255, 0.6);
            margin-top: 20px;
        }

        .youtube-button i {
            font-size: 18px;
            color: #ff4d4d;
        }

        .youtube-button:hover {
            background: rgba(255, 255, 255, 0.5);
            transform: scale(1.05);
            box-shadow: 0 6px 20px rgba(255, 105, 180, 0.3);
        }

        .floating-hearts {
            position: relative;
            height: 60px;
            margin: 15px 0;
        }

        .floating-hearts i {
            position: absolute;
            color: #ff69b4;
            animation: floatHeart 3s ease-in-out infinite;
            font-size: 20px;
        }

        @keyframes floatHeart {
            0% { transform: translateY(0) scale(1); opacity: 0.8; }
            100% { transform: translateY(-50px) scale(1.2); opacity: 0; }
        }

        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(255, 105, 180, 0.3);
            backdrop-filter: blur(5px);
            z-index: 2000;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .modal.active {
            display: flex;
        }

        .modal-content {
            background: white;
            padding: 35px 25px;
            border-radius: 50px;
            text-align: center;
            width: 100%;
            max-width: 380px;
            animation: modalPop 0.3s ease;
            box-shadow: 0 30px 50px rgba(255, 105, 180, 0.3);
            border: 3px solid #ffe4ec;
        }

        @keyframes modalPop {
            from { transform: scale(0.9); opacity: 0; }
            to { transform: scale(1); opacity: 1; }
        }

        .modal-content i {
            font-size: 60px;
            color: #ff69b4;
            margin: 10px 0;
        }

        .modal-content h2 {
            font-size: 30px;
            color: #b24b73;
            margin: 15px 0;
        }

        .modal-content p {
            font-size: 22px;
            color: #8b3a62;
            line-height: 1.5;
            margin: 15px 0;
        }

        .close-modal {
            background: #ffb6c1;
            color: white;
            border: none;
            padding: 12px 35px;
            border-radius: 40px;
            font-size: 18px;
            cursor: pointer;
            margin-top: 20px;
            transition: all 0.3s ease;
            border: 2px solid rgba(255, 255, 255, 0.3);
            font-weight: 500;
        }

        .close-modal:active {
            transform: scale(0.95);
            background: #ff9eb5;
        }

        @media (max-width: 380px) {
            .tab {
                font-size: 12px;
                padding: 8px 10px;
            }
            
            .section-title {
                font-size: 20px;
            }
            
            .gallery-item .overlay {
                font-size: 18px;
                padding: 15px;
            }
            
            .note-card p {
                font-size: 16px;
            }
            
            .note-card .emoji-row {
                font-size: 24px;
            }
        }
    </style>
</head>
<body>
    <div class="heart-bg" id="heartBg"></div>

    <div class="container">
        <div class="tabs">
            <button class="tab active" onclick="switchTab('gallery')">
                <i class="fas fa-camera-retro"></i> Фото
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
                <h2 class="section-title">
                    <i class="fas fa-camera"></i> Наши моменты
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
                <h2 class="section-title">
                    <i class="fas fa-heartbeat"></i> Признания
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
                        <p>Твоя улыбка — мой любимый момент</p>
                        <div class="emoji-row">🥰 💕 😘</div>
                    </div>
                </div>
            </div>

            <div class="tab-pane" id="messages">
                <div class="message-section">
                    <h2>💌 Моему любимому</h2>
                    <i class="fas fa-heart" style="font-size: 45px; color: #ff69b4; margin: 10px;"></i>
                    <p>Владислав,</p>
                    <p>Каждый день с тобой - это особенное чудо. Ты делаешь мой мир ярче, теплее и счастливее. Спасибо тебе за твою заботу, нежность и бесконечную любовь.</p>
                    <p>Ты - самый удивительный человек в моей жизни, и я бесконечно благодарна судьбе за нашу встречу. Рядом с тобой я чувствую себя любимой и защищенной.</p>
                    <p>Помни: ты самый важный человек для меня. Твои мечты - это и мои мечты. Мы вместе преодолеем всё, потому что наша любовь сильнее всего.</p>
                    
                    <div class="big-emoji">
                        💖 🥰 💕 😘 💗
                    </div>
                    <p>С днём рождения, мой любименький! 🎉</p>
                    <p style="font-size: 24px; margin-top: 20px;">Навсегда с тобой ❤️</p>
                </div>
            </div>

            <div class="tab-pane" id="surprise">
                <div class="message-section" style="background: linear-gradient(135deg, #ffd9e8 0%, #ffc0cb 100%);">
                    <h2>🎉 СЮРПРИЗ!</h2>
                    <div class="floating-hearts" id="floatingHearts"></div>
                    <div class="big-emoji">
                        🎈 💝 🎁 💖 🎈
                    </div>
                    <p style="font-size: 20px;">Ты - самый лучший парень на свете!</p>
                    <p style="font-size: 18px; font-style: italic; color: #b24b73;">Я приготовила для тебя особенное послание:</p>
                    <p style="font-size: 22px; font-weight: 600; color: #b24b73; margin: 20px; background: white; padding: 15px; border-radius: 40px; border: 2px solid #ffb6c1;">
                        "Спасибо, что ты есть у меня!"
                    </p>
                    <button class="surprise-button" onclick="createRainbowHearts()">
                        <i class="fas fa-heart"></i> Нажми на удачу
                    </button>
                    
                    <a href="https://youtu.be/oeLvR-JtDRE?si=L6-DldGyUg0auVVZ" target="_blank" class="youtube-button">
                        <i class="fab fa-youtube"></i>
                        <span>🎵Нажми❤️</span>
                    </a>
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
            for (let i = 0; i < 30; i++) {
                const heart = document.createElement('i');
                heart.className = 'fas fa-heart';
                heart.style.left = Math.random() * 100 + '%';
                heart.style.top = Math.random() * 100 + '%';
                heart.style.animationDelay = Math.random() * 5 + 's';
                heart.style.fontSize = (Math.random() * 20 + 10) + 'px';
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
            document.getElementById('modalMessage').innerHTML = message;
            
            for (let i = 0; i < 15; i++) {
                setTimeout(() => {
                    createFloatingHeart();
                }, i * 80);
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
            heart.style.fontSize = (Math.random() * 30 + 20) + 'px';
            heart.style.zIndex = '2001';
            heart.style.animation = 'floatHeart 2s ease-out forwards';
            document.body.appendChild(heart);
            
            setTimeout(() => {
                heart.remove();
            }, 2000);
        }

        function createRainbowHearts() {
            const colors = ['#ff69b4', '#ffb6c1', '#ff9eb5', '#ff8da1'];
            for (let i = 0; i < 20; i++) {
                setTimeout(() => {
                    const heart = document.createElement('i');
                    heart.className = 'fas fa-heart';
                    heart.style.position = 'fixed';
                    heart.style.left = Math.random() * 100 + '%';
                    heart.style.bottom = '0';
                    heart.style.color = colors[Math.floor(Math.random() * colors.length)];
                    heart.style.fontSize = (Math.random() * 40 + 25) + 'px';
                    heart.style.zIndex = '2001';
                    heart.style.animation = 'floatHeart 2.5s ease-out forwards';
                    document.body.appendChild(heart);
                    
                    setTimeout(() => {
                        heart.remove();
                    }, 2500);
                }, i * 120);
            }
            
            alert('💖 Ты — мой самый любимый, милый, добрый, красивый, очаровательный человек! Спасибо, что ты у меня есть 💖');
        }

        window.onload = function() {
            createHearts();
            
            document.querySelectorAll('.gallery-item').forEach(item => {
                item.addEventListener('click', function() {
                    const text = this.querySelector('.overlay').textContent.trim();
                    alert('❤️ ' + text + ' ❤️');
                });
            });
        };

        document.getElementById('loveModal').addEventListener('click', function(e) {
            if (e.target === this) closeLoveModal();
        });
    </script>
</body>
</html>
