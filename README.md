# Gita
html
<!DOCTYPE html>
<html lang="en" class="dark">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bhagavad Gita for Gen Z</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        cyber: {
                            bg: '#070913',
                            card: 'rgba(15, 18, 36, 0.7)',
                            primary: '#8b5cf6', / Violet
                            secondary: '#ec4899', / Pink
                            accent: '#eab308', / Gold
                            cyan: '#06b6d4', / Cyan
                        }
                    },
                    fontFamily: {
                        sans: ['Plus Jakarta Sans', 'Inter', 'sans-serif'],
                        serif: ['Cinzel', 'Playfair Display', 'serif'],
                    }
                }
            }
        }
    </script>
    <-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@500;700;900&family=Plus+Jakarta+Sans:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <-- Font Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
<style>
        body {
            background-color: #070913;
            overflow-x: hidden;
        }
        / Custom scrollbar /
        ::-webkit-scrollbar {
            width: 6px;
        }
        ::-webkit-scrollbar-track {
            background: #070913;
        }
        ::-webkit-scrollbar-thumb {
            background: #1e1b4b;
            border-radius: 3px;
        }
        / Neon glowing text & borders */
        .neon-text-cyan {
            text-shadow: 0 0 10px rgba(6, 182, 212, 0.6), 0 0 20px rgba(6, 182, 212, 0.3);
        }
        .neon-text-gold {
            text-shadow: 0 0 10px rgba(234, 179, 8, 0.6), 0 0 20px rgba(234, 179, 8, 0.3);
        }
        .neon-border {
            box-shadow: 0 0 15px rgba(139, 92, 246, 0.2);
            border: 1px solid rgba(139, 92, 246, 0.3);
        }
        .neon-border-gold {
            box-shadow: 0 0 15px rgba(234, 179, 8, 0.15);
            border: 1px solid rgba(234, 179, 8, 0.3);
        }
        / Page flip & fade transitions */
        .slide-transition {
            transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
        }
    </style>
</head>
<body class="text-slate-100 font-sans min-h-screen flex flex-col justify-between">
<-- BACKGROUND GRAPHICS (SANSKRIT MANDALA & NEON ORBS) -->
    <div class="fixed inset-0 pointer-events-none z-0 overflow-hidden">
        <div class="absolute top-[-20%] left-[-10%] w-[600px] h-[600px] rounded-full bg-violet-900/15 blur-[120px]"></div>
        <div class="absolute bottom-[-25%] right-[-10%] w-[700px] h-[700px] rounded-full bg-pink-900/15 blur-[150px]"></div>
        <div class="absolute top-[40%] right-[10%] w-[300px] h-[300px] rounded-full bg-cyan-900/10 blur-[100px]"></div>
        <-- Grid overlay -->
        <div class="absolute inset-0 bg-[linear-gradient(rgba(255,255,255,0.01)_1px,transparent_1px),linear-gradient(90deg,rgba(255,255,255,0.01)_1px,transparent_1px)] bg-[size:40px_40px]"></div>
    </div>
<-- HEADER / NAVIGATION -->
    <header class="relative z-10 w-full px-6 py-4 flex justify-between items-center bg-cyber-bg/60 backdrop-blur-md border-b border-white/5">
        <div class="flex items-center gap-3">
            <div class="w-10 h-10 rounded-xl bg-gradient-to-tr from-cyber-primary to-cyber-secondary flex items-center justify-center shadow-lg">
                <i class="fa-solid fa-dharmachakra text-white text-xl animate-spin" style="animation-duration: 20s;"></i>
            </div>
            <div>
                <h1 class="font-serif font-black text-lg tracking-wider bg-gradient-to-r from-cyan-400 via-violet-400 to-pink-500 bg-clip-text text-transparent">GITA FOR GEN Z</h1>
                <p class="text-[10px] text-slate-400 uppercase tracking-widest">Ancient Code • Modern Dev</p>
            </div>
        </div>
        
