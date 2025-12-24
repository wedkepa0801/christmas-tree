<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>圣诞快乐🎄</title>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { 
            background: #000814; 
            min-height: 100vh; 
            display: flex; 
            justify-content: center; 
            align-items: center; 
            overflow: hidden;
        }
        /* 雪花动画 */
        .snow {
            position: absolute;
            top: -10px;
            color: #fff;
            font-size: 12px;
            animation: snowfall linear infinite;
        }
        @keyframes snowfall {
            to { transform: translateY(100vh); }
        }
        /* 圣诞树主体 */
        .christmas-tree {
            position: relative;
            z-index: 10;
        }
        .tree-top {
            width: 0;
            height: 0;
            border-left: 60px solid transparent;
            border-right: 60px solid transparent;
            border-bottom: 90px solid #228B22;
            margin: 0 auto;
            filter: drop-shadow(0 0 5px #00ff41);
        }
        .tree-middle {
            width: 0;
            height: 0;
            border-left: 80px solid transparent;
            border-right: 80px solid transparent;
            border-bottom: 110px solid #228B22;
            margin: -20px auto 0;
            filter: drop-shadow(0 0 5px #00ff41);
        }
        .tree-bottom {
            width: 0;
            height: 0;
            border-left: 100px solid transparent;
            border-right: 100px solid transparent;
            border-bottom: 130px solid #228B22;
            margin: -20px auto 0;
            filter: drop-shadow(0 0 5px #00ff41);
        }
        .tree-trunk {
            width: 25px;
            height: 50px;
            background: #8B4513;
            margin: 0 auto;
            border-radius: 3px;
        }
        /* 闪烁装饰球 */
        .ornament {
            position: absolute;
            width: 18px;
            height: 18px;
            border-radius: 50%;
            animation: flash 1.5s infinite alternate;
        }
        @keyframes flash {
            from { filter: brightness(1); }
            to { filter: brightness(1.8); }
        }
        .ornament1 { top: 30px; left: 20px; background: #FF0000; }
        .ornament2 { top: 70px; right: 15px; background: #FFD700; }
        .ornament3 { top: 100px; left: 40px; background: #FF69B4; }
        .ornament4 { top: 140px; right: 30px; background: #00BFFF; }
        .ornament5 { top: 80px; left: 60px; background: #9370DB; }
        .ornament6 { top: 120px; right: 50px; background: #32CD32; }
        /* 星星 */
        .star {
            position: absolute;
            top: -20px;
            left: 50%;
            transform: translateX(-50%);
            font-size: 30px;
            color: #FFD700;
            animation: spin 5s linear infinite;
        }
        @keyframes spin {
            to { transform: translateX(-50%) rotate(360deg); }
        }
        /* 祝福语 */
        .text {
            position: absolute;
            bottom: 50px;
            color: #fff;
            font-size: 18px;
            text-align: center;
            font-family: "微软雅黑";
            text-shadow: 0 0 10px #fff;
        }
    </style>
</head>
<body>
    <div class="christmas-tree">
        <div class="star">⭐</div>
        <div class="tree-top"></div>
        <div class="tree-middle"></div>
        <div class="tree-bottom"></div>
        <div class="tree-trunk"></div>
        <div class="ornament ornament1"></div>
        <div class="ornament ornament2"></div>
        <div class="ornament ornament3"></div>
        <div class="ornament ornament4"></div>
        <div class="ornament ornament5"></div>
        <div class="ornament ornament6"></div>
    </div>
    <div class="text">圣诞快乐 🎁 平安喜乐</div>

    <!-- 圣诞音乐（自动播放，需用户点击页面后播放） -->
    <audio id="music" loop>
        <source src="https://freetestdata.com/wp-content/uploads/2021/09/Free_Test_Data_1MB_MP3.mp3" type="audio/mp3">
    </audio>

    <script>
        // 生成雪花
        function createSnow() {
            const snow = document.createElement('div');
            snow.className = 'snow';
            snow.textContent = '❄️';
            snow.style.left = Math.random() * 100 + 'vw';
            snow.style.animationDuration = Math.random() * 5 + 5 + 's';
            snow.style.opacity = Math.random() * 0.8 + 0.2;
            document.body.appendChild(snow);
            setTimeout(() => snow.remove(), 10000);
        }
        setInterval(createSnow, 200);

        // 点击页面播放音乐
        document.addEventListener('click', () => {
            const music = document.getElementById('music');
            music.play().catch(err => console.log('需手动点击播放音乐'));
        });
    </script>
</body>
</html>
