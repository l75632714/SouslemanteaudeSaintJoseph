<!DOCTYPE html>
<html lang="fr" class="h-full">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
  <title>Sous le manteau de Saint Joseph</title>

  <script src="https://cdn.tailwindcss.com"></script>

  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,400;0,600;0,700;1,400;1,700&display=swap" rel="stylesheet">

  <style>
    body {
      font-family: 'Open Sans', sans-serif;
      -webkit-tap-highlight-color: transparent;
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
    .halo-effect {
      box-shadow: 0 0 15px rgba(212, 175, 55, 0.25);
      transition: all 0.5s ease;
    }
    .halo-container:hover .halo-effect {
      box-shadow: 0 0 35px rgba(212, 175, 55, 0.65);
      transform: scale(1.01);
    }
  </style>
</head>
<body class="bg-slate-900 text-slate-800 min-h-screen flex flex-col relative">

  <!-- Arrière-plan global corrigé : z-index négatif et affichage forcé -->
  <div style="position: fixed; inset: 0; z-index: -10; pointer-events: none; overflow: hidden;">
    <img src="Sketch1793913958083allrightsreservedtoLouiseÉmilieSchreiber.png" alt="Arrière-plan dessin" style="width: 100%; height: 100%; object-fit: cover; -webkit-user-select: none; user-select: none;">
  </div>

  <div class="relative z-10 min-h-screen flex flex-col justify-between">

    <!-- En-tête -->
    <header class="bg-blue-600 text-white shadow-md w-full">
      <div class="max-w-7xl mx-auto px-4 py-3 flex items-center justify-between">
        <div class="w-10"></div>
        <h1 class="text-lg md:text-2xl tracking-wide text-amber-400 text-center font-opensans-bold m-0 p-0">
          Sous le manteau de Saint Joseph
        </h1>
        <div class="w-10"></div>
      </div>
    </header>

    <!-- Layout Principal -->
    <div class="max-w-7xl mx-auto px-4 md:px-6 py-8 flex-grow w-full flex flex-col md:flex-row gap-8 items-stretch">
      
      <!-- Panneau Latéral Gauche : Neuvaine -->
      <aside class="w-full md:w-72 flex-shrink-0 flex flex-col">
        <div class="bg-white rounded-2xl p-6 shadow-sm border border-slate-200/80 h-full flex flex-col justify-between">
          <div>
            <div class="mb-6 flex flex-col items-start text-left">
              <h2 class="font-opensans-bold text-slate-900 text-lg mb-1">
                Neuvaine à Saint Joseph
              </h2>
              <p class="text-xs text-slate-500 italic">
                Suivez l'avancement de votre neuvaine :
              </p>
            </div>

            <div id="neuvaine-list" class="space-y-2.5"></div>
          </div>

          <!-- Message de fin de neuvaine -->
          <div id="neuvaine-completion-msg" class="hidden mt-6 pt-4 border-t border-amber-200/60 text-center">
            <p class="text-xs font-opensans-bold text-amber-700 italic">
              Que vos prières soient exaucées.
            </p>
          </div>
        </div>
      </aside>

      <!-- Zone Principale -->
      <main class="flex-grow w-full flex flex-col">
        <section class="bg-white rounded-2xl p-6 md:p-10 shadow-sm border border-slate-200/80 relative flex flex-col justify-between h-full">
          
          <div class="flex flex-col h-full justify-between">
            <div class="flex flex-col items-center">
              <h2 class="font-opensans-bold text-2xl md:text-4xl text-slate-900 mb-4 tracking-tight text-center">
                Saint Joseph
              </h2>
            </div>

            <div class="halo-container max-w-md mx-auto relative flex flex-col items-center w-full flex-grow justify-center">
              
              <div class="relative rounded-2xl overflow-hidden halo-effect border-2 border-amber-400/40 p-1 bg-slate-900 w-full flex justify-center h-full max-h-[580px]">
                <img 
                  src="https://noma.org/wp-content/uploads/2018/01/56-63-old.jpg" 
                  alt="Saint Joseph et l'Enfant-Jésus" 
                  class="w-full h-full object-cover rounded-xl"
                />

                <button onclick="openModal('dates')" class="absolute top-1/4 left-1/4 transform -translate-x-1/2 -translate-y-1/2 w-7 h-7 rounded-full bg-amber-500 hover:bg-amber-400 shadow-lg animate-pulse cursor-pointer">
                </button>

                <button onclick="openModal('titles')" class="absolute top-1/3 right-1/4 transform translate-x-1/2 -translate-y-1/2 w-7 h-7 rounded-full bg-blue-600 hover:bg-blue-500 shadow-lg animate-pulse cursor-pointer">
                </button>

                <button onclick="openModal('chaste-heart')" class="absolute top-[52%] right-[25%] transform translate-x-1/2 -translate-y-1/2 w-7 h-7 rounded-full bg-red-700 hover:bg-red-600 shadow-lg animate-pulse cursor-pointer">
                </button>
              </div>

              <button onclick="window.open('https://www.biblewalks.com/nazareth_maps/', '_blank')" title="Cartes et sites de Nazareth" class="absolute top-[65%] left-1/4 transform -translate-x-1/2 -translate-y-1/2 w-7 h-7 rounded-full bg-emerald-600 hover:bg-emerald-500 shadow-lg animate-pulse cursor-pointer">
              </button>

              <p class="text-[11px] text-slate-400 mt-2 italic text-center">
                Source : Object Lesson: St. Joseph and the Christ Child — NOMA
              </p>
            </div>
          </div>

          <!-- Modale -->
          <div id="interactive-modal" class="hidden fixed inset-0 z-50 flex items-center justify-center bg-slate-950/60 backdrop-blur-sm p-4">
            <div id="modal-container" class="bg-white rounded-2xl max-w-2xl w-full p-6 md:p-8 shadow-2xl border border-amber-200 relative max-h-[90vh] overflow-y-auto">
              <button onclick="closeModal()" class="absolute top-4 right-4 text-slate-400 hover:text-slate-700 p-2 rounded-lg text-lg font-bold cursor-pointer">
                ✕
              </button>
              <div id="modal-content" class="space-y-4"></div>
            </div>
          </div>

        </section>
      </main>

    </div>

    <!-- Bloc Nazareth -->
    <div class="relative z-10 -mb-6 flex justify-center px-4">
      <div class="inline-flex items-center gap-4 rounded-xl border border-amber-200/60 bg-white/95 px-6 py-3 shadow-md backdrop-blur-sm text-lg font-opensans-bold text-slate-800">
        <span class="text-slate-500 font-normal">Nazareth :</span>
        <a href="https://artsandculture.google.com/entity/nazareth/m05fz3?hl=fr" target="_blank" rel="noopener noreferrer" class="hover:text-amber-700 hover:underline transition-colors rounded">Découvrir</a>
        <span class="text-slate-300">•</span>
        <a href="https://artsandculture.google.com/search?q=Nazareth&hl=fr" target="_blank" rel="noopener noreferrer" class="hover:text-amber-700 hover:underline transition-colors rounded">Galerie</a>
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
          completionMsg.classList.remove("hidden");
        } else {
          completionMsg.classList.add("hidden");
        }
      }
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
          <div class="flex flex-col items-start justify-start text-left space-y-3 py-2">
            <h3 class="font-opensans-bold text-2xl text-slate-900 mb-2 w-full text-left">
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
      } else if (prayerKey === 'pie-x') {
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