<-- Quick Stats / Controls -->
        <div class="flex items-center gap-4">
            <button id="toggle-sidebar" class="bg-violet-950/40 hover:bg-violet-900/40 border border-violet-500/30 px-3 py-1.5 rounded-lg text-xs font-semibold flex items-center gap-2 text-violet-300 transition-all">
                <i class="fa-solid fa-robot"></i> Ask Krishna AI
            </button>
            <button id="fullscreen-btn" class="text-slate-400 hover:text-white transition" title="Toggle Fullscreen">
                <i class="fa-solid fa-expand"></i>
            </button>
        </div>
    </header>
<-- MAIN PRESENTATION AREA -->
    <main class="relative z-10 flex-1 w-full max-w-7xl mx-auto px-4 md:px-6 py-6 flex flex-col md:flex-row gap-6 items-stretch">
        
<-- SLIDE CONTENT WINDOW -->
        <div class="flex-1 flex flex-col justify-between bg-cyber-card backdrop-blur-xl rounded-2xl neon-border overflow-hidden relative min-h-[550px] md:min-h-[600px]">
                <-- Slide Progress indicator bar -->
            <div class="absolute top-0 left-0 h-1 bg-gradient-to-r from-cyan-500 via-violet-500 to-pink-500 transition-all duration-500" id="progress-bar" style="width: 10%;"></div>
<-- SLIDE WRAPPER -->
            <div class="flex-1 p-6 md:p-10 flex flex-col justify-center overflow-y-auto" id="slide-container">
                <-- Slide templates will be injected here dynamically -->
            </div>
 <-- CONTROLS & META FOOTER -->
            <div class="border-t border-white/5 bg-slate-950/50 p-4 flex flex-col sm:flex-row justify-between items-center gap-4">
                <div class="flex items-center gap-2">
                    <span class="text-xs bg-slate-900 border border-white/10 text-slate-400 px-2.5 py-1 rounded-full font-mono" id="slide-counter">SLIDE 01 / 10</span>
                    <button id="autoplay-btn" class="text-xs text-slate-400 hover:text-white flex items-center gap-1.5 px-2 py-1 rounded-lg hover:bg-white/5 transition">
                        <i class="fa-solid fa-play"></i> Autoplay
                    </button>
                </div>

 <-- Slide Navigation Dots -->
                <div class="flex items-center gap-1.5" id="nav-dots">
                    <-- Dots generated here -->
                </div>
 <-- Action Nav buttons -->
                <div class="flex items-center gap-3">
                    <button id="prev-btn" class="w-10 h-10 rounded-xl bg-slate-900 border border-white/10 hover:border-violet-500/40 text-slate-300 hover:text-white flex items-center justify-center transition">
                        <i class="fa-solid fa-arrow-left"></i>
                    </button>
                    <button id="next-btn" class="h-10 px-5 rounded-xl bg-gradient-to-r from-violet-600 to-pink-600 hover:from-violet-500 hover:to-pink-500 text-white font-semibold flex items-center justify-center gap-2 shadow-lg shadow-violet-950/40 transition">
                        Next <i class="fa-solid fa-arrow-right"></i>
                    </button>
                </div>
            </div>
        </div>
 <-- SIDEBAR: "ASK KRISHNA AI CHAT" & TEXT RESOURCE -->
        <aside id="ai-sidebar" class="w-full md:w-[380px] bg-cyber-card backdrop-blur-xl rounded-2xl border border-white/10 p-5 flex flex-col justify-between hidden md:flex transition-all">
            <div class="flex flex-col h-full">
                <-- Sidebar Header -->
                <div class="flex justify-between items-center pb-4 border-b border-white/5 mb-4">
                    <div class="flex items-center gap-2">
                        <div class="w-8 h-8 rounded-lg bg-yellow-500/20 border border-yellow-500/40 flex items-center justify-center">
                            <i class="fa-solid fa-wand-magic-sparkles text-yellow-400 text-sm"></i>
                        </div>
                        <div>
                            <h2 class="font-serif font-bold text-sm tracking-wide text-yellow-400">Krishna AI Coach</h2>
                            <p class="text-[10px] text-slate-400">Ask modern dilemmas, get Gita wisdom</p>
                        </div>
                    </div>
                    <-- Status Indicator -->
                    <span class="inline-flex items-center gap-1 text-[10px] bg-emerald-500/10 text-emerald-400 px-2 py-0.5 rounded-full border border-emerald-500/20">
                        <span class="w-1.5 h-1.5 rounded-full bg-emerald-400 animate-pulse"></span> Active
                    </span>
                </div>

 <-- Dilemmas / Quick Prompts -->
                <div id="quick-prompts" class="mb-4">
                    <p class="text-[11px] text-slate-400 uppercase tracking-wider font-bold mb-2">🔥 Common Gen Z Dilemmas:</p>
                    <div class="grid grid-cols-1 gap-1.5">
                        <button class="quick-prompt-btn text-left text-xs bg-slate-900/40 hover:bg-violet-950/20 border border-white/5 hover:border-violet-500/30 p-2 rounded-lg text-slate-300 hover:text-violet-200 transition">
                            "I'm burnt out. How do I act without worrying about outcomes?"
                        </button>
                        <button class="quick-prompt-btn text-left text-xs bg-slate-900/40 hover:bg-violet-950/20 border border-white/5 hover:border-violet-500/30 p-2 rounded-lg text-slate-300 hover:text-violet-200 transition">
                            "How do I quiet my mind when social media ruins my focus?"
                        </button>
                        <button class="quick-prompt-btn text-left text-xs bg-slate-900/40 hover:bg-violet-950/20 border border-white/5 hover:border-violet-500/30 p-2 rounded-lg text-slate-300 hover:text-violet-200 transition">
                            "I have major fear of missing out (FOMO). Help me find balance."
                        </button>
                    </div>
                </div>
