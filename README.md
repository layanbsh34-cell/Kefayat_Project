# Kefayat_Project
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>قاعدة الاستثناء في اللغة العربية</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;700;900&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Cairo', sans-serif;
            background: linear-gradient(135deg, #f0fdf4 0%, #dcfce7 100%);
            min-height: 100vh;
        }
        .animate-pop {
            animation: popIn 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275) forwards;
        }
        @keyframes popIn {
            0% { transform: scale(0.9); opacity: 0; }
            100% { transform: scale(1); opacity: 1; }
        }
    </style>
</head>
<body class="text-slate-800 flex flex-col min-h-screen">

    <header class="bg-emerald-700 text-white shadow-lg sticky top-0 z-50">
        <div class="max-w-md mx-auto px-4 py-4 flex justify-between items-center">
            <div class="flex items-center space-x-2 space-x-reverse">
                <span class="bg-emerald-600 p-2 rounded-xl text-xl">📚</span>
                <div>
                    <h1 class="font-bold text-lg leading-tight">النحو الميسر</h1>
                    <p class="text-xs text-emerald-200">درس الاستثناء وأحكامه</p>
                </div>
            </div>
            <button onclick="resetApp()" class="text-xs bg-emerald-800 hover:bg-emerald-900 px-3 py-1.5 rounded-lg transition">الرئيسية</button>
        </div>
    </header>

    <main class="flex-1 max-w-md w-full mx-auto p-4 pb-20">
        
        <!-- Welcome / Home View -->
        <div id="home-view" class="space-y-4 animate-pop">
            <div class="bg-white rounded-2xl p-6 shadow-sm border border-emerald-100 text-center relative overflow-hidden">
                <div class="absolute -right-6 -top-6 w-24 h-24 bg-emerald-50 rounded-full z-0"></div>
                <div class="relative z-10">
                    <span class="text-4xl mb-3 block">✨</span>
                    <h2 class="text-xl font-bold text-emerald-900 mb-2">أهلاً بك في عالم النحو العربي</h2>
                    <p class="text-sm text-slate-600 mb-6">استكشف درس "الاستثناء" بكل سهولة ويسر، مع أمثلة واضحة واختبار تفاعلي.</p>
                    <button onclick="switchView('lesson-view')" class="w-full bg-emerald-600 hover:bg-emerald-700 text-white font-bold py-3.5 px-4 rounded-xl shadow-md transition flex items-center justify-center space-x-2 space-x-reverse">
                        <span>ابدأ التعلم الآن</span>
                        <span>←</span>
                    </button>
                </div>
            </div>

            <!-- Quick Navigation Cards -->
            <div class="grid grid-cols-2 gap-3">
                <button onclick="switchView('lesson-view'); setActiveTab('def')" class="bg-white p-4 rounded-xl shadow-sm border border-emerald-100 text-right hover:border-emerald-400 transition">
                    <span class="text-2xl mb-1 block">📖</span>
                    <h3 class="font-bold text-sm text-emerald-900">التعريف والأركان</h3>
                    <p class="text-xs text-slate-500 mt-1">ما هو الاستثناء؟</p>
                </button>
                <button onclick="switchView('lesson-view'); setActiveTab('types')" class="bg-white p-4 rounded-xl shadow-sm border border-emerald-100 text-right hover:border-emerald-400 transition">
                    <span class="text-2xl mb-1 block">🌿</span>
                    <h3 class="font-bold text-sm text-emerald-900">أنواع الاستثناء</h3>
                    <p class="text-xs text-slate-500 mt-1">تام، منفي، مفرغ...</p>
                </button>
                <button onclick="switchView('lesson-view'); setActiveTab('tools')" class="bg-white p-4 rounded-xl shadow-sm border border-emerald-100 text-right hover:border-emerald-400 transition">
                    <span class="text-2xl mb-1 block">🛠️</span>
                    <h3 class="font-bold text-sm text-emerald-900">أدوات الاستثناء</h3>
                    <p class="text-xs text-slate-500 mt-1">إلا، غير، سوى...</p>
                </button>
                <button onclick="startQuiz()" class="bg-emerald-800 text-white p-4 rounded-xl shadow-sm text-right hover:bg-emerald-900 transition">
                    <span class="text-2xl mb-1 block">🎯</span>
                    <h3 class="font-bold text-sm text-white">اختبر معلوماتك</h3>
                    <p class="text-xs text-emerald-200 mt-1">تحدي الأسئلة</p>
                </button>
            </div>
        </div>

        <!-- Lesson View -->
        <div id="lesson-view" class="hidden space-y-4 animate-pop">
            <!-- Tabs Bar -->
            <div class="flex bg-white p-1 rounded-xl shadow-sm border border-emerald-100 overflow-x-auto text-xs">
                <button onclick="setActiveTab('def')" id="tab-def" class="flex-1 py-2 px-3 rounded-lg font-bold transition whitespace-nowrap">التعريف والأركان</button>
                <button onclick="setActiveTab('types')" id="tab-types" class="flex-1 py-2 px-3 rounded-lg font-bold transition whitespace-nowrap">الأنواع</button>
                <button onclick="setActiveTab('tools')" id="tab-tools" class="flex-1 py-2 px-3 rounded-lg font-bold transition whitespace-nowrap">الأدوات</button>
            </div>

            <!-- Tab Content 1: Definition & Components -->
            <div id="content-def" class="space-y-4">
                <div class="bg-white rounded-2xl p-5 shadow-sm border border-emerald-100">
                    <h3 class="font-bold text-emerald-900 text-base mb-2 flex items-center">
                        <span class="bg-emerald-100 text-emerald-800 p-1.5 rounded-lg ml-2 text-sm">💡</span>
                        تعريف الاستثناء
                    </h3>
                    <p class="text-sm text-slate-600 leading-relaxed">
                        هو إخراج اسم (مستثنى) من حكم ما قبل أداة الاستثناء (المستثنى منه)، بحيث يخالف ما بعده ما قبله في الحكم.
                    </p>
                    <div class="mt-4 bg-emerald-50 p-3 rounded-xl border border-emerald-100 text-xs text-emerald-900">
                        <strong>مثال توضيحي:</strong> "حضر الطلاب إلا خالداً" (الطلاب حضروا، لكن خالداً مُستثنى ولم يحضُر).
                    </div>
                </div>

                <div class="bg-white rounded-2xl p-5 shadow-sm border border-emerald-100">
                    <h3 class="font-bold text-emerald-900 text-base mb-3 flex items-center">
                        <span class="bg-emerald-100 text-emerald-800 p-1.5 rounded-lg ml-2 text-sm">🧩</span>
                        أركان جملة الاستثناء (بإلا)
                    </h3>
                    <div class="space-y-3">
                        <div class="p-3 bg-slate-50 rounded-xl border border-slate-100">
                            <span class="font-bold text-emerald-800 block text-sm">1. المستثنى منه</span>
                            <span class="text-xs text-slate-600">الاسم الواقع قبل الأداة، ويُذكر غالباً في الكلام. (مثال: الطلاب)</span>
                        </div>
                        <div class="p-3 bg-slate-50 rounded-xl border border-slate-100">
                            <span class="font-bold text-emerald-800 block text-sm">2. أداة الاستثناء</span>
                            <span class="text-xs text-slate-600">الحرف أو الاسم أو الفعل الذي يربط بين الطرفين. (مثال: إلا)</span>
                        </div>
                        <div class="p-3 bg-slate-50 rounded-xl border border-slate-100">
                            <span class="font-bold text-emerald-800 block text-sm">3. المستثنى</span>
                            <span class="text-xs text-slate-600">الاسم الواقع بعد الأداة والمخالف لما قبلها. (مثال: خالداً)</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Tab Content 2: Types of Exception -->
            <div id="content-types" class="hidden space-y-4">
                <div class="bg-white rounded-2xl p-5 shadow-sm border border-emerald-100">
                    <h3 class="font-bold text-emerald-900 text-base mb-2">1. التام المثبت (الموجب)</h3>
                    <p class="text-xs text-slate-600 mb-2">هو ما ذكر فيه المستثنى منه ولم يسبقه نفي أو نهي.</p>
                    <div class="bg-emerald-50 p-3 rounded-xl text-xs text-emerald-900">
                        <strong>حكمه:</strong> يجب نصب المستثنى بعد (إلا).<br>
                        <strong>مثال:</strong> قرأت الكتاب إلا صفحةً.
                    </div>
                </div>

                <div class="bg-white rounded-2xl p-5 shadow-sm border border-emerald-100">
                    <h3 class="font-bold text-emerald-900 text-base mb-2">2. التام المنفي</h3>
                    <p class="text-xs text-slate-600 mb-2">هو ما ذكر فيه المستثنى منه ولكن سبق الجملة نفي أو شبهه.</p>
                    <div class="bg-emerald-50 p-3 rounded-xl text-xs text-emerald-900">
                        <strong>حكمه:</strong> يجوز نصبه على الاستثناء، أو إتباعه للمستثنى منه (بدل).<br>
                        <strong>مثال:</strong> ما حضر الضيوف إلا زيداً / زيدٌ.
                    </div>
                </div>

                <div class="bg-white rounded-2xl p-5 shadow-sm border border-emerald-100">
                    <h3 class="font-bold text-emerald-900 text-base mb-2">3. الناقص المنفي (المفرّغ)</h3>
                    <p class="text-xs text-slate-600 mb-2">هو ما لم يُذكر فيه المستثنى منه وسبق بنفي.</p>
                    <div class="bg-emerald-50 p-3 rounded-xl text-xs text-emerald-900">
                        <strong>حكمه:</strong> يُعرب المستثنى حسب موضع في الجملة كأن (إلا) غير موجودة.<br>
                        <strong>مثال:</strong> ما محمدٌ إلا رسولٌ (رسولٌ: خبر مرفوع).
                    </div>
                </div>
            </div>

            <!-- Tab Content 3: Tools -->
            <div id="content-tools" class="hidden space-y-4">
                <div class="bg-white rounded-2xl p-5 shadow-sm border border-emerald-100">
                    <h3 class="font-bold text-emerald-900 text-base mb-3">أدوات الاستثناء الرئيسية</h3>
                    
                    <div class="space-y-3">
                        <div class="p-3 bg-slate-50 rounded-xl">
                            <span class="font-bold text-emerald-800 text-sm">حرف (إلا)</span>
                            <p class="text-xs text-slate-600 mt-1">الأداة الأصلية والأكثر استخداماً في الاستثناء.</p>
                        </div>
                        <div class="p-3 bg-slate-50 rounded-xl">
                            <span class="font-bold text-emerald-800 text-sm">اسمان (غير وسوى)</span>
                            <p class="text-xs text-slate-600 mt-1">يأخذان حكم المستثنى بإلا، وما بعدهما يعرب مضافاً إليه دائماً.</p>
                        </div>
                        <div class="p-3 bg-slate-50 rounded-xl">
                            <span class="font-bold text-emerald-800 text-sm">أفعال / حروف (خلا، عدا، حاشا)</span>
                            <p class="text-xs text-slate-600 mt-1">يجوز إعراب ما بعدها مفعولاً به (على أنها أفعال) أو اسم مجرور (على أنها حروف جر).</p>
                        </div>
                    </div>
                </div>
            </div>

            <div class="flex justify-between pt-2">
                <button onclick="switchView('home-view')" class="px-4 py-2 rounded-xl bg-slate-200 text-slate-700 text-xs font-bold">الرجوع للرئيسية</button>
                <button onclick="startQuiz()" class="px-4 py-2 rounded-xl bg-emerald-600 text-white text-xs font-bold shadow-md">الانتقال للاختبار 🎯</button>
            </div>
        </div>

        <!-- Quiz View -->
        <div id="quiz-view" class="hidden space-y-4 animate-pop">
            <div class="bg-white rounded-2xl p-6 shadow-sm border border-emerald-100">
                <div class="flex justify-between items-center mb-4 border-b pb-3">
                    <span id="quiz-counter" class="text-xs font-bold bg-emerald-50 text-emerald-800 px-3 py-1 rounded-full">السؤال 1 من 3</span>
                    <span id="quiz-score" class="text-xs text-slate-500 font-semibold">النتيجة: 0</span>
                </div>

                <h3 id="question-text" class="font-bold text-emerald-900 text-base mb-4">نص السؤال يظهر هنا...</h3>

                <div id="options-container" class="space-y-2.5 mb-4">
                    <!-- Options injected dynamically -->
                </div>

                <div id="feedback-box" class="hidden p-3 rounded-xl text-xs mb-4 font-semibold"></div>

                <button id="next-btn" onclick="nextQuestion()" class="hidden w-full bg-emerald-600 hover:bg-emerald-700 text-white font-bold py-3 rounded-xl transition text-sm">السؤال التالي</button>
            </div>
        </div>

        <!-- Quiz Result View -->
        <div id="result-view" class="hidden space-y-4 animate-pop text-center">
            <div class="bg-white rounded-2xl p-6 shadow-sm border border-emerald-100">
                <span class="text-5xl mb-3 block">🏆</span>
                <h3 class="text-xl font-bold text-emerald-900 mb-2">أحسنت! انتهى الاختبار</h3>
                <p id="final-score-text" class="text-sm text-slate-600 mb-6">لقد أجبت على الأسئلة بنجاح.</p>
                <div class="space-y-2">
                    <button onclick="startQuiz()" class="w-full bg-emerald-600 hover:bg-emerald-700 text-white font-bold py-3 rounded-xl transition text-sm">إعادة الاختبار</button>
                    <button onclick="switchView('home-view')" class="w-full bg-slate-100 hover:bg-slate-200 text-slate-700 font-bold py-3 rounded-xl transition text-sm">العودة للرئيسية</button>
                </div>
            </div>
        </div>

    </main>

    <footer class="bg-white border-t border-emerald-100 py-3 fixed bottom-0 left-0 right-0 z-40 shadow-lg">
        <div class="max-w-md mx-auto px-6 flex justify-around items-center">
            <button onclick="switchView('home-view')" class="flex flex-col items-center text-emerald-700 text-xs font-bold">
                <span class="text-xl mb-0.5">🏠</span>
                الرئيسية
            </button>
            <button onclick="switchView('lesson-view'); setActiveTab('def')" class="flex flex-col items-center text-slate-500 hover:text-emerald-700 text-xs font-bold">
                <span class="text-xl mb-0.5">📖</span>
                الدرس
            </button>
            <button onclick="startQuiz()" class="flex flex-col items-center text-slate-500 hover:text-emerald-700 text-xs font-bold">
                <span class="text-xl mb-0.5">🎯</span>
                التحدي
            </button>
        </div>
    </footer>

    <script>
        const quizData = [
            {
                question: "ما نوع الاستثناء في الجملة التالية: \"ما حضر الطلاب إلا زيداً\"؟",
                options: [
                    "تام مثبت",
                    "تام منفي",
                    "ناقص منفي (مفرغ)",
                    "غير ذلك"
                ],
                correct: 1,
                explanation: "الاستثناء هنا (تام منفي) لأنه ذكر المستثنى منه (الطلاب) وسبق بنفي (ما)."
            },
            {
                question: "في جملة \"ما نجح إلا الطالبُ\"، إعراب كلمة (الطالبُ):",
                options: [
                    "مستثنى منصوب وجوباً",
                    "فاعل مرفوع وعلامة رفعه الضمة (حسب موضعها)",
                    "مضاف إليه مجرور",
                    "بدل مرفوع"
                ],
                correct: 1,
                explanation: "لأن الجملة ناقصة منفية (مفرغة)، كأن (ما وإلا) غير موجودة (نجح الطالبُ)."
            },
            {
                question: "أي من الآتي يعتبر من أدوات الاستثناء الاسمية؟",
                options: [
                    "إلا",
                    "خلا",
                    "غير وسوى",
                    "عدا"
                ],
                correct: 2,
                explanation: "(غير وسوى) اسمان وليسا حرفين أو فعلين."
            }
        ];

        let currentQuestionIndex = 0;
        let score = 0;
        let answered = false;

        function switchView(viewId) {
            ['home-view', 'lesson-view', 'quiz-view', 'result-view'].forEach(id => {
                document.getElementById(id).classList.add('hidden');
            });
            document.getElementById(viewId).classList.remove('hidden');
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        function setActiveTab(tabName) {
            ['def', 'types', 'tools'].forEach(t => {
                const btn = document.getElementById('tab-' + t);
                const content = document.getElementById('content-' + t);
                if (t === tabName) {
                    btn.className = "flex-1 py-2 px-3 rounded-lg font-bold transition whitespace-nowrap bg-emerald-700 text-white shadow-sm";
                    content.classList.remove('hidden');
                } else {
                    btn.className = "flex-1 py-2 px-3 rounded-lg font-bold transition whitespace-nowrap text-slate-600 hover:bg-slate-100";
                    content.classList.add('hidden');
                }
            });
        }

        function startQuiz() {
            currentQuestionIndex = 0;
            score = 0;
            switchView('quiz-view');
            loadQuestion();
        }

        function loadQuestion() {
            answered = false;
            const q = quizData[currentQuestionIndex];
            document.getElementById('quiz-counter').innerText = `السؤال ${currentQuestionIndex + 1} من ${quizData.length}`;
            document.getElementById('quiz-score').innerText = `النتيجة: ${score}`;
            document.getElementById('question-text').innerText = q.question;
            
            const optionsContainer = document.getElementById('options-container');
            optionsContainer.innerHTML = '';
            
            q.options.forEach((opt, index) => {
                const btn = document.createElement('button');
                btn.className = "w-full text-right p-3 rounded-xl border border-slate-200 bg-slate-50 hover:bg-emerald-50 hover:border-emerald-300 transition text-xs font-semibold text-slate-700";
                btn.innerText = opt;
                btn.onclick = () => selectOption(index);
                optionsContainer.appendChild(btn);
            });

            document.getElementById('feedback-box').classList.add('hidden');
            document.getElementById('next-btn').classList.add('hidden');
        }

        function selectOption(selectedIndex) {
            if (answered) return;
            answered = true;

            const q = quizData[currentQuestionIndex];
            const optionsContainer = document.getElementById('options-container');
            const buttons = optionsContainer.getElementsByTagName('button');
            const feedbackBox = document.getElementById('feedback-box');

            for (let i = 0; i < buttons.length; i++) {
                buttons[i].disabled = true;
                if (i === q.correct) {
                    buttons[i].className = "w-full text-right p-3 rounded-xl border border-emerald-300 bg-emerald-100 text-emerald-900 text-xs font-bold";
                } else if (i === selectedIndex) {
                    buttons[i].className = "w-full text-right p-3 rounded-xl border border-red-300 bg-red-100 text-red-900 text-xs font-bold";
                }
            }

            if (selectedIndex === q.correct) {
                score++;
                feedbackBox.className = "p-3 rounded-xl text-xs mb-4 font-semibold bg-emerald-50 text-emerald-800 border border-emerald-200";
                feedbackBox.innerText = "إجابة صحيحة! أحسنت 🌟 " + q.explanation;
            } else {
                feedbackBox.className = "p-3 rounded-xl text-xs mb-4 font-semibold bg-red-50 text-red-800 border border-red-200";
                feedbackBox.innerText = "إجابة خاطئة. ❌ " + q.explanation;
            }

            feedbackBox.classList.remove('hidden');
            document.getElementById('quiz-score').innerText = `النتيجة: ${score}`;
            document.getElementById('next-btn').classList.remove('hidden');
        }

        function nextQuestion() {
            currentQuestionIndex++;
            if (currentQuestionIndex < quizData.length) {
                loadQuestion();
            } else {
                showResult();
            }
        }

        function showResult() {
            switchView('result-view');
            document.getElementById('final-score-text').innerText = `لقد أجبت بشكل صحيح على ${score} من أصل ${quizData.length} أسئلة بنجاح تام!`;
        }

        function resetApp() {
            switchView('home-view');
        }

        // Initialize default tab on load
        setActiveTab('def');
    </script>
</body>
</html>
