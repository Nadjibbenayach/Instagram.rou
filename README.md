<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="تطبيق متكامل لتحليل أداء اللاعبين وتحديد مركزهم بناءً على الإحصائيات والتحديات">
    <title>نظام الذكاء الاصطناعي لتقييم اللاعبين</title>
    <style>
        :root {
            --main-color: #FFD700;
            --secondary-color: #005B82;
        }

        body {
            font-family: 'Tajawal', sans-serif;
            background: linear-gradient(135deg, #1a1a1a, #2d2d2d);
            color: white;
            min-height: 100vh;
            margin: 0;
            transition: background 0.3s;
        }

        .container {
            max-width: 900px;
            margin: auto;
            padding: 20px;
            text-align: center;
        }

        .ai-section {
            background: rgba(0, 0, 0, 0.7);
            border-radius: 15px;
            padding: 20px;
            margin: 20px 0;
            backdrop-filter: blur(10px);
        }

        .skill-meter {
            width: 100%;
            height: 20px;
            background: #333;
            border-radius: 10px;
            margin: 10px 0;
            overflow: hidden;
        }

        .skill-fill {
            height: 100%;
            border-radius: 10px;
            background: var(--main-color);
            transition: width 1s ease-in-out;
        }

        .badge {
            display: inline-block;
            padding: 5px 10px;
            background: var(--secondary-color);
            border-radius: 15px;
            margin: 5px;
            animation: pop 0.5s ease-out;
        }

        @keyframes slideUp {
            from { transform: translateY(50px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        @keyframes pop {
            0% { transform: scale(0); }
            90% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }

        .result-box {
            margin-top: 20px;
            padding: 15px;
            border-radius: 10px;
            background: #444;
            animation: slideUp 0.5s ease-out;
        }

        .theme-picker {
            position: fixed;
            top: 10px;
            left: 10px;
        }

        .theme-btn {
            width: 30px;
            height: 30px;
            border-radius: 50%;
            margin: 5px;
            cursor: pointer;
            border: 2px solid white;
        }

        /* باقي الأنماط كما هي مع إضافة التحسينات */
    </style>
</head>
<body>
    <div class="theme-picker">
        <button class="theme-btn" style="background: #FFD700" onclick="changeTheme('gold')"></button>
        <button class="theme-btn" style="background: #00FF00" onclick="changeTheme('green')"></button>
        <button class="theme-btn" style="background: #0099FF" onclick="changeTheme('blue')"></button>
    </div>

    <div class="container">
        <h1>نظام الذكاء الاصطناعي لتقييم اللاعبين ⚽</h1>

        <!-- النموذج الأصلي هنا -->

        <div class="result-box" id="result-box" style="display: none;">
            <h2>نتيجة التحليل</h2>
            <div id="skill-meters"></div>
            <div id="achievements"></div>
            <div id="training-tips"></div>
            <h3>المركز المقترح: <span id="suggested-position"></span></h3>
            <div class="share-buttons">
                <button class="btn" onclick="shareResult()">مشاركة النتائج 📤</button>
            </div>
        </div>

        <div class="leaderboard">
            <h3>🏆 أفضل اللاعبين هذا الأسبوع</h3>
            <ol id="top-players">
                <li>جار التحميل...</li>
            </ol>
        </div>

        <div class="faq">
            <details>
                <summary>كيف يتم حساب النتائج؟</summary>
                <p>نستخدم خوارزميات ذكاء اصطناعي متقدمة تحلل أداءك في التحديات المختلفة...</p>
            </details>
        </div>
    </div>

    <script>
        // دالة التحليل الأساسية مع التحسينات
        function calculatePlayerStats() {
            // الحسابات الأصلية هنا

            // عرض النتائج الجديدة
            showResults(speed, passing, shooting, dribbling, physical, position);
            showAchievements(shooting, dribbling);
            showTrainingTips(position);
            updateLeaderboard();
        }

        function showResults(...scores) {
            const skills = ['السرعة', 'التمرير', 'التسديد', 'المراوغة', 'البدنية'];
            let html = '';
            
            scores.forEach((score, index) => {
                html += `
                    <div class="skill-meter">
                        <div class="skill-fill" style="width: ${score}%"></div>
                        <span>${skills[index]}: ${score}%</span>
                    </div>
                `;
            });
            
            document.getElementById("skill-meters").innerHTML = html;
        }

        function showAchievements(shooting, dribbling) {
            let badges = [];
            if (shooting >= 90) badges.push("نقّاب المرمى 🥅");
            if (dribbling >= 85) badges.push("ساحر الكرة 🎩");
            
            document.getElementById("achievements").innerHTML = 
                badges.map(b => `<div class="badge">${b}</div>`).join('');
        }

        function changeTheme(color) {
            const themes = {
                gold: ['#FFD700', '#005B82'],
                green: ['#00FF00', '#006400'],
                blue: ['#0099FF', '#00008B']
            };
            document.documentElement.style.setProperty('--main-color', themes[color][0]);
            document.documentElement.style.setProperty('--secondary-color', themes[color][1]);
        }

        function shareResult() {
            const results = `نتائج تحليل اللاعب:
سرعة: ${document.getElementById("speed-result").textContent}%
تمرير: ${document.getElementById("passing-result").textContent}% 
شارك التحدي! ⚽`;
            
            window.open(`https://twitter.com/intent/tweet?text=${encodeURIComponent(results)}`);
        }

        // باقي الدوال الجديدة
    </script>
</body>
</html># Instagram.rou
Website for sharing information 
