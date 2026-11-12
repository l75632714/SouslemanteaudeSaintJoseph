<!DOCTYPE html>
<html lang="fr" class="h-full bg-white">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
  <title>Sous le manteau de Saint Joseph</title>

  <!-- Tailwind CSS CDN -->
  <script src="https://cdn.tailwindcss.com"></script>

  <!-- Google Fonts: Open Sans -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,400;0,600;0,700;1,400;1,700&display=swap" rel="stylesheet">

  <style>
    body {
      font-family: 'Open Sans', sans-serif;
      -webkit-tap-highlight-color: transparent;
      background-color: #ffffff !important;
    }
    .font-opensans-bold {
      font-family: 'Open Sans', sans-serif;
      font-weight: 700;
    }

    h1, h2, h3, h4, h5, h6 {
      border: none !important;
      border-bottom: none !important;
      outline: none !important;
      text-decoration: none !important;
      box-shadow: none !important;
    }

    .soothing-mode {
      background-color: #0f172a !important;
      color: #f8fafc !important;
    }
    .soothing-mode .bg-card {
      background-color: #1e293b !important;
      border-color: #334155 !important;
      color: #f8fafc !important;
    }
    .soothing-mode .header-bg {
      background-color: #020617 !important;
    }
    .soothing-mode .text-royal {
      color: #93c5fd !important;
    }

    .halo-effect {
      box-shadow: 0 0 15px rgba(212, 175, 55, 0.25);
      transition: all 0.5s ease;
    }
    .halo-container:hover .halo-effect {
      box-shadow: 0 0 35px rgba(212, 175, 55, 0.65);
      transform: scale(1.01);
    }

    .bg-custom-blue {
      background-color: #2563eb;
    }
    .soothing-mode .bg-custom-blue {
      background-color: #1e293b !important;
    }
  </style>
