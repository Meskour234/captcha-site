<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Captcha</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            direction: rtl; /* Added for right-to-left text direction */
        }
        .captcha-container {
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            text-align: center;
        }
        h1 {
            margin-bottom: 20px;
        }
        select {
            margin-bottom: 20px;
            padding: 5px;
        }
        .offer {
            margin-bottom: 20px;
        }
        .offer a {
            display: inline-block;
            padding: 10px 20px;
            background-color: #007bff;
            color: #fff;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            text-decoration: none;
        }
        .offer a:hover {
            background-color: #0056b3;
        }
        .timer {
            font-size: 2em;
            margin-bottom: 20px;
        }
    </style>
</head>
<body>
    <div class="captcha-container">
        <h1>re CAPTCHA</h1>
        <select>
            <option value="ar">اختر اللغة</option>
            <option value="en">English</option>
            <!-- Add other languages as needed -->
        </select>
        <p>أكمل عرضًا واحدًا أدناه، لإثبات أنك لست روبوتًا. لا تقلق، إنه سهل للغاية!</p>
        <div class="offer">
            <a href="https://www.opera.com/gx" target="_blank" onclick="startTimer()">تحميل وتشغيل متصفح OperaGX!</a>
        </div>
        <div id="timer" class="timer">10:00</div>
        <p>ستفتح هذه الصفحة تلقائيًا، وستُسلم مواردك إلى اسم المستخدم الخاص بك قريبًا.</p>
    </div>
    <script>
        function startTimer() {
            var timer = document.getElementById('timer');
            var time = timer.innerHTML.split(':');
            var minutes = parseInt(time[0]);
            var seconds = parseInt(time[1]);

            var interval = setInterval(function() {
                if (seconds === 0 && minutes === 0) {
                    clearInterval(interval);
                    // Add the action to be performed when the timer ends
                    alert('انتهى الوقت!');
                } else {
                    if (seconds === 0) {
                        minutes--;
                        seconds = 59;
                    } else {
                        seconds--;
                    }
                    timer.innerHTML = `${minutes < 10 ? '0' + minutes : minutes}:${seconds < 10 ? '0' + seconds : seconds}`;
                }
            }, 1000);
        }
    </script>
</body>
</html>
# captcha-site
captcha
