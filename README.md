# espace-classe-3eme
<!DOCTYPE html>
<html lang="fr" class="dark">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Espace Classe 3ème - Délégués Tao & Fatima</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- FontAwesome Icons -->
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
    <!-- Google Font: Plus Jakarta Sans -->
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">

    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        darkbg: '#0f172a',
                        darkcard: '#1e293b',
                        neonPurple: '#a855f7',
                        neonCyan: '#06b6d4',
                        neonGreen: '#10b981',
                        neonPink: '#ec4899',
                        neonAmber: '#f59e0b'
                    },
                    fontFamily: {
                        sans: ['Plus Jakarta Sans', 'sans-serif'],
                    }
                }
            }
        }
    </script>
    <style>
        body {
            background-color: #0f172a;
            color: #f8fafc;
            font-family: 'Plus Jakarta Sans', sans-serif;
            overflow-x: hidden;
        }
        .glow-purple { box-shadow: 0 0 20px -3px rgba(168, 85, 247, 0.4); }
        .glow-cyan { box-shadow: 0 0 20px -3px rgba(6, 182, 212, 0.4); }
        .glow-pink { box-shadow: 0 0 20px -3px rgba(236, 72, 153, 0.4); }
        .glow-green { box-shadow: 0 0 20px -3px rgba(16, 185, 129, 0.4); }
        .glow-amber { box-shadow: 0 0 20px -3px rgba(245, 158, 11, 0.4); }
        
        ::-webkit-scrollbar { width: 8px; height: 8px; }
        ::-webkit-scrollbar-track { background: #0f172a; }
        ::-webkit-scrollbar-thumb { background: #334155; border-radius: 4px; }
        ::-webkit-scrollbar-thumb:hover { background: #475569; }

        @media print {
            header, footer, nav, .no-print { display: none !important; }
            body { background: white !important; color: black !important; }
            .print-card { border: 1px solid #ccc !important; background: white !important; color: black !important; page-break-inside: avoid; }
        }
    </style>
</head>
<body class="min-h-screen flex flex-col justify-between selection:bg-neonPurple selection:text-white">

    <header class="sticky top-0 z-40 bg-slate-900/90 backdrop-blur-md border-b border-slate-800 shadow-lg">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-20">
                <!-- Logo & Title -->
                <div class="flex items-center gap-3 cursor-pointer" onclick="switchTab('calendar')">
                    <div class="w-12 h-12 rounded-xl bg-gradient-to-tr from-neonPurple via-neonCyan to-neonGreen p-0.5 glow-purple">
                        <div class="w-full h-full bg-slate-900 rounded-[10px] flex items-center justify-center">
                            <i class="fa-solid fa-graduation-cap text-2xl text-transparent bg-clip-text bg-gradient-to-r from-neonCyan to-neonPurple"></i>
                        </div>
                    </div>
                    <div>
                        <h1 class="text-xl font-extrabold tracking-tight bg-gradient-to-r from-white via-slate-200 to-slate-400 bg-clip-text text-transparent">Espace Classe 3<sup>e</sup></h1>
                        <p class="text-xs text-slate-400 font-medium">Délégués : <span class="text-neonCyan font-bold">Tao</span> & <span class="text-neonPink font-bold">Fatima</span></p>
                    </div>
                </div>

                <!-- Navigation Tabs (Desktop) -->
                <nav class="hidden lg:flex space-x-1 bg-slate-800/80 p-1.5 rounded-2xl border border-slate-700/60 shadow-inner">
                    <button onclick="switchTab('calendar')" id="tab-calendar" class="nav-btn px-4 py-2 rounded-xl text-sm font-semibold transition-all duration-200 flex items-center gap-2 text-slate-300 hover:text-white hover:bg-slate-700/60">
                        <i class="fa-regular fa-calendar-days text-neonCyan"></i> Calendrier
                    </button>
                    <button onclick="switchTab('ideas')" id="tab-ideas" class="nav-btn px-4 py-2 rounded-xl text-sm font-semibold transition-all duration-200 flex items-center gap-2 text-slate-300 hover:text-white hover:bg-slate-700/60">
                        <i class="fa-regular fa-lightbulb text-yellow-400"></i> Boîte à idées
                    </button>
                    <button onclick="switchTab('contact')" id="tab-contact" class="nav-btn px-4 py-2 rounded-xl text-sm font-semibold transition-all duration-200 flex items-center gap-2 text-slate-300 hover:text-white hover:bg-slate-700/60">
                        <i class="fa-regular fa-paper-plane text-neonPink"></i> Contact
                    </button>
                    <button onclick="switchTab('qcm')" id="tab-qcm" class="nav-btn px-4 py-2 rounded-xl text-sm font-semibold transition-all duration-200 flex items-center gap-2 text-slate-300 hover:text-white hover:bg-slate-700/60">
                        <i class="fa-regular fa-clipboard text-neonGreen"></i> Questionnaire
                    </button>
                    <button onclick="switchTab('admin')" id="tab-admin" class="nav-btn px-4 py-2 rounded-xl text-sm font-semibold transition-all duration-200 flex items-center gap-2 text-slate-300 hover:text-white hover:bg-slate-700/60">
                        <i class="fa-solid fa-lock text-neonPurple"></i> Admin
                    </button>
                </nav>

                <!-- Status & Audio Toggle -->
                <div class="flex items-center gap-3">
                    <div id="cloud-status-badge" class="hidden sm:flex items-center gap-2 text-xs px-3 py-1.5 rounded-xl bg-emerald-500/10 text-emerald-400 border border-emerald-500/20">
                        <span class="w-2 h-2 rounded-full bg-emerald-400 animate-pulse"></span>
                        <span id="cloud-status-text">Firebase Connecté</span>
                    </div>
                    <button onclick="toggleAudio()" id="audio-toggle-btn" title="Activer/Désactiver le son" class="p-2.5 rounded-xl bg-slate-800 border border-slate-700 text-slate-300 hover:text-neonCyan hover:border-neonCyan transition-all">
                        <i id="audio-icon" class="fa-solid fa-volume-high"></i>
                    </button>
                    <button id="mobile-menu-btn" onclick="toggleMobileMenu()" class="lg:hidden p-2.5 rounded-xl bg-slate-800 border border-slate-700 text-slate-300 hover:text-white focus:outline-none">
                        <i class="fa-solid fa-bars text-xl"></i>
                    </button>
                </div>
            </div>
        </div>

        <div id="mobile-menu" class="hidden lg:hidden bg-slate-900/95 border-b border-slate-800 px-4 pt-2 pb-4 space-y-2 backdrop-blur-lg">
            <button onclick="switchTab('calendar')" class="w-full text-left px-4 py-3 rounded-xl text-base font-medium text-slate-300 flex items-center gap-3 hover:bg-slate-800">
                <i class="fa-regular fa-calendar-days text-neonCyan w-5"></i> Calendrier de Classe
            </button>
            <button onclick="switchTab('ideas')" class="w-full text-left px-4 py-3 rounded-xl text-base font-medium text-slate-300 flex items-center gap-3 hover:bg-slate-800">
                <i class="fa-regular fa-lightbulb text-yellow-400 w-5"></i> Boîte à idées
            </button>
            <button onclick="switchTab('contact')" class="w-full text-left px-4 py-3 rounded-xl text-base font-medium text-slate-300 flex items-center gap-3 hover:bg-slate-800">
                <i class="fa-regular fa-paper-plane text-neonPink w-5"></i> Contact Délégués
            </button>
            <button onclick="switchTab('qcm')" class="w-full text-left px-4 py-3 rounded-xl text-base font-medium text-slate-300 flex items-center gap-3 hover:bg-slate-800">
                <i class="fa-regular fa-clipboard text-neonGreen w-5"></i> Questionnaire Conseil
            </button>
            <button onclick="switchTab('admin')" class="w-full text-left px-4 py-3 rounded-xl text-base font-medium text-slate-300 flex items-center gap-3 hover:bg-slate-800">
                <i class="fa-solid fa-lock text-neonPurple w-5"></i> Espace Admin
            </button>
        </div>
    </header>

    <main class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-8 flex-grow">

        <!-- SECTION 1: CALENDAR -->
        <section id="content-calendar" class="tab-content">
            <div class="flex flex-col lg:flex-row gap-8">
                <!-- Main Calendar Grid View -->
                <div class="lg:w-2/3 bg-slate-800/80 backdrop-blur-md rounded-3xl p-6 border border-slate-700/60 shadow-xl">
                    <div class="flex flex-wrap items-center justify-between gap-4 mb-6">
                        <div class="flex items-center gap-3">
                            <div class="p-3 bg-neonCyan/10 text-neonCyan rounded-2xl glow-cyan">
                                <i class="fa-solid fa-calendar-check text-xl"></i>
                            </div>
                            <div>
                                <h2 class="text-2xl font-bold text-white">Calendrier de Classe</h2>
                                <p class="text-xs text-slate-400">Devoirs, contrôles, sorties & conseil de classe</p>
                            </div>
                        </div>
                        <div class="flex items-center gap-2 bg-slate-900/80 p-1.5 rounded-2xl border border-slate-700">
                            <button onclick="changeMonth(-1)" class="p-2 hover:bg-slate-800 rounded-xl text-slate-300 transition-all"><i class="fa-solid fa-chevron-left"></i></button>
                            <span id="calendar-month-year" class="text-sm font-bold px-3 min-w-[130px] text-center text-neonCyan">--</span>
                            <button onclick="changeMonth(1)" class="p-2 hover:bg-slate-800 rounded-xl text-slate-300 transition-all"><i class="fa-solid fa-chevron-right"></i></button>
                        </div>
                    </div>

                    <!-- Category Legend -->
                    <div class="flex flex-wrap gap-4 mb-4 text-xs font-semibold px-1">
                        <span class="flex items-center gap-1.5 text-slate-300"><span class="w-3 h-3 rounded-full bg-neonPink inline-block"></span> Devoir / Contrôle</span>
                        <span class="flex items-center gap-1.5 text-slate-300"><span class="w-3 h-3 rounded-full bg-neonPurple inline-block"></span> Conseil de Classe</span>
                        <span class="flex items-center gap-1.5 text-slate-300"><span class="w-3 h-3 rounded-full bg-neonCyan inline-block"></span> Sortie / Activité</span>
                        <span class="flex items-center gap-1.5 text-slate-300"><span class="w-3 h-3 rounded-full bg-neonGreen inline-block"></span> Autre</span>
                    </div>

                    <!-- Weekdays -->
                    <div class="grid grid-cols-7 gap-2 mb-2 text-center text-xs font-extrabold text-slate-400 uppercase tracking-wider">
                        <div>Lun</div><div>Mar</div><div>Mer</div><div>Jeu</div><div>Ven</div><div>Sam</div><div>Dim</div>
                    </div>
                    <!-- Days Grid -->
                    <div id="calendar-days" class="grid grid-cols-7 gap-2"></div>
                </div>

                <!-- Event List Sidebar -->
                <div class="lg:w-1/3 flex flex-col gap-6">
                    <div class="bg-slate-800/80 backdrop-blur-md rounded-3xl p-6 border border-slate-700/60 shadow-xl flex-grow">
                        <div class="flex items-center justify-between mb-4">
                            <h3 class="text-lg font-bold text-white flex items-center gap-2">
                                <i class="fa-solid fa-list-check text-neonPink"></i> Événements à venir
                            </h3>
                            <span id="events-count-badge" class="bg-neonPink/20 text-neonPink text-xs px-2.5 py-1 rounded-full font-bold">0</span>
                        </div>
                        <div id="events-list" class="space-y-3 max-h-[500px] overflow-y-auto pr-1"></div>
                    </div>
                </div>
            </div>
        </section>

        <!-- SECTION 2: IDEAS BOX -->
        <section id="content-ideas" class="tab-content hidden">
            <div class="flex flex-col md:flex-row items-start md:items-center justify-between gap-4 mb-8">
                <div>
                    <h2 class="text-3xl font-extrabold text-white flex items-center gap-3">
                        <span class="p-3 bg-yellow-500/10 text-yellow-400 rounded-2xl inline-block glow-amber"><i class="fa-solid fa-lightbulb"></i></span>
                        Boîte à Idées de la Classe
                    </h2>
                    <p class="text-slate-400 mt-1">Exprime tes propositions, vote pour celles de tes camarades et suis leur avancement en temps réel !</p>
                </div>
                
                <button onclick="openModal('add-idea-modal')" class="bg-gradient-to-r from-neonPurple to-neonCyan text-white font-bold px-6 py-3.5 rounded-2xl shadow-lg glow-purple hover:opacity-95 transition-all flex items-center gap-2">
                    <i class="fa-solid fa-plus"></i> Proposer une idée
                </button>
            </div>

            <!-- Filter Toolbar -->
            <div class="flex flex-wrap items-center justify-between bg-slate-800/60 p-3 rounded-2xl border border-slate-700/60 mb-6 gap-4">
                <div class="flex flex-wrap gap-2">
                    <button onclick="setIdeasFilter('all')" id="filter-all" class="px-4 py-2 rounded-xl text-xs font-bold transition-all bg-slate-700 text-white">Toutes</button>
                    <button onclick="setIdeasFilter('vie-de-classe')" id="filter-vie" class="px-4 py-2 rounded-xl text-xs font-bold transition-all text-slate-400 hover:text-white">Vie de classe</button>
                    <button onclick="setIdeasFilter('sorties')" id="filter-sorties" class="px-4 py-2 rounded-xl text-xs font-bold transition-all text-slate-400 hover:text-white">Sorties / Projets</button>
                    <button onclick="setIdeasFilter('materiel')" id="filter-materiel" class="px-4 py-2 rounded-xl text-xs font-bold transition-all text-slate-400 hover:text-white">Matériel</button>
                </div>
                <div class="flex items-center gap-2 text-xs text-slate-400">
                    <label>Trier par :</label>
                    <select id="sort-ideas" onchange="renderIdeas()" class="bg-slate-900 border border-slate-700 text-white text-xs rounded-xl px-3 py-2 focus:outline-none focus:border-neonCyan">
                        <option value="votes">Popularité (Pouces 👍)</option>
                        <option value="recent">Plus récentes</option>
                    </select>
                </div>
            </div>

            <!-- Idea Cards Grid -->
            <div id="ideas-grid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6"></div>
        </section>

        <!-- SECTION 3: CONTACT FORM -->
        <section id="content-contact" class="tab-content hidden">
            <div class="max-w-3xl mx-auto">
                <div class="text-center mb-8">
                    <div class="inline-block p-4 bg-neonPink/10 text-neonPink rounded-3xl mb-3 glow-pink">
                        <i class="fa-solid fa-paper-plane text-3xl"></i>
                    </div>
                    <h2 class="text-3xl font-extrabold text-white">Contacter tes Délégués</h2>
                    <p class="text-slate-400 mt-2">Écris directement à Tao ou Fatima avec le choix de mettre ton nom ou de rester anonyme.</p>
                </div>

                <div class="bg-slate-800/80 backdrop-blur-md rounded-3xl p-6 sm:p-8 border border-slate-700/60 shadow-2xl">
                    <form id="contact-form" onsubmit="handleContactSubmit(event)" class="space-y-6">
                        <!-- Choice of Recipient -->
                        <div>
                            <label class="block text-xs font-bold uppercase tracking-wider text-slate-300 mb-3">Choisis le destinataire *</label>
                            <div class="grid grid-cols-1 sm:grid-cols-3 gap-3">
                                <label class="cursor-pointer">
                                    <input type="radio" name="recipient" value="Tao" class="peer hidden" checked>
                                    <div class="p-4 rounded-2xl border-2 border-slate-700 peer-checked:border-neonCyan peer-checked:bg-neonCyan/10 text-center transition-all hover:bg-slate-700/40">
                                        <i class="fa-solid fa-user-astronaut text-neonCyan text-2xl mb-1 block"></i>
                                        <span class="text-sm font-bold text-white">Tao</span>
                                    </div>
                                </label>
                                <label class="cursor-pointer">
                                    <input type="radio" name="recipient" value="Fatima" class="peer hidden">
                                    <div class="p-4 rounded-2xl border-2 border-slate-700 peer-checked:border-neonPink peer-checked:bg-neonPink/10 text-center transition-all hover:bg-slate-700/40">
                                        <i class="fa-solid fa-user-ninja text-neonPink text-2xl mb-1 block"></i>
                                        <span class="text-sm font-bold text-white">Fatima</span>
                                    </div>
                                </label>
                                <label class="cursor-pointer">
                                    <input type="radio" name="recipient" value="Les deux (Tao & Fatima)" class="peer hidden">
                                    <div class="p-4 rounded-2xl border-2 border-slate-700 peer-checked:border-neonPurple peer-checked:bg-neonPurple/10 text-center transition-all hover:bg-slate-700/40">
                                        <i class="fa-solid fa-users text-neonPurple text-2xl mb-1 block"></i>
                                        <span class="text-sm font-bold text-white">Les deux</span>
                                    </div>
                                </label>
                            </div>
                        </div>

                        <!-- Anonymity Toggle -->
                        <div class="p-4 bg-slate-900/60 rounded-2xl border border-slate-700 flex items-center justify-between gap-4">
                            <div>
                                <h4 class="text-sm font-bold text-white">Mode Anonyme</h4>
                                <p class="text-xs text-slate-400">Ton identité ne sera pas révélée aux délégués</p>
                            </div>
                            <label class="relative inline-flex items-center cursor-pointer">
                                <input type="checkbox" id="contact-anonymous" onchange="toggleAnonymityInput()" class="sr-only peer">
                                <div class="w-11 h-6 bg-slate-700 peer-focus:outline-none rounded-full peer peer-checked:after:translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:border-slate-300 after:border after:rounded-full after:h-5 after:w-5 after:transition-all peer-checked:bg-neonPink"></div>
                            </label>
                        </div>

                        <!-- Name Input (Hidden if Anonymous) -->
                        <div id="contact-name-container">
                            <label class="block text-xs font-bold uppercase tracking-wider text-slate-300 mb-2">Ton Nom & Prénom</label>
                            <input type="text" id="contact-sender-name" placeholder="Ex: Thomas Martin" class="w-full bg-slate-900 border border-slate-700 rounded-xl px-4 py-3 text-white placeholder-slate-500 focus:outline-none focus:border-neonCyan transition-all">
                        </div>

                        <!-- Subject -->
                        <div>
                            <label class="block text-xs font-bold uppercase tracking-wider text-slate-300 mb-2">Sujet du message *</label>
                            <input type="text" id="contact-subject" required placeholder="Ex: Remarque pour le Conseil de Classe" class="w-full bg-slate-900 border border-slate-700 rounded-xl px-4 py-3 text-white placeholder-slate-500 focus:outline-none focus:border-neonCyan transition-all">
                        </div>

                        <!-- Message Content -->
                        <div>
                            <label class="block text-xs font-bold uppercase tracking-wider text-slate-300 mb-2">Message *</label>
                            <textarea id="contact-message" required rows="5" placeholder="Explique ton idée, question ou difficulté..." class="w-full bg-slate-900 border border-slate-700 rounded-xl px-4 py-3 text-white placeholder-slate-500 focus:outline-none focus:border-neonCyan transition-all resize-none"></textarea>
                        </div>

                        <button type="submit" class="w-full py-4 rounded-xl font-bold bg-gradient-to-r from-neonPink via-neonPurple to-neonCyan text-white shadow-lg hover:opacity-95 transition-all text-center">
                            <i class="fa-solid fa-paper-plane mr-2"></i> Envoyer le message
                        </button>
                    </form>
                </div>
            </div>
        </section>

        <!-- SECTION 4: QCM QUESTIONNAIRE -->
        <section id="content-qcm" class="tab-content hidden">
            <div class="max-w-4xl mx-auto">
                <div class="text-center mb-8">
                    <div class="inline-block p-4 bg-neonGreen/10 text-neonGreen rounded-3xl mb-3 glow-green">
                        <i class="fa-solid fa-file-signature text-3xl"></i>
                    </div>
                    <h2 class="text-3xl font-extrabold text-white">Fiche Préparatoire au Conseil de Classe</h2>
                    <p class="text-slate-400 mt-2">Conçu par Tao Patruno-Riche. Tes réponses permettent à Tao, Fatima et la prof d'analyser la classe.</p>
                </div>

                <form id="qcm-form" onsubmit="handleQcmSubmit(event)" class="space-y-8">
                    
                    <!-- Identification -->
                    <div class="bg-slate-800/80 backdrop-blur-md rounded-3xl p-6 border border-slate-700/60 shadow-xl">
                        <h3 class="text-lg font-bold text-white mb-4 flex items-center gap-2">
                            <i class="fa-solid fa-id-card text-neonCyan"></i> Identification Élève
                        </h3>
                        <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                            <div>
                                <label class="block text-xs font-bold text-slate-300 mb-2">Nom et Prénom *</label>
                                <input type="text" id="qcm-student-name" required placeholder="Ex: Lucas Dupont" class="w-full bg-slate-900 border border-slate-700 rounded-xl px-4 py-3 text-white focus:border-neonCyan focus:outline-none">
                            </div>
                            <div>
                                <label class="block text-xs font-bold text-slate-300 mb-2">Classe *</label>
                                <input type="text" id="qcm-student-class" required value="3ème B" class="w-full bg-slate-900 border border-slate-700 rounded-xl px-4 py-3 text-white focus:border-neonCyan focus:outline-none">
                            </div>
                        </div>
                    </div>

                    <!-- 1. Bilan Personnel -->
                    <div class="bg-slate-800/80 backdrop-blur-md rounded-3xl p-6 border border-slate-700/60 shadow-xl space-y-5">
                        <h3 class="text-lg font-bold text-neonPurple flex items-center gap-2">
                            <i class="fa-solid fa-smile text-neonPurple"></i> 1. Bilan Personnel
                        </h3>
                        
                        <div>
                            <label class="block text-xs font-bold text-slate-300 mb-3">1.1 Comment te sens-tu en classe cette période ? *</label>
                            <div class="grid grid-cols-2 sm:grid-cols-5 gap-2">
                                <label class="cursor-pointer text-center p-3 rounded-xl border border-slate-700 bg-slate-900/60 hover:border-neonPurple flex flex-col items-center">
                                    <input type="radio" name="q1_feeling" value="Très bien" required class="mb-1">
                                    <span class="text-2xl mb-1">😄</span>
                                    <span class="text-xs text-slate-300">Très bien</span>
                                </label>
                                <label class="cursor-pointer text-center p-3 rounded-xl border border-slate-700 bg-slate-900/60 hover:border-neonPurple flex flex-col items-center">
                                    <input type="radio" name="q1_feeling" value="Bien" class="mb-1">
                                    <span class="text-2xl mb-1">🙂</span>
                                    <span class="text-xs text-slate-300">Bien</span>
                                </label>
                                <label class="cursor-pointer text-center p-3 rounded-xl border border-slate-700 bg-slate-900/60 hover:border-neonPurple flex flex-col items-center">
                                    <input type="radio" name="q1_feeling" value="Moyennement bien" class="mb-1">
                                    <span class="text-2xl mb-1">😐</span>
                                    <span class="text-xs text-slate-300">Moyennement</span>
                                </label>
                                <label class="cursor-pointer text-center p-3 rounded-xl border border-slate-700 bg-slate-900/60 hover:border-neonPurple flex flex-col items-center">
                                    <input type="radio" name="q1_feeling" value="Mal" class="mb-1">
                                    <span class="text-2xl mb-1">🙁</span>
                                    <span class="text-xs text-slate-300">Mal</span>
                                </label>
                                <label class="cursor-pointer text-center p-3 rounded-xl border border-slate-700 bg-slate-900/60 hover:border-neonPurple flex flex-col items-center">
                                    <input type="radio" name="q1_feeling" value="Très mal" class="mb-1">
                                    <span class="text-2xl mb-1">😩</span>
                                    <span class="text-xs text-slate-300">Très mal</span>
                                </label>
                            </div>
                        </div>

                        <div>
                            <label class="block text-xs font-bold text-slate-300 mb-2">1.2 Quels sont tes points forts cette période ?</label>
                            <textarea id="q1_strengths" rows="2" placeholder="Ex: Participation orale, bon esprit d'équipe..." class="w-full bg-slate-900 border border-slate-700 rounded-xl px-4 py-2.5 text-white focus:border-neonPurple focus:outline-none text-sm"></textarea>
                        </div>

                        <div>
                            <label class="block text-xs font-bold text-slate-300 mb-2">1.3 Quels sont les points que tu dois améliorer ?</label>
                            <textarea id="q1_improvements" rows="2" placeholder="Ex: Concentration en fin de journée, révision régulière..." class="w-full bg-slate-900 border border-slate-700 rounded-xl px-4 py-2.5 text-white focus:border-neonPurple focus:outline-none text-sm"></textarea>
                        </div>
                    </div>

                    <!-- 2. Travail et Méthode -->
                    <div class="bg-slate-800/80 backdrop-blur-md rounded-3xl p-6 border border-slate-700/60 shadow-xl space-y-5">
                        <h3 class="text-lg font-bold text-neonCyan flex items-center gap-2">
                            <i class="fa-solid fa-brain text-neonCyan"></i> 2. Travail et Méthode
                        </h3>

                        <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                            <div>
                                <label class="block text-xs font-bold text-slate-300 mb-2">2.1 Es-tu satisfait(e) de ton travail en classe ? *</label>
                                <div class="flex gap-4">
                                    <label class="flex items-center gap-2 text-sm text-slate-300"><input type="radio" name="q2_satisfaction_class" value="Oui" required> Oui</label>
                                    <label class="flex items-center gap-2 text-sm text-slate-300"><input type="radio" name="q2_satisfaction_class" value="En partie"> En partie</label>
                                    <label class="flex items-center gap-2 text-sm text-slate-300"><input type="radio" name="q2_satisfaction_class" value="Non"> Non</label>
                                </div>
                            </div>
                            <div>
                                <label class="block text-xs font-bold text-slate-300 mb-2">2.2 Es-tu satisfait(e) de ton travail à la maison ? *</label>
                                <div class="flex gap-4">
                                    <label class="flex items-center gap-2 text-sm text-slate-300"><input type="radio" name="q2_satisfaction_home" value="Oui" required> Oui</label>
                                    <label class="flex items-center gap-2 text-sm text-slate-300"><input type="radio" name="q2_satisfaction_home" value="En partie"> En partie</label>
                                    <label class="flex items-center gap-2 text-sm text-slate-300"><input type="radio" name="q2_satisfaction_home" value="Non"> Non</label>
                                </div>
                            </div>
                        </div>

                        <div>
                            <label class="block text-xs font-bold text-slate-300 mb-2">2.3 As-tu rencontré des difficultés particulières ? Si oui, lesquelles ?</label>
                            <textarea id="q2_difficulties" rows="2" placeholder="Ex: Trop de devoirs certains soirs, devoirs complexes..." class="w-full bg-slate-900 border border-slate-700 rounded-xl px-4 py-2.5 text-white focus:border-neonCyan focus:outline-none text-sm"></textarea>
                        </div>
                    </div>

                    <!-- 3. Résultats Scolaires -->
                    <div class="bg-slate-800/80 backdrop-blur-md rounded-3xl p-6 border border-slate-700/60 shadow-xl space-y-5">
                        <h3 class="text-lg font-bold text-neonAmber flex items-center gap-2">
                            <i class="fa-solid fa-chart-line text-neonAmber"></i> 3. Résultats Scolaires
                        </h3>

                        <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                            <div>
                                <label class="block text-xs font-bold text-slate-300 mb-2">3.1 Matière(s) la/les plus facile(s) & Pourquoi ?</label>
                                <textarea id="q3_easy_subjects" rows="2" placeholder="Ex: Histoire (j'aime les explications)..." class="w-full bg-slate-900 border border-slate-700 rounded-xl px-4 py-2.5 text-white focus:border-neonAmber focus:outline-none text-sm"></textarea>
                            </div>
                            <div>
                                <label class="block text-xs font-bold text-slate-300 mb-2">3.2 Matière(s) la/les plus difficile(s) & Pourquoi ?</label>
                                <textarea id="q3_hard_subjects" rows="2" placeholder="Ex: Maths (formules à retenir)..." class="w-full bg-slate-900 border border-slate-700 rounded-xl px-4 py-2.5 text-white focus:border-neonAmber focus:outline-none text-sm"></textarea>
                            </div>
                        </div>
                    </div>

                    <!-- 4. Vie de Classe -->
                    <div class="bg-slate-800/80 backdrop-blur-md rounded-3xl p-6 border border-slate-700/60 shadow-xl space-y-5">
                        <h3 class="text-lg font-bold text-neonPink flex items-center gap-2">
                            <i class="fa-solid fa-users text-neonPink"></i> 4. Vie de Classe et Comportement
                        </h3>

                        <div>
                            <label class="block text-xs font-bold text-slate-300 mb-3">4.1 Comment est l'ambiance dans la classe ? *</label>
                            <div class="grid grid-cols-2 sm:grid-cols-5 gap-2">
                                <label class="cursor-pointer text-center p-2.5 rounded-xl border border-slate-700 bg-slate-900/60 hover:border-neonPink text-xs text-slate-300"><input type="radio" name="q4_atmosphere" value="Très bonne" required class="mr-1"> Très bonne</label>
                                <label class="cursor-pointer text-center p-2.5 rounded-xl border border-slate-700 bg-slate-900/60 hover:border-neonPink text-xs text-slate-300"><input type="radio" name="q4_atmosphere" value="Bonne" class="mr-1"> Bonne</label>
                                <label class="cursor-pointer text-center p-2.5 rounded-xl border border-slate-700 bg-slate-900/60 hover:border-neonPink text-xs text-slate-300"><input type="radio" name="q4_atmosphere" value="Moyenne" class="mr-1"> Moyenne</label>
                                <label class="cursor-pointer text-center p-2.5 rounded-xl border border-slate-700 bg-slate-900/60 hover:border-neonPink text-xs text-slate-300"><input type="radio" name="q4_atmosphere" value="Mauvaise" class="mr-1"> Mauvaise</label>
                                <label class="cursor-pointer text-center p-2.5 rounded-xl border border-slate-700 bg-slate-900/60 hover:border-neonPink text-xs text-slate-300"><input type="radio" name="q4_atmosphere" value="Très mauvaise" class="mr-1"> Très mauvaise</label>
                            </div>
                        </div>

                        <div>
                            <label class="block text-xs font-bold text-slate-300 mb-2">4.2 Te sens-tu bien intégré(e) dans ta classe ? *</label>
                            <div class="flex gap-4">
                                <label class="flex items-center gap-2 text-sm text-slate-300"><input type="radio" name="q4_integrated" value="Oui" required> Oui</label>
                                <label class="flex items-center gap-2 text-sm text-slate-300"><input type="radio" name="q4_integrated" value="En partie"> En partie</label>
                                <label class="flex items-center gap-2 text-sm text-slate-300"><input type="radio" name="q4_integrated" value="Non"> Non</label>
                            </div>
                        </div>
                    </div>

                    <!-- Submit -->
                    <button type="submit" class="w-full py-4 rounded-2xl font-extrabold bg-gradient-to-r from-neonGreen via-neonCyan to-neonPurple text-white shadow-xl hover:opacity-95 transition-all text-lg flex items-center justify-center gap-2">
                        <i class="fa-solid fa-paper-plane"></i> Envoyer ma Fiche Conseil
                    </button>
                </form>
            </div>
        </section>

        <!-- SECTION 5: ADMIN PANEL -->
        <section id="content-admin" class="tab-content hidden">
            <!-- Login State -->
            <div id="admin-login-card" class="max-w-md mx-auto bg-slate-800/80 backdrop-blur-md rounded-3xl p-8 border border-slate-700/60 shadow-2xl">
                <div class="text-center mb-6">
                    <div class="w-16 h-16 bg-neonPurple/10 text-neonPurple rounded-2xl flex items-center justify-center mx-auto mb-3 glow-purple">
                        <i class="fa-solid fa-shield-halved text-3xl"></i>
                    </div>
                    <h2 class="text-2xl font-extrabold text-white">Espace Administration</h2>
                    <p class="text-xs text-slate-400 mt-1">Réservé à Tao, Fatima et le Professeur Principal</p>
                </div>

                <form onsubmit="handleAdminLogin(event)" class="space-y-4">
                    <div>
                        <label class="block text-xs font-bold text-slate-300 mb-2">Identifiant / Rôle</label>
                        <select id="admin-role-select" class="w-full bg-slate-900 border border-slate-700 text-white rounded-xl px-4 py-3 text-sm focus:outline-none focus:border-neonPurple">
                            <option value="Tao">Tao (Délégué)</option>
                            <option value="Fatima">Fatima (Déléguée)</option>
                            <option value="Professeur">Professeur Principal</option>
                        </select>
                    </div>
                    <div>
                        <label class="block text-xs font-bold text-slate-300 mb-2">Mot de passe</label>
                        <input type="password" id="admin-password" required placeholder="Mot de passe" class="w-full bg-slate-900 border border-slate-700 text-white rounded-xl px-4 py-3 text-sm focus:outline-none focus:border-neonPurple">
                    </div>
                    <button type="submit" class="w-full py-3.5 rounded-xl font-bold bg-gradient-to-r from-neonPurple to-neonCyan text-white shadow-lg hover:opacity-95 transition-all">
                        Connexion Admin
                    </button>
                </form>
            </div>

            <!-- Dashboard View (When Logged In) -->
            <div id="admin-dashboard" class="hidden">
                <div class="flex flex-col md:flex-row items-start md:items-center justify-between gap-4 mb-6">
                    <div>
                        <div class="flex items-center gap-2">
                            <span class="px-2.5 py-1 rounded-full bg-neonPurple/20 text-neonPurple font-bold text-xs">Connecté</span>
                            <h2 class="text-2xl font-extrabold text-white">Tableau de Bord Admin</h2>
                        </div>
                        <p class="text-xs text-slate-400 mt-0.5">Bienvenue <span id="current-admin-name" class="font-bold text-neonCyan">--</span> ! Tout est synchronisé en temps réel.</p>
                    </div>

                    <div class="flex gap-2">
                        <button onclick="logoutAdmin()" class="px-4 py-2 bg-slate-800 hover:bg-slate-700 text-slate-300 border border-slate-700 rounded-xl text-xs font-bold transition-all">
                            <i class="fa-solid fa-right-from-bracket mr-1"></i> Déconnexion
                        </button>
                    </div>
                </div>

                <!-- Admin Navigation Subtabs -->
                <div class="flex flex-wrap gap-2 border-b border-slate-800 pb-4 mb-6">
                    <button onclick="switchAdminTab('qcm')" id="admin-subtab-qcm" class="px-4 py-2.5 rounded-xl text-xs font-bold transition-all bg-neonPurple text-white">
                        <i class="fa-solid fa-chart-pie mr-1.5"></i> Résultats & Stats QCM
                    </button>
                    <button onclick="switchAdminTab('messages')" id="admin-subtab-messages" class="px-4 py-2.5 rounded-xl text-xs font-bold transition-all text-slate-400 hover:bg-slate-800">
                        <i class="fa-solid fa-envelope mr-1.5"></i> Messages Reçus (<span id="unread-count">0</span>)
                    </button>
                    <button onclick="switchAdminTab('ideas')" id="admin-subtab-ideas" class="px-4 py-2.5 rounded-xl text-xs font-bold transition-all text-slate-400 hover:bg-slate-800">
                        <i class="fa-solid fa-lightbulb mr-1.5"></i> Modération Idées
                    </button>
                    <button onclick="switchAdminTab('events')" id="admin-subtab-events" class="px-4 py-2.5 rounded-xl text-xs font-bold transition-all text-slate-400 hover:bg-slate-800">
                        <i class="fa-solid fa-calendar-plus mr-1.5"></i> Gestion Calendrier
                    </button>
                    <button onclick="switchAdminTab('settings')" id="admin-subtab-settings" class="px-4 py-2.5 rounded-xl text-xs font-bold transition-all text-slate-400 hover:bg-slate-800">
                        <i class="fa-solid fa-key mr-1.5"></i> Paramètres
                    </button>
                </div>

                <!-- Subtab 1: QCM Stats & Responses -->
                <div id="admin-view-qcm" class="admin-view space-y-6">
                    <div class="flex flex-wrap items-center justify-between gap-4">
                        <h3 class="text-lg font-bold text-white flex items-center gap-2">
                            <i class="fa-solid fa-poll text-neonGreen"></i> Synthèse des Réponses au Conseil de Classe
                        </h3>
                        <div class="flex gap-2">
                            <button onclick="exportQcmCSV()" class="px-3.5 py-2 rounded-xl bg-slate-800 hover:bg-slate-700 text-xs font-bold text-slate-200 border border-slate-700 flex items-center gap-1.5">
                                <i class="fa-solid fa-file-csv text-neonGreen"></i> Exporter CSV
                            </button>
                            <button onclick="window.print()" class="px-3.5 py-2 rounded-xl bg-slate-800 hover:bg-slate-700 text-xs font-bold text-slate-200 border border-slate-700 flex items-center gap-1.5">
                                <i class="fa-solid fa-print text-neonCyan"></i> Imprimer PDF
                            </button>
                        </div>
                    </div>

                    <!-- Percentages Breakdown Grid -->
                    <div class="grid grid-cols-1 md:grid-cols-3 gap-4" id="qcm-stats-grid"></div>

                    <!-- List of Individual Responses -->
                    <div class="bg-slate-800/80 backdrop-blur-md rounded-3xl p-6 border border-slate-700/60 shadow-xl">
                        <h4 class="text-sm font-bold text-white uppercase tracking-wider mb-4">Réponses Individuelles par Élève</h4>
                        <div id="qcm-individual-list" class="space-y-4"></div>
                    </div>
                </div>

                <!-- Subtab 2: Messages Received -->
                <div id="admin-view-messages" class="admin-view hidden space-y-4">
                    <div id="admin-messages-list" class="space-y-4"></div>
                </div>

                <!-- Subtab 3: Ideas Moderation -->
                <div id="admin-view-ideas" class="admin-view hidden space-y-4">
                    <div id="admin-ideas-list" class="grid grid-cols-1 md:grid-cols-2 gap-4"></div>
                </div>

                <!-- Subtab 4: Add Calendar Event -->
                <div id="admin-view-events" class="admin-view hidden space-y-6">
                    <div class="max-w-xl bg-slate-800/80 backdrop-blur-md rounded-3xl p-6 border border-slate-700/60">
                        <h3 class="text-lg font-bold text-white mb-4">Ajouter un Événement au Calendrier</h3>
                        <form onsubmit="handleAddEvent(event)" class="space-y-4">
                            <div>
                                <label class="block text-xs font-bold text-slate-300 mb-1">Titre *</label>
                                <input type="text" id="event-title" required placeholder="Ex: Controle de Mathématiques" class="w-full bg-slate-900 border border-slate-700 rounded-xl px-4 py-2.5 text-white text-sm focus:outline-none focus:border-neonCyan">
                            </div>
                            <div class="grid grid-cols-2 gap-3">
                                <div>
                                    <label class="block text-xs font-bold text-slate-300 mb-1">Date *</label>
                                    <input type="date" id="event-date" required class="w-full bg-slate-900 border border-slate-700 rounded-xl px-4 py-2.5 text-white text-sm focus:outline-none focus:border-neonCyan">
                                </div>
                                <div>
                                    <label class="block text-xs font-bold text-slate-300 mb-1">Catégorie *</label>
                                    <select id="event-category" class="w-full bg-slate-900 border border-slate-700 text-white rounded-xl px-4 py-2.5 text-sm focus:outline-none focus:border-neonCyan">
                                        <option value="devoir">Devoir / Contrôle</option>
                                        <option value="conseil">Conseil de classe</option>
                                        <option value="sortie">Sortie / Activité</option>
                                        <option value="autre">Autre</option>
                                    </select>
                                </div>
                            </div>
                            <div>
                                <label class="block text-xs font-bold text-slate-300 mb-1">Description (optionnelle)</label>
                                <input type="text" id="event-desc" placeholder="Ex: Chapitre 4 et 5" class="w-full bg-slate-900 border border-slate-700 rounded-xl px-4 py-2.5 text-white text-sm focus:outline-none focus:border-neonCyan">
                            </div>
                            <button type="submit" class="w-full py-3 rounded-xl font-bold bg-neonCyan text-slate-950 hover:opacity-90 transition-all">
                                Ajout au Calendrier
                            </button>
                        </form>
                    </div>
                </div>

                <!-- Subtab 5: Admin Password Settings -->
                <div id="admin-view-settings" class="admin-view hidden space-y-6">
                    <div class="max-w-md bg-slate-800/80 backdrop-blur-md rounded-3xl p-6 border border-slate-700/60">
                        <h3 class="text-lg font-bold text-white mb-4">Modifier mon Mot de Passe</h3>
                        <form onsubmit="handleChangePassword(event)" class="space-y-4">
                            <div>
                                <label class="block text-xs font-bold text-slate-300 mb-1">Nouveau Mot de Passe</label>
                                <input type="password" id="new-admin-password" required placeholder="Tapez le nouveau mot de passe" class="w-full bg-slate-900 border border-slate-700 rounded-xl px-4 py-2.5 text-white text-sm focus:outline-none focus:border-neonPurple">
                            </div>
                            <button type="submit" class="w-full py-3 rounded-xl font-bold bg-neonPurple text-white hover:opacity-90 transition-all">
                                Mettre à jour le mot de passe
                            </button>
                        </form>
                    </div>
                </div>
            </div>
        </section>

    </main>

    <!-- MODAL: ADD IDEA -->
    <div id="add-idea-modal" class="fixed inset-0 bg-slate-950/80 backdrop-blur-sm z-50 flex items-center justify-center p-4 hidden">
        <div class="bg-slate-800 rounded-3xl max-w-lg w-full p-6 border border-slate-700 shadow-2xl space-y-5">
            <div class="flex items-center justify-between border-b border-slate-700 pb-3">
                <h3 class="text-lg font-bold text-white flex items-center gap-2">
                    <i class="fa-solid fa-lightbulb text-yellow-400"></i> Proposer une idée pour la classe
                </h3>
                <button onclick="closeModal('add-idea-modal')" class="text-slate-400 hover:text-white"><i class="fa-solid fa-xmark text-xl"></i></button>
            </div>
            
            <form onsubmit="handleAddIdeaSubmit(event)" class="space-y-4">
                <div>
                    <label class="block text-xs font-bold text-slate-300 mb-1">Titre de l'idée *</label>
                    <input type="text" id="idea-title" required placeholder="Ex: Organiser un tournoi de Foot à la récréation" class="w-full bg-slate-900 border border-slate-700 rounded-xl px-4 py-2.5 text-white text-sm focus:outline-none focus:border-yellow-400">
                </div>
                <div>
                    <label class="block text-xs font-bold text-slate-300 mb-1">Catégorie *</label>
                    <select id="idea-category" class="w-full bg-slate-900 border border-slate-700 text-white rounded-xl px-4 py-2.5 text-sm focus:outline-none focus:border-yellow-400">
                        <option value="vie-de-classe">Vie de classe</option>
                        <option value="sorties">Sortie / Projet</option>
                        <option value="materiel">Matériel / Équipement</option>
                    </select>
                </div>
                <div>
                    <label class="block text-xs font-bold text-slate-300 mb-1">Explication / Détails *</label>
                    <textarea id="idea-desc" required rows="3" placeholder="Explique ton idée en détail pour convaincre tes camarades..." class="w-full bg-slate-900 border border-slate-700 rounded-xl px-4 py-2.5 text-white text-sm focus:outline-none focus:border-yellow-400 resize-none"></textarea>
                </div>
                <div>
                    <label class="block text-xs font-bold text-slate-300 mb-1">Ton prénom (Optionnel)</label>
                    <input type="text" id="idea-author" placeholder="Anonyme si vide" class="w-full bg-slate-900 border border-slate-700 rounded-xl px-4 py-2.5 text-white text-sm focus:outline-none focus:border-yellow-400">
                </div>

                <div class="flex justify-end gap-3 pt-2">
                    <button type="button" onclick="closeModal('add-idea-modal')" class="px-4 py-2.5 rounded-xl text-xs font-bold bg-slate-700 text-slate-300 hover:bg-slate-600">Annuler</button>
                    <button type="submit" class="px-6 py-2.5 rounded-xl text-xs font-bold bg-yellow-400 text-slate-950 hover:bg-yellow-300">Publier l'idée</button>
                </div>
            </form>
        </div>
    </div>

    <!-- TOAST NOTIFICATION -->
    <div id="toast" class="fixed bottom-6 right-6 bg-slate-800 border border-slate-700 text-white px-5 py-3.5 rounded-2xl shadow-2xl z-50 transition-all duration-300 opacity-0 translate-y-10 flex items-center gap-3">
        <i id="toast-icon" class="fa-solid fa-circle-check text-neonGreen text-xl"></i>
        <span id="toast-message" class="text-sm font-semibold">--</span>
    </div>

    <footer class="bg-slate-900 border-t border-slate-800 py-6 text-center text-xs text-slate-500">
        <p>Espace Classe 3<sup>ème</sup> &bull; Créé pour la classe par <span class="text-neonCyan font-bold">Tao Patruno-Riche</span> & <span class="text-neonPink font-bold">Fatima</span></p>
    </footer>

    <!-- FIREBASE MODULE SCRIPT -->
    <script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-app.js";
        import { getAuth, signInAnonymously, signInWithCustomToken } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-auth.js";
        import { getFirestore, collection, doc, addDoc, setDoc, updateDoc, deleteDoc, onSnapshot } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-firestore.js";

        // Firebase Configuration Detection
        const appId = typeof __app_id !== 'undefined' ? __app_id : 'classroom-hub-3eme';
        const firebaseConfig = typeof __firebase_config !== 'undefined' ? JSON.parse(__firebase_config) : {
            apiKey: "demo-key",
            authDomain: "demo-app.firebaseapp.com",
            projectId: "demo-app",
            storageBucket: "demo-app.appspot.com",
            messagingSenderId: "123456789",
            appId: "1:123456789:web:abcdef"
        };

        let app, db, auth, user;

        try {
            app = initializeApp(firebaseConfig);
            db = getFirestore(app);
            auth = getAuth(app);
        } catch (e) {
            console.warn("Firebase Init fallback:", e);
        }

        // Mandatory Auth Setup
        async function initAuth() {
            try {
                if (typeof __initial_auth_token !== 'undefined' && __initial_auth_token) {
                    const userCred = await signInWithCustomToken(auth, __initial_auth_token);
                    user = userCred.user;
                } else {
                    const userCred = await signInAnonymously(auth);
                    user = userCred.user;
                }
                console.log("Firebase Auth success. UID:", user.uid);
                setupRealtimeListeners();
            } catch (err) {
                console.error("Auth error, using local state fallback:", err);
                document.getElementById('cloud-status-text').innerText = "Mode Local (Hors-Ligne)";
                document.getElementById('cloud-status-badge').className = "hidden sm:flex items-center gap-2 text-xs px-3 py-1.5 rounded-xl bg-amber-500/10 text-amber-400 border border-amber-500/20";
            }
        }

        // Setup Realtime Collections Listeners (RULE 1 strictly applied)
        function setupRealtimeListeners() {
            if (!user || !db) return;

            // 1. Ideas Listener
            const ideasRef = collection(db, 'artifacts', appId, 'public', 'data', 'ideas');
            onSnapshot(ideasRef, (snapshot) => {
                const ideas = [];
                snapshot.forEach(docSnap => {
                    ideas.push({ id: docSnap.id, ...docSnap.data() });
                });
                if (ideas.length > 0) {
                    window.appState.ideas = ideas;
                    window.renderIdeas();
                    if (window.appState.currentAdmin) window.renderAdminIdeas();
                }
            }, (err) => console.log("Ideas snapshot fallback:", err));

            // 2. Events Listener
            const eventsRef = collection(db, 'artifacts', appId, 'public', 'data', 'events');
            onSnapshot(eventsRef, (snapshot) => {
                const events = [];
                snapshot.forEach(docSnap => {
                    events.push({ id: docSnap.id, ...docSnap.data() });
                });
                if (events.length > 0) {
                    window.appState.events = events;
                    window.renderCalendar();
                    window.renderUpcomingEvents();
                }
            }, (err) => console.log("Events snapshot fallback:", err));

            // 3. QCM Responses Listener
            const qcmRef = collection(db, 'artifacts', appId, 'public', 'data', 'qcm_responses');
            onSnapshot(qcmRef, (snapshot) => {
                const qcms = [];
                snapshot.forEach(docSnap => {
                    qcms.push({ id: docSnap.id, ...docSnap.data() });
                });
                window.appState.qcmResponses = qcms;
                if (window.appState.currentAdmin) window.renderAdminQcmStats();
            }, (err) => console.log("QCM snapshot fallback:", err));

            // 4. Messages Listener
            const messagesRef = collection(db, 'artifacts', appId, 'public', 'data', 'messages');
            onSnapshot(messagesRef, (snapshot) => {
                const msgs = [];
                snapshot.forEach(docSnap => {
                    msgs.push({ id: docSnap.id, ...docSnap.data() });
                });
                window.appState.messages = msgs;
                if (window.appState.currentAdmin) window.renderAdminMessages();
            }, (err) => console.log("Messages snapshot fallback:", err));
        }

        // Global Firebase Helper Actions
        window.firebaseSaveIdea = async function(ideaObj) {
            if (!user || !db) return false;
            try {
                const ideasRef = collection(db, 'artifacts', appId, 'public', 'data', 'ideas');
                await addDoc(ideasRef, ideaObj);
                return true;
            } catch (e) {
                console.error("Save idea error:", e);
                return false;
            }
        };

        window.firebaseVoteIdea = async function(ideaId, updatedVotes, voterUid) {
            if (!user || !db) return;
            try {
                const ideaDoc = doc(db, 'artifacts', appId, 'public', 'data', 'ideas', ideaId);
                await updateDoc(ideaDoc, { votes: updatedVotes, voterIds: updatedVotes });
            } catch (e) {
                console.error("Vote update error:", e);
            }
        };

        window.firebaseUpdateIdeaStatus = async function(ideaId, newStatus) {
            if (!user || !db) return;
            try {
                const ideaDoc = doc(db, 'artifacts', appId, 'public', 'data', 'ideas', ideaId);
                await updateDoc(ideaDoc, { status: newStatus });
            } catch (e) {
                console.error("Status update error:", e);
            }
        };

        window.firebaseDeleteIdea = async function(ideaId) {
            if (!user || !db) return;
            try {
                const ideaDoc = doc(db, 'artifacts', appId, 'public', 'data', 'ideas', ideaId);
                await deleteDoc(ideaDoc);
            } catch (e) {
                console.error("Delete idea error:", e);
            }
        };

        window.firebaseSaveContactMessage = async function(msgObj) {
            if (!user || !db) return false;
            try {
                const msgsRef = collection(db, 'artifacts', appId, 'public', 'data', 'messages');
                await addDoc(msgsRef, msgObj);
                return true;
            } catch (e) {
                console.error("Save message error:", e);
                return false;
            }
        };

        window.firebaseDeleteMessage = async function(msgId) {
            if (!user || !db) return;
            try {
                const msgDoc = doc(db, 'artifacts', appId, 'public', 'data', 'messages', msgId);
                await deleteDoc(msgDoc);
            } catch (e) {
                console.error("Delete msg error:", e);
            }
        };

        window.firebaseSaveQcm = async function(qcmData) {
            if (!user || !db) return false;
            try {
                const qcmRef = collection(db, 'artifacts', appId, 'public', 'data', 'qcm_responses');
                await addDoc(qcmRef, qcmData);
                return true;
            } catch (e) {
                console.error("Save QCM error:", e);
                return false;
            }
        };

        window.firebaseSaveEvent = async function(evtObj) {
            if (!user || !db) return false;
            try {
                const eventsRef = collection(db, 'artifacts', appId, 'public', 'data', 'events');
                await addDoc(eventsRef, evtObj);
                return true;
            } catch (e) {
                console.error("Save event error:", e);
                return false;
            }
        };

        window.firebaseDeleteEvent = async function(evtId) {
            if (!user || !db) return;
            try {
                const evtDoc = doc(db, 'artifacts', appId, 'public', 'data', 'events', evtId);
                await deleteDoc(evtDoc);
            } catch (e) {
                console.error("Delete event error:", e);
            }
        };

        window.addEventListener('load', initAuth);
    </script>

    <!-- APPLICATION STATE & UI JS LOGIC -->
    <script>
        // User unique client ID for upvoting thumbs-up
        let clientUid = localStorage.getItem('class_hub_client_uid');
        if (!clientUid) {
            clientUid = 'user_' + Math.random().toString(36).substr(2, 9);
            localStorage.setItem('class_hub_client_uid', clientUid);
        }

        // Sound Synthesis (Web Audio API - No external files)
        let audioEnabled = true;
        const audioCtx = new (window.AudioContext || window.webkitAudioContext)();

        function playSound(type) {
            if (!audioEnabled) return;
            try {
                const osc = audioCtx.createOscillator();
                const gain = audioCtx.createGain();
                osc.connect(gain);
                gain.connect(audioCtx.destination);

                if (type === 'click') {
                    osc.frequency.value = 400;
                    gain.gain.setValueAtTime(0.05, audioCtx.currentTime);
                    gain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + 0.05);
                    osc.start();
                    osc.stop(audioCtx.currentTime + 0.05);
                } else if (type === 'success') {
                    osc.type = 'triangle';
                    osc.frequency.setValueAtTime(300, audioCtx.currentTime);
                    osc.frequency.exponentialRampToValueAtTime(600, audioCtx.currentTime + 0.15);
                    gain.gain.setValueAtTime(0.08, audioCtx.currentTime);
                    gain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + 0.15);
                    osc.start();
                    osc.stop(audioCtx.currentTime + 0.15);
                }
            } catch(e){}
        }

        function toggleAudio() {
            audioEnabled = !audioEnabled;
            const btn = document.getElementById('audio-toggle-btn');
            const icon = document.getElementById('audio-icon');
            if (audioEnabled) {
                icon.className = 'fa-solid fa-volume-high';
                btn.className = 'p-2.5 rounded-xl bg-slate-800 border border-slate-700 text-slate-300 hover:text-neonCyan transition-all';
                showToast("Son activé");
            } else {
                icon.className = 'fa-solid fa-volume-xmark';
                btn.className = 'p-2.5 rounded-xl bg-slate-800 border border-slate-700 text-slate-500 transition-all';
                showToast("Son désactivé");
            }
        }

        // Global State
        window.appState = {
            currentTab: 'calendar',
            ideasFilter: 'all',
            ideasSort: 'votes',
            currentAdmin: null,
            adminPasswords: JSON.parse(localStorage.getItem('admin_passwords')) || {
                'Tao': 'admin123',
                'Fatima': 'admin123',
                'Professeur': 'admin123'
            },
            currentDate: new Date(2026, 9, 1), // Default Oct 2026
            events: [
                { id: '1', title: 'Contrôle d\'Histoire-Géo', date: '2026-10-12', category: 'devoir', desc: 'Réviser la Seconde Guerre Mondiale' },
                { id: '2', title: 'Conseil de Classe 1er Trimestre', date: '2026-10-22', category: 'conseil', desc: 'Présence des délégués Tao & Fatima' },
                { id: '3', title: 'Sortie Musée des Sciences', date: '2026-10-28', category: 'sortie', desc: 'Prévoir un pique-nique' }
            ],
            ideas: [
                { id: 'i1', title: 'Créer un club d\'échecs le vendredi midi', category: 'vie-de-classe', desc: 'On pourrait utiliser la salle 104 pendant la pause de midi.', author: 'Tao', votes: 12, voterIds: ['user_1'], status: 'accepted', date: '2026-10-01' },
                { id: 'i2', title: 'Avoir un casier supplémentaire pour le sport', category: 'materiel', desc: 'Les sacs de sport prennent trop de place en classe.', author: 'Fatima', votes: 8, voterIds: [], status: 'in-progress', date: '2026-10-02' }
            ],
            messages: [],
            qcmResponses: []
        };

        // Navigation Switcher
        window.switchTab = function(tabName) {
            playSound('click');
            window.appState.currentTab = tabName;
            
            document.querySelectorAll('.tab-content').forEach(el => el.classList.add('hidden'));
            document.getElementById('content-' + tabName).classList.remove('hidden');

            document.querySelectorAll('.nav-btn').forEach(btn => {
                btn.classList.remove('bg-slate-700', 'text-white', 'shadow');
                btn.classList.add('text-slate-300');
            });
            const activeNav = document.getElementById('tab-' + tabName);
            if (activeNav) {
                activeNav.classList.add('bg-slate-700', 'text-white', 'shadow');
            }

            // Close mobile menu if open
            document.getElementById('mobile-menu').classList.add('hidden');

            if (tabName === 'calendar') window.renderCalendar();
            if (tabName === 'ideas') window.renderIdeas();
        };

        window.toggleMobileMenu = function() {
            playSound('click');
            const menu = document.getElementById('mobile-menu');
            menu.classList.toggle('hidden');
        };

        // 1. CALENDAR LOGIC
        window.renderCalendar = function() {
            const grid = document.getElementById('calendar-days');
            grid.innerHTML = '';
            
            const currDate = window.appState.currentDate;
            const year = currDate.getFullYear();
            const month = currDate.getMonth();

            const monthNames = ["Janvier", "Février", "Mars", "Avril", "Mai", "Juin", "Juillet", "Août", "Septembre", "Octobre", "Novembre", "Décembre"];
            document.getElementById('calendar-month-year').innerText = `${monthNames[month]} ${year}`;

            const firstDayIndex = (new Date(year, month, 1).getDay() + 6) % 7; 
            const daysInMonth = new Date(year, month + 1, 0).getDate();

            // Empty previous month padding
            for (let i = 0; i < firstDayIndex; i++) {
                const emptyCell = document.createElement('div');
                emptyCell.className = 'h-16 sm:h-20 bg-slate-900/30 rounded-xl border border-slate-800/40 opacity-30';
                grid.appendChild(emptyCell);
            }

            // Days cells
            for (let day = 1; day <= daysInMonth; day++) {
                const dayStr = `${year}-${String(month + 1).padStart(2, '0')}-${String(day).padStart(2, '0')}`;
                const dayEvents = window.appState.events.filter(e => e.date === dayStr);

                const cell = document.createElement('div');
                cell.className = 'h-16 sm:h-20 bg-slate-900/60 rounded-xl border border-slate-700/50 p-1.5 flex flex-col justify-between transition-all hover:border-slate-500';

                const dayNum = document.createElement('span');
                dayNum.className = 'text-xs font-bold text-slate-300';
                dayNum.innerText = day;
                cell.appendChild(dayNum);

                const dotsContainer = document.createElement('div');
                dotsContainer.className = 'flex flex-wrap gap-1 mt-1';

                dayEvents.forEach(evt => {
                    const badge = document.createElement('div');
                    let color = 'bg-neonGreen';
                    if (evt.category === 'devoir') color = 'bg-neonPink';
                    if (evt.category === 'conseil') color = 'bg-neonPurple';
                    if (evt.category === 'sortie') color = 'bg-neonCyan';

                    badge.className = `w-2 h-2 sm:w-2.5 sm:h-2.5 rounded-full ${color}`;
                    badge.title = evt.title;
                    dotsContainer.appendChild(badge);
                });

                cell.appendChild(dotsContainer);
                grid.appendChild(cell);
            }
        };

        window.changeMonth = function(dir) {
            playSound('click');
            window.appState.currentDate.setMonth(window.appState.currentDate.getMonth() + dir);
            window.renderCalendar();
        };

        window.renderUpcomingEvents = function() {
            const container = document.getElementById('events-list');
            container.innerHTML = '';

            const sorted = [...window.appState.events].sort((a,b) => new Date(a.date) - new Date(b.date));
            document.getElementById('events-count-badge').innerText = sorted.length;

            if (sorted.length === 0) {
                container.innerHTML = `<p class="text-xs text-slate-500 text-center py-4">Aucun événement prévu</p>`;
                return;
            }

            sorted.forEach(evt => {
                let badgeColor = 'bg-neonGreen/20 text-neonGreen border-neonGreen/30';
                let icon = 'fa-asterisk';
                if (evt.category === 'devoir') { badgeColor = 'bg-neonPink/20 text-neonPink border-neonPink/30'; icon = 'fa-pen-to-square'; }
                if (evt.category === 'conseil') { badgeColor = 'bg-neonPurple/20 text-neonPurple border-neonPurple/30'; icon = 'fa-user-group'; }
                if (evt.category === 'sortie') { badgeColor = 'bg-neonCyan/20 text-neonCyan border-neonCyan/30'; icon = 'fa-bus'; }

                const card = document.createElement('div');
                card.className = 'p-3.5 bg-slate-900/60 rounded-2xl border border-slate-700/60 flex items-start justify-between gap-3';
                card.innerHTML = `
                    <div class="flex items-start gap-3">
                        <div class="p-2.5 rounded-xl border ${badgeColor} flex items-center justify-center">
                            <i class="fa-solid ${icon} text-sm"></i>
                        </div>
                        <div>
                            <h4 class="text-xs font-bold text-white">${evt.title}</h4>
                            <p class="text-[11px] text-slate-400">${evt.desc || 'Pas de description'}</p>
                            <span class="text-[10px] text-slate-500 font-semibold mt-1 inline-block"><i class="fa-regular fa-clock mr-1"></i>${evt.date}</span>
                        </div>
                    </div>
                `;
                container.appendChild(card);
            });
        };

        // 2. IDEAS BOX LOGIC
        window.setIdeasFilter = function(filter) {
            playSound('click');
            window.appState.ideasFilter = filter;
            ['all', 'vie', 'sorties', 'materiel'].forEach(f => {
                const btn = document.getElementById('filter-' + f);
                if (btn) {
                    btn.className = "px-4 py-2 rounded-xl text-xs font-bold transition-all text-slate-400 hover:text-white";
                }
            });
            const activeBtn = document.getElementById('filter-' + (filter === 'vie-de-classe' ? 'vie' : filter));
            if (activeBtn) activeBtn.className = "px-4 py-2 rounded-xl text-xs font-bold transition-all bg-slate-700 text-white";
            
            window.renderIdeas();
        };

        window.renderIdeas = function() {
            const grid = document.getElementById('ideas-grid');
            grid.innerHTML = '';

            const sortVal = document.getElementById('sort-ideas').value;
            let list = [...window.appState.ideas];

            if (window.appState.ideasFilter !== 'all') {
                list = list.filter(i => i.category === window.appState.ideasFilter);
            }

            if (sortVal === 'votes') {
                list.sort((a,b) => (b.votes || 0) - (a.votes || 0));
            } else {
                list.sort((a,b) => new Date(b.date || '2026-01-01') - new Date(a.date || '2026-01-01'));
            }

            if (list.length === 0) {
                grid.innerHTML = `
                    <div class="col-span-full text-center py-12 bg-slate-800/40 rounded-3xl border border-slate-700/50">
                        <i class="fa-solid fa-lightbulb text-slate-600 text-4xl mb-2"></i>
                        <p class="text-sm text-slate-400 font-medium">Aucune idée proposée pour le moment dans cette catégorie.</p>
                        <button onclick="openModal('add-idea-modal')" class="mt-3 text-xs text-neonCyan font-bold hover:underline">Soyez le premier à proposer une idée !</button>
                    </div>
                `;
                return;
            }

            list.forEach(idea => {
                const voterIds = idea.voterIds || [];
                const hasVoted = voterIds.includes(clientUid);

                let statusBadge = '<span class="px-2.5 py-1 rounded-full text-[10px] font-bold bg-amber-500/10 text-amber-400 border border-amber-500/20">En attente</span>';
                if (idea.status === 'accepted') statusBadge = '<span class="px-2.5 py-1 rounded-full text-[10px] font-bold bg-emerald-500/10 text-emerald-400 border border-emerald-500/20">Adoptée</span>';
                if (idea.status === 'in-progress') statusBadge = '<span class="px-2.5 py-1 rounded-full text-[10px] font-bold bg-cyan-500/10 text-cyan-400 border border-cyan-500/20">En cours</span>';
                if (idea.status === 'rejected') statusBadge = '<span class="px-2.5 py-1 rounded-full text-[10px] font-bold bg-pink-500/10 text-pink-400 border border-pink-500/20">Refusée</span>';

                const card = document.createElement('div');
                card.className = 'bg-slate-800/80 backdrop-blur-md rounded-3xl p-6 border border-slate-700/60 shadow-xl flex flex-col justify-between hover:border-slate-600 transition-all';
                card.innerHTML = `
                    <div>
                        <div class="flex items-center justify-between mb-3">
                            ${statusBadge}
                            <span class="text-[10px] font-bold text-slate-500 uppercase tracking-wider">${idea.category}</span>
                        </div>
                        <h3 class="text-base font-extrabold text-white mb-2">${idea.title}</h3>
                        <p class="text-xs text-slate-300 leading-relaxed mb-4">${idea.desc}</p>
                    </div>

                    <div class="flex items-center justify-between border-t border-slate-700/60 pt-4 mt-2">
                        <span class="text-xs text-slate-400 font-medium">Par <strong class="text-slate-200">${idea.author || 'Anonyme'}</strong></span>
                        <button onclick="toggleUpvote('${idea.id}')" class="px-3.5 py-2 rounded-xl text-xs font-bold transition-all flex items-center gap-2 ${hasVoted ? 'bg-neonCyan text-slate-950 font-extrabold glow-cyan' : 'bg-slate-900 border border-slate-700 text-slate-300 hover:border-neonCyan'}">
                            <i class="fa-solid fa-thumbs-up text-sm"></i>
                            <span>${idea.votes || 0}</span>
                        </button>
                    </div>
                `;
                grid.appendChild(card);
            });
        };

        window.toggleUpvote = async function(ideaId) {
            playSound('click');
            const idea = window.appState.ideas.find(i => i.id === ideaId);
            if (!idea) return;

            idea.voterIds = idea.voterIds || [];
            const idx = idea.voterIds.indexOf(clientUid);

            if (idx > -1) {
                idea.voterIds.splice(idx, 1);
                idea.votes = Math.max(0, (idea.votes || 1) - 1);
                showToast("Vote retiré");
            } else {
                idea.voterIds.push(clientUid);
                idea.votes = (idea.votes || 0) + 1;
                playSound('success');
                showToast("Votre vote a été pris en compte ! 👍");
            }

            window.renderIdeas();
            if (window.firebaseVoteIdea) {
                await window.firebaseVoteIdea(ideaId, idea.votes, idea.voterIds);
            }
        };

        window.handleAddIdeaSubmit = async function(e) {
            e.preventDefault();
            const title = document.getElementById('idea-title').value;
            const category = document.getElementById('idea-category').value;
            const desc = document.getElementById('idea-desc').value;
            const author = document.getElementById('idea-author').value || 'Anonyme';

            const newIdea = {
                title, category, desc, author,
                votes: 1,
                voterIds: [clientUid],
                status: 'pending',
                date: new Date().toISOString().split('T')[0]
            };

            window.appState.ideas.unshift(newIdea);
            window.renderIdeas();
            closeModal('add-idea-modal');
            e.target.reset();

            playSound('success');
            showToast("Votre idée a été soumise avec succès !");

            if (window.firebaseSaveIdea) {
                await window.firebaseSaveIdea(newIdea);
            }
        };

        // 3. CONTACT FORM LOGIC
        window.toggleAnonymityInput = function() {
            playSound('click');
            const isAnon = document.getElementById('contact-anonymous').checked;
            const container = document.getElementById('contact-name-container');
            if (isAnon) {
                container.classList.add('hidden');
            } else {
                container.classList.remove('hidden');
            }
        };

        window.handleContactSubmit = async function(e) {
            e.preventDefault();
            const recipient = document.querySelector('input[name="recipient"]:checked').value;
            const isAnon = document.getElementById('contact-anonymous').checked;
            const name = isAnon ? 'Anonyme' : (document.getElementById('contact-sender-name').value || 'Anonyme');
            const subject = document.getElementById('contact-subject').value;
            const message = document.getElementById('contact-message').value;

            const msgObj = {
                recipient, name, isAnon, subject, message,
                date: new Date().toLocaleString('fr-FR'),
                read: false
            };

            window.appState.messages.unshift(msgObj);
            e.target.reset();

            playSound('success');
            showToast(`Message envoyé confidentiellement à ${recipient} !`);

            if (window.firebaseSaveContactMessage) {
                await window.firebaseSaveContactMessage(msgObj);
            }
        };

        // 4. QCM FORM LOGIC
        window.handleQcmSubmit = async function(e) {
            e.preventDefault();
            const getVal = (name) => {
                const el = document.querySelector(`input[name="${name}"]:checked`);
                return el ? el.value : 'Non renseigné';
            };

            const qcmData = {
                studentName: document.getElementById('qcm-student-name').value,
                studentClass: document.getElementById('qcm-student-class').value,
                q1_feeling: getVal('q1_feeling'),
                q1_strengths: document.getElementById('q1_strengths').value,
                q1_improvements: document.getElementById('q1_improvements').value,
                q2_satisfaction_class: getVal('q2_satisfaction_class'),
                q2_satisfaction_home: getVal('q2_satisfaction_home'),
                q2_difficulties: document.getElementById('q2_difficulties').value,
                q3_easy_subjects: document.getElementById('q3_easy_subjects').value,
                q3_hard_subjects: document.getElementById('q3_hard_subjects').value,
                q4_atmosphere: getVal('q4_atmosphere'),
                q4_integrated: getVal('q4_integrated'),
                submittedAt: new Date().toLocaleString('fr-FR')
            };

            window.appState.qcmResponses.push(qcmData);
            e.target.reset();

            playSound('success');
            showToast("Votre questionnaire a bien été enregistré ! Merci.");

            if (window.firebaseSaveQcm) {
                await window.firebaseSaveQcm(qcmData);
            }
        };

        // 5. ADMIN LOGIC
        window.handleAdminLogin = function(e) {
            e.preventDefault();
            const role = document.getElementById('admin-role-select').value;
            const pwd = document.getElementById('admin-password').value;

            const correctPwd = window.appState.adminPasswords[role] || 'admin123';

            if (pwd === correctPwd) {
                playSound('success');
                window.appState.currentAdmin = role;
                document.getElementById('admin-login-card').classList.add('hidden');
                document.getElementById('admin-dashboard').classList.remove('hidden');
                document.getElementById('current-admin-name').innerText = role;

                window.renderAdminQcmStats();
                window.renderAdminMessages();
                window.renderAdminIdeas();
                showToast(`Bienvenue dans l'espace Admin, ${role} !`);
            } else {
                playSound('click');
                showToast("Mot de passe incorrect. (Par défaut: admin123)", "error");
            }
        };

        window.logoutAdmin = function() {
            playSound('click');
            window.appState.currentAdmin = null;
            document.getElementById('admin-login-card').classList.remove('hidden');
            document.getElementById('admin-dashboard').classList.add('hidden');
            document.getElementById('admin-password').value = '';
        };

        window.switchAdminTab = function(subtab) {
            playSound('click');
            document.querySelectorAll('.admin-view').forEach(v => v.classList.add('hidden'));
            
            const targetView = document.getElementById('admin-view-' + subtab);
            if (targetView) targetView.classList.remove('hidden');

            // Reset subtab buttons style
            ['qcm', 'messages', 'ideas', 'events', 'settings'].forEach(st => {
                const btn = document.getElementById('admin-subtab-' + st);
                if (btn) {
                    btn.className = "px-4 py-2.5 rounded-xl text-xs font-bold transition-all text-slate-400 hover:bg-slate-800";
                }
            });

            const activeBtn = document.getElementById('admin-subtab-' + subtab);
            if (activeBtn) {
                activeBtn.className = "px-4 py-2.5 rounded-xl text-xs font-bold transition-all bg-neonPurple text-white";
            }
        };

        // Admin View 1: QCM Stats & Percentages
        window.renderAdminQcmStats = function() {
            const grid = document.getElementById('qcm-stats-grid');
            const list = document.getElementById('qcm-individual-list');
            const data = window.appState.qcmResponses;

            grid.innerHTML = '';
            list.innerHTML = '';

            if (data.length === 0) {
                grid.innerHTML = `<div class="col-span-full p-6 text-center text-slate-400 bg-slate-800/40 rounded-2xl border border-slate-700">Aucune réponse au questionnaire pour le moment.</div>`;
                return;
            }

            const total = data.length;

            // Helper percentage function
            const calcPerc = (key, val) => {
                const count = data.filter(d => d[key] === val).length;
                return Math.round((count / total) * 100);
            };

            // Stat Card 1: Ressenti General
            grid.innerHTML += `
                <div class="bg-slate-800/80 p-5 rounded-3xl border border-slate-700">
                    <h4 class="text-xs font-extrabold uppercase tracking-wider text-neonPurple mb-3"><i class="fa-solid fa-smile mr-1.5"></i> Ressenti Général</h4>
                    <div class="space-y-2 text-xs">
                        <div>
                            <div class="flex justify-between text-slate-300 font-semibold mb-1"><span>Très bien / Bien</span><span>${calcPerc('q1_feeling', 'Très bien') + calcPerc('q1_feeling', 'Bien')}%</span></div>
                            <div class="w-full bg-slate-900 h-2 rounded-full overflow-hidden"><div class="bg-neonPurple h-full" style="width: ${calcPerc('q1_feeling', 'Très bien') + calcPerc('q1_feeling', 'Bien')}%"></div></div>
                        </div>
                        <div>
                            <div class="flex justify-between text-slate-300 font-semibold mb-1"><span>Moyennement</span><span>${calcPerc('q1_feeling', 'Moyennement bien')}%</span></div>
                            <div class="w-full bg-slate-900 h-2 rounded-full overflow-hidden"><div class="bg-neonAmber h-full" style="width: ${calcPerc('q1_feeling', 'Moyennement bien')}%"></div></div>
                        </div>
                        <div>
                            <div class="flex justify-between text-slate-300 font-semibold mb-1"><span>Mal / Très mal</span><span>${calcPerc('q1_feeling', 'Mal') + calcPerc('q1_feeling', 'Très mal')}%</span></div>
                            <div class="w-full bg-slate-900 h-2 rounded-full overflow-hidden"><div class="bg-neonPink h-full" style="width: ${calcPerc('q1_feeling', 'Mal') + calcPerc('q1_feeling', 'Très mal')}%"></div></div>
                        </div>
                    </div>
                </div>
            `;

            // Stat Card 2: Ambiance de Classe
            grid.innerHTML += `
                <div class="bg-slate-800/80 p-5 rounded-3xl border border-slate-700">
                    <h4 class="text-xs font-extrabold uppercase tracking-wider text-neonCyan mb-3"><i class="fa-solid fa-users mr-1.5"></i> Ambiance de Classe</h4>
                    <div class="space-y-2 text-xs">
                        <div>
                            <div class="flex justify-between text-slate-300 font-semibold mb-1"><span>Très bonne / Bonne</span><span>${calcPerc('q4_atmosphere', 'Très bonne') + calcPerc('q4_atmosphere', 'Bonne')}%</span></div>
                            <div class="w-full bg-slate-900 h-2 rounded-full overflow-hidden"><div class="bg-neonCyan h-full" style="width: ${calcPerc('q4_atmosphere', 'Très bonne') + calcPerc('q4_atmosphere', 'Bonne')}%"></div></div>
                        </div>
                        <div>
                            <div class="flex justify-between text-slate-300 font-semibold mb-1"><span>Moyenne</span><span>${calcPerc('q4_atmosphere', 'Moyenne')}%</span></div>
                            <div class="w-full bg-slate-900 h-2 rounded-full overflow-hidden"><div class="bg-neonAmber h-full" style="width: ${calcPerc('q4_atmosphere', 'Moyenne')}%"></div></div>
                        </div>
                        <div>
                            <div class="flex justify-between text-slate-300 font-semibold mb-1"><span>Mauvaise</span><span>${calcPerc('q4_atmosphere', 'Mauvaise') + calcPerc('q4_atmosphere', 'Très mauvaise')}%</span></div>
                            <div class="w-full bg-slate-900 h-2 rounded-full overflow-hidden"><div class="bg-neonPink h-full" style="width: ${calcPerc('q4_atmosphere', 'Mauvaise') + calcPerc('q4_atmosphere', 'Très mauvaise')}%"></div></div>
                        </div>
                    </div>
                </div>
            `;

            // Stat Card 3: Satisfaction Travail Classe
            grid.innerHTML += `
                <div class="bg-slate-800/80 p-5 rounded-3xl border border-slate-700">
                    <h4 class="text-xs font-extrabold uppercase tracking-wider text-neonGreen mb-3"><i class="fa-solid fa-book-open mr-1.5"></i> Satisfaction Travail</h4>
                    <div class="space-y-2 text-xs">
                        <div>
                            <div class="flex justify-between text-slate-300 font-semibold mb-1"><span>Oui</span><span>${calcPerc('q2_satisfaction_class', 'Oui')}%</span></div>
                            <div class="w-full bg-slate-900 h-2 rounded-full overflow-hidden"><div class="bg-neonGreen h-full" style="width: ${calcPerc('q2_satisfaction_class', 'Oui')}%"></div></div>
                        </div>
                        <div>
                            <div class="flex justify-between text-slate-300 font-semibold mb-1"><span>En partie</span><span>${calcPerc('q2_satisfaction_class', 'En partie')}%</span></div>
                            <div class="w-full bg-slate-900 h-2 rounded-full overflow-hidden"><div class="bg-neonAmber h-full" style="width: ${calcPerc('q2_satisfaction_class', 'En partie')}%"></div></div>
                        </div>
                        <div>
                            <div class="flex justify-between text-slate-300 font-semibold mb-1"><span>Non</span><span>${calcPerc('q2_satisfaction_class', 'Non')}%</span></div>
                            <div class="w-full bg-slate-900 h-2 rounded-full overflow-hidden"><div class="bg-neonPink h-full" style="width: ${calcPerc('q2_satisfaction_class', 'Non')}%"></div></div>
                        </div>
                    </div>
                </div>
            `;

            // Render Individual Responses
            data.forEach((resp) => {
                const item = document.createElement('div');
                item.className = 'p-4 bg-slate-900/60 rounded-2xl border border-slate-700 text-xs space-y-2';
                item.innerHTML = `
                    <div class="flex items-center justify-between border-b border-slate-800 pb-2">
                        <strong class="text-white text-sm">${resp.studentName} (${resp.studentClass})</strong>
                        <span class="text-slate-500">${resp.submittedAt}</span>
                    </div>
                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-2 text-slate-300">
                        <p><strong>Ressenti:</strong> ${resp.q1_feeling}</p>
                        <p><strong>Ambiance:</strong> ${resp.q4_atmosphere}</p>
                        <p><strong>Points forts:</strong> ${resp.q1_strengths || 'Aucun'}</p>
                        <p><strong>À améliorer:</strong> ${resp.q1_improvements || 'Aucun'}</p>
                        <p><strong>Difficultés:</strong> ${resp.q2_difficulties || 'Aucune'}</p>
                        <p><strong>Matières difficiles:</strong> ${resp.q3_hard_subjects || 'Aucune'}</p>
                    </div>
                `;
                list.appendChild(item);
            });
        };

        // Admin View 2: Messages
        window.renderAdminMessages = function() {
            const list = document.getElementById('admin-messages-list');
            list.innerHTML = '';
            const msgs = window.appState.messages;

            document.getElementById('unread-count').innerText = msgs.filter(m => !m.read).length;

            if (msgs.length === 0) {
                list.innerHTML = `<p class="text-center text-slate-400 py-8">Aucun message reçu pour le moment.</p>`;
                return;
            }

            msgs.forEach((msg, idx) => {
                const card = document.createElement('div');
                card.className = 'p-5 bg-slate-800/80 rounded-3xl border border-slate-700 flex flex-col justify-between gap-3';
                card.innerHTML = `
                    <div>
                        <div class="flex items-center justify-between mb-2">
                            <span class="px-2.5 py-1 rounded-full text-[10px] font-bold bg-neonPink/20 text-neonPink border border-neonPink/30">Pour : ${msg.recipient}</span>
                            <span class="text-[10px] text-slate-500">${msg.date}</span>
                        </div>
                        <h4 class="text-sm font-bold text-white mb-1">${msg.subject}</h4>
                        <p class="text-xs text-slate-300 leading-relaxed bg-slate-900/60 p-3 rounded-xl border border-slate-800">${msg.message}</p>
                    </div>
                    <div class="flex items-center justify-between text-xs pt-1">
                        <span class="text-slate-400 font-medium">De : <strong class="text-slate-200">${msg.name}</strong></span>
                        <button onclick="deleteAdminMessage('${msg.id || idx}')" class="text-slate-500 hover:text-pink-400 transition-all"><i class="fa-solid fa-trash mr-1"></i> Supprimer</button>
                    </div>
                `;
                list.appendChild(card);
            });
        };

        window.deleteAdminMessage = async function(id) {
            playSound('click');
            if (window.firebaseDeleteMessage) await window.firebaseDeleteMessage(id);
            window.appState.messages = window.appState.messages.filter((m, i) => m.id !== id && i !== parseInt(id));
            window.renderAdminMessages();
            showToast("Message supprimé");
        };

        // Admin View 3: Ideas Moderation
        window.renderAdminIdeas = function() {
            const list = document.getElementById('admin-ideas-list');
            list.innerHTML = '';

            window.appState.ideas.forEach(idea => {
                const card = document.createElement('div');
                card.className = 'p-4 bg-slate-800/80 rounded-2xl border border-slate-700 space-y-3';
                card.innerHTML = `
                    <div class="flex items-center justify-between">
                        <h4 class="text-sm font-bold text-white">${idea.title}</h4>
                        <span class="text-xs font-bold text-neonCyan">👍 ${idea.votes || 0}</span>
                    </div>
                    <p class="text-xs text-slate-300">${idea.desc}</p>
                    <div class="flex items-center justify-between pt-2 border-t border-slate-700">
                        <select onchange="updateIdeaStatus('${idea.id}', this.value)" class="bg-slate-900 border border-slate-700 text-xs text-white rounded-lg px-2 py-1">
                            <option value="pending" ${idea.status === 'pending' ? 'selected' : ''}>En attente</option>
                            <option value="in-progress" ${idea.status === 'in-progress' ? 'selected' : ''}>En cours</option>
                            <option value="accepted" ${idea.status === 'accepted' ? 'selected' : ''}>Adoptée</option>
                            <option value="rejected" ${idea.status === 'rejected' ? 'selected' : ''}>Refusée</option>
                        </select>
                        <button onclick="deleteAdminIdea('${idea.id}')" class="text-xs text-slate-500 hover:text-pink-400"><i class="fa-solid fa-trash"></i></button>
                    </div>
                `;
                list.appendChild(card);
            });
        };

        window.updateIdeaStatus = async function(ideaId, newStatus) {
            playSound('click');
            const idea = window.appState.ideas.find(i => i.id === ideaId);
            if (idea) idea.status = newStatus;
            window.renderIdeas();
            if (window.firebaseUpdateIdeaStatus) await window.firebaseUpdateIdeaStatus(ideaId, newStatus);
            showToast("Statut de l'idée mis à jour");
        };

        window.deleteAdminIdea = async function(ideaId) {
            playSound('click');
            window.appState.ideas = window.appState.ideas.filter(i => i.id !== ideaId);
            window.renderIdeas();
            window.renderAdminIdeas();
            if (window.firebaseDeleteIdea) await window.firebaseDeleteIdea(ideaId);
            showToast("Idée supprimée");
        };

        // Admin View 4: Add Event
        window.handleAddEvent = async function(e) {
            e.preventDefault();
            const title = document.getElementById('event-title').value;
            const date = document.getElementById('event-date').value;
            const category = document.getElementById('event-category').value;
            const desc = document.getElementById('event-desc').value;

            const evtObj = { title, date, category, desc };
            window.appState.events.push(evtObj);

            window.renderCalendar();
            window.renderUpcomingEvents();
            e.target.reset();

            playSound('success');
            showToast("Événement ajouté au calendrier !");

            if (window.firebaseSaveEvent) await window.firebaseSaveEvent(evtObj);
        };

        // Admin View 5: Change Password
        window.handleChangePassword = function(e) {
            e.preventDefault();
            const role = window.appState.currentAdmin;
            const newPwd = document.getElementById('new-admin-password').value;

            window.appState.adminPasswords[role] = newPwd;
            localStorage.setItem('admin_passwords', JSON.stringify(window.appState.adminPasswords));

            playSound('success');
            e.target.reset();
            showToast(`Mot de passe mis à jour pour ${role} !`);
        };

        // Export QCM to CSV
        window.exportQcmCSV = function() {
            playSound('click');
            const data = window.appState.qcmResponses;
            if (data.length === 0) {
                showToast("Aucune donnée à exporter", "error");
                return;
            }

            let csv = "Nom,Classe,Ressenti,Ambiance,Difficultes,Points Forts\n";
            data.forEach(d => {
                csv += `"${d.studentName}","${d.studentClass}","${d.q1_feeling}","${d.q4_atmosphere}","${d.q2_difficulties || ''}","${d.q1_strengths || ''}"\n`;
            });

            const blob = new Blob([csv], { type: 'text/csv;charset=utf-8;' });
            const link = document.createElement("a");
            link.href = URL.createObjectURL(blob);
            link.download = "reponses_conseil_de_classe.csv";
            link.click();
            showToast("Exportation du fichier CSV réussie !");
        };

        // Helpers Modals & Toasts
        window.openModal = function(id) {
            playSound('click');
            document.getElementById(id).classList.remove('hidden');
        };

        window.closeModal = function(id) {
            playSound('click');
            document.getElementById(id).classList.add('hidden');
        };

        function showToast(msg, type = "success") {
            const toast = document.getElementById('toast');
            const toastMsg = document.getElementById('toast-message');
            const toastIcon = document.getElementById('toast-icon');

            toastMsg.innerText = msg;
            toastIcon.className = type === 'error' ? 'fa-solid fa-circle-xmark text-neonPink text-xl' : 'fa-solid fa-circle-check text-neonGreen text-xl';

            toast.classList.remove('opacity-0', 'translate-y-10');
            toast.classList.add('opacity-100', 'translate-y-0');

            setTimeout(() => {
                toast.classList.remove('opacity-100', 'translate-y-0');
                toast.classList.add('opacity-0', 'translate-y-10');
            }, 3000);
        }

        // Initial Initialization
        window.addEventListener('DOMContentLoaded', () => {
            window.renderCalendar();
            window.renderUpcomingEvents();
            window.renderIdeas();
        });
    </script>
</body>
</html>
