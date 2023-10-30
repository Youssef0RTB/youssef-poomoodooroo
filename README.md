# youssef-poomoodooroo
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>youssef Timer</title>
    <style>
        /* إضافة أنماط التصميم الأساسية هنا */
        body {
            font-family: Arial, sans-serif;
            text-align: center;
        }
        #timer {
            font-size: 36px;
            margin-top: 20px;
        }
        #startButton, #resetButton {
            padding: 10px 20px;
            font-size: 18px;
            margin: 10px;
        }
        #ad-container {
            /* تصميم مساحة الإعلان هنا */
            background-color: #373e9a;
            padding: 10px;
            margin: 20px;
        }
    </style>
</head>
<body>
    <h1>Pomodoro Timer</h1>
    <div id="timer">25:00</div>
    <button id="startButton">سمايكا بين ليا </button>
    <button id="resetButton">سيمو عاود عاود هاد لقطة لله يحفضك  </button>
    <div id="ad-container">
    <script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
                  <ins class="adsbygoogle" style="display:block; text-align:center;" data-ad-client="ca-pub-1234567890" data-ad-slot="1234567890" data-ad-format="auto"></ins>
                  <script>(adsbygoogle = window.adsbygoogle || []).push({});</script>
        -->
    </div>
    <script>
        // JavaScript لتنفيذ مؤقت Pomodoro
        let timer;
        let minutes = 25;
        let seconds = 0;
        let isRunning = false;

        const timerDisplay = document.getElementById('timer');
        const startButton = document.getElementById('startButton');
        const resetButton = document.getElementById('resetButton');

        function updateTimer() {
            const formattedMinutes = String(minutes).padStart(2, '0');
            const formattedSeconds = String(seconds).padStart(2, '0');
            timerDisplay.innerText = `${formattedMinutes}:${formattedSeconds}`;
        }

        function startTimer() {
            if (!isRunning) {
                isRunning = true;
                timer = setInterval(function () {
                    if (minutes === 0 && seconds === 0) {
                        clearInterval(timer);
                        isRunning = false;
                    } else if (seconds === 0) {
                        minutes--;
                        seconds = 59;
                    } else {
                        seconds--;
                    }
                    updateTimer();
                }, 1000);
            }
        }

        function resetTimer() {
            clearInterval(timer);
            minutes = 25;
            seconds = 0;
            isRunning = false;
            updateTimer();
        }

        startButton.addEventListener('click', startTimer);
        resetButton.addEventListener('click', resetTimer);
        resetTimer(); // بدء المؤقت عند تحميل الصفحة
    </script>
</body>
</html>
