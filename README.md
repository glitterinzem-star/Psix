<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>переходник психолога</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            -webkit-tap-highlight-color: transparent;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
            line-height: 1.6;
            color: #ffe6e6;
            background: linear-gradient(135deg, #400000 0%, #200000 100%);
            min-height: 100vh;
            padding: env(safe-area-inset-top) env(safe-area-inset-right) env(safe-area-inset-bottom) env(safe-area-inset-left);
        }

        .container {
            max-width: 100%;
            margin: 0 auto;
            padding: 1rem;
            min-height: 100vh;
        }

        header {
            text-align: center;
            margin-bottom: 2rem;
            color: #ffffff;
            padding: 0 0.5rem;
        }

        h1 {
            font-size: clamp(1.8rem, 6vw, 3rem);
            margin-bottom: 0.5rem;
            text-shadow: 2px 2px 8px rgba(0,0,0,0.5);
            color: #ffffff;
            font-weight: 700;
        }

        .subtitle {
            font-size: clamp(0.9rem, 3.5vw, 1.2rem);
            opacity: 0.9;
            color: #ffb3b3;
            line-height: 1.4;
        }

        /* Основной контент */
        .content-wrapper {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
            background: rgba(80, 0, 0, 0.8);
            border-radius: 12px;
            padding: 1.5rem;
            box-shadow: 0 8px 32px rgba(139, 0, 0, 0.6);
            border: 1px solid #990000;
            margin: 0 auto;
            max-width: 600px;
            backdrop-filter: blur(10px);
        }

        /* Панель кнопок */
        .button-panel {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 0.8rem;
            width: 100%;
        }

        .theme-btn {
            padding: 14px 16px;
            border: none;
            border-radius: 10px;
            background: linear-gradient(135deg, #800000, #600000);
            color: #ffffff;
            font-size: clamp(0.9rem, 3.5vw, 1rem);
            cursor: pointer;
            transition: all 0.2s ease;
            text-align: center;
            position: relative;
            overflow: hidden;
            border: 1px solid #cc0000;
            font-weight: 500;
            touch-action: manipulation;
            min-height: 50px;
            display: flex;
            align-items: center;
            justify-content: center;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.5);
            text-decoration: none;
        }

        .theme-btn:active {
            transform: scale(0.96);
            box-shadow: 0 0 20px rgba(255, 0, 0, 0.7);
            background: linear-gradient(135deg, #900000, #700000);
        }

        .theme-btn.active {
            background: linear-gradient(135deg, #cc0000, #990000);
            border-left: 3px solid #ff3333;
            box-shadow: 0 0 15px rgba(255, 0, 0, 0.6);
        }

        .full-width-btn {
            background: linear-gradient(135deg, #990000, #770000);
            grid-column: 1 / -1;
            font-weight: 600;
        }

        .full-width-btn:active {
            background: linear-gradient(135deg, #aa0000, #880000);
        }

        .channel-btn {
            background: linear-gradient(135deg, #cc0000, #aa0000);
            font-weight: 600;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 100%;
            max-width: 200px;
            margin-top: 1rem;
        }

        .channel-btn:active {
            background: linear-gradient(135deg, #dd0000, #bb0000);
        }

        /* Область с текстом */
        .text-display {
            background: rgba(60, 0, 0, 0.9);
            border-radius: 10px;
            padding: 1.5rem;
            min-height: 300px;
            border-left: 3px solid #ff3333;
            position: relative;
            box-shadow: inset 0 0 20px rgba(139, 0, 0, 0.8);
            border: 1px solid #800000;
        }

        .text-content {
            opacity: 0;
            transform: translateY(15px);
            transition: all 0.4s ease;
            position: absolute;
            width: calc(100% - 3rem);
            top: 1.5rem;
        }

        .text-content.active {
            opacity: 1;
            transform: translateY(0);
            position: relative;
        }

        .text-content h2 {
            color: #ffffff;
            margin-bottom: 1rem;
            font-size: clamp(1.3rem, 5vw, 1.8rem);
            text-shadow: 1px 1px 4px rgba(255, 0, 0, 0.5);
            font-weight: 600;
        }

        .text-content p {
            margin-bottom: 1rem;
            font-size: clamp(0.95rem, 3.5vw, 1.1rem);
            line-height: 1.6;
            color: #ffe6e6;
        }

        .highlight {
            background: linear-gradient(120deg, #990000 0%, #cc0000 100%);
            padding: 0.2rem 0.5rem;
            border-radius: 4px;
            font-weight: 600;
            color: #ffffff;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.5);
            border: 1px solid #ff3333;
        }

        /* Дополнительные стили */
        .feature-list {
            list-style: none;
            margin: 1rem 0;
        }

        .feature-list li {
            padding: 0.5rem 0;
            border-bottom: 1px solid #800000;
            position: relative;
            padding-left: 1.5rem;
            font-size: clamp(0.9rem, 3.5vw, 1rem);
            color: #ffe6e6;
        }

        .feature-list li:before {
            content: "►";
            color: #ff3333;
            font-weight: bold;
            position: absolute;
            left: 0;
            font-size: 0.8rem;
            text-shadow: 0 0 5px rgba(255, 0, 0, 0.7);
        }

        /* Специальные стили для Telegram */
        .tg-mobile .container {
            padding: 0.5rem;
        }

        .tg-mobile .content-wrapper {
            padding: 1rem;
            gap: 1rem;
        }

        .tg-mobile .text-display {
            padding: 1rem;
            min-height: 250px;
        }

        /* Адаптивность для очень маленьких экранов */
        @media (max-width: 360px) {
            .container {
                padding: 0.5rem;
            }
            
            .content-wrapper {
                padding: 1rem;
                border-radius: 10px;
            }
            
            .button-panel {
                grid-template-columns: 1fr;
                gap: 0.6rem;
            }
            
            .theme-btn {
                padding: 12px 14px;
                min-height: 45px;
                font-size: 0.9rem;
            }
            
            .text-display {
                padding: 1rem;
                min-height: 200px;
            }
            
            .text-content {
                width: calc(100% - 2rem);
            }
        }

        /* Планшеты и десктоп */
        @media (min-width: 768px) {
            .container {
                padding: 2rem;
                display: flex;
                flex-direction: column;
                justify-content: center;
                max-width: 800px;
            }
            
            .content-wrapper {
                display: grid;
                grid-template-columns: 1fr 2fr;
                gap: 2rem;
                max-width: 100%;
            }
            
            .button-panel {
                grid-template-columns: 1fr;
                gap: 1rem;
            }
            
            .theme-btn:hover {
                transform: translateX(5px);
                box-shadow: 0 5px 20px rgba(255, 0, 0, 0.5);
                background: linear-gradient(135deg, #900000, #700000);
            }
            
            .theme-btn.active:hover {
                transform: translateX(5px);
            }
            
            .full-width-btn:hover {
                background: linear-gradient(135deg, #aa0000, #880000);
            }
            
            .channel-btn:hover {
                background: linear-gradient(135deg, #dd0000, #bb0000);
            }
        }

        /* Поддержка безопасных зон (iPhone X и новее) */
        @supports(padding: max(0px)) {
            .container {
                padding-left: max(1rem, env(safe-area-inset-left));
                padding-right: max(1rem, env(safe-area-inset-right));
                padding-bottom: max(1rem, env(safe-area-inset-bottom));
            }
        }

        a {
            color: #ffffff;
            text-decoration: none;
            display: block;
        }

        /* Улучшения для производительности */
        .theme-btn, .text-display {
            will-change: transform;
            backface-visibility: hidden;
        }

        /* Кровавые акценты */
        .blood-accent {
            position: fixed;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
            opacity: 0.1;
            background: radial-gradient(circle at 20% 80%, #ff0000 0%, transparent 50%),
                       radial-gradient(circle at 80% 20%, #cc0000 0%, transparent 50%);
        }
    </style>
</head>
<body>
    <div class="blood-accent"></div>
    
    <div class="container">
        <header>
            <h1>переходник психолога</h1>
            <p class="subtitle">Информация о проектах и услугах</p>
        </header>

        <div class="content-wrapper">
            <!-- Панель с кнопками -->
            <div class="button-panel">
                <a href="https://t.me/info_psixo" target="_blank" class="theme-btn full-width-btn">Проект</a>
                <a href="https://t.me/psixaxaxy" target="_blank" class="theme-btn full-width-btn">Продажа физов</a>
                <a href="https://t.me/Psixotatia" target="_blank" class="theme-btn full-width-btn">Профиль</a>
                <a href="https://t.me/PsixoxoxFell" target="_blank" class="theme-btn full-width-btn">Новости о физах</a>
            </div>

            <!-- Область отображения текста -->
            <div class="text-display">
                <!-- Главная -->
                <div class="text-content active" id="main-content">
                    <h2>Добро пожаловать! 👋</h2>
                    <p>Это официальная страница с актуальными ссылками на все проекты.</p>
                    
                    <ul class="feature-list">
                        <li><span class="highlight">Проект</span> - основная информация</li>
                        <li><span class="highlight">Продажа физов</span> - продажа физических аккаунтов</li>
                        <li><span class="highlight">Профиль</span> - профиль телеграм</li>
                        <li><span class="highlight">Новости о физах</span> - актуальные цены и наличие</li>
                    </ul>
                </div>
            </div>
        </div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const buttons = document.querySelectorAll('.theme-btn');
            
            // Определяем, открыто ли в Telegram
            function detectTelegram() {
                const userAgent = navigator.userAgent.toLowerCase();
                if (userAgent.includes('telegram') || userAgent.includes('webview')) {
                    document.body.classList.add('tg-mobile');
                }
                
                // Добавляем класс для iPhone X и новее
                if (/iPhone/.test(navigator.userAgent) && !/Safari/.test(navigator.userAgent)) {
                    document.body.classList.add('tg-ios');
                }
            }
            
            // Упрощенные эффекты для кнопок (не мешающие переходам)
            buttons.forEach(button => {
                button.addEventListener('click', function(e) {
                    // Позволяем ссылке работать нормально
                    // Эффекты будут применены только визуально
                    this.style.transform = 'scale(0.95)';
                    setTimeout(() => {
                        this.style.transform = '';
                    }, 150);
                });
            });
            
            // Инициализация
            detectTelegram();
        });
    </script>
</body>
</html>