<-- Chat Messages Window -->
                <div id="chat-messages" class="flex-1 min-h-[150px] max-h-[250px] md:max-h-none overflow-y-auto mb-4 p-3 bg-slate-950/40 rounded-xl border border-white/5 flex flex-col gap-3">
                    <-- Initial Welcome Message -->
                    <div class="text-xs text-slate-400 bg-slate-900/40 p-2.5 rounded-lg border border-white/5">
                        <span class="font-bold text-yellow-400"><i class="fa-solid fa-om mr-1"></i> Arjuna, ask your question:</span>
                        "Tell me your current challenge, dilemma or doubt, and I will show you how to apply the wisdom of the Gita to solve it."
                    </div>
                </div>
  <-- Input box -->
                <div class="relative">
                    <input type="text" id="chat-input" placeholder="Type your modern dilemma here..." class="w-full bg-slate-900/60 border border-white/10 rounded-xl px-4 py-3 text-xs focus:outline-none focus:border-violet-500 transition-all pr-12 text-slate-200">
                    <button id="send-chat-btn" class="absolute right-2 top-2 w-8 h-8 rounded-lg bg-gradient-to-r from-violet-600 to-pink-600 hover:from-violet-500 hover:to-pink-500 flex items-center justify-center text-white transition shadow-md">
                        <i class="fa-solid fa-paper-plane text-xs"></i>
                    </button>
                </div>
            </div>
        </aside>
    </main>

  <-- AUDIO PLAYER / VOICE CAPABILITY NOTIF (Bottom left float) -->
    <div id="audio-notifier" class="fixed bottom-6 left-6 z-20 bg-slate-950/80 backdrop-blur-md border border-white/10 rounded-full px-4 py-2 flex items-center gap-2 shadow-lg max-w-sm hidden transition-all duration-300">
        <div class="w-2.5 h-2.5 rounded-full bg-cyan-400 animate-ping"></div>
        <span class="text-[10px] text-slate-300 font-mono" id="audio-text">Synthesizing shloka recitation...</span>
    </div>
