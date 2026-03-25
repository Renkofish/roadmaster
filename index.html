<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>城市生活規劃挑戰 - 連續疾走</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Noto+Sans+TC:wght@400;500;700;900&display=swap');
        
        :root {
            --latte-bg: #f3e9dc; 
            --amber-deep: #5e3023; 
            --accent-gold: #c08552; 
            --glow-color: #ffb703; 
            --text-dark: #2d1600;
        }

        body { 
            font-family: 'Noto Sans TC', sans-serif; 
            background-color: var(--latte-bg);
            color: var(--text-dark);
            overflow: hidden;
        }

        .glass-panel {
            background: rgba(255, 255, 255, 0.97);
            backdrop-filter: blur(10px);
            border: 3px solid var(--amber-deep);
            box-shadow: 0 6px 20px rgba(0,0,0,0.1);
        }

        .current-location-glow {
            stroke: var(--glow-color) !important;
            stroke-width: 14px !important;
            filter: drop-shadow(0 0 18px var(--glow-color));
        }

        .location-node { cursor: pointer; transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1); }
        .location-node:hover { filter: brightness(1.1); transform: translateY(-2px); }

        .route-line { 
            stroke-dasharray: 8;
            animation: flow 35s linear infinite;
            stroke-opacity: 0.5;
        }
        @keyframes flow { to { stroke-dashoffset: 1000; } }

        .map-text {
            font-size: 24px;
            font-weight: 900;
            paint-order: stroke;
            stroke: #fff;
            stroke-width: 6px;
        }

        .time-text {
            font-size: 16px;
            font-weight: 800;
            fill: #d00000;
            paint-order: stroke;
            stroke: #fff;
            stroke-width: 4px;
        }

        .route-label-text {
            font-size: 18px;
            font-weight: 900;
            fill: var(--amber-deep);
            paint-order: stroke;
            stroke: #fff;
            stroke-width: 5px;
        }
        .route-sub-text {
            font-size: 16px;
            font-weight: 800;
            fill: #895737;
        }

        .btn-warm {
            background: linear-gradient(135deg, #a68a64, #5e3023);
            color: white;
            box-shadow: 0 6px 12px rgba(0,0,0,0.2);
            transition: all 0.2s;
        }
        .btn-warm:hover { transform: scale(1.02); filter: brightness(1.1); }
    </style>
</head>
<body class="h-screen w-screen flex flex-col">

    <!-- 開始/劇情介面 -->
    <div id="start-screen" class="fixed inset-0 z-[100] flex items-center justify-center bg-[#f3e9dc]">
        <div class="max-w-2xl w-full p-8 text-center">
            <div class="bg-white p-12 rounded-[2.5rem] shadow-2xl border-4 border-[#5e3023] mb-8">
                <div id="intro-icon" class="text-7xl mb-6">☕</div>
                <h1 id="intro-title" class="text-4xl font-black text-[#5e3023] mb-8 tracking-tight">忙碌週三的清單</h1>
                <div id="intro-text" class="text-[#5e3023] text-xl text-left font-medium leading-relaxed space-y-6">
                    <p>今天的行程比想像中擁擠。原本只想安靜地過個週三，但剛剛才想起下午三點前要完成房租匯款，否則房東又要嘮叨了。</p>
                    <p>除了日常要跑的診所拿藥、去市場補點菜，傍晚六點還有一場觀望已久的面試。對了，圖書館的那本書也到期了。</p>
                    <p class="font-bold text-[#895737] border-l-8 border-[#895737] pl-6 text-2xl">現在是早上八點，規劃你的路線，從容完成這一切吧！</p>
                </div>
                <button onclick="startGame()" class="btn-warm mt-12 px-20 py-5 rounded-full text-2xl font-bold tracking-wide">
                    開始行動
                </button>
            </div>
        </div>
    </div>

    <!-- 狀態列 -->
    <div class="h-24 glass-panel border-b-4 border-amber-900/20 flex items-center justify-between px-12 z-10">
        <div class="flex items-center gap-8">
            <div id="lvl-badge" class="p-4 bg-[#5e3023] rounded-2xl text-3xl shadow-md text-white">1</div>
            <div>
                <h1 id="level-name" class="text-2xl font-black text-[#5e3023]">第一關：平凡週三</h1>
                <p class="text-base font-bold text-[#895737]">當前：<span id="current-loc-name" class="bg-white px-3 py-1 rounded shadow-sm">溫馨起點</span></p>
            </div>
        </div>

        <div class="flex gap-12">
            <div class="text-center">
                <p class="text-xs font-black text-[#895737] uppercase tracking-widest mb-1">目前時間</p>
                <p id="current-time" class="text-3xl font-black text-[#5e3023]">08:00</p>
            </div>
            <div class="text-center">
                <p class="text-xs font-black text-[#895737] uppercase tracking-widest mb-1">錢包餘額</p>
                <p id="current-money" class="text-3xl font-black text-green-800">$800</p>
            </div>
        </div>
    </div>

    <div class="flex-1 flex overflow-hidden">
        <div class="w-96 glass-panel border-r-4 border-amber-900/20 p-8 flex flex-col gap-8 overflow-y-auto">
            <div class="flex items-center justify-between border-b-2 border-amber-100 pb-3">
                <h3 class="text-xl font-black text-[#5e3023]">📝 任務清單</h3>
                <span id="task-progress" class="text-sm bg-[#5e3023] text-white px-3 py-1 rounded-full">0/5</span>
            </div>
            <div id="task-list" class="space-y-4"></div>
            
            <div class="mt-auto bg-amber-50 p-6 rounded-3xl border-2 border-amber-100">
                <h4 class="font-bold text-base text-[#5e3023] mb-2">💡 小叮嚀</h4>
                <p id="level-hint" class="text-sm text-[#895737] leading-relaxed">銀行 15:00 關門。注意交通成本，不要讓錢包見底！</p>
            </div>
        </div>

        <!-- 地圖區域 -->
        <div class="flex-1 relative bg-[#f1f1f1] overflow-hidden">
            <div id="map-container" class="w-full h-full origin-top-left transition-transform duration-300" style="transform: scale(1.2);">
                <svg id="map-svg" viewBox="0 0 1400 900" class="w-full h-full">
                    <g id="connections"></g>
                    <g id="nodes"></g>
                </svg>
            </div>

            <div class="absolute bottom-10 right-10 flex flex-col gap-4">
                <button onclick="zoomMap(1.2)" class="w-14 h-14 bg-white rounded-2xl flex items-center justify-center text-2xl shadow-xl border-2 border-[#5e3023]/20 hover:bg-amber-50">＋</button>
                <button onclick="zoomMap(0.8)" class="w-14 h-14 bg-white rounded-2xl flex items-center justify-center text-2xl shadow-xl border-2 border-[#5e3023]/20 hover:bg-amber-50">－</button>
            </div>
        </div>
    </div>

    <!-- 事件視窗 -->
    <div id="event-modal" class="hidden fixed inset-0 z-50 flex items-center justify-center p-6 bg-black/40 backdrop-blur-sm">
        <div class="bg-white border-4 border-[#5e3023] rounded-[2.5rem] p-12 max-w-md w-full text-center shadow-2xl">
            <div class="text-7xl mb-6">🔔</div>
            <h3 id="card-name" class="text-3xl font-black text-[#5e3023] mb-4">突發狀況</h3>
            <p id="card-desc" class="text-xl font-medium text-[#895737] mb-10">描述內容...</p>
            <button onclick="closeEventModal()" class="btn-warm w-full py-5 rounded-2xl font-bold text-xl">了解</button>
        </div>
    </div>

    <!-- 結算視窗 -->
    <div id="result-modal" class="hidden fixed inset-0 z-50 flex items-center justify-center p-6 bg-[#5e3023]/95">
        <div class="text-center text-white p-10">
            <div id="result-icon" class="text-9xl mb-10">🍵</div>
            <h3 id="result-title" class="text-5xl font-black mb-6">任務完結</h3>
            <p id="result-msg" class="text-2xl font-medium mb-12 max-w-lg mx-auto opacity-90">訊息內容...</p>
            <div id="result-btns" class="flex flex-col gap-4 items-center">
                <button id="next-level-btn" onclick="goToNextLevel()" class="hidden bg-[#ffb703] text-black px-16 py-5 rounded-full font-black text-2xl hover:scale-105 transition shadow-2xl">挑戰下一關</button>
                <button onclick="location.reload()" class="bg-white text-[#5e3023] px-16 py-5 rounded-full font-black text-2xl hover:bg-amber-100 shadow-2xl">重頭開始</button>
            </div>
        </div>
    </div>

    <script>
        const locations = {
            'HOME': { id: 'HOME', name: '溫馨起點', x: 150, y: 450, open: 0, close: 24, color: '#5e3023', icon: '🏠' },
            'PARK': { id: 'PARK', name: '中央公園', x: 450, y: 450, open: 0, close: 24, color: '#2d6a4f', icon: '🌳' },
            'CAFE': { id: 'CAFE', name: '晨間咖啡', x: 350, y: 200, open: 7, close: 20, color: '#8b5e34', icon: '☕' },
            'CLINIC': { id: 'CLINIC', name: '社區診所', x: 650, y: 700, open: 9, close: 18, color: '#bc4749', icon: '🏥' },
            'BANK': { id: 'BANK', name: '金融中心', x: 800, y: 250, open: 9, close: 15, color: '#003049', icon: '🏦' },
            'MARKET': { id: 'MARKET', name: '老街市場', x: 1000, y: 550, open: 6, close: 14, color: '#bc4749', icon: '🍱' },
            'SHOP': { id: 'SHOP', name: '陽光超市', x: 750, y: 50, open: 8, close: 23, color: '#386641', icon: '🛒' },
            'STATION': { id: 'STATION', name: '核心樞紐', x: 1050, y: 300, open: 5, close: 24, color: '#3c096c', icon: '🚉' },
            'LIBRARY': { id: 'LIBRARY', name: '市立圖書', x: 1250, y: 650, open: 9, close: 21, color: '#5e3023', icon: '📖' },
            'OFFICE': { id: 'OFFICE', name: '商務大樓', x: 1300, y: 150, open: 8, close: 18, color: '#000000', icon: '🏢' }
        };

        const routes = [
            { from: 'HOME', to: 'CAFE', time: 30, cost: 0, label: '步行', color: '#a68a64' },
            { from: 'HOME', to: 'PARK', time: 20, cost: 0, label: '步行', color: '#5e3023' },
            { from: 'CAFE', to: 'SHOP', time: 40, cost: 50, label: '公車', color: '#c08552' },
            { from: 'PARK', to: 'CLINIC', time: 35, cost: 40, label: '接駁車', color: '#c08552' },
            { from: 'PARK', to: 'BANK', time: 50, cost: 60, label: '公車', color: '#c08552' },
            { from: 'SHOP', to: 'BANK', time: 20, cost: 200, label: '計程車', color: '#bc4749' },
            { from: 'CLINIC', to: 'MARKET', time: 45, cost: 0, label: '慢走', color: '#a68a64' },
            { from: 'BANK', to: 'STATION', time: 15, cost: 80, label: '捷運', color: '#7b2cbf' },
            { from: 'MARKET', to: 'STATION', time: 25, cost: 50, label: '公車', color: '#c08552' },
            { from: 'STATION', to: 'LIBRARY', time: 30, cost: 60, label: '捷運', color: '#7b2cbf' },
            { from: 'STATION', to: 'OFFICE', time: 20, cost: 300, label: '特急車', color: '#5e3023' },
            { from: 'LIBRARY', to: 'OFFICE', time: 60, cost: 0, label: '散步', color: '#a68a64' },
            { from: 'BANK', to: 'OFFICE', time: 45, cost: 100, label: '公車', color: '#c08552' }
        ];

        const levelData = [
            {
                id: 1,
                name: "第一關：平凡週三",
                icon: "☕",
                introTitle: "忙碌週三的清單",
                introText: `<p>原本只想安靜度過週三，但下午三點前要完成房租匯款。</p><p>還要領藥、補菜、還書，以及一場傍晚六點的面試。</p>`,
                money: 800,
                time: 8.0,
                hint: "銀行 15:00 關門，市場 14:00 收攤。",
                tasks: [
                    { id: 1, desc: '匯出房租 (15:00 前)', target: 'BANK', done: false },
                    { id: 2, desc: '診所領取常備藥', target: 'CLINIC', done: false },
                    { id: 3, desc: '市場補菜 (14:00 前)', target: 'MARKET', done: false },
                    { id: 4, desc: '還書至圖書館', target: 'LIBRARY', done: false },
                    { id: 5, desc: '傍晚面試 (18:00 前)', target: 'OFFICE', done: false }
                ]
            },
            {
                id: 2,
                name: "第二關：狂歡週五",
                icon: "⚡",
                introTitle: "極限週五的生存戰",
                introText: `<p>今天是週五！你答應了死黨晚上七點要在核心樞紐見面去旅行。</p><p>但在那之前，你得幫老闆去商務大樓送急件(11:00前)、去銀行換外幣(15:00前)、去市場幫媽媽拿訂好的龍蝦(13:00前)、去超市買旅行零食，以及去診所拿過敏藥。</p>`,
                money: 650, // 預算更緊
                time: 9.0, // 起床更晚
                hint: "老闆的急件是第一優先！交通費變貴了，請謹慎選擇路線。",
                tasks: [
                    { id: 1, desc: '送達急件 (11:00 前)', target: 'OFFICE', done: false },
                    { id: 2, desc: '市場拿龍蝦 (13:00 前)', target: 'MARKET', done: false },
                    { id: 3, desc: '領取過敏藥', target: 'CLINIC', done: false },
                    { id: 4, desc: '銀行換外幣 (15:00 前)', target: 'BANK', done: false },
                    { id: 5, desc: '核心樞紐集合 (19:00)', target: 'STATION', done: false }
                ],
                routePriceMultiplier: 1.5, // 交通費漲價
                eventChance: 0.2 // 突發事件機率翻倍
            }
        ];

        let currentLvlIndex = 0;
        let state = {
            money: 0,
            time: 0,
            currentPos: 'HOME',
            zoom: 1.2,
            tasks: []
        };

        function setupLevel(idx) {
            const data = levelData[idx];
            state.money = data.money;
            state.time = data.time;
            state.tasks = JSON.parse(JSON.stringify(data.tasks));
            state.currentPos = 'HOME';

            // 更新介面內容
            document.getElementById('intro-icon').innerText = data.icon;
            document.getElementById('intro-title').innerText = data.introTitle;
            document.getElementById('intro-text').innerHTML = data.introText;
            document.getElementById('level-name').innerText = data.name;
            document.getElementById('lvl-badge').innerText = data.id;
            document.getElementById('level-hint').innerText = data.hint;
            document.getElementById('start-screen').classList.remove('hidden');
            
            initMap();
            updateUI();
        }

        function initMap() {
            const nodesG = document.getElementById('nodes');
            const linesG = document.getElementById('connections');
            linesG.innerHTML = ''; nodesG.innerHTML = '';

            const mult = levelData[currentLvlIndex].routePriceMultiplier || 1;

            routes.forEach(r => {
                const f = locations[r.from], t = locations[r.to];
                const finalCost = Math.round(r.cost * mult);

                const line = document.createElementNS("http://www.w3.org/2000/svg", "line");
                line.setAttribute("x1", f.x); line.setAttribute("y1", f.y);
                line.setAttribute("x2", t.x); line.setAttribute("y2", t.y);
                line.setAttribute("stroke", r.color); line.setAttribute("stroke-width", "8");
                line.setAttribute("class", "route-line");
                linesG.appendChild(line);

                const g = document.createElementNS("http://www.w3.org/2000/svg", "g");
                const main = document.createElementNS("http://www.w3.org/2000/svg", "text");
                main.setAttribute("x", (f.x + t.x)/2); main.setAttribute("y", (f.y + t.y)/2 - 26);
                main.setAttribute("class", "route-label-text"); main.setAttribute("text-anchor", "middle");
                main.textContent = `${r.label} $${finalCost}`;
                
                const sub = document.createElementNS("http://www.w3.org/2000/svg", "text");
                sub.setAttribute("x", (f.x + t.x)/2); sub.setAttribute("y", (f.y + t.y)/2 - 2);
                sub.setAttribute("class", "route-sub-text"); sub.setAttribute("text-anchor", "middle");
                sub.textContent = `${r.time}m`;

                g.appendChild(main); g.appendChild(sub);
                linesG.appendChild(g);
            });

            Object.values(locations).forEach(loc => {
                const g = document.createElementNS("http://www.w3.org/2000/svg", "g");
                g.setAttribute("class", "location-node");
                g.onclick = () => handleMove(loc.id);

                const c = document.createElementNS("http://www.w3.org/2000/svg", "circle");
                c.setAttribute("cx", loc.x); c.setAttribute("cy", loc.y);
                c.setAttribute("r", "40"); 
                c.setAttribute("fill", "#fff");
                c.setAttribute("stroke", loc.color); c.setAttribute("stroke-width", "5");
                c.id = `node-${loc.id}`;

                const ico = document.createElementNS("http://www.w3.org/2000/svg", "text");
                ico.setAttribute("x", loc.x); ico.setAttribute("y", loc.y + 14);
                ico.setAttribute("font-size", "36"); ico.setAttribute("text-anchor", "middle");
                ico.textContent = loc.icon;

                const name = document.createElementNS("http://www.w3.org/2000/svg", "text");
                const timeInfo = document.createElementNS("http://www.w3.org/2000/svg", "text");
                
                if (loc.id === 'SHOP') {
                    name.setAttribute("x", loc.x); name.setAttribute("y", loc.y - 80);
                    timeInfo.setAttribute("x", loc.x); timeInfo.setAttribute("y", loc.y - 55);
                    name.setAttribute("text-anchor", "middle");
                    timeInfo.setAttribute("text-anchor", "middle");
                } else if (loc.id === 'STATION') {
                    name.setAttribute("x", loc.x + 60); name.setAttribute("y", loc.y - 5);
                    timeInfo.setAttribute("x", loc.x + 60); timeInfo.setAttribute("y", loc.y + 20);
                    name.setAttribute("text-anchor", "start");
                    timeInfo.setAttribute("text-anchor", "start");
                } else {
                    name.setAttribute("x", loc.x); name.setAttribute("y", loc.y + 85);
                    timeInfo.setAttribute("x", loc.x); timeInfo.setAttribute("y", loc.y + 110);
                    name.setAttribute("text-anchor", "middle");
                    timeInfo.setAttribute("text-anchor", "middle");
                }

                name.setAttribute("class", "map-text");
                name.textContent = loc.name;
                timeInfo.setAttribute("class", "time-text");
                timeInfo.textContent = loc.open === 0 && loc.close === 24 ? "24H 營業" : `${loc.open}:00-${loc.close}:00`;

                g.appendChild(c); g.appendChild(ico); g.appendChild(name); g.appendChild(timeInfo);
                nodesG.appendChild(g);
            });
        }

        function handleMove(targetId) {
            if (targetId === state.currentPos) return;
            const r = routes.find(x => (x.from === state.currentPos && x.to === targetId) || (x.to === state.currentPos && x.from === targetId));
            if (!r) return;

            const mult = levelData[currentLvlIndex].routePriceMultiplier || 1;
            state.money -= Math.round(r.cost * mult);
            state.time += (r.time / 60);
            
            const targetLoc = locations[targetId];
            const arrivalHour = state.time % 24;
            if (arrivalHour < targetLoc.open) {
                state.time = Math.floor(state.time / 24) * 24 + targetLoc.open;
            }

            state.currentPos = targetId;

            const chance = levelData[currentLvlIndex].eventChance || 0.1;
            if (Math.random() < chance) {
                const c = [
                    { n: '大塞車', d: '路上遇到事故，整整塞了 40 分鐘', e: s => s.time += 0.66 },
                    { n: '捷運故障', d: '受困車廂內，多花了 30 分鐘', e: s => s.time += 0.5 },
                    { n: '錢包破損', d: '零錢掉一地，損失了 $50', e: s => s.money -= 50 }
                ][Math.floor(Math.random()*3)];
                document.getElementById('card-name').innerText = c.n;
                document.getElementById('card-desc').innerText = c.d;
                c.e(state);
                document.getElementById('event-modal').classList.remove('hidden');
            }
            checkLogic();
            updateUI();
        }

        function checkLogic() {
            const h = state.time % 24;
            const loc = locations[state.currentPos];
            
            // 處理關卡2的特殊時間限制
            if (currentLvlIndex === 1) {
                if (!state.tasks[0].done && h > 11) return end(false, "糟糕！老闆的急件送太遲了，你被開除了...");
                if (!state.tasks[1].done && h > 13) return end(false, "市場已經收攤，拿不到媽媽要的龍蝦了，今晚不敢回家...");
            } else {
                if (!state.tasks[2].done && h > 14) return end(false, "市場收攤了，沒買到晚餐食材。");
            }

            state.tasks.forEach(t => { if(t.target === state.currentPos) t.done = true; });

            if (state.money < 0) return end(false, "錢包完全空了！你沒錢坐車，只能在路邊徘徊...");
            if (h >= loc.close) return end(false, `${loc.name} 已結束營業，無法完成任務。`);
            
            if (state.tasks.every(t => t.done)) {
                if (currentLvlIndex < levelData.length - 1) {
                    end(true, "太出色了！你完成了今天的任務，但明天還有更大的挑戰等著你...", true);
                } else {
                    end(true, "恭喜！你成功的征服了這座城市的瘋狂生活。你是真正的規劃大師！");
                }
            }
        }

        function end(win, msg, showNext = false) {
            document.getElementById('result-modal').classList.remove('hidden');
            document.getElementById('result-icon').innerText = win ? "🏆" : "💤";
            document.getElementById('result-title').innerText = win ? "順利通關" : "未能趕上";
            document.getElementById('result-msg').innerText = msg;
            
            const nxtBtn = document.getElementById('next-level-btn');
            if (showNext) nxtBtn.classList.remove('hidden');
            else nxtBtn.classList.add('hidden');
        }

        function goToNextLevel() {
            currentLvlIndex++;
            document.getElementById('result-modal').classList.add('hidden');
            setupLevel(currentLvlIndex);
        }

        function updateUI() {
            const hr = Math.floor(state.time % 24), min = Math.round((state.time % 1)*60);
            document.getElementById('current-time').innerText = `${hr.toString().padStart(2,'0')}:${min.toString().padStart(2,'0')}`;
            document.getElementById('current-money').innerText = `$${state.money}`;
            document.getElementById('current-loc-name').innerText = locations[state.currentPos].name;

            const doneCount = state.tasks.filter(t => t.done).length;
            document.getElementById('task-progress').innerText = `${doneCount}/${state.tasks.length}`;

            document.getElementById('task-list').innerHTML = state.tasks.map(t => `
                <div class="p-4 rounded-2xl border-2 ${t.done ? 'bg-green-50 border-green-200 opacity-60' : 'bg-white border-[#5e3023]/20 shadow-sm'} flex items-center gap-4">
                    <span class="text-xl">${t.done ? '✅' : '📌'}</span>
                    <div class="flex flex-col">
                        <span class="text-base font-bold ${t.done ? 'line-through text-green-700' : 'text-[#5e3023]'}">${t.desc}</span>
                        <span class="text-xs text-amber-900/60">${locations[t.target].name}</span>
                    </div>
                </div>
            `).join('');

            Object.keys(locations).forEach(id => {
                const node = document.getElementById(`node-${id}`);
                if (node) node.classList.remove('current-location-glow');
            });
            const currNode = document.getElementById(`node-${state.currentPos}`);
            if (currNode) currNode.classList.add('current-location-glow');
        }

        function zoomMap(f) {
            state.zoom *= f;
            state.zoom = Math.min(Math.max(state.zoom, 0.4), 2.5);
            document.getElementById('map-container').style.transform = `scale(${state.zoom})`;
        }

        function startGame() { document.getElementById('start-screen').classList.add('hidden'); }
        function closeEventModal() { document.getElementById('event-modal').classList.add('hidden'); updateUI(); }

        window.onload = () => { setupLevel(0); };
    </script>
</body>
</html>
