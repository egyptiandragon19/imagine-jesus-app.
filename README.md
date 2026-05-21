<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Imagine Jesus - رحلة استكشاف تفاعلية</title>
    <!-- خط جوجول الأنيق Tajawal -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700;800&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --primary: #1e293b;
            --primary-light: #334155;
            --accent: #c5a880;
            --accent-hover: #b39369;
            --bg: #f8fafc;
            --card-bg: #ffffff;
            --text: #0f172a;
            --text-light: #64748b;
            --success: #10b981;
            --danger: #ef4444;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Tajawal', sans-serif;
            -webkit-tap-highlight-color: transparent;
        }

        body {
            background-color: var(--bg);
            color: var(--text);
            line-height: 1.7;
            padding: 10px;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
        }

        .container {
            max-width: 800px;
            width: 100%;
            background: var(--card-bg);
            padding: 30px 25px;
            border-radius: 24px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.04);
            border: 1px solid rgba(226, 232, 240, 0.8);
            position: relative;
            overflow: hidden;
        }

        header {
            text-align: center;
            margin-bottom: 25px;
            border-bottom: 2px dashed #e2e8f0;
            padding-bottom: 20px;
        }

        .creator-badge {
            display: inline-block;
            background: #f1f5f9;
            color: var(--primary-light);
            font-size: 0.85rem;
            padding: 6px 14px;
            border-radius: 50px;
            margin-bottom: 12px;
            font-weight: 700;
            border: 1px solid #e2e8f0;
        }

        header h1 {
            color: var(--primary);
            font-size: 2rem;
            font-weight: 800;
            margin-bottom: 6px;
        }

        header p {
            color: var(--text-light);
            font-size: 1rem;
        }

        /* القائمة الرئيسية */
        .tabs-menu {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 10px;
            margin-bottom: 25px;
        }

        @media (min-width: 600px) {
            .tabs-menu {
                grid-template-columns: repeat(4, 1fr);
            }
        }

        .tab-btn {
            background-color: #f1f5f9;
            border: 1px solid #e2e8f0;
            padding: 14px 10px;
            border-radius: 12px;
            cursor: pointer;
            font-weight: 700;
            color: var(--primary-light);
            font-size: 0.95rem;
            transition: all 0.2s ease;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 6px;
        }

        .tab-btn svg {
            width: 20px;
            height: 20px;
            fill: currentColor;
        }

        .tab-btn:hover {
            background-color: #e2e8f0;
        }

        .tab-btn.active {
            background-color: var(--primary);
            color: #ffffff;
            border-color: var(--primary);
            box-shadow: 0 4px 12px rgba(30, 41, 59, 0.15);
        }

        /* محتويات التبويبات */
        .tab-content {
            display: none;
            animation: slideUp 0.4s cubic-bezier(0.16, 1, 0.3, 1) forwards;
        }

        .tab-content.active {
            display: block;
        }

        .section-title {
            color: var(--accent);
            font-size: 1.4rem;
            font-weight: 800;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .intro-text {
            color: var(--text-light);
            font-size: 1.05rem;
            margin-bottom: 25px;
        }

        /* 1. التثليث التفاعلي - درع العقيدة */
        .trinity-explorer {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 20px;
            background: #fafbfd;
            padding: 20px;
            border-radius: 16px;
            border: 1px dashed #e2e8f0;
        }

        @media (min-width: 650px) {
            .trinity-explorer {
                flex-direction: row-reverse;
                justify-content: space-around;
            }
        }

        .trinity-svg-container {
            width: 250px;
            height: 250px;
            position: relative;
        }

        .shield-btn {
            cursor: pointer;
            transition: filter 0.2s;
        }

        .shield-btn:hover {
            filter: brightness(1.1);
        }

        .trinity-info-box {
            flex: 1;
            width: 100%;
            background: var(--card-bg);
            padding: 20px;
            border-radius: 12px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.02);
            border-left: 4px solid var(--accent);
            min-height: 150px;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        .trinity-info-box h4 {
            color: var(--primary);
            margin-bottom: 8px;
            font-size: 1.15rem;
            font-weight: 700;
        }

        /* 2. تجسد الكلمة - خطوات تفاعلية */
        .stepper-container {
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        .step-item {
            background: #f8fafc;
            border: 1px solid #e2e8f0;
            border-radius: 12px;
            overflow: hidden;
            transition: all 0.3s ease;
        }

        .step-header {
            padding: 15px 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            cursor: pointer;
            background: #f1f5f9;
            font-weight: 700;
            color: var(--primary);
        }

        .step-header .step-num {
            background: var(--accent);
            color: #fff;
            width: 26px;
            height: 26px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.85rem;
            margin-left: 10px;
        }

        .step-header-title {
            display: flex;
            align-items: center;
        }

        .step-arrow {
            transition: transform 0.3s ease;
        }

        .step-body {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.3s ease-out;
            padding: 0 20px;
            background: #fff;
        }

        .step-body-content {
            padding: 15px 0;
            font-size: 1rem;
            color: var(--text-light);
        }

        .step-item.active {
            border-color: var(--accent);
            box-shadow: 0 4px 12px rgba(197, 168, 128, 0.1);
        }

        .step-item.active .step-header {
            background: #faf8f5;
            color: var(--accent);
        }

        .step-item.active .step-body {
            max-height: 200px; /* كافية للنص */
        }

        .step-item.active .step-arrow {
            transform: rotate(180deg);
        }

        /* 3. محبة الله - البوصلة والأبعاد */
        .love-dimensions {
            display: grid;
            grid-template-columns: 1fr;
            gap: 15px;
        }

        @media (min-width: 600px) {
            .love-dimensions {
                grid-template-columns: repeat(3, 1fr);
            }
        }

        .dimension-card {
            background: #f8fafc;
            border: 1px solid #e2e8f0;
            padding: 20px;
            border-radius: 16px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .dimension-card:hover {
            transform: translateY(-5px);
            border-color: var(--accent);
            background: #fff;
            box-shadow: 0 10px 20px rgba(197, 168, 128, 0.08);
        }

        .dimension-icon {
            font-size: 2.5rem;
            margin-bottom: 10px;
            display: inline-block;
        }

        .dimension-card h3 {
            font-size: 1.1rem;
            margin-bottom: 8px;
            color: var(--primary);
        }

        .dimension-card p {
            font-size: 0.9rem;
            color: var(--text-light);
            display: none;
            margin-top: 10px;
            text-align: right;
            border-top: 1px dashed #e2e8f0;
            padding-top: 10px;
            animation: fadeIn 0.3s ease;
        }

        .dimension-card.open p {
            display: block;
        }

        /* 4. محاكاة ميزان العدل والرحمة التفاعلي */
        .scale-simulator {
            background: #fafbfd;
            border: 1px solid #e2e8f0;
            border-radius: 20px;
            padding: 25px;
            text-align: center;
        }

        .scale-visualization {
            height: 160px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: flex-end;
            margin-bottom: 25px;
            position: relative;
        }

        /* تصميم ميزان تفاعلي بالـ CSS */
        .scale-base {
            width: 120px;
            height: 10px;
            background: var(--primary-light);
            border-radius: 4px;
        }

        .scale-pillar {
            width: 14px;
            height: 90px;
            background: var(--primary-light);
            position: relative;
        }

        .scale-beam {
            width: 240px;
            height: 8px;
            background: var(--accent);
            position: absolute;
            top: 65px;
            left: calc(50% - 120px);
            border-radius: 4px;
            transition: transform 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            transform-origin: center center;
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            padding: 0 5px;
        }

        .scale-pan {
            width: 50px;
            height: 50px;
            border: 3px solid var(--accent);
            border-radius: 50%;
            background: #fff;
            position: relative;
            margin-top: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.8rem;
            font-weight: 700;
            color: var(--primary);
            box-shadow: 0 4px 6px rgba(0,0,0,0.05);
            transition: transform 0.6s ease;
        }

        /* تأثيرات توازن الكفتين حسب الميل */
        .scale-beam.tilt-left {
            transform: rotate(-15deg);
        }
        .scale-beam.tilt-left .pan-left {
            transform: translateY(15px) rotate(15deg);
        }
        .scale-beam.tilt-left .pan-right {
            transform: translateY(-15px) rotate(15deg);
        }

        .scale-beam.tilt-right {
            transform: rotate(15deg);
        }
        .scale-beam.tilt-right .pan-left {
            transform: translateY(-15px) rotate(-15deg);
        }
        .scale-beam.tilt-right .pan-right {
            transform: translateY(15px) rotate(-15deg);
        }

        .scale-beam.balanced {
            transform: rotate(0deg);
        }
        .scale-beam.balanced .pan-left, .scale-beam.balanced .pan-right {
            transform: translateY(0) rotate(0);
        }

        .scale-simulator-controls {
            display: grid;
            grid-template-columns: 1fr;
            gap: 10px;
            margin-bottom: 20px;
        }

        @media (min-width: 550px) {
            .scale-simulator-controls {
                grid-template-columns: repeat(3, 1fr);
            }
        }

        .sim-btn {
            padding: 10px 15px;
            border-radius: 10px;
            border: 1px solid #cbd5e1;
            background: #fff;
            cursor: pointer;
            font-weight: 700;
            transition: all 0.2s;
            color: var(--primary-light);
        }

        .sim-btn:hover {
            border-color: var(--primary);
            background: #f8fafc;
        }

        .sim-btn.active-sim {
            background-color: var(--primary);
            color: #fff;
            border-color: var(--primary);
        }

        .sim-btn.active-sim.cross-btn {
            background-color: var(--success);
            border-color: var(--success);
        }

        .scale-explain-card {
            background: #fff;
            padding: 15px;
            border-radius: 12px;
            border: 1px solid #e2e8f0;
            min-height: 80px;
            font-size: 0.95rem;
            display: flex;
            align-items: center;
            justify-content: center;
            line-height: 1.6;
            color: var(--text);
            box-shadow: inset 0 2px 4px rgba(0,0,0,0.01);
        }

        /* ذيل الصفحة */
        footer {
            text-align: center;
            margin-top: 35px;
            font-size: 0.85rem;
            color: var(--text-light);
            border-top: 1px solid #f0ede4;
            padding-top: 20px;
        }

        footer strong {
            color: var(--primary);
            display: block;
            margin-top: 4px;
        }

        @keyframes slideUp {
            from { opacity: 0; transform: translateY(15px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
    </style>
</head>
<body>

<div class="container">
    <header>
        <span class="creator-badge">فكرة وإعداد: أ/ عماد سامي</span>
        <h1>Imagine Jesus</h1>
        <p>رحلة تفاعلية لشرح المفاهيم العقائدية بأسلوب مبسط ومستنير للجميع</p>
    </header>

    <!-- قائمة التبويبات الكبرى التفاعلية -->
    <div class="tabs-menu">
        <button class="tab-btn active" onclick="openMainTab(event, 'section1')">
            <svg viewBox="0 0 24 24"><path d="M12 2A10 10 0 0 0 2 12a10 10 0 0 0 10 10 10 10 0 0 0 10-10A10 10 0 0 0 12 2zm0 18c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8z"/></svg>
            الله الواحد
        </button>
        <button class="tab-btn" onclick="openMainTab(event, 'section2')">
            <svg viewBox="0 0 24 24"><path d="M12 2c-5.52 0-10 4.48-10 10s4.48 10 10 10 10-4.48 10-10-4.48-10-10-10zm1 15h-2v-6h2v6zm0-8h-2V7h2v2z"/></svg>
            تجسد الكلمة
        </button>
        <button class="tab-btn" onclick="openMainTab(event, 'section3')">
            <svg viewBox="0 0 24 24"><path d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z"/></svg>
            محبة الله
        </button>
        <button class="tab-btn" onclick="openMainTab(event, 'section4')">
            <svg viewBox="0 0 24 24"><path d="M12 2L1 21h22L12 2zm0 4l7.53 13H4.47L12 6z"/></svg>
            مفهوم الفداء
        </button>
    </div>

    <!-- 1. تبويب: الله الواحد مثلث الأقانيم -->
    <div id="section1" class="tab-content active">
        <h2 class="section-title">١. الله الواحد.. ومفهوم الأقانيم</h2>
        <p class="intro-text">المسيحية تؤمن بإله واحد لا شريك له. ولكن هذا الإله هو إله "حي" ناطق بعقله ومحيي بروحه. اضغط على أجزاء المخطط البصري التفاعلي لتستكشف كيف يعبر كل أقنوم عن ذات الإله الواحد المتكاملة:</p>
        
        <div class="trinity-explorer">
            <!-- درع العقيدة التفاعلي بالـ SVG -->
            <div class="trinity-svg-container">
                <svg viewBox="0 0 200 200" width="100%" height="100%">
                    <!-- خطوط الربط والعلاقات -->
                    <line x1="100" y1="40" x2="100" y2="110" stroke="#cbd5e1" stroke-width="4" />
                    <line x1="50" y1="130" x2="100" y2="110" stroke="#cbd5e1" stroke-width="4" />
                    <line x1="150" y1="130" x2="100" y2="110" stroke="#cbd5e1" stroke-width="4" />
                    
                    <line x1="100" y1="40" x2="50" y2="130" stroke="#cbd5e1" stroke-width="2" stroke-dasharray="4,4" />
                    <line x1="50" y1="130" x2="150" y2="130" stroke="#cbd5e1" stroke-dasharray="4,4" stroke-width="2" />
                    <line x1="150" y1="130" x2="100" y2="40" stroke="#cbd5e1" stroke-dasharray="4,4" stroke-width="2" />

                    <!-- مركز التوحيد: الله الواحد -->
                    <g class="shield-btn" onclick="showTrinityInfo('god')">
                        <circle cx="100" cy="110" r="26" fill="#1e293b" />
                        <text x="100" y="114" fill="#ffffff" font-size="12" font-weight="bold" text-anchor="middle">الله</text>
                    </g>

                    <!-- أقنوم الآب -->
                    <g class="shield-btn" onclick="showTrinityInfo('father')">
                        <circle cx="100" cy="40" r="22" fill="#c5a880" />
                        <text x="100" y="44" fill="#ffffff" font-size="11" font-weight="bold" text-anchor="middle">الآب</text>
                    </g>

                    <!-- أقنوم الابن -->
                    <g class="shield-btn" onclick="showTrinityInfo('son')">
                        <circle cx="50" cy="130" r="22" fill="#c5a880" />
                        <text x="50" y="134" fill="#ffffff" font-size="11" font-weight="bold" text-anchor="middle">الابن</text>
                    </g>

                    <!-- أقنوم الروح القدس -->
                    <g class="shield-btn" onclick="showTrinityInfo('spirit')">
                        <circle cx="150" cy="130" r="22" fill="#c5a880" />
                        <text x="150" y="134" fill="#ffffff" font-size="10" font-weight="bold" text-anchor="middle">الروح القدس</text>
                    </g>
                </svg>
            </div>

            <!-- مربع المعلومات المنبثق بالتفاعل -->
            <div class="trinity-info-box" id="trinity-box">
                <h4 id="trinity-title">اضغط على أحد الأزرار الدائرية</h4>
                <p id="trinity-desc">قم بالضغط على (الله)، (الآب)، (الابن) أو (الروح القدس) في الشكل التوضيحي لتفهم بالتفصيل العلاقة الدقيقة والتطبيقية لكل صفة ذاتية في طبيعة الله وجوهره.</p>
            </div>
        </div>
    </div>

    <!-- ٢. تبويب: تجسد الكلمة -->
    <div id="section2" class="tab-content">
        <h2 class="section-title">٢. سر تجسد الكلمة.. كيف ولماذا؟</h2>
        <p class="intro-text">تجسد المسيح لا يعنى تحول إنسان ليكون إلهاً، بل العكس: هو تنازل الله بدافع الحب ليعلن عن ذاته بلغة بشرية يمكننا فهمها والتعامل معها. اضغط على المراحل التالية لتتبع تفاصيل هذا المفهوم:</p>

        <div class="stepper-container">
            <!-- خطوة 1 -->
            <div class="step-item active" id="step1">
                <div class="step-header" onclick="toggleStep('step1')">
                    <div class="step-header-title">
                        <span class="step-num">١</span>
                        <span>فكرة التنازل الإلهي</span>
                    </div>
                    <span class="step-arrow">▼</span>
                </div>
                <div class="step-body">
                    <div class="step-body-content">
                        الله روح غير محدود وفوق إدراك العقول المحدودة. لكي نتمكن من رؤيته وفهمه، كان يجب أن يعلن عن نفسه بأسلوب وبشكل يطابق طبيعتنا المحدودة، كأب يتنازل ليتحدث بلغة طفله الصغير ليفهمه الطفل.
                    </div>
                </div>
            </div>

            <!-- خطوة 2 -->
            <div class="step-item" id="step2">
                <div class="step-header" onclick="toggleStep('step2')">
                    <div class="step-header-title">
                        <span class="step-num">٢</span>
                        <span>الاتحاد بدون اختلاط</span>
                    </div>
                    <span class="step-arrow">▼</span>
                </div>
                <div class="step-body">
                    <div class="step-body-content">
                        في التجسد، اتحد لاهوت الله الكامل (الذات الإلهية) بالناسوت الكامل (الجسد الإنساني والنفس الإنسانية) للمسيح دون اختلاط أو امتزاج، تماماً كما تتحد النار بالحديد؛ فيبقى الحديد حديداً والنار ناراً، لكنهما يشتركان معاً في فعل الحرارة والصلابة.
                    </div>
                </div>
            </div>

            <!-- خطوة 3 -->
            <div class="step-item" id="step3">
                <div class="step-header" onclick="toggleStep('step3')">
                    <div class="step-header-title">
                        <span class="step-num">٣</span>
                        <span>المثال والمقاربة المعاصرة</span>
                    </div>
                    <span class="step-arrow">▼</span>
                </div>
                <div class="step-body">
                    <div class="step-body-content">
                        تخيل فكرة عميقة في عقلك؛ هي غير مرئية للمحيطين، ولكن حين "تجسدها" في كلمات مكتوبة أو منطوقة، تصبح الفكرة ملموسة ومسموعة ومؤثرة في الناس، دون أن تغادر الفكرة الأصلية عقلك أو تفقد جوهرها الحقيقي.
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- ٣. تبويب: محبة الله -->
    <div id="section3" class="tab-content">
        <h2 class="section-title">٣. أبعاد محبة الله اللامشروطة</h2>
        <p class="intro-text">محبة الله ليست نظرية أو مجرد وعود بل هي أفعال ظهرت حية في التجسد؛ حيث شاركنا آلامنا وأوجاعنا. اضغط على أي بُعد من أبعاد المحبة لتكتشف تفاصيله الروحية:</p>

        <div class="love-dimensions">
            <!-- الكارت التفاعلي 1 -->
            <div class="dimension-card" onclick="toggleLoveCard(this)">
                <span class="dimension-icon">🤝</span>
                <h3>تضامن كامل</h3>
                <p>لم يخاطبنا الله من برج عالي، بل نزل إلينا. عاش عيشتنا البسيطة، جاع، وعطش، وبكى، وتألم معنا ليكون قادراً على تعزيتنا بحنان حقيقي مجرَّب.</p>
            </div>

            <!-- الكارت التفاعلي 2 -->
            <div class="dimension-card" onclick="toggleLoveCard(this)">
                <span class="dimension-icon">❤️</span>
                <h3>قبول بلا شروط</h3>
                <p>المسيح في تجسده لم يأتِ ليدين أو يفرز الناس بل ليدعو الخطاة والمنبوذين. إنه يعلن حقيقة أن قيمتك الروحية والإنسانية عظيمة وجوهرية مهما سقطت.</p>
            </div>

            <!-- الكارت التفاعلي 3 -->
            <div class="dimension-card" onclick="toggleLoveCard(this)">
                <span class="dimension-icon">🛡️</span>
                <h3>أمان دائم</h3>
                <p>"أنا معكم كل الأيام وإلى انقضاء الدهر." التجسد أعطى الإنسان ضماناً ملموساً بأن الله يرافقه في سفره وحياته وشدائده، ولم يعد بعيداً أو معزولاً.</p>
            </div>
        </div>
    </div>

    <!-- ٤. تبويب: مفهوم الفداء (محاكاة الميزان التفاعلي) -->
    <div id="section4" class="tab-content">
        <h2 class="section-title">٤. ميزان الفداء (العدالة والرحمة)</h2>
        <p class="intro-text">سقوط الإنسان خلق فجوة عميقة: فالعدالة تقتضي محاسبة المخطئ، والرحمة تنادي بنجاة الإنسان المحبوب. جرب محاكاة الميزان التفاعلية بالأسفل لترى كيف التقت العدالة والرحمة معاً:</p>

        <div class="scale-simulator">
            <div class="scale-visualization">
                <div class="scale-beam balanced" id="interactive-scale">
                    <div class="scale-pan pan-left" id="pan-left">الرحمة</div>
                    <div class="scale-pan pan-right" id="pan-right">العدل</div>
                </div>
                <div class="scale-pillar"></div>
                <div class="scale-base"></div>
            </div>

            <div class="scale-simulator-controls">
                <button class="sim-btn" onclick="simulateScale('justice', this)">العدل وحده</button>
                <button class="sim-btn" onclick="simulateScale('mercy', this)">الرحمة وحدها</button>
                <button class="sim-btn cross-btn" id="redemption-btn" onclick="simulateScale('redemption', this)">الصليب والفداء</button>
            </div>

            <div class="scale-explain-card" id="scale-explain">
                اضغط على الخيارات أعلاه لتشاهد كيف توازن الفداء بين عدل الله الصارم ورحمته الأبوية اللامتناهية.
            </div>
        </div>
    </div>

    <footer>
        <p>( جميع الحقوق محفوظة لصفحة <strong>Imagine Jesus</strong> )</p>
        <p style="font-size: 0.8rem; margin-top: 5px; color: var(--accent);">إشراف وإعداد فكري: أ/ عماد سامي</p>
    </footer>
</div>

<script>
    // التبديل بين التبويبات الكبرى
    function openMainTab(evt, sectionId) {
        const tabContents = document.getElementsByClassName("tab-content");
        for (let i = 0; i < tabContents.length; i++) {
            tabContents[i].classList.remove("active");
        }

        const tabButtons = document.getElementsByClassName("tab-btn");
        for (let i = 0; i < tabButtons.length; i++) {
            tabButtons[i].classList.remove("active");
        }

        document.getElementById(sectionId).classList.add("active");
        evt.currentTarget.classList.add("active");
        
        // إعادة تعيين الحالات التفاعلية عند تغيير التبويب للتأكد من تصفير الحركات
        if (sectionId === 'section4') {
            simulateScale('balanced');
        }
    }

    // تفاعل التثليث (القسم الأول)
    function showTrinityInfo(type) {
        const titleEl = document.getElementById("trinity-title");
        const descEl = document.getElementById("trinity-desc");
        const boxEl = document.getElementById("trinity-box");
        
        // تغيير لون الحافة الأمامية حسب المفهوم لإضفاء جمالية بصرية
        boxEl.style.borderLeftColor = "#c5a880";

        if (type === 'god') {
            titleEl.innerText = "الله: الجوهر الإلهي الواحد";
            descEl.innerText = "المسيحية تعلن بكل وضوح: 'الله واحد'. هو الكيان والجوهر الواحد والوحيد الخالق للكون، وكل الأقانيم الثلاثة تتساوى وتتشابه في هذا الجوهر الواحد المطلق دون تفوق أو تدرج.";
            boxEl.style.borderLeftColor = "#1e293b";
        } else if (type === 'father') {
            titleEl.innerText = "الآب: الذات والينبوع";
            descEl.innerText = "أقنوم الآب يعبّر عن الله من حيث هو أصل الوجود، فوق كل شيء، العقل المدبر والذات غير المرئية التي لم يرها أحد قط، بل أعلنها الابن.";
        } else if (type === 'son') {
            titleEl.innerText = "الابن: نطق الله وكلمته المتجسدة";
            descEl.innerText = "الابن هو عقل الله الحكيم وصوته المعبر، وبما أن الله عاقل دائماً، فإن كلمته أزلية معه. هذا الكلمة هو الذي اتخذ جسداً وصار إنساناً ليعلمنا المحبة.";
        } else if (type === 'spirit') {
            titleEl.innerText = "الروح القدس: روح الحياة والحرارة الإلهية";
            descEl.innerText = "الروح القدس هو روح الله الحية المعزية، التي تمنح الحياة للخليقة، وتعمل في قلوب البشر لتنير بصائرهم وتثبتهم في الإيمان والخير والمحبة.";
        }
    }

    // تفاعل خطوات التجسد (القسم الثاني)
    function toggleStep(stepId) {
        const steps = ['step1', 'step2', 'step3'];
        steps.forEach(id => {
            const el = document.getElementById(id);
            if (id === stepId) {
                el.classList.add('active');
            } else {
                el.classList.remove('active');
            }
        });
    }

    // تفاعل كروت أبعاد المحبة (القسم الثالث)
    function toggleLoveCard(cardElement) {
        // غلق باقي الكروت المفتوحة لتركيز الانتباه
        const cards = document.getElementsByClassName("dimension-card");
        for (let i = 0; i < cards.length; i++) {
            if (cards[i] !== cardElement) {
                cards[i].classList.remove("open");
            }
        }
        cardElement.classList.toggle("open");
    }

    // تفاعل ميزان الفداء والعدالة والرحمة (القسم الرابع)
    function simulateScale(state, button) {
        const scale = document.getElementById("interactive-scale");
        const explain = document.getElementById("scale-explain");
        const panLeft = document.getElementById("pan-left");
        const panRight = document.getElementById("pan-right");
        
        // إزالة الكلاس النشط من جميع أزرار المحاكاة
        const simBtns = document.getElementsByClassName("sim-btn");
        for (let i = 0; i < simBtns.length; i++) {
            simBtns[i].classList.remove("active-sim");
        }
        
        if (button) {
            button.classList.add("active-sim");
        }

        // مسح أي أنماط ألوان طارئة
        panLeft.style.background = "#fff";
        panRight.style.background = "#fff";
        panLeft.style.color = "var(--primary)";
        panRight.style.color = "var(--primary)";

        if (state === 'justice') {
            scale.className = "scale-beam tilt-right";
            panRight.style.background = "var(--danger)";
            panRight.style.color = "#fff";
            explain.innerHTML = "<strong>العدل بمفرده:</strong> يُلزم بعقوبة الإنسان لمخالفته الناموس الأخلاقي، مما يعني هلاك الإنسان وانفصاله تماماً عن الله دون إعطاء فرصة للرجوع أو النجاة.";
        } else if (state === 'mercy') {
            scale.className = "scale-beam tilt-left";
            panLeft.style.background = "var(--accent)";
            panLeft.style.color = "#fff";
            explain.innerHTML = "<strong>الرحمة بمفردها:</strong> تتغاضى عن الخطأ وتتسامح فيه، لكن هذا يكسر هيبة العدل والقانون الأخلاقي ويصبح العفو بلا أي قيمة حقيقية أو أساس عادل.";
        } else if (state === 'redemption') {
            scale.className = "scale-beam balanced";
            panLeft.style.background = "var(--success)";
            panRight.style.background = "var(--success)";
            panLeft.style.color = "#fff";
            panRight.style.color = "#fff";
            explain.innerHTML = "<strong>المصالحة على الصليب:</strong> الفداء توازنت فيه الكفتان تماماً؛ حيث تحققت <strong>العدالة</strong> بموت المسيح النيابي الفادي، وانسكبت <strong>الرحمة</strong> الإلهية بغفران جميع الخطايا للإنسان المحبب لقلب الله.";
        } else {
            scale.className = "scale-beam balanced";
            explain.innerHTML = "اضغط على الخيارات أعلاه لتشاهد كيف توازن الفداء بين عدل الله الصارم ورحمته الأبوية اللامتناهية.";
        }
    }
</script>

</body>
</html>
