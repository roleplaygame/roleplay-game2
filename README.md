# roleplay-game2<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>情侣挑战任务</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #ff9a9e, #fad0c4);
            color: #333;
            height: 100vh;
            margin: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }
        .container {
            width: 90%;
            max-width: 800px;
            background: rgba(255,255,255,0.9);
            border-radius: 15px;
            padding: 20px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        h1 {
            color: #d23669;
            text-align: center;
        }
        .buttons {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 30px 0;
        }
        button {
            padding: 12px 25px;
            font-size: 16px;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s;
            font-weight: bold;
        }
        #generateMale {
            background: #5d69b3;
            color: white;
        }
        #generateFemale {
            background: #e84393;
            color: white;
        }
        button:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 10px rgba(0,0,0,0.2);
        }
        .result {
            margin-top: 30px;
            padding: 20px;
            border-radius: 10px;
            min-height: 100px;
            display: flex;
            flex-direction: column;
            gap: 15px;
        }
        .task {
            padding: 15px;
            border-radius: 8px;
            font-size: 18px;
            animation: fadeIn 0.5s;
        }
        .male-task {
            background: rgba(93, 105, 179, 0.2);
            border-left: 5px solid #5d69b3;
        }
        .female-task {
            background: rgba(232, 67, 147, 0.2);
            border-left: 5px solid #e84393;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .disclaimer {
            margin-top: 30px;
            font-size: 12px;
            color: #666;
            text-align: center;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>❤️ 情侣挑战任务 ❤️</h1>
        
        <div class="buttons">
            <button id="generateMale">生成男生任务</button>
            <button id="generateFemale">生成女生任务</button>
        </div>
        
        <div class="result" id="result">
            <!-- 任务将在这里显示 -->
        </div>
        
        <p class="disclaimer">注意：请确保所有活动都是双方完全自愿，并提前设立安全词</p>
    </div>

    <script>
        const maleTasks = [
            "跪在地上完成整场游戏",
            "吃女生双脚各十秒",
            "脱光衣服",
            "让女生扇三个嘴巴",
            "用嘴帮女生脱掉一件衣物",
            "全程只能用一只手触碰女生",
            "模仿女生指定的动物叫声",
            "被女生用口红在身上写字",
            "全程必须称呼女生为'女王大人'",
            "用舌头在女生手心写指定字母"
        ];
        
        const femaleTasks = [
            "骑在男生背上完成整场游戏",
            "用脚踩男生胸口十秒",
            "只穿内衣进行游戏",
            "扇男生三个嘴巴",
            "用嘴给男生喂一颗水果",
            "全程必须俯视男生",
            "在男生身上贴满便利贴",
            "用口红在男生脸上画画",
            "全程必须称呼男生为'小奴隶'",
            "用指甲在男生背上轻轻划圈"
        ];
        
        document.getElementById('generateMale').addEventListener('click', function() {
            generateTask('male');
        });
        
        document.getElementById('generateFemale').addEventListener('click', function() {
            generateTask('female');
        });
        
        function generateTask(gender) {
            const resultDiv = document.getElementById('result');
            resultDiv.innerHTML = '';
            
            const randomIndex = Math.floor(Math.random() * (gender === 'male' ? maleTasks : femaleTasks).length);
            const task = gender === 'male' ? maleTasks[randomIndex] : femaleTasks[randomIndex];
            
            const taskElement = document.createElement('div');
            taskElement.className = `task ${gender}-task`;
            taskElement.innerHTML = `<strong>${gender === 'male' ? '男生任务' : '女生任务'}:</strong> ${task}`;
            
            resultDiv.appendChild(taskElement);
        }
    </script>
</body>
</html>