</head>
<body class="bg-white text-slate-800 font-['Open_Sans'] min-h-screen flex flex-col bg-cover bg-center bg-no-repeat bg-fixed transition-colors duration-500" style="background-image: url('sketch1793913958083allrightsreservedtoLouiseÉmilieSchreiber.png'); background-color: #ffffff;">

  <div id="app" class="min-h-screen flex flex-col justify-between bg-white/90">

    <!-- En-tête -->
    <header class="header-bg bg-custom-blue text-white shadow-md w-full border-0">
      <div class="max-w-7xl mx-auto px-4 py-3 flex items-center justify-between border-0">
        
        <!-- Zone Gauche : Icônes -->
        <div class="flex items-center space-x-2">
          <button id="dove-btn" onclick="toggleDoveSound()" title="Ambiance Musicale" class="p-1.5 rounded-full bg-black hover:bg-slate-800 text-white transition cursor-pointer flex items-center justify-center active:scale-95">
            <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15.536 8.464a5 5 0 010 7.072m2.828-9.9a9 9 0 010 12.728M5.586 15H4a1 1 0 01-1-1v-4a1 1 0 011-1h1.586l4.707-4.707C10.923 3.663 12 4.109 12 5v14c0 .891-1.077 1.337-1.707.707L5.586 15z"></path>
            </svg>
          </button>

          <button id="light-btn" onclick="toggleSoothingLight()" title="Lumière apaisante" class="p-1.5 rounded-full bg-black hover:bg-slate-800 text-white transition cursor-pointer flex items-center justify-center active:scale-95">
            <svg class="w-4 h-4" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <circle cx="12" cy="12" r="4"/>
              <path d="M12 2v2"/>
              <path d="M12 20v2"/>
              <path d="m4.93 4.93 1.41 1.41"/>
              <path d="m17.66 17.66 1.41 1.41"/>
              <path d="M2 12h2"/>
              <path d="M20 12h2"/>
              <path d="m6.34 17.66-1.41 1.41"/>
              <path d="m19.07 4.93-1.41 1.41"/>
            </svg>
          </button>
        </div>

        <h1 class="text-lg md:text-2xl tracking-wide text-amber-400 text-center font-opensans-bold m-0 p-0 border-0 flex-1">
          Sous le manteau de Saint Joseph
        </h1>

        <div class="w-14"></div>

      </div>
    </header>

    <!-- Layout Principal -->
    <div class="max-w-7xl mx-auto px-4 md:px-6 py-8 flex-grow w-full flex flex-col md:flex-row gap-8 items-stretch">
      
      <!-- Panneau Latéral Gauche : Neuvaine -->
      <aside class="w-full md:w-72 flex-shrink-0 flex flex-col">
        <div id="neuvaine-panel" class="bg-card bg-white rounded-2xl p-6 shadow-sm border border-slate-200/80 transition-colors duration-500 h-full flex flex-col justify-between">
          <div>
            <div class="mb-6 flex flex-col items-start text-left border-0">
              <h2 class="font-opensans-bold text-slate-900 text-royal mb-1 m-0 p-0 border-0 whitespace-nowrap" style="font-size: 18px !important;">
                Neuvaine à Saint Joseph
              </h2>
              <p class="text-xs text-slate-500 italic m-0 p-0 border-0">
                Suivez l'avancement de votre neuvaine :
              </p>
            </div>

            <!-- Liste verticale des 9 jours -->
            <div id="neuvaine-list" class="space-y-2.5"></div>
          </div>

          <!-- Message de fin de neuvaine -->
          <div id="neuvaine-completion-msg" class="mt-6 pt-4 border-t border-amber-200/60 text-center" style="display: none;">
            <p class="text-xs font-opensans-bold text-amber-700 italic">
              Que vos prières soient exaucées.
            </p>
          </div>
        </div>
      </aside>

      <!-- Zone Principale -->
      <main class="flex-grow w-full flex flex-col">
        <section id="main-section" class="bg-card bg-white rounded-2xl p-6 md:p-10 shadow-sm border border-slate-200/80 transition-colors duration-500 relative flex flex-col justify-between h-full">
          
          <div class="flex flex-col h-full justify-between">
            <div class="flex flex-col items-center border-0">
              <h2 class="font-opensans-bold text-2xl md:text-4xl text-slate-900 text-royal mb-4 tracking-tight text-center m-0 p-0 border-0">
                Saint Joseph
              </h2>
            </div>

            <!-- Conteneur avec le tableau principal de NOMA et les pastilles interactives -->
            <div class="halo-container max-w-md mx-auto relative flex flex-col items-center w-full flex-grow justify-center">
              
              <div class="relative rounded-2xl overflow-hidden halo-effect border-2 border-amber-400/40 p-1 bg-white w-full flex justify-center h-full max-h-[580px]">
                <img 
                  src="https://noma.org/wp-content/uploads/2018/01/56-63-old.jpg" 
                  alt="Saint Joseph et l'Enfant-Jésus" 
                  class="w-full h-full object-cover rounded-xl transition-transform duration-500 bg-white"
                />

                <!-- Pastilles interactives -->
                <button onclick="openModal('dates')" class="absolute top-1/4 left-1/4 transform -translate-x-1/2 -translate-y-1/2 w-7 h-7 rounded-full bg-amber-500 hover:bg-amber-400 shadow-lg animate-pulse transition hover:scale-110 active:scale-95 z-20">
                </button>

                <button onclick="openModal('titles')" class="absolute top-1/3 right-1/4 transform translate-x-1/2 -translate-y-1/2 w-7 h-7 rounded-full bg-blue-600 hover:bg-blue-500 shadow-lg animate-pulse transition hover:scale-110 active:scale-95 z-20">
                </button>

                <button onclick="openModal('chaste-heart')" class="absolute top-[52%] right-[25%] transform translate-x-1/2 -translate-y-1/2 w-7 h-7 rounded-full bg-red-700 hover:bg-red-600 shadow-lg animate-pulse transition hover:scale-110 active:scale-95 z-20">
                </button>
              </div>

              <button onclick="window.open('https://www.biblewalks.com/nazareth_maps/', '_blank')" title="Cartes et sites de Nazareth (BibleWalks)" class="absolute top-[65%] left-1/4 transform -translate-x-1/2 -translate-y-1/2 w-7 h-7 rounded-full bg-emerald-600 hover:bg-emerald-500 shadow-lg animate-pulse transition hover:scale-110 active:scale-95 cursor-pointer">
              </button>

              <p class="text-[11px] text-slate-400 mt-2 italic text-center">
                Source : Object Lesson: St. Joseph and the Christ Child — NOMA
              </p>
            </div>
          </div>

          <!-- Modale -->
          <div id="interactive-modal" class="hidden fixed inset-0 z-50 flex items-center justify-center bg-slate-950/60 backdrop-blur-sm p-4">
            <div id="modal-container" class="bg-white rounded-2xl max-w-2xl w-full p-6 md:p-8 shadow-2xl border border-amber-200 relative animate-in fade-in zoom-in duration-200 max-h-[90vh] overflow-y-auto">
              <button onclick="closeModal()" class="absolute top-4 right-4 text-slate-400 hover:text-slate-700 p-2 rounded-lg text-lg font-bold cursor-pointer">
                ✕
              </button>
              <div id="modal-content" class="space-y-4"></div>
            </div>
          </div>

        </section>
      </main>

    </div>

    <!-- Bloc superposé Nazareth -->
    <div class="relative z-10 -mb-6 flex justify-center px-4">
      <div class="inline-flex items-center gap-4 rounded-xl border border-amber-200/60 bg-white px-6 py-3 shadow-md backdrop-blur-sm text-lg font-opensans-bold text-slate-800">
        <span class="text-slate-500 font-normal">Nazareth :</span>
        <a href="https://artsandculture.google.com/entity/nazareth/m05fz3?hl=fr" target="_blank" rel="noopener noreferrer" class="hover:text-amber-700 hover:underline transition-colors focus:outline-none focus:ring-2 focus:ring-amber-500 rounded">Découvrir</a>
        <span class="text-slate-300">•</span>
        <a href="https://artsandculture.google.com/search?q=Nazareth&hl=fr" target="_blank" rel="noopener noreferrer" class="hover:text-amber-700 hover:underline transition-colors focus:outline-none focus:ring-2 focus:ring-amber-500 rounded">Galerie</a>
      </div>
    </div>

    <!-- Pied de Page -->
    <footer class="w-full text-center py-6 text-xs text-slate-400 border-t border-slate-200/60 bg-white">
      <small>&copy; 2026 Sous le manteau de Saint Joseph. Tous droits réservés.</small>
    </footer>

  </div>

  <!-- Scripts -->
  <script>
    document.addEventListener("DOMContentLoaded", () => {
      renderNeuvaine();
    });

    function renderNeuvaine() {
      const container = document.getElementById("neuvaine-list");
      if (!container) return;
      container.innerHTML = "";

      for (let i = 1; i <= 9; i++) {
        const storageKey = `neuvaine_jour_${i}`;
        const isChecked = localStorage.getItem(storageKey) === "true";

        const label = document.createElement("label");
        label.className = "flex items-center justify-between p-3 rounded-xl border border-slate-100 bg-slate-50/60 hover:bg-amber-50/40 hover:border-amber-200/60 cursor-pointer transition group";
        
        label.innerHTML = `
          <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900">Jour ${i}</span>
          <input type="checkbox" data-day="${i}" ${isChecked ? "checked" : ""} class="w-4 h-4 accent-amber-600 rounded focus:ring-amber-500 cursor-pointer">
        `;

        const checkbox = label.querySelector("input");
        checkbox.addEventListener("change", (e) => {
          localStorage.setItem(storageKey, e.target.checked);
          checkCompletion();
        });

        container.appendChild(label);
      }

      checkCompletion();
    }

    function checkCompletion() {
      let allChecked = true;
      for (let i = 1; i <= 9; i++) {
        if (localStorage.getItem(`neuvaine_jour_${i}`) !== "true") {
          allChecked = false;
          break;
        }
      }
      const completionMsg = document.getElementById("neuvaine-completion-msg");
      if (completionMsg) {
        if (allChecked) {
          completionMsg.style.display = "block";
        } else {
          completionMsg.style.display = "none";
        }
      }
    }

    let audioCtx = null;
    let isPlayingDove = false;
    let melodyInterval = null;

    function initAudio() {
      if (!audioCtx) {
        audioCtx = new (window.AudioContext || window.webkitAudioContext)();
      }
    }

    function toggleDoveSound() {
      initAudio();
      if (isPlayingDove) {
        stopDoveSound();
      } else {
        startDoveSound();
      }
    }

    function startDoveSound() {
      if (audioCtx.state === 'suspended') {
        audioCtx.resume();
      }

      isPlayingDove = true;
      document.getElementById('dove-btn').classList.add('bg-amber-600', 'ring-2', 'ring-amber-300');

      playPureNote();
      melodyInterval = setInterval(() => {
        if (isPlayingDove) {
          playPureNote();
        }
      }, 4000);
    }

    function playPureNote() {
      if (!audioCtx || !isPlayingDove) return;

      const osc = audioCtx.createOscillator();
      const gain = audioCtx.createGain();

      const notes = [523.25, 659.25, 783.99, 880.00, 1046.50];
      const randomFreq = notes[Math.floor(Math.random() * notes.length)];

      osc.type = 'sine';
      const now = audioCtx.currentTime;

      osc.frequency.setValueAtTime(randomFreq, now);

      gain.gain.setValueAtTime(0.001, now);
      gain.gain.linearRampToValueAtTime(0.03, now + 0.3);
      gain.gain.exponentialRampToValueAtTime(0.0001, now + 3.0);

      osc.connect(gain);
      gain.connect(audioCtx.destination);

      osc.start(now);
      osc.stop(now + 3.0);
    }

    function stopDoveSound() {
      isPlayingDove = false;
      if (melodyInterval) {
        clearInterval(melodyInterval);
      }
      document.getElementById('dove-btn').classList.remove('bg-amber-600', 'ring-2', 'ring-amber-300');
    }

    function toggleSoothingLight() {
      document.body.classList.toggle('soothing-mode');
    }

    function openModal(type) {
      const modal = document.getElementById('interactive-modal');
      const container = document.getElementById('modal-container');
      const content = document.getElementById('modal-content');

      container.style.maxHeight = '90vh';

      if (type === 'dates') {
        content.innerHTML = `
          <div class="space-y-3">
            <div class="w-full p-4 rounded-xl bg-blue-600/10 border border-blue-600/20 flex flex-col gap-1">
              <span class="text-xs font-bold text-red-700 uppercase">19 Mars</span>
              <button onclick="showPrayer('ave-joseph')" class="text-left text-sm font-semibold text-slate-800 hover:text-black underline transition cursor-pointer">
                Époux de la bienheureuse Vierge Marie
              </button>
            </div>
            <div class="w-full p-4 rounded-xl bg-blue-600/10 border border-blue-600/20 flex flex-col gap-1">
              <span class="text-xs font-bold text-red-700 uppercase">1er Mai</span>
              <button onclick="showPrayer('pie-x')" class="text-left text-sm font-semibold text-slate-800 hover:text-black underline transition cursor-pointer">
                Travailleur
              </button>
            </div>
          </div>
        `;
      } else if (type === 'titles') {
        content.innerHTML = `
          <div class="flex flex-col items-start justify-start text-left space-y-3 py-2 border-0">
            <h3 class="font-opensans-bold text-2xl text-slate-900 mb-2 w-full text-left m-0 p-0 border-0">
              Saint Joseph
            </h3>
            <p class="text-base font-semibold text-slate-800 w-full text-left leading-normal m-0">Le Juste,</p>
            <p class="text-base font-semibold text-slate-800 w-full text-left leading-normal m-0">Travailleur,</p>
            <p class="text-base font-semibold text-slate-800 w-full text-left leading-normal m-0">Terreur des démons,</p>
            <p class="text-base font-semibold text-slate-800 w-full text-left leading-normal m-0">Protecteur de la Sainte Église.</p>
          </div>
        `;
      } else if (type === 'chaste-heart') {
        container.style.maxHeight = 'fit-content';
        content.innerHTML = `
          <div class="flex flex-col items-start justify-start text-left py-1">
            <p class="text-base font-semibold text-slate-800 w-full text-left leading-normal m-0">Je bénis le cœur très chaste de Saint Joseph.</p>
          </div>
        `;
      }

      modal.classList.remove('hidden');
    }

    function showPrayer(prayerKey) {
      const content = document.getElementById('modal-content');

      if (prayerKey === 'ave-joseph') {
        content.innerHTML = `
          <div class="flex items-center justify-between mb-4 pb-2">
            <button onclick="openModal('dates')" class="text-xs font-bold text-red-700 hover:text-red-800 flex items-center gap-1 cursor-pointer">
              ← Retour
            </button>
            <span class="text-xs font-bold text-red-700 uppercase">19 Mars</span>
          </div>
          <div class="text-sm text-slate-700 leading-relaxed italic bg-blue-600/10 p-4 rounded-xl border border-blue-600/20 mb-4 space-y-2">
            <p>Je vous salue Joseph,</p>
            <p>Vous que la grâce divine a comblé ;</p>
            <p>le Sauveur a reposé dans vos bras et grandi sous vos yeux.</p>
            <p>Vous êtes béni entre tous les hommes et Jésus,</p>
            <p>l’Enfant divin de votre virginale Épouse est béni.</p>
            <p>Saint Joseph, donné pour père au Fils de Dieu,</p>
            <p>priez pour nous dans nos soucis de famille,</p>
            <p>de santé et de travail, jusqu’à nos derniers jours,</p>
            <p>et daignez nous secourir à l’heure de notre mort.</p>
            <p>Amen.</p>
          </div>
          <div class="text-[11px] text-slate-400 border-t border-slate-100 pt-3 text-center">
            <p><strong>Source :</strong> nd-de-graces.com</p>
          </div>
        `;
      } else if (prayerKey ===_ 'pie-x') {
        content.innerHTML = `
          <div class="flex items-center justify-between mb-4 pb-2">
            <button onclick="openModal('dates')" class="text-xs font-bold text-red-700 hover:text-red-800 flex items-center gap-1 cursor-pointer">
              ← Retour
            </button>
            <span class="text-xs font-bold text-red-700 uppercase">1er Mai</span>
          </div>
          <div class="text-sm text-slate-700 leading-relaxed italic bg-blue-600/10 p-4 rounded-xl border border-blue-600/20 mb-4 space-y-3">
            <p>Glorieux saint Joseph, modèle de tous ceux qui sont voués au travail, obtenez-moi la grâce de travailler en esprit de pénitence pour l’expiation de mes nombreux péchés ;</p>
            <p>de travailler en conscience, mettant le culte du devoir au-dessus de mes inclinations ;</p>
            <p>de travailler avec reconnaissance et joie, regardant comme un honneur d’employer et de développer par le travail les dons reçus de Dieu ;</p>
            <p>de travailler avec ordre, paix, modération et patience, sans jamais reculer devant la lassitude et les difficultés ;</p>
            <p>de travailler surtout avec pureté d’intention et avec détachement de moi-même ayant sans cesse devant les yeux la mort et le compte que je devrai rendre du temps perdu, des talents inutilisés, du bien omis et des vaines complaisances dans le succès, si funeste à l’œuvre de Dieu.</p>
            <p>Tout pour Jésus, tout pour Marie, tout à votre imitation, patriarche Joseph ! telle sera ma devise à la vie à la mort. Ainsi soit-il</p>
          </div>
          <div class="text-[11px] text-slate-400 border-t border-slate-100 pt-3 text-center">
            <p><strong>Prière de saint Pie X au glorieux Saint Joseph, modèle des travailleurs</strong></p>
            <p><strong>Source :</strong> laportelatine.org</p>
          </div>
        `;
      }
    }

    function closeModal() {
      const modal = document.getElementById('interactive-modal');
      modal.classList.add('hidden');
    }
  </script>
</body>
</html>
