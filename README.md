<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>البوابة العظمى للأمن السيبراني | THE ULTIMATE CYBER-SECURITY HUB</title>
    <style>
        /* --- [1. نظام الألوان والخطوط - CSS Variables] --- */
        :root {
            --primary-neon: #00ffcc; /* لون النيون الأساسي */
            --secondary-blue: #0a84ff; /* لون الروابط والمسارات */
            --bg-deep: #020205; /* خلفية سوداء عميقة */
            --card-bg: #0d0d14; /* خلفية الكروت */
            --text-main: #e0e0e0;
            --text-muted: #8892b0;
            --danger: #ff0055;
            --warning: #ffcc00;
            --glass-bg: rgba(13, 13, 20, 0.85);
            --border-color: #1f1f2e;
            --font-main: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
        }

        /* --- [2. التنسيق العام - Global Reset] --- */
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: var(--font-main);
            background-color: var(--bg-deep);
            color: var(--text-main);
            line-height: 1.8;
            overflow-x: hidden;
        }

        /* --- [3. شريط التنقل - Cyber Navigation] --- */
        nav {
            background: var(--glass-bg);
            backdrop-filter: blur(15px);
            padding: 0 5%;
            height: 80px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: sticky;
            top: 0;
            z-index: 9999;
            border-bottom: 2px solid var(--primary-neon);
            box-shadow: 0 4px 30px rgba(0, 255, 204, 0.1);
        }

        .logo {
            font-size: 26px;
            font-weight: 900;
            color: var(--primary-neon);
            text-transform: uppercase;
            letter-spacing: 3px;
            text-shadow: 0 0 10px var(--primary-neon);
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 15px;
        }

        nav ul li a {
            color: var(--text-main);
            text-decoration: none;
            padding: 10px 20px;
            border-radius: 5px;
            font-size: 14px;
            font-weight: 600;
            cursor: pointer;
            position: relative;
        }

        nav ul li a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            width: 0;
            height: 2px;
            background: var(--primary-neon);
            transition: 0.3s;
        }

        nav ul li a:hover::after, nav ul li a.active::after {
            width: 80%;
            left: 10%;
        }

        nav ul li a.active {
            color: var(--primary-neon);
        }

        /* --- [4. الأقسام الرئيسية - Sections Layout] --- */
        section {
            padding: 100px 10%;
            display: none; /* يتم التحكم بها عبر JS */
            min-height: 100vh;
        }

        section.active {
            display: block;
            animation: fadeIn 0.8s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: scale(0.98); }
            to { opacity: 1; transform: scale(1); }
        }

        /* --- [5. واجهة البداية - Hero Section] --- */
        .hero {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding-top: 150px;
        }

        .hero h1 {
            font-size: clamp(40px, 8vw, 90px);
            font-weight: 900;
            line-height: 1;
            margin-bottom: 20px;
            background: linear-gradient(to bottom, #fff 0%, var(--primary-neon) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero p {
            font-size: 22px;
            color: var(--text-muted);
            max-width: 800px;
            margin-bottom: 40px;
        }

        .cyber-btn {
            padding: 18px 45px;
            font-size: 18px;
            font-weight: 800;
            background: transparent;
            color: var(--primary-neon);
            border: 2px solid var(--primary-neon);
            border-radius: 50px;
            cursor: pointer;
            position: relative;
            overflow: hidden;
            text-transform: uppercase;
        }

        .cyber-btn:hover {
            background: var(--primary-neon);
            color: #000;
            box-shadow: 0 0 40px var(--primary-neon);
            transform: translateY(-5px);
        }

        /* --- [6. الموسوعة - The Encyclopedia Design] --- */
        .encyclopedia-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
            margin-top: 50px;
        }

        .article-card {
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            padding: 40px;
            border-radius: 20px;
            position: relative;
            overflow: hidden;
        }

        .article-card::before {
            content: '';
            position: absolute;
            top: 0;
            right: 0;
            width: 5px;
            height: 100%;
            background: var(--primary-neon);
        }

        .article-card h3 {
            font-size: 26px;
            color: var(--primary-neon);
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .article-card p {
            color: var(--text-muted);
            font-size: 16px;
            margin-bottom: 20px;
        }

        .detail-box {
            background: rgba(0, 0, 0, 0.4);
            padding: 20px;
            border-radius: 10px;
            margin-top: 15px;
            border-right: 2px solid var(--secondary-blue);
        }

        .detail-box b {
            color: #fff;
            display: block;
            margin-bottom: 5px;
        }

        /* --- [7. خارطة الطريق - Roadmap Timeline] --- */
        .roadmap-timeline {
            position: relative;
            max-width: 1000px;
            margin: 50px auto;
        }

        .roadmap-timeline::after {
            content: '';
            position: absolute;
            width: 4px;
            background: var(--border-color);
            top: 0;
            bottom: 0;
            right: 50%;
            margin-right: -2px;
        }

        .roadmap-item {
            padding: 10px 40px;
            position: relative;
            width: 50%;
            text-align: left;
        }

        .roadmap-item.right {
            right: 50%;
            text-align: right;
        }

        .roadmap-item.left {
            left: 50%;
        }

        .roadmap-content {
            padding: 30px;
            background: var(--card-bg);
            border-radius: 15px;
            border: 1px solid var(--primary-neon);
        }

        /* --- [8. التذييل - Professional Footer] --- */
        footer {
            padding: 80px 10%;
            background: #000;
            border-top: 1px solid var(--border-color);
            text-align: center;
        }

        footer .f-logo {
            font-size: 30px;
            color: var(--primary-neon);
            font-weight: 900;
            margin-bottom: 20px;
        }

        /* --- [9. شريط التمرير المخصص - Custom Scrollbar] --- */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: var(--bg-deep);
        }
        ::-webkit-scrollbar-thumb {
            background: #222;
            border-radius: 10px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: var(--primary-neon);
        }
    </style>
