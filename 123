<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>词汇记忆挑战 - ESL B1学习者</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f5f7fa;
            color: #333;
            line-height: 1.6;
            padding: 20px;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        header {
            text-align: center;
            margin-bottom: 30px;
            padding: 20px;
            background: linear-gradient(135deg, #4b6cb7 0%, #182848 100%);
            color: white;
            border-radius: 12px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        h1 {
            font-size: 2.5rem;
            margin-bottom: 10px;
        }
        
        .subtitle {
            font-size: 1.2rem;
            opacity: 0.9;
        }
        
        .game-container {
            display: flex;
            flex-direction: column;
            gap: 25px;
        }
        
        .control-panel {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: center;
            background-color: white;
            padding: 20px;
            border-radius: 12px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }
        
        .mode-selector {
            display: flex;
            gap: 10px;
        }
        
        .mode-btn {
            padding: 10px 20px;
            border: none;
            background-color: #e9ecef;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s ease;
        }
        
        .mode-btn.active {
            background-color: #4b6cb7;
            color: white;
        }
        
        .mode-btn:hover:not(.active) {
            background-color: #d0d7e2;
        }
        
        .progress-info {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .progress-bar {
            width: 200px;
            height: 10px;
            background-color: #e9ecef;
            border-radius: 5px;
            overflow: hidden;
        }
        
        .progress-fill {
            height: 100%;
            background-color: #4CAF50;
            width: 0%;
            transition: width 0.5s ease;
        }
        
        .game-area {
            display: flex;
            flex-direction: column;
            gap: 25px;
        }
        
        .flashcard-container, .match-container, .spell-container {
            background-color: white;
            border-radius: 12px;
            padding: 30px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            display: none;
        }
        
        .active-game {
            display: block;
            animation: fadeIn 0.5s ease;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        .card {
            perspective: 1000px;
            width: 100%;
            height: 300px;
            margin: 0 auto;
        }
        
        .card-inner {
            position: relative;
            width: 100%;
            height: 100%;
            text-align: center;
            transition: transform 0.8s;
            transform-style: preserve-3d;
            cursor: pointer;
        }
        
        .card.flipped .card-inner {
            transform: rotateY(180deg);
        }
        
        .card-front, .card-back {
            position: absolute;
            width: 100%;
            height: 100%;
            backface-visibility: hidden;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            border-radius: 12px;
            padding: 30px;
        }
        
        .card-front {
            background-color: #4b6cb7;
            color: white;
        }
        
        .card-back {
            background-color: #f8f9fa;
            color: #333;
            transform: rotateY(180deg);
            border: 2px solid #4b6cb7;
        }
        
        .word {
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 15px;
        }
        
        .phonetic {
            font-size: 1.5rem;
            font-style: italic;
            margin-bottom: 20px;
            opacity: 0.9;
        }
        
        .meaning {
            font-size: 2.2rem;
            font-weight: 600;
            margin-bottom: 15px;
            color: #182848;
        }
        
        .example {
            font-size: 1.2rem;
            font-style: italic;
            color: #666;
        }
        
        .card-controls {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-top: 25px;
        }
        
        .btn {
            padding: 12px 25px;
            border: none;
            border-radius: 8px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .btn-primary {
            background-color: #4b6cb7;
            color: white;
        }
        
        .btn-primary:hover {
            background-color: #3a5aa0;
        }
        
        .btn-success {
            background-color: #4CAF50;
            color: white;
        }
        
        .btn-success:hover {
            background-color: #3d8b40;
        }
        
        .btn-secondary {
            background-color: #6c757d;
            color: white;
        }
        
        .btn-secondary:hover {
            background-color: #545b62;
        }
        
        .match-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }
        
        .match-card {
            height: 120px;
            background-color: #f8f9fa;
            border-radius: 8px;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 1.3rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            text-align: center;
            padding: 15px;
            border: 2px solid transparent;
        }
        
        .match-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .match-card.selected {
            border-color: #4b6cb7;
            background-color: #e7f0ff;
        }
        
        .match-card.matched {
            border-color: #4CAF50;
            background-color: #e8f5e9;
            cursor: default;
        }
        
        .match-card.matched:hover {
            transform: none;
            box-shadow: none;
        }
        
        .spell-input-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 25px;
            margin-top: 20px;
        }
        
        .spell-question {
            font-size: 1.8rem;
            text-align: center;
            margin-bottom: 10px;
        }
        
        .spell-input {
            width: 100%;
            max-width: 500px;
            padding: 15px;
            font-size: 1.5rem;
            border: 2px solid #ddd;
            border-radius: 8px;
            text-align: center;
        }
        
        .spell-input:focus {
            outline: none;
            border-color: #4b6cb7;
        }
        
        .hint {
            font-size: 1.2rem;
            color: #666;
            font-style: italic;
        }
        
        .feedback {
            padding: 15px;
            border-radius: 8px;
            font-weight: 600;
            text-align: center;
            margin-top: 20px;
            display: none;
        }
        
        .feedback.correct {
            background-color: #e8f5e9;
            color: #2e7d32;
            display: block;
        }
        
        .feedback.incorrect {
            background-color: #ffebee;
            color: #c62828;
            display: block;
        }
        
        .vocab-list {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 15px;
            margin-top: 20px;
        }
        
        .vocab-item {
            background-color: white;
            padding: 15px;
            border-radius: 8px;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.05);
            border-left: 4px solid #4b6cb7;
        }
        
        .vocab-word {
            font-weight: 700;
            font-size: 1.3rem;
            margin-bottom: 5px;
        }
        
        .vocab-meaning {
            color: #666;
        }
        
        footer {
            text-align: center;
            margin-top: 40px;
            padding-top: 20px;
            border-top: 1px solid #ddd;
            color: #666;
            font-size: 0.9rem;
        }
        
        @media (max-width: 768px) {
            .control-panel {
                flex-direction: column;
                gap: 20px;
            }
            
            .match-grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
            
            .word {
                font-size: 2.5rem;
            }
            
            .meaning {
                font-size: 1.8rem;
            }
        }
    </style>
</head>
<body>
    <header>
        <h1>词汇记忆挑战</h1>
        <p class="subtitle">ESL B1学习者 - 记住生词的发音和中文意思</p>
    </header>
    
    <div class="game-container">
        <div class="control-panel">
            <div class="mode-selector">
                <button class="mode-btn active" data-mode="flashcard">闪卡学习</button>
                <button class="mode-btn" data-mode="match">匹配游戏</button>
                <button class="mode-btn" data-mode="spell">拼写练习</button>
                <button class="mode-btn" data-mode="list">词汇列表</button>
            </div>
            
            <div class="progress-info">
                <span>进度: <span id="progress-text">0/25</span></span>
                <div class="progress-bar">
                    <div class="progress-fill" id="progress-fill"></div>
                </div>
            </div>
        </div>
        
        <div class="game-area">
            <!-- 闪卡模式 -->
            <div id="flashcard-container" class="flashcard-container active-game">
                <h2>闪卡学习</h2>
                <p>点击卡片查看单词意思和例句，使用按钮进行导航</p>
                
                <div class="card" id="flashcard">
                    <div class="card-inner">
                        <div class="card-front">
                            <div class="word" id="card-word">appearance</div>
                            <div class="phonetic" id="card-phonetic">/əˈpɪrəns/</div>
                            <p>点击卡片查看中文意思</p>
                        </div>
                        <div class="card-back">
                            <div class="meaning" id="card-meaning">外表，外观</div>
                            <div class="example" id="card-example">His appearance changed after he lost weight.</div>
                            <p>点击卡片返回</p>
                        </div>
                    </div>
                </div>
                
                <div class="card-controls">
                    <button class="btn btn-secondary" id="prev-btn">上一个</button>
                    <button class="btn btn-primary" id="speak-btn">发音</button>
                    <button class="btn btn-success" id="master-btn">已掌握</button>
                    <button class="btn btn-secondary" id="next-btn">下一个</button>
                </div>
            </div>
            
            <!-- 匹配游戏模式 -->
            <div id="match-container" class="match-container">
                <h2>匹配游戏</h2>
                <p>点击一个英文单词，然后点击对应的中文意思进行匹配</p>
                
                <div class="match-grid" id="match-grid">
                    <!-- 匹配卡片会通过JavaScript动态生成 -->
                </div>
                
                <div class="feedback" id="match-feedback"></div>
                
                <div style="text-align: center; margin-top: 25px;">
                    <button class="btn btn-primary" id="reset-match-btn">重新开始匹配游戏</button>
                </div>
            </div>
            
            <!-- 拼写练习模式 -->
            <div id="spell-container" class="spell-container">
                <h2>拼写练习</h2>
                <p>根据中文意思拼写正确的英文单词</p>
                
                <div class="spell-input-container">
                    <div class="spell-question" id="spell-question">根据中文意思拼写单词：外表，外观</div>
                    <input type="text" class="spell-input" id="spell-input" placeholder="输入英文单词">
                    <div class="hint" id="spell-hint">提示: 单词以 'a' 开头，有 10 个字母</div>
                    
                    <div>
                        <button class="btn btn-primary" id="check-spell-btn">检查答案</button>
                        <button class="btn btn-secondary" id="next-spell-btn">跳过</button>
                    </div>
                </div>
                
                <div class="feedback" id="spell-feedback"></div>
            </div>
            
            <!-- 词汇列表模式 -->
            <div id="list-container" class="spell-container">
                <h2>词汇列表</h2>
                <p>所有需要掌握的单词列表，点击单词可以听发音</p>
                
                <div class="vocab-list" id="vocab-list">
                    <!-- 词汇列表会通过JavaScript动态生成 -->
                </div>
            </div>
        </div>
    </div>
    
    <footer>
        <p>词汇记忆挑战游戏 - 专为ESL B1学习者设计 | 使用浏览器内置语音合成发音</p>
    </footer>

    <script>
        // 词汇数据
        const vocabulary = [
            { word: "appearance", phonetic: "/əˈpɪrəns/", meaning: "外表，外观", example: "His appearance changed after he lost weight." },
            { word: "absolutely", phonetic: "/ˈæbsəˌlutli/", meaning: "绝对地，完全地", example: "I absolutely agree with your opinion." },
            { word: "actually", phonetic: "/ˈæktʃuəli/", meaning: "实际上，事实上", example: "He looks young, but actually he's over 50." },
            { word: "admire", phonetic: "/ədˈmaɪər/", meaning: "钦佩，欣赏", example: "I admire her courage and determination." },
            { word: "advantage", phonetic: "/ədˈvæntɪdʒ/", meaning: "优势，好处", example: "One advantage of living here is the low cost of living." },
            { word: "advertisement", phonetic: "/ˌædvərˈtaɪzmənt/", meaning: "广告", example: "I saw an advertisement for that product on TV." },
            { word: "advise", phonetic: "/ədˈvaɪz/", meaning: "建议，劝告", example: "I advise you to study harder for the exam." },
            { word: "achievement", phonetic: "/əˈtʃivmənt/", meaning: "成就，成绩", example: "Winning the competition was a great achievement." },
            { word: "annoying", phonetic: "/əˈnɔɪɪŋ/", meaning: "恼人的，讨厌的", example: "The constant noise from the street is annoying." },
            { word: "ancient", phonetic: "/ˈeɪnʃənt/", meaning: "古代的，古老的", example: "We visited ancient ruins in Greece." },
            { word: "ambition", phonetic: "/æmˈbɪʃən/", meaning: "雄心，抱负", example: "Her ambition is to become a doctor." },
            { word: "apply", phonetic: "/əˈplaɪ/", meaning: "申请，应用", example: "I will apply for the scholarship next month." },
            { word: "assist", phonetic: "/əˈsɪst/", meaning: "帮助，协助", example: "Can you assist me with this heavy box?" },
            { word: "attention", phonetic: "/əˈtɛnʃən/", meaning: "注意力，关注", example: "Pay attention to the teacher's instructions." },
            { word: "author", phonetic: "/ˈɔθər/", meaning: "作者，作家", example: "She is the author of three bestselling novels." },
            { word: "attract", phonetic: "/əˈtrækt/", meaning: "吸引，引起", example: "The bright colors attract customers to the store." },
            { word: "basic", phonetic: "/ˈbeɪsɪk/", meaning: "基本的，基础的", example: "You need to learn basic grammar first." },
            { word: "band", phonetic: "/bænd/", meaning: "乐队，带子", example: "My favorite band will perform tonight." },
            { word: "believe", phonetic: "/bɪˈliv/", meaning: "相信，认为", example: "I believe we can finish this project on time." },
            { word: "benefit", phonetic: "/ˈbɛnəfɪt/", meaning: "好处，益处", example: "Regular exercise has many health benefits." },
            { word: "biology", phonetic: "/baɪˈɑlədʒi/", meaning: "生物学", example: "She is studying biology at university." },
            { word: "blame", phonetic: "/bleɪm/", meaning: "责备，责怪", example: "Don't blame others for your mistakes." },
            { word: "blood", phonetic: "/blʌd/", meaning: "血，血液", example: "The hospital needs more blood donors." },
            { word: "boring", phonetic: "/ˈbɔrɪŋ/", meaning: "无聊的，乏味的", example: "The lecture was so boring that I fell asleep." },
            { word: "broadcast", phonetic: "/ˈbrɔdkæst/", meaning: "广播，播送", example: "The news will be broadcast at 9 PM." },
            { word: "camera", phonetic: "/ˈkæmərə/", meaning: "照相机，摄像机", example: "I forgot to bring my camera to the party." },
            { word: "capital", phonetic: "/ˈkæpɪtl/", meaning: "首都，资本", example: "Beijing is the capital of China." },
            { word: "career", phonetic: "/kəˈrɪr/", meaning: "职业，事业", example: "He has had a successful career in finance." },
            { word: "brave", phonetic: "/breɪv/", meaning: "勇敢的，无畏的", example: "The brave firefighter saved the child." }
        ];

        // 游戏状态
        let currentMode = 'flashcard';
        let currentIndex = 0;
        let masteredWords = new Set();
        let matchCards = [];
        let selectedMatchCard = null;
        let matchedPairs = 0;
        let spellIndex = 0;

        // 初始化
        document.addEventListener('DOMContentLoaded', function() {
            // 设置初始进度
            updateProgress();
            
            // 初始化闪卡
            updateFlashcard();
            
            // 初始化匹配游戏
            initMatchGame();
            
            // 初始化拼写游戏
            initSpellGame();
            
            // 初始化词汇列表
            initVocabList();
            
            // 模式切换事件
            document.querySelectorAll('.mode-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    // 移除所有活动类
                    document.querySelectorAll('.mode-btn').forEach(b => b.classList.remove('active'));
                    // 添加当前活动类
                    this.classList.add('active');
                    
                    // 隐藏所有游戏区域
                    document.querySelectorAll('.game-area > div').forEach(div => {
                        div.classList.remove('active-game');
                    });
                    
                    // 显示所选模式
                    currentMode = this.dataset.mode;
                    document.getElementById(`${currentMode}-container`).classList.add('active-game');
                    
                    // 如果是匹配游戏，重新初始化
                    if (currentMode === 'match') {
                        initMatchGame();
                    }
                    
                    // 如果是拼写游戏，初始化新单词
                    if (currentMode === 'spell') {
                        initSpellGame();
                    }
                });
            });
            
            // 闪卡控制事件
            document.getElementById('prev-btn').addEventListener('click', prevWord);
            document.getElementById('next-btn').addEventListener('click', nextWord);
            document.getElementById('speak-btn').addEventListener('click', speakWord);
            document.getElementById('master-btn').addEventListener('click', toggleMastered);
            document.getElementById('flashcard').addEventListener('click', flipCard);
            
            // 匹配游戏事件
            document.getElementById('reset-match-btn').addEventListener('click', initMatchGame);
            
            // 拼写游戏事件
            document.getElementById('check-spell-btn').addEventListener('click', checkSpelling);
            document.getElementById('next-spell-btn').addEventListener('click', nextSpellWord);
            document.getElementById('spell-input').addEventListener('keypress', function(e) {
                if (e.key === 'Enter') {
                    checkSpelling();
                }
            });
            
            // 语音合成检查
            if (!('speechSynthesis' in window)) {
                alert("您的浏览器不支持语音合成功能，部分功能可能无法使用。");
            }
        });
        
        // 更新进度显示
        function updateProgress() {
            const progress = masteredWords.size;
            const total = vocabulary.length;
            const percentage = (progress / total) * 100;
            
            document.getElementById('progress-text').textContent = `${progress}/${total}`;
            document.getElementById('progress-fill').style.width = `${percentage}%`;
        }
        
        // 更新闪卡
        function updateFlashcard() {
            const word = vocabulary[currentIndex];
            document.getElementById('card-word').textContent = word.word;
            document.getElementById('card-phonetic').textContent = word.phonetic;
            document.getElementById('card-meaning').textContent = word.meaning;
            document.getElementById('card-example').textContent = word.example;
            
            // 重置卡片为正面
            document.getElementById('flashcard').classList.remove('flipped');
            
            // 更新掌握按钮状态
            const masterBtn = document.getElementById('master-btn');
            if (masteredWords.has(currentIndex)) {
                masterBtn.textContent = '取消掌握';
                masterBtn.classList.remove('btn-success');
                masterBtn.classList.add('btn-secondary');
            } else {
                masterBtn.textContent = '已掌握';
                masterBtn.classList.remove('btn-secondary');
                masterBtn.classList.add('btn-success');
            }
        }
        
        // 上一个单词
        function prevWord() {
            currentIndex = (currentIndex - 1 + vocabulary.length) % vocabulary.length;
            updateFlashcard();
        }
        
        // 下一个单词
        function nextWord() {
            currentIndex = (currentIndex + 1) % vocabulary.length;
            updateFlashcard();
        }
        
        // 发音功能
        function speakWord() {
            const word = vocabulary[currentIndex].word;
            const utterance = new SpeechSynthesisUtterance(word);
            utterance.rate = 0.8; // 稍微放慢语速
            utterance.lang = 'en-US';
            window.speechSynthesis.speak(utterance);
        }
        
        // 切换单词掌握状态
        function toggleMastered() {
            if (masteredWords.has(currentIndex)) {
                masteredWords.delete(currentIndex);
            } else {
                masteredWords.add(currentIndex);
            }
            updateFlashcard();
            updateProgress();
        }
        
        // 翻转卡片
        function flipCard() {
            document.getElementById('flashcard').classList.toggle('flipped');
        }
        
        // 初始化匹配游戏
        function initMatchGame() {
            // 清空游戏区域
            const matchGrid = document.getElementById('match-grid');
            matchGrid.innerHTML = '';
            matchedPairs = 0;
            selectedMatchCard = null;
            
            // 清空反馈
            const feedback = document.getElementById('match-feedback');
            feedback.className = 'feedback';
            feedback.textContent = '';
            
            // 创建配对卡片
            matchCards = [];
            
            // 随机选择8个单词
            const shuffledVocabulary = [...vocabulary].sort(() => 0.5 - Math.random()).slice(0, 8);
            
            // 创建英文单词卡片
            shuffledVocabulary.forEach((word, index) => {
                matchCards.push({
                    id: `word-${index}`,
                    content: word.word,
                    meaning: word.meaning,
                    type: 'word'
                });
                
                matchCards.push({
                    id: `meaning-${index}`,
                    content: word.meaning,
                    word: word.word,
                    type: 'meaning'
                });
            });
            
            // 洗牌
            matchCards.sort(() => 0.5 - Math.random());
            
            // 添加到游戏区域
            matchCards.forEach(card => {
                const cardElement = document.createElement('div');
                cardElement.className = 'match-card';
                cardElement.id = card.id;
                cardElement.textContent = card.content;
                cardElement.addEventListener('click', () => selectMatchCard(card.id));
                matchGrid.appendChild(cardElement);
            });
        }
        
        // 选择匹配卡片
        function selectMatchCard(cardId) {
            const cardElement = document.getElementById(cardId);
            const card = matchCards.find(c => c.id === cardId);
            
            // 如果卡片已经匹配，不做任何操作
            if (cardElement.classList.contains('matched')) {
                return;
            }
            
            // 如果已经选择了一张卡片
            if (selectedMatchCard) {
                // 如果点击了同一张卡片，取消选择
                if (selectedMatchCard === cardId) {
                    cardElement.classList.remove('selected');
                    selectedMatchCard = null;
                    return;
                }
                
                const firstCardElement = document.getElementById(selectedMatchCard);
                const firstCard = matchCards.find(c => c.id === selectedMatchCard);
                
                // 检查是否匹配
                if (
                    (firstCard.type === 'word' && card.type === 'meaning' && firstCard.content === card.word) ||
                    (firstCard.type === 'meaning' && card.type === 'word' && firstCard.word === card.content)
                ) {
                    // 匹配成功
                    cardElement.classList.add('matched');
                    firstCardElement.classList.add('matched');
                    matchedPairs++;
                    
                    // 显示反馈
                    const feedback = document.getElementById('match-feedback');
                    feedback.textContent = `匹配成功！${firstCard.content} - ${card.content}`;
                    feedback.className = 'feedback correct';
                    
                    // 检查游戏是否完成
                    if (matchedPairs === 8) {
                        setTimeout(() => {
                            feedback.textContent = '恭喜！你完成了匹配游戏！';
                        }, 500);
                    }
                } else {
                    // 匹配失败
                    cardElement.classList.add('selected');
                    
                    // 显示反馈
                    const feedback = document.getElementById('match-feedback');
                    feedback.textContent = '不匹配，再试一次！';
                    feedback.className = 'feedback incorrect';
                    
                    // 1秒后重置选择
                    setTimeout(() => {
                        cardElement.classList.remove('selected');
                        firstCardElement.classList.remove('selected');
                        feedback.className = 'feedback';
                        feedback.textContent = '';
                    }, 1000);
                }
                
                selectedMatchCard = null;
            } else {
                // 选择第一张卡片
                cardElement.classList.add('selected');
                selectedMatchCard = cardId;
                
                // 清空反馈
                const feedback = document.getElementById('match-feedback');
                feedback.className = 'feedback';
                feedback.textContent = '';
            }
        }
        
        // 初始化拼写游戏
        function initSpellGame() {
            // 随机选择一个单词
            spellIndex = Math.floor(Math.random() * vocabulary.length);
            const word = vocabulary[spellIndex];
            
            // 更新问题
            document.getElementById('spell-question').textContent = `根据中文意思拼写单词：${word.meaning}`;
            
            // 更新提示
            const hint = `提示: 单词以 '${word.word.charAt(0).toLowerCase()}' 开头，有 ${word.word.length} 个字母`;
            document.getElementById('spell-hint').textContent = hint;
            
            // 清空输入和反馈
            document.getElementById('spell-input').value = '';
            const feedback = document.getElementById('spell-feedback');
            feedback.className = 'feedback';
            feedback.textContent = '';
            
            // 聚焦输入框
            document.getElementById('spell-input').focus();
        }
        
        // 检查拼写
        function checkSpelling() {
            const userInput = document.getElementById('spell-input').value.trim().toLowerCase();
            const correctWord = vocabulary[spellIndex].word.toLowerCase();
            const feedback = document.getElementById('spell-feedback');
            
            if (userInput === correctWord) {
                // 拼写正确
                feedback.textContent = `正确！${vocabulary[spellIndex].word} 的意思是 "${vocabulary[spellIndex].meaning}"`;
                feedback.className = 'feedback correct';
                
                // 3秒后跳转到下一个单词
                setTimeout(() => {
                    nextSpellWord();
                }, 2000);
            } else {
                // 拼写错误
                feedback.textContent = `不正确。正确答案是: ${vocabulary[spellIndex].word}`;
                feedback.className = 'feedback incorrect';
            }
        }
        
        // 下一个拼写单词
        function nextSpellWord() {
            initSpellGame();
        }
        
        // 初始化词汇列表
        function initVocabList() {
            const vocabList = document.getElementById('vocab-list');
            vocabList.innerHTML = '';
            
            vocabulary.forEach((word, index) => {
                const item = document.createElement('div');
                item.className = 'vocab-item';
                item.innerHTML = `
                    <div class="vocab-word">${word.word}</div>
                    <div class="vocab-phonetic">${word.phonetic}</div>
                    <div class="vocab-meaning">${word.meaning}</div>
                `;
                
                // 添加点击发音功能
                item.addEventListener('click', () => {
                    const utterance = new SpeechSynthesisUtterance(word.word);
                    utterance.rate = 0.8;
                    utterance.lang = 'en-US';
                    window.speechSynthesis.speak(utterance);
                });
                
                vocabList.appendChild(item);
            });
        }
    </script>
</body>
</html>