<-- MAIN DATA CONFIGURATION FOR SLIDES -->
    <script>
        const SLIDE_DATA = [
            {
                id: 1,
                title: "Bhagavad Gita for Gen Z",
                subtitle: "Timeless Wisdom in a Digital Age",
                graphicType: "silhouette",
                shloka: "यदा यदा हि धर्मस्य ग्लानिर्भवति भारत।\nअभ्युत्थानमधर्मस्य तदात्मानं सृजाम्यहम्॥",
                chapter: "Chapter 4, Verse 7",
                translation: "Whenever there is a decline in righteousness (Dharma) and an uprise in chaos, I manifest myself to restore harmony.",
                genZTake: "When the vibes are off and social chaos reaches its peak, natural forces step in to correct course. Trust the system upgrade.",
                bgGradient: "from-cyan-950/40 via-violet-950/30 to-slate-950/40"
            },
            {
                id: 2,
                title: "What is the Gita?",
                subtitle: "Ancient Tech Support for the Soul",
                graphicType: "interactive-cards",
                bullets: [
                    { icon: "fa-comments", label: "Ultimate Dialogue", desc: "A raw conversation between Krishna (the mentor) & Arjuna (the warrior undergoing a panic attack)." },
                    { icon: "fa-book-open", label: "700 Golden Verses", desc: "Encoded inside the ancient epic Mahabharata; formatted in 18 masterclass chapters." },
                    { icon: "fa-compass", label: "The Universal Playbook", desc: "Not a dogma, but an operating system centered on duty, self-realization, and dynamic balance." }
                ],
                shloka: "धर्मक्षेत्रे कुरुक्षेत्रे समवेता युयुत्सवः।\nमामकाः पाण्डवाश्चैव किमकुर्वत सञ्जय॥",
                chapter: "Chapter 1, Verse 1",
                translation: "On the holy field of Kurukshetra, gathered and eager to fight, what did my people and the sons of Pandu do?",
                genZTake: "Kurukshetra isn't just history—it's your internal battleground. Peer pressure, self-doubt, and high ambitions fight daily.",
                bgGradient: "from-blue-950/30 via-slate-950 to-slate-950"
            },
            {
                id: 3,
                title: "Why Gen Z Needs It",
                subtitle: "Navigating Digital Overload & FOMO",
                graphicType: "comparison-grid",
                dilemma: {
                    symptoms: ["Social media comparison", "Digital hyper-fatigue", "Constant career FOMO & anxiety"],
                    gitaSolution: "Detached action and inner clarity"
                },
                shloka: "सुखदुःखे समे कृत्वा लाभालाभौ जयाजयौ।\nततो युद्धाय युज्यस्व नैवं पापमवाप्स्यसि॥",
                chapter: "Chapter 2, Verse 38",
                translation: "Treating pleasure and pain, gain and loss, victory and defeat as equal, prepare yourself for battle. Thus, you will never incur sin.",
                genZTake: "Develop a 'teflon coat' for your mental health. Don't let algorithmic likes dictate your joy or algorithmic downvotes cause a spiral.",
                bgGradient: "from-purple-950/40 via-slate-950 to-pink-950/20"
            },
            {
                id: 4,
                title: "Self-Discovery",
                subtitle: "You Are More Than Your Digital Identity",
                graphicType: "atman-graphic",
                shloka: "न जायते म्रियते वा कदाचित्\nनायं भूत्वा भविता वा न भूयः।\nअजो नित्यः शाश्वतोऽयं पुराणो\nन हन्यते हन्यमाने शरीरे॥",
                chapter: "Chapter 2, Verse 20",
                translation: "The soul is never born, nor does it ever die. It is unborn, eternal, ever-existing, and primeval. It is not slain when the body is slain.",
                genZTake: "Your self-worth isn't tied to physical labels, school ranks, or your follower count. Your core self (Atman) is indestructible and infinite.",
                bgGradient: "from-slate-950 via-emerald-950/20 to-slate-950"
            },
            {
                id: 5,
                title: "Detachment in Action",
                subtitle: "Focus on Output, Release the Anxiety",
                graphicType: "process-diagram",
                shloka: "कर्मण्येवाधिकारस्ते मा फलेषु कदाचन।\nमा कर्मफलहेतुर्भूर्मा ते सङ्गोऽस्त्वकर्मणि॥",
                chapter: "Chapter 2, Verse 47",
                translation: "You have a right to perform your prescribed duties, but you are not entitled to the fruits of your actions. Never consider yourself the cause of results, and never be attached to inaction.",
                genZTake: "Master Karma Yoga. Put 100% efforts into coding, writing, or studying because you love the craft. Detach from views/grades. No expectations = zero anxiety.",
                bgGradient: "from-pink-950/30 via-slate-950 to-violet-950/40"
            },
            {
                id: 6,
                title: "Mind Management",
                subtitle: "Debugging the Mental CPU",
                graphicType: "mind-split",
                shloka: "उद्धरेदात्मनात्मानं नात्मानमवसादयेत्।\nआत्मैव ह्यात्मनो बन्धुरात्मैव रिपुरात्मनः॥",
                chapter: "Chapter 6, Verse 5",
                translation: "Elevate yourself through the power of your mind, and do not degrade yourself. For the mind can be your greatest ally, or your worst enemy.",
                genZTake: "Your mind is a neural network. Feed it garbage content/endless scrolling, it hallucinates. Program it with meditation & discipline, and it acts as your supercomputer.",
                bgGradient: "from-cyan-950/30 via-slate-950 to-purple-950/20"
            },
            {
                id: 7,
                title: "Leadership Lessons",
                subtitle: "From Imposter Syndrome to Absolute Clarity",
                graphicType: "leadership-guide",
                shloka: "यथा दीपो निवातस्थो नेङ्गते सोपमा स्मृता।\nयोगिनो यतचित्तस्य युञ्जतो योगमात्मनः॥",
                chapter: "Chapter 6, Verse 19",
                translation: "As a lamp in a windless place does not flicker, so is the disciplined mind of a yogi meditating on the Supreme Self.",
                genZTake: "A stellar leader is unflappable. When peer pressure or market uncertainty blows like a storm, keep your focus laser-steady, just like a calm, golden flame.",
                bgGradient: "from-yellow-950/20 via-slate-950 to-slate-950"
            },
            {
                id: 8,
                title: "Daily Life Relevance",
                subtitle: "Real-World Practice over Theory",
                graphicType: "practical-framework",
                shloka: "योगस्थः कुरु कर्माणि सङ्गं त्यक्त्वा धनञ्जय।\nसिद्ध्यसिद्ध्योः समो भूत्वा समत्वं योग उच्यते॥",
                chapter: "Chapter 2, Verse 48",
                translation: "Be steadfast in yoga, O Arjuna. Perform your duty and abandon attachment to success or failure. Such evenness of mind is called Yoga.",
                genZTake: "Whether you pass an exam or fail an interview, look at both objectively as feedback loops. Recalibrate and try again. This is called high emotional intelligence (Samatvam).",
                bgGradient: "from-slate-950 via-indigo-950/30 to-pink-950/20"
            },
            {
                id: 9,
                title: "Inspirational Quotes",
                subtitle: "Swipe Cards of Instant Wisdom",
                graphicType: "quotes-carousel",
                quotes: [
                    { quote: "Change is the law of the universe. What you think of as death, is indeed life.", tag: "Reinventing yourself", ch: "2.14" },
                    { quote: "The mind is restless and difficult to control, but it can be trained by constant practice and detachment