</head>
<body>

    <nav>
        <div class="logo">CYBER.PORTAL</div>
        <ul id="main-nav">
            <li><a onclick="showSection('home')" id="n-home" class="active">الرئيسية</a></li>
            <li><a onclick="showSection('encyclopedia')" id="n-encyclopedia">الموسوعة الموسعة</a></li>
            <li><a onclick="showSection('academy')" id="n-academy">الأكاديمية</a></li>
            <li><a onclick="showSection('threats')" id="n-threats">مركز التهديدات</a></li>
            <li><a onclick="showSection('contact')" id="n-contact">تواصل معنا</a></li>
        </ul>
    </nav>

    <section id="home" class="active">
        <div class="hero">
            <h1>عصر الحماية القادم</h1>
            <p>أهلاً بك في أضخم منصة تقنية متكاملة لعلوم الأمن السيبراني. نحن هنا لتمكينك من فهم أسرار الأنظمة، حماية البيانات، واحتراف اختبار الاختراق بأحدث المعايير العالمية.</p>
            <div style="display: flex; gap: 20px;">
                <button class="cyber-btn" onclick="showSection('encyclopedia')">تصفح الموسوعة</button>
                <button class="cyber-btn" style="border-color: var(--secondary-blue); color: var(--secondary-blue);" onclick="showSection('academy')">خارطة الطريق</button>
            </div>
        </div>
    </section>

    <section id="encyclopedia">
        <h2>الموسوعة التقنية الكبرى</h2>
        <p style="text-align: center; color: var(--text-muted); margin-bottom: 50px;">تعمق في أدق تفاصيل الأمن الرقمي (Low-Level Security Concepts)</p>

        <div class="encyclopedia-grid">
            
            <div class="article-card">
                <h3>01. علم التشفير (Cryptography)</h3>
                <p>التشفير ليس مجرد إخفاء بيانات، بل هو نظام رياضي معقد لضمان أربع ركائز: السرية، السلامة، المصادقة، وعدم الإنكار.</p>
                
                <div class="detail-box">
                    <b>• التشفير المتماثل (Symmetric):</b>
                    <p>استخدام مفتاح واحد للعمليتين. خوارزمية <b>AES-256</b> هي المعيار الذهبي حالياً وتعتبر مستحيلة الكسر بالقوة الحسابية الحالية.</p>
                </div>
                
                <div class="detail-box">
                    <b>• التشفير غير المتماثل (Asymmetric):</b>
                    <p>يعتمد على "المفتاح العام" و "المفتاح الخاص". بروتوكول <b>RSA</b> و <b>Diffie-Hellman</b> هما الأساس في تأمين اتصالات الإنترنت (SSL/TLS).</p>
                </div>

                <div class="detail-box">
                    <b>• التشفير الكمي (Post-Quantum):</b>
                    <p>الجيل القادم من التشفير المصمم لمقاومة الحواسيب الكمية التي يمكنها كسر تشفير RSA في ثوانٍ معدودة.</p>
                </div>
            </div>

            <div class="article-card">
                <h3>02. هندسة الثغرات (Exploit Engineering)</h3>
                <p>دراسة الأخطاء البرمجية العميقة التي تسمح للمهاجم بالتحكم في تدفق البرنامج (Control Flow Hijacking).</p>
                
                <div class="detail-box">
                    <b>• Buffer Overflow:</b>
                    <p>ثغرة تحدث في لغات C/C++ عندما يتم كتابة بيانات تتجاوز سعة الذاكرة المخصصة، مما يسمح بحقن كود خبيث في الـ Stack.</p>
                </div>

                <div class="detail-box">
                    <b>• SQL Injection (Advanced):</b>
                    <p>ليس فقط سرقة بيانات، بل يمكن عبر ثغرات الحقن المتقدمة (Out-of-band) تنفيذ أوامر مباشرة على خادم قاعدة البيانات.</p>
                </div>

                <div class="detail-box">
                    <b>• Zero-Day Vulnerabilities:</b>
                    <p>الثغرات التي لا يعرف عنها المطور وتكون مجهولة للعالم، وهي الأغلى ثمناً في سوق الأمن السيبراني.</p>
                </div>
            </div>

            <div class="article-card">
                <h3>03. أمن الشبكات والبنية التحتية</h3>
                <p>حماية القنوات التي تتدفق عبرها البيانات من الهجمات التي تستهدف البروتوكولات الأساسية.</p>
                
                <div class="detail-box">
                    <b>• BGP Hijacking:</b>
                    <p>هجوم متقدم يتم فيه تضليل مسارات الإنترنت العالمية لتوجيه حركة البيانات من دولة كاملة عبر خوادم المهاجم.</p>
                </div>

                <div class="detail-box">
                    <b>• Zero Trust Architecture:</b>
                    <p>فلسفة أمنية حديثة تقول: "لا تثق بأحد أبداً، تحقق من كل شيء دائماً" (Never Trust, Always Verify).</p>
                </div>
            </div>

            <div class="article-card">
                <h3>04. الهندسة العكسية (Reverse Engineering)</h3>
                <p>عملية تفكيك البرمجيات لفهم كيفية عملها بدون امتلاك الكود المصدري (Source Code).</p>
                
                <div class="detail-box">
                    <b>• Static Analysis:</b>
                    <p>فحص الكود باستخدام أدوات مثل IDA Pro و Ghidra لتحليل الـ Assembly وفهم منطق البرنامج.</p>
                </div>

                <div class="detail-box">
                    <b>• Dynamic Analysis:</b>
                    <p>تشغيل البرنامج داخل Debugger ومراقبة الذاكرة والمعالج أثناء التنفيذ لكشف السلوك الخفي للفيروسات.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="academy">
        <h2>خارطة الطريق لعام 2026</h2>
        <div class="roadmap-timeline">
            
            <div class="roadmap-item right">
                <div class="roadmap-content">
                    <h3 style="color: var(--warning);">المرحلة 1: التأسيس الصلب</h3>
                    <p>تعلم أنظمة تشغيل Linux (إدارة السيرفرات)، الشبكات (CompTIA Network+)، وأساسيات البرمجة بلغة Python و Bash.</p>
                </div>
            </div>

            <div class="roadmap-item right">
                <div class="roadmap-content">
                    <h3 style="color: var(--primary-neon);">المرحلة 2: الدفاع الرقمي</h3>
                    <p>تعلم كيف تفكر كمدافع (Blue Team). دراسة SOC، تحليل السجلات (SIEM)، والتحقيق الجنائي الرقمي (Digital Forensics).</p>
                </div>
            </div>

            <div class="roadmap-item right">
                <div class="roadmap-content">
                    <h3 style="color: var(--danger);">المرحلة 3: الهجوم الأخلاقي</h3>
                    <p>احتراف اختبار الاختراق (OSCP). تعلم اختراق المواقع، الشبكات اللاسلكية، والبحث عن ثغرات الأنظمة المتقدمة.</p>
                </div>
            </div>

            <div class="roadmap-item right">
                <div class="roadmap-content">
                    <h3 style="color: var(--secondary-blue);">المرحلة 4: التخصص الدقيق</h3>
                    <p>اختيار مجال واحد: أمن الحوسبة السحابية (Cloud Security)، أمن إنترنت الأشياء (IoT)، أو هندسة أمن الـ AI.</p>
                </div>
            </div>

        </div>
    </section>

    <section id="threats">
        <h2>رادار التهديدات العالمية</h2>
        <div class="grid">
            <div class="article-card">
                <h3>هجمات الفدية (Ransomware 2.0)</h3>
                <p>لم يعد الأمر مجرد تشفير ملفات، بل أصبح "الابتزاز المزدوج": تشفير الملفات وتهديد الشركة بتسريب بيانات العملاء للعلن.</p>
            </div>
            <div class="article-card">
                <h3>التزييف العميق (Deepfakes)</h3>
                <p>استخدام الذكاء الاصطناعي لتزييف الوجوه والأصوات للقيام بهجمات هندسة اجتماعية متطورة لخداع مديري البنوك والشركات.</p>
            </div>
            <div class="article-card">
                <h3>هجمات سلاسل التوريد (Supply Chain)</h3>
                <p>استهداف شركة برمجيات واحدة لاختراق آلاف الشركات التي تستخدم برامجها (مثل هجوم SolarWinds الشهير).</p>
            </div>
        </div>
    </section>

    <section id="contact">
        <div style="text-align: center; max-width: 800px; margin: 0 auto; background: var(--card-bg); padding: 60px; border-radius: 30px; border: 2px dashed var(--primary-neon);">
            <h2>تواصل مع المركز التقني</h2>
            <p style="font-size: 20px; color: var(--text-muted); margin-bottom: 30px;">لطلب الاستشارات الأمنية، التدريب المتخصص، أو التعاون التقني.</p>
            
            <div style="display: flex; flex-direction: column; gap: 20px; align-items: center;">
                <a href="https://www.instagram.com/mha40471" target="_blank" class="cyber-btn" style="text-decoration: none; display: block; width: fit-content;">راسنا عبر انستغرام</a>
                <p style="color: var(--primary-neon); font-weight: bold;"> الامن السيبراني  </p>
            </div>
        </div>
    </section>

    <footer>
        <div class="f-logo">GLOBAL.CYBER.ACADEMY</div>
        <p>نحن نبني جيلاً من المحترفين القادرين على حماية العالم الرقمي.</p>
        <div style="margin: 30px 0; display: flex; justify-content: center; gap: 20px; color: var(--text-muted);">
            <span>#Linux</span> | <span>#Python</span> | <span>#CyberSecurity</span> | <span>#Jordan</span>
        </div>
        <p style="opacity: 0.3; font-size: 12px;">© 2026 جميع الحقوق محفوظة - تم تطوير الكود لأغراض تعليمية احترافية.</p>
    </footer>

    <script>
        /**
         * وظيفة الانتقال بين الأقسام (Single Page Application Logic)
         * @param {string} sectionId - معرف القسم المراد إظهاره
         */
        function showSection(sectionId) {
            // 1. إخفاء جميع الأقسام بإزالة فئة active
            const sections = document.querySelectorAll('section');
            sections.forEach(sec => {
                sec.classList.remove('active');
            });

            // 2. إظهار القسم المطلوب بإضافة فئة active
            const target = document.getElementById(sectionId);
            if (target) {
                target.classList.add('active');
            } else {
                console.error("Section not found: " + sectionId);
                return;
            }

            // 3. تحديث روابط القائمة (Navigation Links State)
            const links = document.querySelectorAll('nav ul li a');
            links.forEach(link => {
                link.classList.remove('active');
            });

            const activeLink = document.getElementById('n-' + sectionId);
            if (activeLink) {
                activeLink.classList.add('active');
            }

            // 4. التمرير إلى أعلى الصفحة بسلاسة عند تغيير القسم
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });

            // 5. تحديث عنوان الصفحة (اختياري)
            const titles = {
                'home': 'الرئيسية | بوابة الأمن',
                'encyclopedia': 'الموسوعة التقنية الكبرى',
                'academy': 'خارطة الطريق الأكاديمية',
                'threats': 'مركز تحليل التهديدات',
                'contact': 'اتصل بنا'
            };
            document.title = titles[sectionId] || "البوابة الأمنية";
        }

        // إضافة تأثيرات بصرية عند التمرير (Reveal Animation)
        window.addEventListener('scroll', () => {
            const cards = document.querySelectorAll('.article-card, .roadmap-content');
            cards.forEach(card => {
                const cardTop = card.getBoundingClientRect().top;
                if (cardTop < window.innerHeight - 100) {
                    card.style.opacity = '1';
                    card.style.transform = 'translateY(0)';
                }
            });
        });

        // رسالة ترحيب في الكونسول (للمبرمجين)
        console.log("%cتم تشغيل بوابة الأمن السيبراني بنجاح!", "color: #00ffcc; font-size: 20px; font-weight: bold;");
        console.log("نظام التشغيل: Virtual Cyber Environment 2026");
    </script>

    </body>
</html>
