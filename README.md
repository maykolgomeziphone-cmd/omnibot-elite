<!DOCTYPE html>
<html lang="es" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>OmniBot Elite Pro - Consola Unificada de 80 Herramientas</title>
    <!-- Tailwind CSS para el diseño fluid-responsive -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        void: {
                            900: '#020308',
                            950: '#010204'
                        },
                        neon: {
                            indigo: '#6366f1',
                            violet: '#a855f7',
                            emerald: '#10b981',
                            amber: '#f59e0b',
                            rose: '#f43f5e',
                            teal: '#14b8a6',
                            sky: '#0ea5e9',
                            lime: '#84cc16'
                        }
                    }
                }
            }
        }
    </script>
    <!-- Google Fonts: Inter & Space Grotesk -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Space+Grotesk:wght@400;600;700;900&display=swap" rel="stylesheet">
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #020308;
            overflow-x: hidden;
        }
        .font-space {
            font-family: 'Space Grotesk', sans-serif;
        }
        .aurora-blur-1 {
            background: radial-gradient(circle, rgba(99, 102, 241, 0.12) 0%, rgba(0,0,0,0) 70%);
        }
        .aurora-blur-2 {
            background: radial-gradient(circle, rgba(168, 85, 247, 0.12) 0%, rgba(0,0,0,0) 70%);
        }
        .glass-panel {
            background: rgba(10, 12, 22, 0.65);
            backdrop-filter: blur(25px);
            -webkit-backdrop-filter: blur(25px);
            border: 1px solid rgba(255, 255, 255, 0.05);
        }
        .glass-card {
            background: rgba(14, 18, 36, 0.45);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.02);
            transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
        }
        .glass-card:hover {
            transform: translateY(-5px) scale(1.01);
            background: rgba(18, 23, 46, 0.65);
            border-color: rgba(99, 102, 241, 0.3);
            box-shadow: 0 20px 40px -15px rgba(99, 102, 241, 0.25);
        }
        /* Personalización de barra de desplazamiento estilo cyberpunk */
        ::-webkit-scrollbar {
            width: 8px;
            height: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #020308;
        }
        ::-webkit-scrollbar-thumb {
            background: #12182c;
            border-radius: 99px;
            border: 2px solid #020308;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #6366f1;
        }
    </style>
</head>
<body class="text-slate-200 min-h-screen flex flex-col antialiased relative">

    <!-- Blobs decorativos de fondo para profundidad visual -->
    <div class="absolute top-0 left-1/4 w-[500px] h-[500px] aurora-blur-1 -z-10 pointer-events-none"></div>
    <div class="absolute bottom-1/4 right-1/4 w-[600px] h-[600px] aurora-blur-2 -z-10 pointer-events-none"></div>

    <!-- Header Principal -->
    <header class="sticky top-0 z-40 glass-panel border-b border-slate-900/60">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-20 flex items-center justify-between">
            <div class="flex items-center gap-3.5">
                <div class="bg-gradient-to-tr from-indigo-500 via-purple-500 to-rose-400 text-white p-3 rounded-2xl shadow-lg shadow-indigo-500/20 flex items-center justify-center">
                    <i class="fa-solid fa-cubes text-2xl animate-pulse"></i>
                </div>
                <div>
                    <h1 class="font-space font-black text-xl tracking-tight bg-gradient-to-r from-indigo-400 via-purple-400 to-rose-400 bg-clip-text text-transparent">
                        OmniBot Elite Master
                    </h1>
                    <p class="text-[9px] text-indigo-400 font-extrabold tracking-widest uppercase">Estación Inteligente Unificada de 80 Herramientas</p>
                </div>
            </div>

            <div class="flex items-center gap-4">
                <span class="inline-flex items-center gap-1.5 px-3 py-1.5 rounded-full text-[10px] font-bold bg-indigo-950/40 border border-indigo-500/30 text-indigo-300">
                    <span class="w-2 h-2 rounded-full bg-indigo-400 animate-ping"></span>
                    80 Motores Operativos Activos
                </span>
            </div>
        </div>
    </header>

    <div class="flex-grow max-w-7xl w-full mx-auto px-4 sm:px-6 lg:px-8 py-6 flex flex-col lg:flex-row gap-6">
        
        <!-- Sidebar de Categorías -->
        <aside class="lg:w-72 flex-shrink-0">
            <div class="glass-panel rounded-3xl p-4 space-y-2 sticky top-24">
                <div class="p-3 bg-slate-950/60 rounded-2xl border border-slate-900/80 mb-2">
                    <label class="block text-[9px] font-bold text-slate-500 uppercase tracking-widest mb-1.5">Llave de Acceso Global</label>
                    <input type="password" id="custom-api-key" placeholder="API Key de Gemini (Opcional)" 
                        class="w-full text-[10px] px-3 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none focus:ring-1 focus:ring-indigo-500 placeholder:text-slate-600 transition-all">
                </div>

                <p class="text-[10px] font-bold text-slate-500 uppercase tracking-widest px-3 mb-1">Módulos de Control</p>
                
                <nav class="space-y-1" id="category-navigation">
                    <!-- Los botones de navegación se inicializan dinámicamente o se controlan de forma estricta por JS -->
                    <button onclick="filterCategory('all')" id="cat-btn-all" class="w-full text-left px-4 py-2.5 rounded-2xl text-xs font-bold transition-all flex items-center justify-between bg-indigo-600 text-white shadow-lg">
                        <span class="flex items-center gap-3"><i class="fa-solid fa-shapes"></i> Todo el Sistema</span>
                        <span class="text-[10px] bg-indigo-700/60 px-2 py-0.5 rounded-md font-bold">80</span>
                    </button>
                    <button onclick="filterCategory('estudios')" id="cat-btn-estudios" class="w-full text-left px-4 py-2.5 rounded-2xl text-xs font-semibold text-slate-400 hover:bg-slate-900/50 hover:text-white transition-all flex items-center justify-between">
                        <span class="flex items-center gap-3"><i class="fa-solid fa-graduation-cap text-indigo-400"></i> Estudios & Academia</span>
                        <span class="text-[10px] bg-slate-900 px-2 py-0.5 rounded-md font-bold">10</span>
                    </button>
                    <button onclick="filterCategory('desarrollo')" id="cat-btn-desarrollo" class="w-full text-left px-4 py-2.5 rounded-2xl text-xs font-semibold text-slate-400 hover:bg-slate-900/50 hover:text-white transition-all flex items-center justify-between">
                        <span class="flex items-center gap-3"><i class="fa-solid fa-code text-purple-400"></i> Desarrollo & Tech</span>
                        <span class="text-[10px] bg-slate-900 px-2 py-0.5 rounded-md font-bold">10</span>
                    </button>
                    <button onclick="filterCategory('salud')" id="cat-btn-salud" class="w-full text-left px-4 py-2.5 rounded-2xl text-xs font-semibold text-slate-400 hover:bg-slate-900/50 hover:text-white transition-all flex items-center justify-between">
                        <span class="flex items-center gap-3"><i class="fa-solid fa-heart-pulse text-emerald-400"></i> Salud & Bienestar</span>
                        <span class="text-[10px] bg-slate-900 px-2 py-0.5 rounded-md font-bold">10</span>
                    </button>
                    <button onclick="filterCategory('gestion')" id="cat-btn-gestion" class="w-full text-left px-4 py-2.5 rounded-2xl text-xs font-semibold text-slate-400 hover:bg-slate-900/50 hover:text-white transition-all flex items-center justify-between">
                        <span class="flex items-center gap-3"><i class="fa-solid fa-chart-line text-amber-400"></i> Gestión & Finanzas</span>
                        <span class="text-[10px] bg-slate-900 px-2 py-0.5 rounded-md font-bold">10</span>
                    </button>
                    <button onclick="filterCategory('creatividad')" id="cat-btn-creatividad" class="w-full text-left px-4 py-2.5 rounded-2xl text-xs font-semibold text-slate-400 hover:bg-slate-900/50 hover:text-white transition-all flex items-center justify-between">
                        <span class="flex items-center gap-3"><i class="fa-solid fa-wand-magic-sparkles text-rose-400"></i> Creatividad & Ocio</span>
                        <span class="text-[10px] bg-slate-900 px-2 py-0.5 rounded-md font-bold">10</span>
                    </button>
                    <button onclick="filterCategory('utilidades')" id="cat-btn-utilidades" class="w-full text-left px-4 py-2.5 rounded-2xl text-xs font-semibold text-slate-400 hover:bg-slate-900/50 hover:text-white transition-all flex items-center justify-between">
                        <span class="flex items-center gap-3"><i class="fa-solid fa-screwdriver-wrench text-teal-400"></i> Utilidades Diarias</span>
                        <span class="text-[10px] bg-slate-900 px-2 py-0.5 rounded-md font-bold">10</span>
                    </button>
                    <button onclick="filterCategory('marketing')" id="cat-btn-marketing" class="w-full text-left px-4 py-2.5 rounded-2xl text-xs font-semibold text-slate-400 hover:bg-slate-900/50 hover:text-white transition-all flex items-center justify-between">
                        <span class="flex items-center gap-3"><i class="fa-solid fa-bullhorn text-sky-400"></i> Marketing & Redes</span>
                        <span class="text-[10px] bg-slate-900 px-2 py-0.5 rounded-md font-bold">10</span>
                    </button>
                    <button onclick="filterCategory('lifestyle')" id="cat-btn-lifestyle" class="w-full text-left px-4 py-2.5 rounded-2xl text-xs font-semibold text-slate-400 hover:bg-slate-900/50 hover:text-white transition-all flex items-center justify-between">
                        <span class="flex items-center gap-3"><i class="fa-solid fa-compass text-lime-400"></i> Estilo de Vida & Viajes</span>
                        <span class="text-[10px] bg-slate-900 px-2 py-0.5 rounded-md font-bold">10</span>
                    </button>
                </nav>
            </div>
        </aside>

        <main class="flex-grow flex flex-col gap-6 overflow-hidden">
            
            <!-- Barra de Búsqueda y Filtro Rápido -->
            <div class="glass-panel p-5 rounded-3xl flex flex-col sm:flex-row gap-4 justify-between items-center">
                <div class="relative w-full sm:max-w-md">
                    <span class="absolute inset-y-0 left-0 flex items-center pl-4 text-slate-500">
                        <i class="fa-solid fa-magnifying-glass text-xs"></i>
                    </span>
                    <input type="text" id="tool-search-input" onkeyup="searchTools()" placeholder="Buscar entre las 80 herramientas..." 
                        class="w-full pl-10 pr-4 py-3 rounded-2xl bg-slate-950/80 border border-slate-800 text-xs text-slate-200 placeholder:text-slate-600 focus:outline-none focus:ring-1 focus:ring-indigo-500 transition-all">
                </div>
                <div class="flex items-center gap-2 text-xs text-slate-400">
                    <i class="fa-solid fa-sliders text-indigo-400"></i>
                    <span>Categoría:</span>
                    <strong class="text-white font-bold" id="current-category-label">Todo el Sistema</strong>
                </div>
            </div>

            <!-- Contenedor del Espacio de Trabajo de Herramientas (Modales/Vistas Activas) -->
            <div id="active-tool-workspace" class="hidden glass-panel rounded-3xl p-6 bg-gradient-to-b from-slate-950/40 via-slate-950/80 to-slate-950 relative">
                <button onclick="closeWorkspace()" class="absolute top-4 right-4 text-slate-500 hover:text-white transition-colors p-2 rounded-xl bg-slate-900/80 border border-slate-800" title="Cerrar Herramienta">
                    <i class="fa-solid fa-xmark"></i>
                </button>
                <div id="workspace-loader" class="absolute inset-0 bg-slate-950/90 rounded-3xl flex flex-col items-center justify-center space-y-4 z-10 hidden">
                    <div class="w-10 h-10 border-4 border-indigo-500 border-t-transparent rounded-full animate-spin"></div>
                    <p class="text-xs text-slate-400 font-semibold" id="workspace-loader-text">Procesando comando...</p>
                </div>
                <div id="workspace-dynamic-content">
                    <!-- Contenido renderizado de forma dinámica por JS -->
                </div>
            </div>
<div id="active-tool-workspace" class="hidden glass-panel rounded-3xl p-8 mb-8 border border-indigo-500/20 animate-in fade-in zoom-in duration-300">
    <h2 id="tool-title" class="text-2xl font-bold mb-4 text-white"></h2>
    <div id="tool-content" class="text-slate-400"></div>
    <button onclick="document.getElementById('active-tool-workspace').classList.add('hidden')" class="mt-6 bg-slate-800 px-6 py-2 rounded-xl text-xs font-bold hover:bg-slate-700 transition">CERRAR SESIÓN</button>
</div>
            <!-- Rejilla de Tarjetas de las 80 Herramientas -->
            <div class="grid grid-cols-1 md:grid-cols-2 xl:grid-cols-3 gap-4" id="tools-main-grid">
                <!-- Se cargará de manera dinámica para mantener el archivo limpio y no repetir código repetitivo -->
            </div>

        </main>
    </div>

    <!-- Notificación Flotante Estilo Holograma -->
    <div id="suite-toast" class="fixed bottom-6 right-6 bg-slate-900/90 border border-slate-800 p-4 rounded-2xl shadow-2xl z-50 flex items-start gap-3 hidden max-w-sm">
        <div class="bg-indigo-950 text-indigo-400 p-2 rounded-xl border border-indigo-500/20" id="toast-icon">
            <i class="fa-solid fa-circle-check"></i>
        </div>
        <div>
            <h4 class="font-bold text-xs text-white" id="toast-title-text">Operación Correcta</h4>
            <p class="text-[10px] text-slate-400 mt-0.5" id="toast-desc-text">Configurado correctamente.</p>
        </div>
    </div>

    <!-- Pie de Página -->
  <footer class="bg-slate-950/40 border-t border-slate-900/60 py-8 text-center flex-shrink-0 mt-auto">
    <p class="text-[10px] text-slate-600 font-semibold tracking-wider uppercase font-space">
        &copy; 2026 OmniBot Elite Master | Desarrollado por: <b>Maykol Gomez (2do A)</b> | Estación Inteligente Unificada
    </p>
</footer>

    <script>
        // Efecto de sonido de clic de alta gama usando la API de Web Audio nativa
        function playInterfaceClick(type = 'click') {
            try {
                const ctx = new (window.AudioContext || window.webkitAudioContext)();
                const osc = ctx.createOscillator();
                const gain = ctx.createGain();
                
                osc.connect(gain);
                gain.connect(ctx.destination);
                
                if (type === 'click') {
                    osc.type = 'sine';
                    osc.frequency.setValueAtTime(600, ctx.currentTime);
                    osc.frequency.exponentialRampToValueAtTime(150, ctx.currentTime + 0.1);
                    gain.gain.setValueAtTime(0.08, ctx.currentTime);
                    gain.gain.exponentialRampToValueAtTime(0.01, ctx.currentTime + 0.1);
                    osc.start();
                    osc.stop(ctx.currentTime + 0.1);
                } else if (type === 'success') {
                    osc.type = 'triangle';
                    osc.frequency.setValueAtTime(440, ctx.currentTime);
                    osc.frequency.setValueAtTime(880, ctx.currentTime + 0.1);
                    gain.gain.setValueAtTime(0.06, ctx.currentTime);
                    gain.gain.exponentialRampToValueAtTime(0.01, ctx.currentTime + 0.25);
                    osc.start();
                    osc.stop(ctx.currentTime + 0.25);
                }
            } catch (e) {
                // Silencio en caso de que el navegador bloquee la API de audio
            }
        }

        // Listado completo de las 80 herramientas organizadas en 8 categorías de 10 herramientas cada una
        const originalToolsList = [
            // CATEGORY: ESTUDIOS (10)
            { id: 1, cat: 'estudios', title: 'Tutor Académico IA', icon: 'fa-graduation-cap', color: 'indigo', desc: 'Sube temas académicos y obtén explicaciones paso a paso.', isAI: true },
            { id: 2, cat: 'estudios', title: 'Generador de Exámenes', icon: 'fa-file-lines', color: 'indigo', desc: 'Diseña cuestionarios con opciones para autoevaluación.', isAI: true },
            { id: 3, cat: 'estudios', title: 'Resumidor Ejecutivo', icon: 'fa-align-left', color: 'indigo', desc: 'Reduce bloques extensos de texto en ideas de alta fidelidad.', isAI: true },
            { id: 4, cat: 'estudios', title: 'Creador de Flashcards', icon: 'fa-clone', color: 'indigo', desc: 'Genera tarjetas de memorización sobre conceptos clave.', isAI: true },
            { id: 5, cat: 'estudios', title: 'Simplificador "ELI5"', icon: 'fa-child-reaching', color: 'indigo', desc: 'Explica temas complejos de forma infantil y muy clara.', isAI: true },
            { id: 6, cat: 'estudios', title: 'Traductor Multilingüe', icon: 'fa-language', color: 'indigo', desc: 'Traducción de textos optimizada por modismos de lenguaje.', isAI: true },
            { id: 7, cat: 'estudios', title: 'Corrector Estilístico', icon: 'fa-pen-nib', color: 'indigo', desc: 'Optimiza la ortografía, tono gramatical y coherencia.', isAI: true },
            { id: 8, cat: 'estudios', title: 'Buscador de Sinónimos', icon: 'fa-shuffle', color: 'indigo', desc: 'Encuentra listas de alternativas ricas para enriquecer tu vocabulario.', isAI: true },
            { id: 9, cat: 'estudios', title: 'Citador de Normas APA', icon: 'fa-bookmark', color: 'indigo', desc: 'Genera referencias bibliográficas precisas bajo normas internacionales.', isAI: true },
            { id: 10, cat: 'estudios', title: 'Calculadora Científica', icon: 'fa-calculator', color: 'indigo', desc: 'Calculadora funcional integrada para operaciones complejas.', isAI: false },

            // CATEGORY: DESARROLLO (10)
            { id: 11, cat: 'desarrollo', title: 'Asistente Debugger', icon: 'fa-bug', color: 'purple', desc: 'Detecta vulnerabilidades y errores de sintaxis en tus códigos.', isAI: true },
            { id: 12, cat: 'desarrollo', title: 'Convertidor de Código', icon: 'fa-rotate', color: 'purple', desc: 'Traduce funciones lógicas entre múltiples lenguajes de programación.', isAI: true },
            { id: 13, cat: 'desarrollo', title: 'Constructor de Regex', icon: 'fa-square-check', color: 'purple', desc: 'Crea expresiones regulares y pruébalas interactivamente.', isAI: false },
            { id: 14, cat: 'desarrollo', title: 'Embellecedor de JSON', icon: 'fa-code-compare', color: 'purple', desc: 'Formatea, repara y ordena estructuras de datos JSON.', isAI: false },
            { id: 15, cat: 'desarrollo', title: 'Generador de SQL', icon: 'fa-database', color: 'purple', desc: 'Traduce solicitudes en lenguaje natural a consultas SQL válidas.', isAI: true },
            { id: 16, cat: 'desarrollo', title: 'Previsualizador Markdown', icon: 'fa-file-code', color: 'purple', desc: 'Renderiza tus documentos de texto Markdown a formato HTML visual.', isAI: false },
            { id: 17, cat: 'desarrollo', title: 'Codificador Base64', icon: 'fa-shield-halved', color: 'purple', desc: 'Codifica y decodifica textos de forma rápida con fines de seguridad.', isAI: false },
            { id: 18, cat: 'desarrollo', title: 'Analista de Seguridad', icon: 'fa-user-shield', color: 'purple', desc: 'Evalúa la seguridad y riesgos de tus algoritmos.', isAI: true },
            { id: 19, cat: 'desarrollo', title: 'Generador Dummy Data', icon: 'fa-table-cells', color: 'purple', desc: 'Genera nombres, correos y datos falsos para desarrollo y pruebas.', isAI: false },
            { id: 20, cat: 'desarrollo', title: 'Calculadora de Big O', icon: 'fa-chart-area', color: 'purple', desc: 'Analiza la complejidad computacional temporal de tus algoritmos.', isAI: true },

            // CATEGORY: SALUD (10)
            { id: 21, cat: 'salud', title: 'Planificador de Dietas', icon: 'fa-plate-wheat', color: 'emerald', desc: 'Menús balanceados diseñados según tus ingredientes disponibles.', isAI: true },
            { id: 22, cat: 'salud', title: 'Rutina Deportiva', icon: 'fa-dumbbell', color: 'emerald', desc: 'Diseña rutinas de fuerza adaptadas a tus objetivos musculares.', isAI: true },
            { id: 23, cat: 'salud', title: 'Contador de Calorías', icon: 'fa-apple-whole', color: 'emerald', desc: 'Calculadora de ingesta calórica acumulada diaria.', isAI: false },
            { id: 24, cat: 'salud', title: 'Calculadora de IMC', icon: 'fa-weight-scale', color: 'emerald', desc: 'Calcula tu índice de masa corporal y estado físico.', isAI: false },
            { id: 25, cat: 'salud', title: 'Rastreador de Agua', icon: 'fa-droplet', color: 'emerald', desc: 'Bitácora interactiva de ingesta de líquidos recomendada.', isAI: false },
            { id: 26, cat: 'salud', title: 'Asistente de Flexibilidad', icon: 'fa-person-walking', color: 'emerald', desc: 'Genera planes de estiramiento contra el estrés laboral.', isAI: true },
            { id: 27, cat: 'salud', title: 'Guía de Meditación', icon: 'fa-spa', color: 'emerald', desc: 'Genera ejercicios de respiración rítmica consciente.', isAI: true },
            { id: 28, cat: 'salud', title: 'Diario de Coherencia', icon: 'fa-heart', color: 'emerald', desc: 'Reflexiona sobre tu día y obtén retroalimentación mental positiva.', isAI: true },
            { id: 29, cat: 'salud', title: 'Creador de Hábitos', icon: 'fa-circle-check', color: 'emerald', desc: 'Controlador interactivo de metas semanales.', isAI: false },
            { id: 30, cat: 'salud', title: 'Cronómetro de Sueño', icon: 'fa-moon', color: 'emerald', desc: 'Calcula las horas ideales para despertar sintiéndote descansado.', isAI: false },

            // CATEGORY: GESTION (10)
            { id: 31, cat: 'gestion', title: 'Matriz de Eisenhower', icon: 'fa-calendar-days', color: 'amber', desc: 'Organiza tus actividades diarias por su nivel de importancia.', isAI: false },
            { id: 32, cat: 'gestion', title: 'Divisor de Tareas WBS', icon: 'fa-sitemap', color: 'amber', desc: 'Desglosa metas grandes en pequeñas tareas asignables.', isAI: true },
            { id: 33, cat: 'gestion', title: 'Redactor Profesional', icon: 'fa-envelope', color: 'amber', desc: 'Redacta correos, discursos o comunicados de alto nivel.', isAI: true },
            { id: 34, cat: 'gestion', title: 'Estructurador Proyectos', icon: 'fa-timeline', color: 'amber', desc: 'Planea plazos y fases organizacionales para tu equipo.', isAI: true },
            { id: 35, cat: 'gestion', title: 'Interés Compuesto', icon: 'fa-sack-dollar', color: 'amber', desc: 'Simulador de proyecciones y crecimiento de capital financiero.', isAI: false },
            { id: 36, cat: 'gestion', title: 'Presupuesto Mensual', icon: 'fa-money-bill-transfer', color: 'amber', desc: 'Control de ingresos y egresos de forma segura en el navegador.', isAI: false },
            { id: 37, cat: 'gestion', title: 'Conversor de Divisas', icon: 'fa-coins', color: 'amber', desc: 'Calcula el tipo de cambio entre divisas internacionales.', isAI: false },
            { id: 38, cat: 'gestion', title: 'Simulador de Ahorro', icon: 'fa-piggy-bank', color: 'amber', desc: 'Establece metas financieras y plazos para completarlas.', isAI: false },
            { id: 39, cat: 'gestion', title: 'Generador de Facturas', icon: 'fa-file-invoice-dollar', color: 'amber', desc: 'Crea plantillas de facturas profesionales listas para exportación.', isAI: false },
            { id: 40, cat: 'gestion', title: 'Preparador de Entrevistas', icon: 'fa-comments', color: 'amber', desc: 'Preguntas y respuestas clave según la vacante laboral.', isAI: true },

            // CATEGORY: CREATIVIDAD (10)
            { id: 41, cat: 'creatividad', title: 'Diseñador de Platos Imagen', icon: 'fa-image', color: 'rose', desc: 'Generación visual de fotografías artísticas gastronómicas.', isAI: true, isImage: true },
            { id: 42, cat: 'creatividad', title: 'Dungeon Master RPG', icon: 'fa-dragon', color: 'rose', desc: 'Inicia una partida de rol donde tus decisiones controlan el universo.', isAI: true },
            { id: 43, cat: 'creatividad', title: 'Arcade Space Defender', icon: 'fa-gamepad', color: 'rose', desc: 'Juego retro arcade integrado con motor Canvas.', isAI: false },
            { id: 44, cat: 'creatividad', title: 'Generador Poético', icon: 'fa-feather', color: 'rose', desc: 'Crea versos literarios y poemas adaptados a un estado de ánimo.', isAI: true },
            { id: 45, cat: 'creatividad', title: 'Lluvia de Ideas', icon: 'fa-lightbulb', color: 'rose', desc: 'Genera ideas de negocios innovadores o proyectos creativos.', isAI: true },
            { id: 46, cat: 'creatividad', title: 'Generador de Comedia', icon: 'fa-face-laugh-squint', color: 'rose', desc: 'Inyecta chistes y líneas divertidas sobre conceptos técnicos.', isAI: true },
            { id: 47, cat: 'creatividad', title: 'Creador de Hilos Virales', icon: 'fa-share-nodes', color: 'rose', desc: 'Transforma una idea de texto en hilos y copys de redes sociales.', isAI: true },
            { id: 48, cat: 'creatividad', title: 'Paleta de Colores', icon: 'fa-palette', color: 'rose', desc: 'Genera paletas cromáticas elegantes con códigos CSS integrados.', isAI: false },
            { id: 49, cat: 'creatividad', title: 'Escritor Narrativo', icon: 'fa-book-open', color: 'rose', desc: 'Crea micro-historias sumergibles a partir de una frase guía.', isAI: true },
            { id: 50, cat: 'creatividad', title: 'Asistente de Acordes', icon: 'fa-guitar', color: 'rose', desc: 'Genera secuencias y acordes de guitarra según el ritmo.', isAI: true },

            // CATEGORY: UTILIDADES (10)
            { id: 51, cat: 'utilidades', title: 'Generador de Claves', icon: 'fa-key', color: 'teal', desc: 'Crea contraseñas criptográficas sumamente seguras.', isAI: false },
            { id: 52, cat: 'utilidades', title: 'Temporizador Pomodoro', icon: 'fa-clock', color: 'teal', desc: 'Planifica tus ciclos de alta productividad de 25 minutos.', isAI: false },
            { id: 53, cat: 'utilidades', title: 'Conversor de Unidades', icon: 'fa-scale-balanced', color: 'teal', desc: 'Transforma métricas del sistema métrico de forma instantánea.', isAI: false },
            { id: 54, cat: 'utilidades', title: 'Diseñador de QR', icon: 'fa-qrcode', color: 'teal', desc: 'Genera códigos QR funcionales para cualquier enlace web.', isAI: false },
            { id: 55, cat: 'utilidades', title: 'Extractor de Palabras Clave', icon: 'fa-magnifying-glass-chart', color: 'teal', desc: 'Analiza textos para aislar los conceptos y palabras clave.', isAI: true },
            { id: 56, cat: 'utilidades', title: 'Lector por Voz (TTS)', icon: 'fa-volume-high', color: 'teal', desc: 'Sintetiza tus textos escritos en un archivo de audio legible.', isAI: true, isAudio: true },
            { id: 57, cat: 'utilidades', title: 'Detector de Sentimientos', icon: 'fa-face-meh', color: 'teal', desc: 'Descubre las emociones predominantes en una reseña de cliente.', isAI: true },
            { id: 58, cat: 'utilidades', title: 'Sorteador de Nombres', icon: 'fa-user-group', color: 'teal', desc: 'Elige un ganador aleatorio de forma justa de una lista.', isAI: false },
            { id: 59, cat: 'utilidades', title: 'Zonas Horarias', icon: 'fa-earth-americas', color: 'teal', desc: 'Calcula y compara diferencias horarias internacionales.', isAI: false },
            { id: 60, cat: 'utilidades', title: 'Lista de Compras Inteligente', icon: 'fa-cart-shopping', color: 'teal', desc: 'Lleva tu bitácora de productos por comprar de forma cómoda.', isAI: false },

            // CATEGORY: MARKETING & REDES (10) [NUEVO]
            { id: 61, cat: 'marketing', title: 'Redactor de Copys Ad', icon: 'fa-rectangle-ad', color: 'sky', desc: 'Diseña anuncios persuasivos para Facebook y Google Ads.', isAI: true },
            { id: 62, cat: 'marketing', title: 'Asistente de Hashtags', icon: 'fa-hashtag', color: 'sky', desc: 'Genera etiquetas virales según tu temática y nicho de mercado.', isAI: true },
            { id: 63, cat: 'marketing', title: 'Optimizar SEO Meta', icon: 'fa-chart-simple', color: 'sky', desc: 'Estructura etiquetas Title y Description de alto impacto SEO.', isAI: true },
            { id: 64, cat: 'marketing', title: 'Idea de Post IG', icon: 'fa-instagram', color: 'sky', desc: 'Lluvia de ideas de publicaciones visuales e historias para Instagram.', isAI: true },
            { id: 65, cat: 'marketing', title: 'Script de Video TikTok', icon: 'fa-video', color: 'sky', desc: 'Escribe guiones dinámicos de 30 segundos ideales para Shorts/TikTok.', isAI: true },
            { id: 66, cat: 'marketing', title: 'Asistente de Newsletter', icon: 'fa-newspaper', color: 'sky', desc: 'Planifica y redacta campañas periódicas de Email Marketing.', isAI: true },
            { id: 67, cat: 'marketing', title: 'Generador de Slogans', icon: 'fa-pen-clip', color: 'sky', desc: 'Crea slogans cortos, pegajosos y comerciales de marca.', isAI: true },
            { id: 68, cat: 'marketing', title: 'Analista de Landing Page', icon: 'fa-rocket', color: 'sky', desc: 'Evalúa la claridad y llamados a la acción de una landing.', isAI: true },
            { id: 69, cat: 'marketing', title: 'Estructurador de Preguntas', icon: 'fa-circle-question', color: 'sky', desc: 'Genera trivias de alto enganche para historias de redes.', isAI: true },
            { id: 70, cat: 'marketing', title: 'Calculador ROI Campañas', icon: 'fa-percent', color: 'sky', desc: 'Calculadora de retorno de inversión publicitaria (ROAS).', isAI: false },

            // CATEGORY: ESTILO DE VIDA & VIAJES (10) [NUEVO]
            { id: 71, cat: 'lifestyle', title: 'Planificador de Viajes', icon: 'fa-plane', color: 'lime', desc: 'Diseña itinerarios detallados por día para tus próximas vacaciones.', isAI: true },
            { id: 72, cat: 'lifestyle', title: 'Creador de Maletas', icon: 'fa-suitcase-rolling', color: 'lime', desc: 'Genera listas de equipaje inteligente según clima y duración.', isAI: true },
            { id: 73, cat: 'lifestyle', title: 'Guía de Hábitos 66D', icon: 'fa-arrows-spin', color: 'lime', desc: 'Crea el bucle de hábitos para los 66 días de automatización.', isAI: true },
            { id: 74, cat: 'lifestyle', title: 'Asistente de Lectura', icon: 'fa-book-open-reader', color: 'lime', desc: 'Planifica tus páginas diarias para terminar tus libros al año.', isAI: false },
            { id: 75, cat: 'lifestyle', title: 'Planificador Financiero 50-30-20', icon: 'fa-vault', color: 'lime', desc: 'Divide tus ingresos en categorías de forma automática.', isAI: false },
            { id: 76, cat: 'lifestyle', title: 'Traductor de Supervivencia', icon: 'fa-passport', color: 'lime', desc: 'Frases clave indispensables en aeropuertos, hoteles y restaurantes.', isAI: true },
            { id: 77, cat: 'lifestyle', title: 'Buscador de Cafés Trabajo', icon: 'fa-mug-hot', color: 'lime', desc: 'Recomendaciones teóricas de locaciones ideales para coworking.', isAI: true },
            { id: 78, cat: 'lifestyle', title: 'Generador de Rutinas Mañana', icon: 'fa-sun', color: 'lime', desc: 'Estructura un despertar productivo (Club de las 5 am).', isAI: true },
            { id: 79, cat: 'lifestyle', title: 'Lista de Gratitud Diaria', icon: 'fa-hands-praying', color: 'lime', desc: 'Bitácora interactiva personal de agradecimientos diarios.', isAI: false },
            { id: 80, cat: 'lifestyle', title: 'Cronómetro de Té', icon: 'fa-hourglass-half', color: 'lime', desc: 'Tiempos ideales de infusión de hierbas para calmar la mente.', isAI: false }
        ];

        let currentActiveCategory = 'all';
        let searchKeyword = '';

        document.addEventListener('DOMContentLoaded', () => {
            renderToolsGrid();
        });

        function filterCategory(category) {
            playInterfaceClick('click');
            currentActiveCategory = category;
            
            // Actualizar estilo de botones de navegación
            document.querySelectorAll('#category-navigation button').forEach(btn => {
                btn.className = "w-full text-left px-4 py-2.5 rounded-2xl text-xs font-semibold text-slate-400 hover:bg-slate-900/50 hover:text-white transition-all flex items-center justify-between";
            });

            const activeBtn = document.getElementById(`cat-btn-${category}`);
            if (activeBtn) {
                activeBtn.className = "w-full text-left px-4 py-2.5 rounded-2xl text-xs font-bold transition-all flex items-center justify-between bg-indigo-600 text-white shadow-lg shadow-indigo-600/20";
            }

            const labelMap = {
                all: 'Todo el Sistema',
                estudios: 'Estudios & Academia',
                desarrollo: 'Desarrollo & Tech',
                salud: 'Salud & Bienestar',
                gestion: 'Gestión & Finanzas',
                creatividad: 'Creatividad & Ocio',
                utilidades: 'Utilidades Diarias',
                marketing: 'Marketing & Redes',
                lifestyle: 'Estilo de Vida & Viajes'
            };
            document.getElementById('current-category-label').innerText = labelMap[category];

            renderToolsGrid();
        }

        function searchTools() {
            searchKeyword = document.getElementById('tool-search-input').value.toLowerCase().trim();
            renderToolsGrid();
        }

        function renderToolsGrid() {
            const grid = document.getElementById('tools-main-grid');
            grid.innerHTML = '';

            const filtered = originalToolsList.filter(t => {
                const matchesCategory = (currentActiveCategory === 'all' || t.cat === currentActiveCategory);
                const matchesSearch = t.title.toLowerCase().includes(searchKeyword) || t.desc.toLowerCase().includes(searchKeyword);
                return matchesCategory && matchesSearch;
            });

            if (filtered.length === 0) {
                grid.innerHTML = `
                    <div class="col-span-full py-12 text-center text-slate-500 text-xs">
                        <i class="fa-solid fa-face-frown text-3xl mb-3 block text-slate-700"></i>
                        No se encontraron herramientas que coincidan con la búsqueda actual.
                    </div>
                `;
                return;
            }

            filtered.forEach(t => {
                const colorMap = {
                    indigo: { ring: 'hover:border-indigo-500/30', bg: 'bg-indigo-950/40 text-indigo-400', bColor: 'border-indigo-500/10' },
                    purple: { ring: 'hover:border-purple-500/30', bg: 'bg-purple-950/40 text-purple-400', bColor: 'border-purple-500/10' },
                    emerald: { ring: 'hover:border-emerald-500/30', bg: 'bg-emerald-950/40 text-emerald-400', bColor: 'border-emerald-500/10' },
                    amber: { ring: 'hover:border-amber-500/30', bg: 'bg-amber-950/40 text-amber-400', bColor: 'border-amber-500/10' },
                    rose: { ring: 'hover:border-rose-500/30', bg: 'bg-rose-950/40 text-rose-400', bColor: 'border-rose-500/10' },
                    teal: { ring: 'hover:border-teal-500/30', bg: 'bg-teal-950/40 text-teal-400', bColor: 'border-teal-500/10' },
                    sky: { ring: 'hover:border-sky-500/30', bg: 'bg-sky-950/40 text-sky-400', bColor: 'border-sky-500/10' },
                    lime: { ring: 'hover:border-lime-500/30', bg: 'bg-lime-950/40 text-lime-400', bColor: 'border-lime-500/10' }
                };
                function executeTool(tool) {
    const workspace = document.getElementById('active-tool-workspace');
    const title = document.getElementById('tool-title');
    const content = document.getElementById('tool-content');

    // Lógica para Generador de Imágenes
    if (tool.includes("Generador") || tool.includes("Imagen")) {
        workspace.classList.remove('hidden');
        title.innerText = "Generador de Imágenes IA";
        content.innerHTML = `
            <input type="text" id="img-prompt" placeholder="Describe la imagen..." class="w-full bg-slate-900 p-3 rounded-xl border border-slate-700 mb-4 text-sm">
            <button onclick="alert('Generando: ' + document.getElementById('img-prompt').value)" class="bg-indigo-600 px-6 py-2 rounded-xl text-xs font-bold hover:bg-indigo-500">GENERAR IMAGEN</button>
        `;
    } 
    // Lógica para Asistente IA
    else if (tool.includes("Asistente") || tool.includes("IA")) {
        workspace.classList.remove('hidden');
        title.innerText = "Asistente IA - Maykol Bot";
        content.innerHTML = `
            <textarea id="ai-chat" class="w-full bg-slate-900 p-3 rounded-xl border border-slate-700 h-24 mb-4 text-sm" placeholder="Pregúntale algo a tu IA..."></textarea>
            <button onclick="alert('IA procesando: ' + document.getElementById('ai-chat').value)" class="bg-indigo-600 px-6 py-2 rounded-xl text-xs font-bold hover:bg-indigo-500">CONSULTAR</button>
        `;
    } 
    else {
        // Tu lógica original de 80 herramientas sigue aquí
        console.log("Ejecutando: " + tool);
    }
}
                const c = colorMap[t.color] || colorMap.indigo;

                const card = document.createElement('div');
                card.className = `glass-card p-5 rounded-3xl cursor-pointer ${c.ring} flex flex-col gap-3 relative overflow-hidden`;
                card.onclick = () => openToolWorkspace(t.id);
                
                card.innerHTML = `
                    <div class="flex items-center gap-3">
                        <div class="w-10 h-10 ${c.bg} rounded-xl flex items-center justify-center text-md flex-shrink-0 border ${c.bColor}">
                            <i class="fa-solid ${t.icon}"></i>
                        </div>
                        <div>
                            <h3 class="font-bold text-xs text-white font-space">${t.title}</h3>
                            <span class="text-[8px] uppercase tracking-wider ${t.isAI ? 'text-indigo-400' : 'text-slate-500'} font-bold">
                                ${t.isAI ? 'Inteligencia Artificial' : 'Motor Local'}
                            </span>
                        </div>
                    </div>
                    <p class="text-[10px] text-slate-400 leading-relaxed">${t.desc}</p>
                    <div class="mt-auto pt-2 border-t border-slate-900/60 flex justify-between items-center text-[9px] text-slate-500">
                        <span>Ref #M${1000 + t.id}</span>
                        <span class="hover:text-white font-bold flex items-center gap-1">Arrancar <i class="fa-solid fa-angle-right"></i></span>
                    </div>
                `;
                grid.appendChild(card);
            });
        }

        function openToolWorkspace(toolId) {
            playInterfaceClick('click');
            const workspace = document.getElementById('active-tool-workspace');
            const dynamicContent = document.getElementById('workspace-dynamic-content');
            
            workspace.classList.remove('hidden');
            workspace.scrollIntoView({ behavior: 'smooth', block: 'start' });

            const t = originalToolsList.find(item => item.id === toolId);
            if (!t) return;

            renderToolInterface(t, dynamicContent);
        }

        function closeWorkspace() {
            playInterfaceClick('click');
            document.getElementById('active-tool-workspace').classList.add('hidden');
        }

        function toggleWorkspaceLoader(show, text = "Procesando comando...") {
            const loader = document.getElementById('workspace-loader');
            document.getElementById('workspace-loader-text').innerText = text;
            if (show) loader.classList.remove('hidden');
            else loader.classList.add('hidden');
        }

        function getAPIKey() {
            return document.getElementById('custom-api-key').value.trim();
        }

        function renderToolInterface(tool, container) {
            let html = `
                <div class="flex items-center gap-3 border-b border-slate-900 pb-3 mb-4">
                    <div class="w-8 h-8 rounded-lg bg-${tool.color}-950 text-${tool.color}-400 flex items-center justify-center text-sm border border-${tool.color}-500/20">
                        <i class="fa-solid ${tool.icon}"></i>
                    </div>
                    <div>
                        <h4 class="font-space font-bold text-sm text-white">${tool.title}</h4>
                        <p class="text-[10px] text-slate-400">${tool.desc}</p>
                    </div>
                </div>
            `;

            // Para no duplicar HTML, las herramientas genéricas se estructuran mediante esquemas limpios
            // Las herramientas sumamente complejas (como juegos, calculadoras y audio) conservan su renderizado único
            switch(tool.id) {
                // --- CATEGORÍA 1: ESTUDIOS ACADÉMICOS ---
                case 1:
                    html += `<div class="space-y-3">
                        <label class="block text-[10px] font-bold text-slate-400 uppercase tracking-wider">Concepto o tema de estudio</label>
                        <input type="text" id="tutor-topic" placeholder="Ej: Las leyes de Kepler y el movimiento orbital" class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="runTutorIA()" class="w-full bg-indigo-600 hover:bg-indigo-500 py-2.5 rounded-xl text-xs font-bold transition-all">Generar Clase Interactiva</button>
                        <div id="tutor-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 2:
                    html += `<div class="space-y-3">
                        <label class="block text-[10px] font-bold text-slate-400 uppercase tracking-wider">Materia u Objeto del Examen</label>
                        <input type="text" id="exam-topic" placeholder="Ej: Historia de la Revolución Industrial" class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="runExamIA()" class="w-full bg-indigo-600 hover:bg-indigo-500 py-2.5 rounded-xl text-xs font-bold transition-all">Generar Examen</button>
                        <div id="exam-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 3:
                    html += `<div class="space-y-3">
                        <label class="block text-[10px] font-bold text-slate-400 uppercase tracking-wider">Bloque de texto a resumir</label>
                        <textarea id="summary-text" placeholder="Pega el contenido extenso aquí..." class="w-full h-32 p-3 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none resize-none"></textarea>
                        <button onclick="runSummaryIA()" class="w-full bg-indigo-600 hover:bg-indigo-500 py-2.5 rounded-xl text-xs font-bold transition-all">Generar Resumen</button>
                        <div id="summary-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 4:
                    html += `<div class="space-y-3">
                        <label class="block text-[10px] font-bold text-slate-400 uppercase tracking-wider">Concepto de Memorización</label>
                        <input type="text" id="flash-topic" placeholder="Ej: Vocabulario de anatomía humana" class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="runFlashIA()" class="w-full bg-indigo-600 hover:bg-indigo-500 py-2.5 rounded-xl text-xs font-bold transition-all">Generar Flashcards</button>
                        <div id="flash-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 5:
                    html += `<div class="space-y-3">
                        <label class="block text-[10px] font-bold text-slate-400 uppercase tracking-wider">Tema Difícil a Simplificar</label>
                        <input type="text" id="eli5-topic" placeholder="Ej: Teoría de la Relatividad General de Einstein" class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="runEli5IA()" class="w-full bg-indigo-600 hover:bg-indigo-500 py-2.5 rounded-xl text-xs font-bold transition-all">Simplificar Tema</button>
                        <div id="eli5-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 6:
                    html += `<div class="space-y-3">
                        <input type="text" id="translate-lang" placeholder="Idioma destino (Ej: Alemán)" class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <textarea id="translate-input" placeholder="Texto a traducir..." class="w-full h-24 p-3 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none resize-none"></textarea>
                        <button onclick="runTranslateIA()" class="w-full bg-indigo-600 hover:bg-indigo-500 py-2.5 rounded-xl text-xs font-bold transition-all">Traducir Texto</button>
                        <div id="translate-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 7:
                    html += `<div class="space-y-3">
                        <textarea id="correct-input" placeholder="Escribe tu texto con errores..." class="w-full h-24 p-3 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none resize-none"></textarea>
                        <button onclick="runCorrectIA()" class="w-full bg-indigo-600 hover:bg-indigo-500 py-2.5 rounded-xl text-xs font-bold transition-all">Mejorar Texto</button>
                        <div id="correct-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 8:
                    html += `<div class="space-y-3">
                        <input type="text" id="syn-word" placeholder="Escribe una palabra (Ej: Espectacular)" class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="runSynonymsIA()" class="w-full bg-indigo-600 hover:bg-indigo-500 py-2.5 rounded-xl text-xs font-bold transition-all">Buscar Sinónimos</button>
                        <div id="syn-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 9:
                    html += `<div class="space-y-3">
                        <input type="text" id="apa-author" placeholder="Autor(es)" class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <input type="text" id="apa-title" placeholder="Título del Libro" class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <div class="grid grid-cols-2 gap-2">
                            <input type="text" id="apa-year" placeholder="Año" class="px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                            <input type="text" id="apa-publisher" placeholder="Editorial" class="px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        </div>
                        <button onclick="runApaCitationIA()" class="w-full bg-indigo-600 hover:bg-indigo-500 py-2.5 rounded-xl text-xs font-bold transition-all">Generar Cita</button>
                        <div id="apa-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 10:
                    html += `<div class="space-y-3">
                        <div class="bg-slate-950/80 p-4 rounded-2xl border border-slate-900 text-right text-xl font-mono text-indigo-400 h-12 overflow-hidden" id="calc-screen">0</div>
                        <div class="grid grid-cols-4 gap-2 font-mono text-xs">
                            <button onclick="pressCalc('C')" class="bg-slate-900/80 p-3 rounded-xl hover:bg-slate-800 text-indigo-400">C</button>
                            <button onclick="pressCalc('(')" class="bg-slate-900/80 p-3 rounded-xl hover:bg-slate-800 text-indigo-400">(</button>
                            <button onclick="pressCalc(')')" class="bg-slate-900/80 p-3 rounded-xl hover:bg-slate-800 text-indigo-400">)</button>
                            <button onclick="pressCalc('/')" class="bg-indigo-950 p-3 rounded-xl hover:bg-indigo-900 text-white">/</button>
                            <button onclick="pressCalc('7')" class="bg-slate-900/50 p-3 rounded-xl hover:bg-slate-800 text-slate-300">7</button>
                            <button onclick="pressCalc('8')" class="bg-slate-900/50 p-3 rounded-xl hover:bg-slate-800 text-slate-300">8</button>
                            <button onclick="pressCalc('9')" class="bg-slate-900/50 p-3 rounded-xl hover:bg-slate-800 text-slate-300">9</button>
                            <button onclick="pressCalc('*')" class="bg-indigo-950 p-3 rounded-xl hover:bg-indigo-900 text-white">*</button>
                            <button onclick="pressCalc('4')" class="bg-slate-900/50 p-3 rounded-xl hover:bg-slate-800 text-slate-300">4</button>
                            <button onclick="pressCalc('5')" class="bg-slate-900/50 p-3 rounded-xl hover:bg-slate-800 text-slate-300">5</button>
                            <button onclick="pressCalc('6')" class="bg-slate-900/50 p-3 rounded-xl hover:bg-slate-800 text-slate-300">6</button>
                            <button onclick="pressCalc('-')" class="bg-indigo-950 p-3 rounded-xl hover:bg-indigo-900 text-white">-</button>
                            <button onclick="pressCalc('1')" class="bg-slate-900/50 p-3 rounded-xl hover:bg-slate-800 text-slate-300">1</button>
                            <button onclick="pressCalc('2')" class="bg-slate-900/50 p-3 rounded-xl hover:bg-slate-800 text-slate-300">2</button>
                            <button onclick="pressCalc('3')" class="bg-slate-900/50 p-3 rounded-xl hover:bg-slate-800 text-slate-300">3</button>
                            <button onclick="pressCalc('+')" class="bg-indigo-950 p-3 rounded-xl hover:bg-indigo-900 text-white">+</button>
                            <button onclick="pressCalc('0')" class="bg-slate-900/50 p-3 rounded-xl hover:bg-slate-800 text-slate-300 col-span-2">0</button>
                            <button onclick="pressCalc('.')" class="bg-slate-900/50 p-3 rounded-xl hover:bg-slate-800 text-slate-300">.</button>
                            <button onclick="pressCalc('=')" class="bg-emerald-600 p-3 rounded-xl hover:bg-emerald-500 text-slate-950 font-bold">=</button>
                        </div>
                    </div>`;
                    break;

                // --- CATEGORÍA 2: DESARROLLO & TECH ---
                case 11:
                    html += `<div class="space-y-3 font-mono text-xs">
                        <textarea id="debug-code" placeholder="Pega tu código con errores aquí..." class="w-full h-32 p-3 rounded-xl bg-slate-900/80 border border-slate-800 text-emerald-400 focus:outline-none resize-none"></textarea>
                        <button onclick="runDebuggerIA()" class="w-full bg-purple-600 hover:bg-purple-500 py-2.5 rounded-xl font-bold transition-all text-white font-sans">Analizar Código</button>
                        <div id="debug-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden overflow-x-auto"></div>
                    </div>`;
                    break;
                case 12:
                    html += `<div class="space-y-3 text-xs font-mono">
                        <div class="grid grid-cols-2 gap-2 font-sans">
                            <input type="text" id="code-from" placeholder="Desde (Ej: JavaScript)" class="px-3 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                            <input type="text" id="code-to" placeholder="Hacia (Ej: Python)" class="px-3 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        </div>
                        <textarea id="converter-code" placeholder="Pega tu función a convertir..." class="w-full h-24 p-3 rounded-xl bg-slate-900/80 border border-slate-800 text-emerald-400 focus:outline-none resize-none"></textarea>
                        <button onclick="runCodeConverterIA()" class="w-full bg-purple-600 hover:bg-purple-500 py-2.5 rounded-xl font-bold transition-all text-white font-sans">Convertir</button>
                        <div id="converter-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden overflow-x-auto"></div>
                    </div>`;
                    break;
                case 13:
                    html += `<div class="space-y-3 text-xs">
                        <input type="text" id="regex-pattern" placeholder="Expresión Regular (Ej: ^[a-zA-Z]+$)" class="w-full px-3 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-white font-mono focus:outline-none">
                        <input type="text" id="regex-string" placeholder="Texto de prueba" class="w-full px-3 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="testRegexLocal()" class="w-full bg-purple-600 hover:bg-purple-500 py-2.5 rounded-xl font-bold transition-all">Probar Expresión</button>
                        <div id="regex-output" class="p-3 rounded-xl bg-slate-950 border border-slate-900 hidden font-mono"></div>
                    </div>`;
                    break;
                case 14:
                    html += `<div class="space-y-3 text-xs">
                        <textarea id="json-input" placeholder="Pega tu estructura JSON rota..." class="w-full h-24 p-3 rounded-xl bg-slate-900/80 border border-slate-800 text-emerald-400 font-mono focus:outline-none resize-none"></textarea>
                        <button onclick="beautifyJsonLocal()" class="w-full bg-purple-600 hover:bg-purple-500 py-2.5 rounded-xl font-bold transition-all">Formatear JSON</button>
                        <div id="json-output" class="p-3 rounded-xl bg-slate-950 border border-slate-900 hidden font-mono overflow-x-auto whitespace-pre"></div>
                    </div>`;
                    break;
                case 15:
                    html += `<div class="space-y-3">
                        <textarea id="sql-prompt" placeholder="Ej: Selecciona todos los usuarios mayores de 18 años ordenados por fecha de creación" class="w-full h-20 p-3 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none resize-none"></textarea>
                        <button onclick="runSqlGenIA()" class="w-full bg-purple-600 hover:bg-purple-500 py-2.5 rounded-xl text-xs font-bold transition-all">Generar Query SQL</button>
                        <div id="sql-output" class="text-xs text-slate-300 font-mono bg-slate-950/60 p-4 rounded-xl border border-slate-900 hidden overflow-x-auto"></div>
                    </div>`;
                    break;
                case 16:
                    html += `<div class="space-y-3 text-xs">
                        <textarea id="markdown-input" onkeyup="renderMarkdownLocal()" placeholder="# Título\\n\\nEscribe en **negrita**..." class="w-full h-28 p-3 rounded-xl bg-slate-900/80 border border-slate-800 text-white font-mono focus:outline-none resize-none"></textarea>
                        <div id="markdown-output" class="p-4 rounded-xl bg-slate-950 border border-slate-900 min-h-[80px] prose prose-invert"></div>
                    </div>`;
                    break;
                case 17:
                    html += `<div class="space-y-3 text-xs">
                        <textarea id="base64-input" placeholder="Texto a procesar..." class="w-full h-20 p-3 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none resize-none"></textarea>
                        <div class="grid grid-cols-2 gap-2">
                            <button onclick="runBase64Local('encode')" class="bg-slate-900 hover:bg-slate-800 p-2 rounded-xl text-purple-400 font-bold border border-slate-800">Codificar</button>
                            <button onclick="runBase64Local('decode')" class="bg-slate-900 hover:bg-slate-800 p-2 rounded-xl text-emerald-400 font-bold border border-slate-800">Decodificar</button>
                        </div>
                        <div id="base64-output" class="p-3 rounded-xl bg-slate-950 border border-slate-900 hidden font-mono"></div>
                    </div>`;
                    break;
                case 18:
                    html += `<div class="space-y-3">
                        <textarea id="vuln-code" placeholder="Pega tu bloque de código sensible..." class="w-full h-24 p-3 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-emerald-400 font-mono focus:outline-none resize-none"></textarea>
                        <button onclick="runVulnAnalysisIA()" class="w-full bg-purple-600 hover:bg-purple-500 py-2.5 rounded-xl text-xs font-bold transition-all">Evaluar Ciberseguridad</button>
                        <div id="vuln-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 19:
                    html += `<div class="space-y-3 text-xs font-sans">
                        <div class="grid grid-cols-2 gap-2">
                            <select id="dummy-type" class="px-3 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-slate-300 focus:outline-none">
                                <option value="usuarios">Usuarios Falsos</option>
                                <option value="productos">Catálogo de Productos</option>
                            </select>
                            <input type="number" id="dummy-count" value="5" min="1" max="50" class="px-3 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        </div>
                        <button onclick="generateDummyDataLocal()" class="w-full bg-purple-600 hover:bg-purple-500 py-2.5 rounded-xl font-bold transition-all">Generar Base de Datos</button>
                        <div id="dummy-output" class="p-3 rounded-xl bg-slate-950 border border-slate-900 hidden font-mono overflow-x-auto whitespace-pre"></div>
                    </div>`;
                    break;
                case 20:
                    html += `<div class="space-y-3 font-mono text-xs">
                        <textarea id="bigo-code" placeholder="Pega tu algoritmo..." class="w-full h-24 p-3 rounded-xl bg-slate-900/80 border border-slate-800 text-emerald-400 focus:outline-none resize-none"></textarea>
                        <button onclick="runBigOAnalysisIA()" class="w-full bg-purple-600 hover:bg-purple-500 py-2.5 rounded-xl font-bold transition-all text-white font-sans">Calcular Complejidad</button>
                        <div id="bigo-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;

                // --- CATEGORÍA 3: SALUD & BIENESTAR ---
                case 21:
                    html += `<div class="space-y-3">
                        <input type="text" id="diet-ingredients" placeholder="Ingredientes disponibles (Ej: Salmón, Brócoli, Patatas)" class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="runDietIA()" class="w-full bg-emerald-600 hover:bg-emerald-500 py-2.5 rounded-xl text-xs font-bold transition-all text-slate-950">Estructurar Menú</button>
                        <div id="diet-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 22:
                    html += `<div class="space-y-3 text-xs">
                        <select id="workout-target" class="w-full px-3 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-slate-300 focus:outline-none">
                            <option value="Aumento de masa muscular">Hipertrofia Muscular</option>
                            <option value="Pérdida de grasa corporal">Cardio / Definición</option>
                        </select>
                        <button onclick="runWorkoutIA()" class="w-full bg-emerald-600 hover:bg-emerald-500 py-2.5 rounded-xl font-bold transition-all text-slate-950">Generar Rutina</button>
                        <div id="workout-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 23:
                    html += `<div class="space-y-3 text-xs">
                        <div class="grid grid-cols-2 gap-2">
                            <input type="text" id="calorie-food" placeholder="Alimento (Ej: Manzana)" class="px-3 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                            <input type="number" id="calorie-count" placeholder="Calorías" class="px-3 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        </div>
                        <button onclick="addCaloriesLocal()" class="w-full bg-emerald-600 hover:bg-emerald-500 py-2 rounded-xl font-bold text-slate-950">Registrar Alimento</button>
                        <div id="calories-log-container" class="bg-slate-950/60 p-3 rounded-xl border border-slate-900 space-y-1.5 min-h-[60px]">
                            <p class="text-[10px] text-slate-500 text-center">Sin alimentos registrados.</p>
                        </div>
                    </div>`;
                    break;
                case 24:
                    html += `<div class="space-y-3 text-xs">
                        <div class="grid grid-cols-2 gap-2">
                            <input type="number" id="imc-height" placeholder="Altura en cm (Ej: 175)" class="px-3 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                            <input type="number" id="imc-weight" placeholder="Peso en kg (Ej: 70)" class="px-3 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        </div>
                        <button onclick="calculateImcLocal()" class="w-full bg-emerald-600 hover:bg-emerald-500 py-2.5 rounded-xl font-bold text-slate-950">Calcular IMC</button>
                        <div id="imc-output" class="p-3 rounded-xl bg-slate-950/60 border border-slate-900 text-center text-sm font-bold text-emerald-400 hidden"></div>
                    </div>`;
                    break;
                case 25:
                    html += `<div class="space-y-4 text-center">
                        <div class="text-3xl font-mono font-bold text-blue-400" id="water-logged">0 ml</div>
                        <div class="flex justify-center gap-3">
                            <button onclick="logWaterLocal(250)" class="bg-slate-900/80 hover:bg-slate-800 p-3 rounded-2xl border border-slate-800 text-xs font-semibold text-blue-300">+250 ml</button>
                            <button onclick="logWaterLocal(500)" class="bg-slate-900/80 hover:bg-slate-800 p-3 rounded-2xl border border-slate-800 text-xs font-semibold text-blue-300">+500 ml</button>
                            <button onclick="resetWaterLocal()" class="bg-slate-900/80 hover:bg-slate-800 p-3 rounded-2xl border border-slate-800 text-xs font-semibold text-rose-400">Limpiar</button>
                        </div>
                    </div>`;
                    break;
                case 26:
                    html += `<div class="space-y-3">
                        <input type="text" id="flex-muscles" placeholder="Ej: Espalda baja y hombros" class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="runFlexIA()" class="w-full bg-emerald-600 hover:bg-emerald-500 py-2.5 rounded-xl text-xs font-bold transition-all text-slate-950">Generar Plan</button>
                        <div id="flex-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 27:
                    html += `<div class="space-y-3">
                        <input type="text" id="meditation-mood" placeholder="Estrés actual" class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="runMeditationIA()" class="w-full bg-emerald-600 hover:bg-emerald-500 py-2.5 rounded-xl text-xs font-bold transition-all text-slate-950">Guía de Respiración</button>
                        <div id="meditation-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 28:
                    html += `<div class="space-y-3">
                        <textarea id="coherence-input" placeholder="Cuéntale a la IA cómo estuvo tu día..." class="w-full h-24 p-3 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none resize-none"></textarea>
                        <button onclick="runCoherenceIA()" class="w-full bg-emerald-600 hover:bg-emerald-500 py-2.5 rounded-xl text-xs font-bold transition-all text-slate-950">Analizar Coherencia</button>
                        <div id="coherence-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 29:
                    html += `<div class="space-y-3 text-xs">
                        <div class="flex gap-2">
                            <input type="text" id="habit-name" placeholder="Nuevo Hábito (Ej: Leer 15 mins)" class="flex-grow px-3 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                            <button onclick="addHabitLocal()" class="bg-emerald-600 hover:bg-emerald-500 px-4 rounded-xl text-slate-950 font-bold">Agregar</button>
                        </div>
                        <div id="habits-list-container" class="space-y-1.5 bg-slate-950/60 p-3 rounded-xl border border-slate-900 min-h-[60px]"></div>
                    </div>`;
                    break;
                case 30:
                    html += `<div class="space-y-3 text-xs text-center">
                        <button onclick="calculateSleepCyclesLocal()" class="bg-emerald-600 hover:bg-emerald-500 px-4 py-2 rounded-xl text-slate-950 font-bold">Calcular Ciclos de Sueño</button>
                        <div id="sleep-output" class="p-3 rounded-xl bg-slate-950/60 border border-slate-900 hidden grid grid-cols-2 gap-2 text-[10px] font-mono"></div>
                    </div>`;
                    break;

                // --- CATEGORÍA 4: GESTIÓN & FINANZAS ---
                case 31:
                    html += `<div class="space-y-3 text-xs">
                        <div class="grid grid-cols-2 gap-2">
                            <input type="text" id="eisen-task" placeholder="Compromiso/Tarea" class="px-3 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                            <select id="eisen-quad" class="px-3 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-slate-300 focus:outline-none">
                                <option value="q1">Q1: Hacer Ya</option>
                                <option value="q2">Q2: Planificar</option>
                            </select>
                        </div>
                        <button onclick="addEisenTaskLocal()" class="w-full bg-amber-600 hover:bg-amber-500 py-2.5 rounded-xl font-bold text-slate-950">Clasificar Tarea</button>
                        <div id="eisen-log-container" class="grid grid-cols-2 gap-2 bg-slate-950/60 p-3 rounded-xl border border-slate-900 min-h-[100px] text-[9px] text-slate-400">
                            <div class="bg-red-950/20 p-2 rounded-lg border border-red-500/10"><strong>Q1</strong><ul id="eisen-list-q1" class="list-disc pl-3 mt-1 space-y-0.5"></ul></div>
                            <div class="bg-indigo-950/20 p-2 rounded-lg border border-indigo-500/10"><strong>Q2</strong><ul id="eisen-list-q2" class="list-disc pl-3 mt-1 space-y-0.5"></ul></div>
                        </div>
                    </div>`;
                    break;
                case 32:
                    html += `<div class="space-y-3">
                        <input type="text" id="wbs-goal" placeholder="Lanzamiento de eCommerce..." class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="runWbsIA()" class="w-full bg-amber-600 hover:bg-amber-500 py-2.5 rounded-xl text-xs font-bold transition-all text-slate-950">Desglosar Proyecto (WBS)</button>
                        <div id="wbs-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 33:
                    html += `<div class="space-y-3 text-xs">
                        <input type="text" id="writing-topic" placeholder="Asunto o tema central..." class="w-full px-3 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="runWritingIA()" class="w-full bg-amber-600 hover:bg-amber-500 py-2.5 rounded-xl font-bold text-slate-950">Escribir Documento</button>
                        <div id="writing-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 34:
                    html += `<div class="space-y-3">
                        <input type="text" id="project-scope" placeholder="Aplicación móvil..." class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="runProjectTimelineIA()" class="w-full bg-amber-600 hover:bg-amber-500 py-2.5 rounded-xl text-xs font-bold transition-all text-slate-950">Crear Cronograma</button>
                        <div id="project-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 35:
                    html += `<div class="space-y-3 text-xs">
                        <div class="grid grid-cols-3 gap-2">
                            <input type="number" id="compound-cap" placeholder="Capital" class="px-2.5 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                            <input type="number" id="compound-rate" placeholder="Tasa %" class="px-2.5 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                            <input type="number" id="compound-years" placeholder="Años" class="px-2.5 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        </div>
                        <button onclick="calculateCompoundInterestLocal()" class="w-full bg-amber-600 hover:bg-amber-500 py-2.5 rounded-xl font-bold text-slate-950">Simular Inversión</button>
                        <div id="compound-output" class="p-3 rounded-xl bg-slate-950/60 border border-slate-900 text-center text-sm font-bold text-amber-400 hidden"></div>
                    </div>`;
                    break;
                case 36:
                    html += `<div class="space-y-3 text-xs">
                        <div class="grid grid-cols-3 gap-2">
                            <input type="text" id="budget-desc" placeholder="Concepto" class="px-2.5 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                            <input type="number" id="budget-amount" placeholder="Monto" class="px-2.5 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                            <select id="budget-type" class="px-2.5 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-slate-300 focus:outline-none">
                                <option value="ingreso">Ingreso</option>
                                <option value="egreso">Egreso</option>
                            </select>
                        </div>
                        <button onclick="addBudgetItemLocal()" class="w-full bg-amber-600 hover:bg-amber-500 py-2 rounded-xl font-bold text-slate-950">Registrar</button>
                        <div id="budget-log-container" class="bg-slate-950/60 p-3 rounded-xl border border-slate-900 min-h-[60px] space-y-1 text-[10px] text-slate-400"></div>
                    </div>`;
                    break;
                case 37:
                    html += `<div class="space-y-3 text-xs">
                        <div class="grid grid-cols-3 gap-2">
                            <input type="number" id="currency-amount" placeholder="Cantidad" class="px-2 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                            <select id="currency-from" class="px-2 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-slate-300 focus:outline-none">
                                <option value="USD">USD</option>
                                <option value="EUR">EUR</option>
                            </select>
                            <select id="currency-to" class="px-2 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-slate-300 focus:outline-none">
                                <option value="EUR">EUR</option>
                                <option value="USD">USD</option>
                            </select>
                        </div>
                        <button onclick="convertCurrencyLocal()" class="w-full bg-amber-600 hover:bg-amber-500 py-2.5 rounded-xl font-bold text-slate-950">Convertir</button>
                        <div id="currency-output" class="p-3 rounded-xl bg-slate-950/60 border border-slate-900 text-center text-sm font-bold text-amber-400 hidden"></div>
                    </div>`;
                    break;
                case 38:
                    html += `<div class="space-y-3 text-xs">
                        <div class="grid grid-cols-2 gap-2">
                            <input type="number" id="saving-target" placeholder="Meta" class="px-3 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                            <input type="number" id="saving-monthly" placeholder="Monto Mensual" class="px-3 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        </div>
                        <button onclick="calculateSavingTimelineLocal()" class="w-full bg-amber-600 hover:bg-amber-500 py-2.5 rounded-xl font-bold text-slate-950">Calcular Plazo</button>
                        <div id="saving-output" class="p-3 rounded-xl bg-slate-950/60 border border-slate-900 text-center text-sm font-bold text-amber-400 hidden"></div>
                    </div>`;
                    break;
                case 39:
                    html += `<div class="space-y-3 text-xs">
                        <input type="text" id="invoice-client" placeholder="Cliente" class="w-full px-3 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <div class="grid grid-cols-2 gap-2">
                            <input type="text" id="invoice-item" placeholder="Servicio" class="px-3 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                            <input type="number" id="invoice-price" placeholder="Monto" class="px-3 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        </div>
                        <button onclick="generateInvoiceLocal()" class="w-full bg-amber-600 hover:bg-amber-500 py-2.5 rounded-xl font-bold text-slate-950">Crear Factura</button>
                        <div id="invoice-output" class="p-4 rounded-xl bg-white text-slate-950 hidden space-y-2 font-mono"></div>
                    </div>`;
                    break;
                case 40:
                    html += `<div class="space-y-3">
                        <input type="text" id="interview-role" placeholder="Puesto de trabajo..." class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="runInterviewPreparationIA()" class="w-full bg-amber-600 hover:bg-amber-500 py-2.5 rounded-xl text-xs font-bold transition-all text-slate-950">Simular Cuestionario</button>
                        <div id="interview-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;

                // --- CATEGORÍA 5: CREATIVIDAD & OCIO ---
                case 41:
                    html += `<div class="space-y-3">
                        <input type="text" id="image-prompt" placeholder="Tacos al pastor gourmet..." class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="runChefImageIA()" class="w-full bg-rose-600 hover:bg-rose-500 py-2.5 rounded-xl text-xs font-bold transition-all text-white">Generar Fotografía</button>
                        <div id="chef-image-container" class="hidden relative aspect-video rounded-xl overflow-hidden border border-slate-800 bg-slate-950 mt-2">
                            <img id="chef-image-output" src="" alt="Render" class="w-full h-full object-cover">
                        </div>
                    </div>`;
                    break;
                case 42:
                    html += `<div class="space-y-3">
                        <div id="rpg-init-box" class="text-center py-6 border border-slate-800 rounded-xl space-y-2">
                            <button onclick="initRpgGameIA('Planeta Desértico')" class="bg-slate-900/80 border border-slate-800 px-3 py-1.5 rounded-lg text-[10px] text-rose-400 font-bold">Planeta Desértico</button>
                        </div>
                        <div id="rpg-story-flow" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-3 hidden max-h-60 overflow-y-auto"></div>
                        <div id="rpg-options-box" class="grid grid-cols-1 gap-1.5 hidden"></div>
                    </div>`;
                    break;
                case 43:
                    html += `<div class="space-y-3 text-center">
                        <div class="relative aspect-video w-full bg-slate-950 rounded-2xl border border-slate-800 overflow-hidden">
                            <canvas id="arcade-play-canvas" class="w-full h-full block bg-slate-950"></canvas>
                        </div>
                    </div>`;
                    setTimeout(initArcadeCanvas, 50);
                    break;
                case 44:
                    html += `<div class="space-y-3">
                        <input type="text" id="poetry-topic" placeholder="Temática poética..." class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="runPoetryIA()" class="w-full bg-rose-600 hover:bg-rose-500 py-2.5 rounded-xl text-xs font-bold transition-all text-white">Generar Poema</button>
                        <div id="poetry-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden italic"></div>
                    </div>`;
                    break;
                case 45:
                    html += `<div class="space-y-3">
                        <input type="text" id="ideas-topic" placeholder="Nicho de interés..." class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="runIdeasIA()" class="w-full bg-rose-600 hover:bg-rose-500 py-2.5 rounded-xl text-xs font-bold transition-all text-white">Generar Propuestas</button>
                        <div id="ideas-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 46:
                    html += `<div class="space-y-3">
                        <input type="text" id="joke-topic" placeholder="Concepto de broma..." class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="runJokeIA()" class="w-full bg-rose-600 hover:bg-rose-500 py-2.5 rounded-xl text-xs font-bold transition-all text-white">Crear Chiste</button>
                        <div id="joke-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 47:
                    html += `<div class="space-y-3">
                        <textarea id="twitter-topic" placeholder="Idea de hilo viral..." class="w-full h-20 p-3 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none resize-none"></textarea>
                        <button onclick="runTwitterIA()" class="w-full bg-rose-600 hover:bg-rose-500 py-2.5 rounded-xl text-xs font-bold transition-all text-white">Generar Hilo</button>
                        <div id="twitter-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 48:
                    html += `<div class="space-y-3 text-xs text-center">
                        <button onclick="generatePaletteLocal()" class="bg-rose-600 hover:bg-rose-500 px-4 py-2 rounded-xl text-white font-bold">Generar Paleta</button>
                        <div id="palette-output" class="p-3 rounded-xl bg-slate-950/60 border border-slate-900 hidden grid grid-cols-5 gap-2 text-[10px] font-mono"></div>
                    </div>`;
                    break;
                case 49:
                    html += `<div class="space-y-3">
                        <input type="text" id="story-premise" placeholder="Un reloj al revés..." class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="runCreativeStoryIA()" class="w-full bg-rose-600 hover:bg-rose-500 py-2.5 rounded-xl text-xs font-bold transition-all text-white">Redactar Micro-Historia</button>
                        <div id="story-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 50:
                    html += `<div class="space-y-3">
                        <input type="text" id="chords-prompt" placeholder="Jazz melancólico..." class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="runChordsIA()" class="w-full bg-rose-600 hover:bg-rose-500 py-2.5 rounded-xl text-xs font-bold transition-all text-white">Generar Acordes</button>
                        <div id="chords-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden font-mono"></div>
                    </div>`;
                    break;

                // --- CATEGORÍA 6: UTILIDADES DIARIAS ---
                case 51:
                    html += `<div class="space-y-3 text-xs">
                        <button onclick="generatePasswordLocal()" class="w-full bg-teal-600 hover:bg-teal-500 py-2.5 rounded-xl font-bold text-slate-950">Generar Clave</button>
                        <div id="pass-output" class="p-3 rounded-xl bg-slate-950/60 border border-slate-900 text-center font-mono text-emerald-400 hidden select-all"></div>
                    </div>`;
                    break;
                case 52:
                    html += `<div class="space-y-3 text-xs text-center">
                        <div class="text-3xl font-mono font-bold text-teal-400" id="pomodoro-timer">25:00</div>
                        <div class="flex justify-center gap-2">
                            <button onclick="startPomodoroLocal()" class="bg-slate-900/80 hover:bg-slate-800 px-3 py-1.5 rounded-xl border border-slate-800 text-teal-300">Arrancar</button>
                            <button onclick="pausePomodoroLocal()" class="bg-slate-900/80 hover:bg-slate-800 px-3 py-1.5 rounded-xl border border-slate-800 text-slate-300">Pausar</button>
                        </div>
                    </div>`;
                    break;
                case 53:
                    html += `<div class="space-y-3 text-xs">
                        <div class="grid grid-cols-2 gap-2">
                            <input type="number" id="unit-val" placeholder="Cantidad" class="px-3 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                            <select id="unit-type" class="px-3 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-slate-300 focus:outline-none">
                                <option value="kgToLb">Kg a Libras</option>
                            </select>
                        </div>
                        <button onclick="convertUnitsLocal()" class="w-full bg-teal-600 hover:bg-teal-500 py-2.5 rounded-xl font-bold text-slate-950">Convertir</button>
                        <div id="unit-output" class="p-3 rounded-xl bg-slate-950/60 border border-slate-900 text-center text-sm font-bold text-teal-400 hidden"></div>
                    </div>`;
                    break;
                case 54:
                    html += `<div class="space-y-3 text-xs text-center">
                        <input type="text" id="qr-link" placeholder="Enlace web..." class="w-full px-3 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="generateQrLocal()" class="w-full bg-teal-600 hover:bg-teal-500 py-2.5 rounded-xl font-bold text-slate-950">Crear QR</button>
                        <div id="qr-container" class="p-3 bg-white rounded-xl max-w-[150px] mx-auto hidden mt-2">
                            <img id="qr-output" src="" alt="QR" class="w-full">
                        </div>
                    </div>`;
                    break;
                case 55:
                    html += `<div class="space-y-3">
                        <textarea id="keywords-input" placeholder="Pega el contenido..." class="w-full h-24 p-3 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none resize-none"></textarea>
                        <button onclick="runKeywordsIA()" class="w-full bg-teal-600 hover:bg-teal-500 py-2.5 rounded-xl text-xs font-bold transition-all text-slate-950">Extraer Términos</button>
                        <div id="keywords-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 56:
                    html += `<div class="space-y-3">
                        <textarea id="tts-input" placeholder="Escribe el párrafo..." class="w-full h-24 p-3 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none resize-none"></textarea>
                        <button onclick="runTtsIA()" class="w-full bg-teal-600 hover:bg-teal-500 py-2.5 rounded-xl text-xs font-bold transition-all text-slate-950">Sintetizar y Escuchar</button>
                    </div>`;
                    break;
                case 57:
                    html += `<div class="space-y-3">
                        <textarea id="sentiment-input" placeholder="Mensaje del usuario..." class="w-full h-24 p-3 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none resize-none"></textarea>
                        <button onclick="runSentimentIA()" class="w-full bg-teal-600 hover:bg-teal-500 py-2.5 rounded-xl text-xs font-bold transition-all text-slate-950">Evaluar Sentimiento</button>
                        <div id="sentiment-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 58:
                    html += `<div class="space-y-3 text-xs">
                        <textarea id="raffle-list" placeholder="Pedro, Juan, Sofia..." class="w-full h-20 p-3 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none resize-none"></textarea>
                        <button onclick="runRaffleLocal()" class="w-full bg-teal-600 hover:bg-teal-500 py-2.5 rounded-xl font-bold text-slate-950">Sorteo Justo</button>
                        <div id="raffle-output" class="p-3 rounded-xl bg-slate-950/60 border border-slate-900 text-center text-sm font-bold text-teal-400 hidden"></div>
                    </div>`;
                    break;
                case 59:
                    html += `<div class="space-y-3 text-xs text-center">
                        <button onclick="compareTimesLocal()" class="bg-teal-600 hover:bg-teal-500 px-4 py-2 rounded-xl text-slate-950 font-bold">Ver Comparación Horaria</button>
                        <div id="timezone-output" class="p-3 rounded-xl bg-slate-950/60 border border-slate-900 hidden grid grid-cols-2 gap-2 text-[10px] font-mono"></div>
                    </div>`;
                    break;
                case 60:
                    html += `<div class="space-y-3 text-xs">
                        <div class="flex gap-2">
                            <input type="text" id="cart-item" placeholder="Artículo por comprar" class="flex-grow px-3 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                            <button onclick="addCartItemLocal()" class="bg-teal-600 hover:bg-teal-500 px-4 rounded-xl text-slate-950 font-bold">Añadir</button>
                        </div>
                        <div id="cart-list-container" class="space-y-1.5 bg-slate-950/60 p-3 rounded-xl border border-slate-900 min-h-[60px]"></div>
                    </div>`;
                    break;

                // --- CATEGORÍA 7: MARKETING & REDES ---
                case 61:
                    html += `<div class="space-y-3">
                        <input type="text" id="mkt-product" placeholder="Nombre de tu producto" class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="runMktCopyIA()" class="w-full bg-sky-600 hover:bg-sky-500 py-2.5 rounded-xl text-xs font-bold transition-all text-white">Escribir Copys Publicitarios</button>
                        <div id="mkt-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 62:
                    html += `<div class="space-y-3">
                        <input type="text" id="mkt-niche" placeholder="Temática de tu marca" class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="runMktHashtagsIA()" class="w-full bg-sky-600 hover:bg-sky-500 py-2.5 rounded-xl text-xs font-bold transition-all text-white">Generar Hashtags</button>
                        <div id="hashtags-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 63:
                    html += `<div class="space-y-3">
                        <input type="text" id="seo-keyword" placeholder="Palabra clave principal" class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="runSeoMetaIA()" class="w-full bg-sky-600 hover:bg-sky-500 py-2.5 rounded-xl text-xs font-bold transition-all text-white">Optimizar Metatags SEO</button>
                        <div id="seo-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden font-mono"></div>
                    </div>`;
                    break;
                case 64:
                    html += `<div class="space-y-3">
                        <input type="text" id="ig-topic" placeholder="Temática o nicho de mercado" class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="runIgIdeasIA()" class="w-full bg-sky-600 hover:bg-sky-500 py-2.5 rounded-xl text-xs font-bold transition-all text-white">Generar Ideas para IG</button>
                        <div id="ig-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 65:
                    html += `<div class="space-y-3">
                        <input type="text" id="tt-hook" placeholder="Ej: 3 trucos para aprender rápido" class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="runTikTokScriptIA()" class="w-full bg-sky-600 hover:bg-sky-500 py-2.5 rounded-xl text-xs font-bold transition-all text-white">Escribir Guión Viral</button>
                        <div id="tt-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 66:
                    html += `<div class="space-y-3">
                        <input type="text" id="nl-campaign" placeholder="Temática del boletín semanal" class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="runNewsletterIA()" class="w-full bg-sky-600 hover:bg-sky-500 py-2.5 rounded-xl text-xs font-bold transition-all text-white">Escribir Boletín</button>
                        <div id="nl-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 67:
                    html += `<div class="space-y-3">
                        <input type="text" id="slogan-desc" placeholder="Descripción de tu negocio o producto" class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="runSlogansIA()" class="w-full bg-sky-600 hover:bg-sky-500 py-2.5 rounded-xl text-xs font-bold transition-all text-white">Generar Slogans</button>
                        <div id="slogans-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 68:
                    html += `<div class="space-y-3">
                        <textarea id="landing-text" placeholder="Pega el contenido o estructura de tu página aquí..." class="w-full h-24 p-3 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none resize-none"></textarea>
                        <button onclick="runLandingAnalysisIA()" class="w-full bg-sky-600 hover:bg-sky-500 py-2.5 rounded-xl text-xs font-bold transition-all text-white">Analizar Conversión</button>
                        <div id="landing-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 69:
                    html += `<div class="space-y-3">
                        <input type="text" id="qa-topic" placeholder="Temática de tu cuenta" class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="runStoryQuestionsIA()" class="w-full bg-sky-600 hover:bg-sky-500 py-2.5 rounded-xl text-xs font-bold transition-all text-white">Generar Preguntas</button>
                        <div id="qa-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 70:
                    html += `<div class="space-y-3 text-xs">
                        <div class="grid grid-cols-2 gap-2">
                            <input type="number" id="roi-spend" placeholder="Inversión Publicitaria" class="px-3 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                            <input type="number" id="roi-rev" placeholder="Retorno o Venta" class="px-3 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        </div>
                        <button onclick="calculateRoiLocal()" class="w-full bg-sky-600 hover:bg-sky-500 py-2.5 rounded-xl font-bold text-white">Calcular ROI</button>
                        <div id="roi-output" class="p-3 rounded-xl bg-slate-950/60 border border-slate-900 text-center text-sm font-bold text-sky-400 hidden"></div>
                    </div>`;
                    break;

                // --- CATEGORÍA 8: ESTILO DE VIDA & VIAJES ---
                case 71:
                    html += `<div class="space-y-3">
                        <input type="text" id="trip-dest" placeholder="Destino (Ej: París)" class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="runTripPlannerIA()" class="w-full bg-lime-600 hover:bg-lime-500 py-2.5 rounded-xl text-xs font-bold transition-all text-slate-950">Planificar Viaje</button>
                        <div id="trip-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 72:
                    html += `<div class="space-y-3">
                        <input type="text" id="pack-dest" placeholder="Destino y clima" class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="runPackBuilderIA()" class="w-full bg-lime-600 hover:bg-lime-500 py-2.5 rounded-xl text-xs font-bold transition-all text-slate-950">Crear Equipaje</button>
                        <div id="pack-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 73:
                    html += `<div class="space-y-3">
                        <input type="text" id="habit-loop-name" placeholder="Ej: Hacer ejercicio diario" class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="runHabit66IA()" class="w-full bg-lime-600 hover:bg-lime-500 py-2.5 rounded-xl text-xs font-bold transition-all text-slate-950">Crear Ciclo de Hábito</button>
                        <div id="habit-loop-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 74:
                    html += `<div class="space-y-3 text-xs">
                        <div class="grid grid-cols-2 gap-2">
                            <input type="number" id="read-total" placeholder="Total de páginas" class="px-3 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                            <input type="number" id="read-days" placeholder="Días meta" class="px-3 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        </div>
                        <button onclick="calculateReadingPlanLocal()" class="w-full bg-lime-600 hover:bg-lime-500 py-2.5 rounded-xl font-bold text-slate-950">Calcular Páginas</button>
                        <div id="read-output" class="p-3 rounded-xl bg-slate-950/60 border border-slate-900 text-center text-sm font-bold text-lime-400 hidden"></div>
                    </div>`;
                    break;
                case 75:
                    html += `<div class="space-y-3 text-xs">
                        <input type="number" id="fin-income" placeholder="Monto total mensual" class="w-full px-3 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="calculateFinances503020Local()" class="w-full bg-lime-600 hover:bg-lime-500 py-2.5 rounded-xl font-bold text-slate-950">Calcular Presupuesto</button>
                        <div id="fin-output" class="p-3 rounded-xl bg-slate-950/60 border border-slate-900 hidden space-y-1.5 text-center text-xs"></div>
                    </div>`;
                    break;
                case 76:
                    html += `<div class="space-y-3">
                        <input type="text" id="lang-target" placeholder="Idioma meta (Ej: Japonés)" class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="runSurvivalLangIA()" class="w-full bg-lime-600 hover:bg-lime-500 py-2.5 rounded-xl text-xs font-bold transition-all text-slate-950">Generar Frases Clave</button>
                        <div id="lang-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden font-mono"></div>
                    </div>`;
                    break;
                case 77:
                    html += `<div class="space-y-3">
                        <input type="text" id="cafe-city" placeholder="Ciudad de búsqueda" class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="runCafeSearchIA()" class="w-full bg-lime-600 hover:bg-lime-500 py-2.5 rounded-xl text-xs font-bold transition-all text-slate-950">Buscar Cafeterías</button>
                        <div id="cafe-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 78:
                    html += `<div class="space-y-3">
                        <input type="text" id="morning-goal" placeholder="Objetivo de productividad" class="w-full px-3 py-2 text-xs rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none">
                        <button onclick="runMorningRoutineIA()" class="w-full bg-lime-600 hover:bg-lime-500 py-2.5 rounded-xl text-xs font-bold transition-all text-slate-950">Generar Rutina</button>
                        <div id="morning-output" class="text-xs text-slate-300 leading-relaxed bg-slate-950/60 p-4 rounded-xl border border-slate-900 space-y-2 hidden"></div>
                    </div>`;
                    break;
                case 79:
                    html += `<div class="space-y-3 text-xs">
                        <textarea id="gratitude-text" placeholder="Escribe tres cosas por las que agradeces hoy..." class="w-full h-20 p-3 rounded-xl bg-slate-900/80 border border-slate-800 text-white focus:outline-none resize-none"></textarea>
                        <button onclick="saveGratitudeLocal()" class="w-full bg-lime-600 hover:bg-lime-500 py-2 rounded-xl font-bold text-slate-950">Guardar Agradecimiento</button>
                        <div id="gratitude-log-container" class="bg-slate-950/60 p-3 rounded-xl border border-slate-900 min-h-[60px] space-y-1 text-[10px] text-slate-400"></div>
                    </div>`;
                    break;
                case 80:
                    html += `<div class="space-y-3 text-xs text-center">
                        <select id="tea-type" class="w-full px-3 py-2 rounded-xl bg-slate-900/80 border border-slate-800 text-slate-300 focus:outline-none">
                            <option value="Té Verde (3 minutos)">Té Verde (3 minutos)</option>
                            <option value="Manzanilla (5 minutos)">Manzanilla (5 minutos)</option>
                        </select>
                        <button onclick="startTeaTimerLocal()" class="bg-lime-600 hover:bg-lime-500 px-4 py-2 rounded-xl text-slate-950 font-bold">Iniciar Temporizador</button>
                        <div id="tea-timer-output" class="text-xl font-mono font-bold text-lime-400 mt-2"></div>
                    </div>`;
                    break;
            }

            container.innerHTML = html;
        }

        // ==========================================
        //  IMPLEMENTACIÓN LÓGICA DE LAS HERRAMIENTAS
        // ==========================================

        // Helper genérico para conectarse a Gemini
        async function fetchGemini(systemPrompt, userQuery) {
            const apiKey = getAPIKey();
            const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-3-flash-preview:generateContent?key=${apiKey}`;

            const response = await fetchWithRetry(apiUrl, {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify({
                    contents: [{ parts: [{ text: userQuery }] }],
                    systemInstruction: { parts: [{ text: systemPrompt }] }
                })
            });

            const result = await response.json();
            return result.candidates?.[0]?.content?.parts?.[0]?.text;
        }

        async function fetchWithRetry(url, options, retries = 3, delayMs = 1500) {
            try {
                const response = await fetch(url, options);
                if (!response.ok) {
                    if (response.status === 429 && retries > 0) {
                        await delay(delayMs);
                        return fetchWithRetry(url, options, retries - 1, delayMs * 2);
                    }
                    throw new Error(`HTTP error! status: ${response.status}`);
                }
                return response;
            } catch (error) {
                if (retries > 0) {
                    await delay(delayMs);
                    return fetchWithRetry(url, options, retries - 1, delayMs * 2);
                }
                throw error;
            }
        }

        function delay(ms) {
            return new Promise(resolve => setTimeout(resolve, ms));
        }

        function triggerToast(title, desc, type = "success") {
            const toast = document.getElementById('suite-toast');
            document.getElementById('toast-title-text').innerText = title;
            document.getElementById('toast-desc-text').innerText = desc;

            const icon = document.getElementById('toast-icon');
            if (type === 'success') {
                playInterfaceClick('success');
                icon.className = "bg-emerald-950 text-emerald-400 p-2 rounded-xl border border-emerald-500/20";
                icon.innerHTML = `<i class="fa-solid fa-circle-check"></i>`;
            } else {
                icon.className = "bg-red-950 text-red-400 p-2 rounded-xl border border-red-500/20";
                icon.innerHTML = `<i class="fa-solid fa-triangle-exclamation"></i>`;
            }

            toast.classList.remove('hidden');
            setTimeout(() => {
                toast.classList.add('hidden');
            }, 5000);
        }

        // --- HANDLERS: CATEGORÍA 1 (ESTUDIOS) ---
        async function runTutorIA() {
            const topic = document.getElementById('tutor-topic').value.trim();
            if (!topic) return;
            toggleWorkspaceLoader(true, "Analizando temática académica...");
            try {
                const result = await fetchGemini("Explicación paso a paso de nivel universitario.", `Explica: "${topic}"`);
                const out = document.getElementById('tutor-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error de Conexión", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function runExamIA() {
            const topic = document.getElementById('exam-topic').value.trim();
            if (!topic) return;
            toggleWorkspaceLoader(true, "Generando cuestionario...");
            try {
                const result = await fetchGemini("Diseña un cuestionario de 3 preguntas de opción múltiple.", `Examen sobre: "${topic}"`);
                const out = document.getElementById('exam-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function runSummaryIA() {
            const text = document.getElementById('summary-text').value.trim();
            if (!text) return;
            toggleWorkspaceLoader(true, "Sintetizando ideas...");
            try {
                const result = await fetchGemini("Extrae 3 ideas principales de forma breve.", `Texto:\n\n${text}`);
                const out = document.getElementById('summary-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function runFlashIA() {
            const topic = document.getElementById('flash-topic').value.trim();
            if (!topic) return;
            toggleWorkspaceLoader(true, "Creando flashcards...");
            try {
                const result = await fetchGemini("Genera 3 tarjetas de memorización Pregunta/Respuesta.", `Concepto: "${topic}"`);
                const out = document.getElementById('flash-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function runEli5IA() {
            const topic = document.getElementById('eli5-topic').value.trim();
            if (!topic) return;
            toggleWorkspaceLoader(true, "Simplificando concepto...");
            try {
                const result = await fetchGemini("Explica de forma muy sencilla como si le hablaras a un niño de 5 años.", `Simplifica: "${topic}"`);
                const out = document.getElementById('eli5-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function runTranslateIA() {
            const text = document.getElementById('translate-input').value.trim();
            const lang = document.getElementById('translate-lang').value.trim() || 'Inglés';
            if (!text) return;
            toggleWorkspaceLoader(true, "Traduciendo lingüística...");
            try {
                const result = await fetchGemini(`Traduce fielmente al idioma: ${lang}`, `Texto:\n\n${text}`);
                const out = document.getElementById('translate-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function runCorrectIA() {
            const text = document.getElementById('correct-input').value.trim();
            if (!text) return;
            toggleWorkspaceLoader(true, "Mejorando gramática...");
            try {
                const result = await fetchGemini("Corrige ortografía y estilo.", `Texto:\n\n${text}`);
                const out = document.getElementById('correct-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function runSynonymsIA() {
            const word = document.getElementById('syn-word').value.trim();
            if (!word) return;
            toggleWorkspaceLoader(true, "Buscando alternativas...");
            try {
                const result = await fetchGemini("Genera una lista de sinónimos con ejemplos de uso.", `Palabra: "${word}"`);
                const out = document.getElementById('syn-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function runApaCitationIA() {
            const author = document.getElementById('apa-author').value.trim();
            const title = document.getElementById('apa-title').value.trim();
            const year = document.getElementById('apa-year').value.trim() || 's.f.';
            const publisher = document.getElementById('apa-publisher').value.trim() || 's.e.';
            if (!author || !title) return;
            toggleWorkspaceLoader(true, "Estructurando cita...");
            try {
                const result = await fetchGemini("Genera la citación en formato normas APA.", `Autor: ${author}, Título: ${title}, Año: ${year}, Editorial: ${publisher}`);
                const out = document.getElementById('apa-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        // Calculadora Científica Local
        let calcVal = '';
        function pressCalc(char) {
            const screen = document.getElementById('calc-screen');
            if (char === 'C') {
                calcVal = '';
                screen.innerText = '0';
            } else if (char === '=') {
                try {
                    calcVal = eval(calcVal).toString();
                    screen.innerText = calcVal;
                } catch (e) {
                    screen.innerText = 'Error';
                    calcVal = '';
                }
            } else {
                calcVal += char;
                screen.innerText = calcVal;
            }
        }

        // --- HANDLERS: CATEGORÍA 2 (DESARROLLO) ---
        async function runDebuggerIA() {
            const code = document.getElementById('debug-code').value.trim();
            if (!code) return;
            toggleWorkspaceLoader(true, "Analizando sintaxis...");
            try {
                const result = await fetchGemini("Encuentra errores de sintaxis y lógica en el código.", `Código:\n\n${code}`);
                const out = document.getElementById('debug-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function runCodeConverterIA() {
            const code = document.getElementById('converter-code').value.trim();
            const from = document.getElementById('code-from').value.trim() || 'Automático';
            const to = document.getElementById('code-to').value.trim() || 'JavaScript';
            if (!code) return;
            toggleWorkspaceLoader(true, "Traduciendo lógica...");
            try {
                const result = await fetchGemini(`Traduce este código de ${from} a ${to}`, `Código:\n\n${code}`);
                const out = document.getElementById('converter-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        function testRegexLocal() {
            const pat = document.getElementById('regex-pattern').value;
            const str = document.getElementById('regex-string').value;
            const out = document.getElementById('regex-output');
            out.classList.remove('hidden');
            try {
                const regex = new RegExp(pat);
                const matches = regex.test(str);
                out.innerHTML = matches ? '<span class="text-emerald-400">¡Coincide correctamente!</span>' : '<span class="text-rose-500">No coincide.</span>';
            } catch (e) {
                out.innerHTML = '<span class="text-rose-500">Expresión Regular Inválida</span>';
            }
        }

        function beautifyJsonLocal() {
            const input = document.getElementById('json-input').value;
            const out = document.getElementById('json-output');
            out.classList.remove('hidden');
            try {
                const parsed = JSON.parse(input);
                out.innerText = JSON.stringify(parsed, null, 4);
                out.className = "p-3 rounded-xl bg-slate-950 border border-slate-900 font-mono text-emerald-400 overflow-x-auto whitespace-pre";
            } catch (e) {
                out.innerText = "Error: El contenido provisto no es una estructura JSON válida.";
                out.className = "p-3 rounded-xl bg-slate-950 border border-slate-900 font-mono text-rose-500";
            }
        }

        async function runSqlGenIA() {
            const prompt = document.getElementById('sql-prompt').value.trim();
            if (!prompt) return;
            toggleWorkspaceLoader(true, "Orquestando query...");
            try {
                const result = await fetchGemini("Genera la consulta SQL basada en la descripción.", `Descripción: "${prompt}"`);
                const out = document.getElementById('sql-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        function renderMarkdownLocal() {
            const val = document.getElementById('markdown-input').value;
            const out = document.getElementById('markdown-output');
            let html = val
                .replace(/^# (.*?)$/gm, '<h1 class="text-lg font-bold my-2 text-purple-400">$1</h1>')
                .replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>')
                .replace(/\n/g, '<br>');
            out.innerHTML = html;
        }

        function runBase64Local(mode) {
            const input = document.getElementById('base64-input').value;
            const out = document.getElementById('base64-output');
            out.classList.remove('hidden');
            try {
                if (mode === 'encode') {
                    out.innerText = btoa(input);
                } else {
                    out.innerText = atob(input);
                }
            } catch (e) {
                out.innerText = "Error de procesamiento Base64.";
            }
        }

        async function runVulnAnalysisIA() {
            const code = document.getElementById('vuln-code').value.trim();
            if (!code) return;
            toggleWorkspaceLoader(true, "Auditando ciberseguridad...");
            try {
                const result = await fetchGemini("Analiza la seguridad y vulnerabilidades lógicas de este código.", `Código:\n\n${code}`);
                const out = document.getElementById('vuln-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        function generateDummyDataLocal() {
            const type = document.getElementById('dummy-type').value;
            const count = parseInt(document.getElementById('dummy-count').value) || 5;
            const out = document.getElementById('dummy-output');
            out.classList.remove('hidden');

            let arr = [];
            for (let i = 1; i <= count; i++) {
                if (type === 'usuarios') {
                    arr.push({ id: i, nombre: `Usuario_${i}`, email: `user${i}@omnisuite.com` });
                } else {
                    arr.push({ id: i, item: `Producto_${i}`, precio: `${(i * 12.5).toFixed(2)} USD` });
                }
            }
            out.innerText = JSON.stringify(arr, null, 2);
        }

        async function runBigOAnalysisIA() {
            const code = document.getElementById('bigo-code').value.trim();
            if (!code) return;
            toggleWorkspaceLoader(true, "Calculando complejidad Big O...");
            try {
                const result = await fetchGemini("Calcula la complejidad temporal y espacial en notación Big O.", `Algoritmo:\n\n${code}`);
                const out = document.getElementById('bigo-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        // --- HANDLERS: CATEGORÍA 3 (SALUD) ---
        async function runDietIA() {
            const ingredients = document.getElementById('diet-ingredients').value.trim();
            if (!ingredients) return;
            toggleWorkspaceLoader(true, "Estructurando recetas...");
            try {
                const result = await fetchGemini("Diseña una receta saludable con los ingredientes indicados.", `Ingredientes: "${ingredients}"`);
                const out = document.getElementById('diet-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function runWorkoutIA() {
            const target = document.getElementById('workout-target').value;
            toggleWorkspaceLoader(true, "Escribiendo plan deportivo...");
            try {
                const result = await fetchGemini("Genera un plan diario de ejercicio detallado con series y repeticiones.", `Meta: "${target}"`);
                const out = document.getElementById('workout-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        let totalCal = 0;
        function addCaloriesLocal() {
            const food = document.getElementById('calorie-food').value.trim();
            const cal = parseInt(document.getElementById('calorie-count').value) || 0;
            if (!food || cal <= 0) return;

            totalCal += cal;
            const log = document.getElementById('calories-log-container');
            if (totalCal === cal) log.innerHTML = '';

            const item = document.createElement('div');
            item.className = "flex justify-between items-center text-[10px] bg-slate-900 px-2 py-1 rounded border border-slate-800";
            item.innerHTML = `<span>${food}</span><strong class="text-emerald-400">${cal} Kcal</strong>`;
            log.appendChild(item);

            document.getElementById('calorie-food').value = '';
            document.getElementById('calorie-count').value = '';
            triggerToast("Alimento Registrado", `Consumo acumulado: ${totalCal} Kcal`, "success");
        }

        function calculateImcLocal() {
            const height = parseFloat(document.getElementById('imc-height').value) / 100;
            const weight = parseFloat(document.getElementById('imc-weight').value);
            const out = document.getElementById('imc-output');
            out.classList.remove('hidden');

            if (!height || !weight) {
                out.innerText = "Error de métricas.";
                return;
            }

            const imc = (weight / (height * height)).toFixed(1);
            let state = imc < 18.5 ? 'Bajo Peso' : (imc < 25 ? 'Normal' : 'Sobrepeso');
            out.innerHTML = `Tu IMC es: <strong class="text-white">${imc}</strong> (${state})`;
        }

        let waterLogged = 0;
        function logWaterLocal(amount) {
            waterLogged += amount;
            document.getElementById('water-logged').innerText = `${waterLogged} ml`;
            triggerToast("Agua Registrada", `Consumo: ${waterLogged} ml`, "success");
        }
        function resetWaterLocal() {
            waterLogged = 0;
            document.getElementById('water-logged').innerText = '0 ml';
        }

        async function runFlexIA() {
            const muscles = document.getElementById('flex-muscles').value.trim();
            if (!muscles) return;
            toggleWorkspaceLoader(true, "Calculando estiramientos...");
            try {
                const result = await fetchGemini("Diseña una rutina de estiramientos contra el estrés.", `Zonas: "${muscles}"`);
                const out = document.getElementById('flex-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function runMeditationIA() {
            const mood = document.getElementById('meditation-mood').value.trim();
            if (!mood) return;
            toggleWorkspaceLoader(true, "Estructurando meditación...");
            try {
                const result = await fetchGemini("Diseña un ejercicio guiado de respiración.", `Estado: "${mood}"`);
                const out = document.getElementById('meditation-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function runCoherenceIA() {
            const text = document.getElementById('coherence-input').value.trim();
            if (!text) return;
            toggleWorkspaceLoader(true, "Analizando bitácora...");
            try {
                const result = await fetchGemini("Analiza emocionalmente el diario del día con tono empático y constructivo.", `Diario: "${text}"`);
                const out = document.getElementById('coherence-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        let habitsList = [];
        function addHabitLocal() {
            const name = document.getElementById('habit-name').value.trim();
            if (!name) return;
            habitsList.push({ name, checked: false });
            document.getElementById('habit-name').value = '';
            renderHabitsLocal();
        }
        function toggleHabitLocal(idx) {
            habitsList[idx].checked = !habitsList[idx].checked;
            renderHabitsLocal();
        }
        function renderHabitsLocal() {
            const container = document.getElementById('habits-list-container');
            container.innerHTML = '';
            habitsList.forEach((h, idx) => {
                const item = document.createElement('div');
                item.className = "flex justify-between items-center text-[10px] bg-slate-900 px-3 py-1.5 rounded-xl border border-slate-800";
                item.innerHTML = `
                    <span class="${h.checked ? 'line-through text-slate-500' : ''}">${h.name}</span>
                    <input type="checkbox" ${h.checked ? 'checked' : ''} onchange="toggleHabitLocal(${idx})" class="rounded border-slate-800 bg-slate-950 text-emerald-500 focus:ring-0">
                `;
                container.appendChild(item);
            });
        }

        function calculateSleepCyclesLocal() {
            const out = document.getElementById('sleep-output');
            out.classList.remove('hidden');
            out.innerHTML = '';
            const now = Date.now();
            for (let i = 4; i <= 6; i++) {
                const cycleTime = new Date(now + i * 90 * 60 * 1000);
                const block = document.createElement('div');
                block.className = "bg-slate-900 p-2 rounded-lg border border-slate-800";
                block.innerHTML = `<strong>${i} Ciclos (${i * 1.5}h)</strong><br>${cycleTime.toLocaleTimeString([], { hour: '2-digit', minute: '2-digit' })}`;
                out.appendChild(block);
            }
        }

        // --- HANDLERS: CATEGORÍA 4 (GESTIÓN) ---
        function addEisenTaskLocal() {
            const name = document.getElementById('eisen-task').value.trim();
            const quad = document.getElementById('eisen-quad').value;
            if (!name) return;
            const list = document.getElementById(`eisen-list-${quad}`);
            const li = document.createElement('li');
            li.innerText = name;
            list.appendChild(li);
            document.getElementById('eisen-task').value = '';
            triggerToast("Clasificado", "Tarea añadida.", "success");
        }

        async function runWbsIA() {
            const goal = document.getElementById('wbs-goal').value.trim();
            if (!goal) return;
            toggleWorkspaceLoader(true, "Desglosando proyecto...");
            try {
                const result = await fetchGemini("Crea un desglose de tareas estructurado (WBS) de 3 niveles.", `Objetivo: "${goal}"`);
                const out = document.getElementById('wbs-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function runWritingIA() {
            const topic = document.getElementById('writing-topic').value.trim();
            if (!topic) return;
            toggleWorkspaceLoader(true, "Escribiendo contenido...");
            try {
                const result = await fetchGemini("Escribe un comunicado formal o correo profesional.", `Tema: "${topic}"`);
                const out = document.getElementById('writing-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function runProjectTimelineIA() {
            const scope = document.getElementById('project-scope').value.trim();
            if (!scope) return;
            toggleWorkspaceLoader(true, "Estructurando fases...");
            try {
                const result = await fetchGemini("Genera un cronograma de 8 semanas para construir el proyecto.", `Alcance: "${scope}"`);
                const out = document.getElementById('project-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        function calculateCompoundInterestLocal() {
            const cap = parseFloat(document.getElementById('compound-cap').value);
            const rate = parseFloat(document.getElementById('compound-rate').value) / 100;
            const years = parseInt(document.getElementById('compound-years').value);
            const out = document.getElementById('compound-output');
            out.classList.remove('hidden');

            if (!cap || !rate || !years) {
                out.innerText = "Error de parámetros.";
                return;
            }

            const total = cap * Math.pow((1 + rate), years);
            out.innerHTML = `Retorno estimado: <strong class="text-white">${total.toFixed(2)} USD</strong>`;
        }

        let budgetItems = [];
        function addBudgetItemLocal() {
            const desc = document.getElementById('budget-desc').value.trim();
            const val = parseFloat(document.getElementById('budget-amount').value) || 0;
            const type = document.getElementById('budget-type').value;
            if (!desc || val <= 0) return;

            budgetItems.push({ desc, val, type });
            document.getElementById('budget-desc').value = '';
            document.getElementById('budget-amount').value = '';
            renderBudgetLocal();
        }
        function renderBudgetLocal() {
            const container = document.getElementById('budget-log-container');
            container.innerHTML = '';
            let balance = 0;
            budgetItems.forEach(item => {
                const row = document.createElement('div');
                row.className = "flex justify-between items-center bg-slate-900/60 p-2 rounded-xl border border-slate-800";
                const sign = item.type === 'ingreso' ? '+' : '-';
                const color = item.type === 'ingreso' ? 'text-emerald-400' : 'text-rose-500';
                row.innerHTML = `<span>${item.desc}</span><strong class="${color}">${sign}${item.val.toFixed(2)} USD</strong>`;
                container.appendChild(row);
                balance += item.type === 'ingreso' ? item.val : -item.val;
            });
            const totalBox = document.createElement('div');
            totalBox.className = "text-right font-bold text-white pt-2 border-t border-slate-900";
            totalBox.innerHTML = `Balance Total: <span class="${balance >= 0 ? 'text-emerald-400' : 'text-rose-500'}">${balance.toFixed(2)} USD</span>`;
            container.appendChild(totalBox);
        }

        function convertCurrencyLocal() {
            const amount = parseFloat(document.getElementById('currency-amount').value) || 0;
            const from = document.getElementById('currency-from').value;
            const to = document.getElementById('currency-to').value;
            const out = document.getElementById('currency-output');
            out.classList.remove('hidden');

            if (amount <= 0 || from === to) return;
            const rates = { USD_EUR: 0.92, EUR_USD: 1.08 };
            const key = `${from}_${to}`;
            const rate = rates[key] || 1;
            out.innerHTML = `Cambio: <strong class="text-white">${(amount * rate).toFixed(2)} ${to}</strong>`;
        }

        function calculateSavingTimelineLocal() {
            const target = parseFloat(document.getElementById('saving-target').value);
            const monthly = parseFloat(document.getElementById('saving-monthly').value);
            const out = document.getElementById('saving-output');
            out.classList.remove('hidden');

            if (!target || !monthly) return;
            const months = Math.ceil(target / monthly);
            out.innerHTML = `Meta en: <strong class="text-white">${months} meses</strong>`;
        }

        function generateInvoiceLocal() {
            const client = document.getElementById('invoice-client').value.trim();
            const item = document.getElementById('invoice-item').value.trim();
            const price = parseFloat(document.getElementById('invoice-price').value) || 0;
            const out = document.getElementById('invoice-output');
            out.classList.remove('hidden');

            if (!client || !item || price <= 0) return;
            out.innerHTML = `
                <div class="border-b border-slate-300 pb-2 mb-2 text-center text-xs font-bold uppercase">Facturación</div>
                <p class="text-[9px]">Cliente: ${client}</p>
                <p class="text-[9px]">Servicio: ${item}</p>
                <p class="text-[10px] font-bold border-t border-slate-300 pt-1 text-right">Total: ${price.toFixed(2)} USD</p>
            `;
        }

        async function runInterviewPreparationIA() {
            const role = document.getElementById('interview-role').value.trim();
            if (!role) return;
            toggleWorkspaceLoader(true, "Generando cuestionario...");
            try {
                const result = await fetchGemini("Genera 3 preguntas de entrevista técnica complejas.", `Puesto: "${role}"`);
                const out = document.getElementById('interview-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        // --- HANDLERS: CATEGORÍA 5 (CREATIVIDAD) ---
        async function runChefImageIA() {
            const prompt = document.getElementById('image-prompt').value.trim();
            if (!prompt) return;

            toggleWorkspaceLoader(true, "Generando fotografía culinaria...");
            const apiKey = getAPIKey();
            const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/imagen-4.0-generate-001:predict?key=${apiKey}`;

            const payload = {
                instances: [{ prompt: `${prompt}, food photography, commercial studio light, detailed.` }],
                parameters: { sampleCount: 1 }
            };

            try {
                const response = await fetchWithRetry(apiUrl, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify(payload)
                });
                const result = await response.json();
                const base64 = result.predictions?.[0]?.bytesBase64Encoded;
                if (base64) {
                    const img = document.getElementById('chef-image-output');
                    img.src = `data:image/png;base64,${base64}`;
                    document.getElementById('chef-image-container').classList.remove('hidden');
                } else {
                    triggerToast("Error", "Imagen-4 sin respuesta.", "error");
                }
            } catch (e) {
                triggerToast("Error", "Fallo al generar imagen.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function initRpgGameIA(scenario) {
            document.getElementById('rpg-init-box').classList.add('hidden');
            const flow = document.getElementById('rpg-story-flow');
            flow.classList.remove('hidden');
            flow.innerHTML = '<p class="text-center py-4 text-[10px] text-slate-500">Iniciando partida...</p>';

            try {
                const result = await fetchGemini("Eres un Dungeon Master de rol. Genera la intro de la aventura.", `Escenario: "${scenario}"`);
                flow.innerHTML = `<p>${result.replace(/\n/g, '<br>')}</p>`;
                const optsBox = document.getElementById('rpg-options-box');
                optsBox.classList.remove('hidden');
                optsBox.innerHTML = '';
                for (let i = 1; i <= 3; i++) {
                    const btn = document.createElement('button');
                    btn.className = "w-full text-left bg-slate-900/80 hover:bg-slate-800 border border-slate-800 p-2 rounded-xl text-[10px] text-rose-400 font-semibold";
                    btn.innerText = `Opción de Acción #${i}`;
                    btn.onclick = () => chooseRpgOptionIA(i);
                    optsBox.appendChild(btn);
                }
            } catch (e) {
                flow.innerHTML = "Error al conectar narrativa.";
            }
        }

        async function chooseRpgOptionIA(optNum) {
            toggleWorkspaceLoader(true, "Narrando consecuencias...");
            const flow = document.getElementById('rpg-story-flow');
            try {
                const result = await fetchGemini("Continúa la aventura de rol de acuerdo a la decisión.", `Elegí la opción #${optNum}`);
                flow.innerHTML += `<hr class="border-slate-900 my-3"><p class="text-teal-400 font-bold mb-1">Elegiste Opción #${optNum}</p><p>${result.replace(/\n/g, '<br>')}</p>`;
                flow.scrollTop = flow.scrollHeight;
            } catch (e) {
                triggerToast("Error", "Fallo narrativo.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        // Arcade Space Defender Engine
        let arcCanvas, arcCtx;
        let arcX = 135;
        let arcIsRunning = false;
        let arcLoopVal = null;

        function initArcadeCanvas() {
            arcCanvas = document.getElementById('arcade-play-canvas');
            if (!arcCanvas) return;
            arcCtx = arcCanvas.getContext('2d');
            arcCanvas.width = 300;
            arcCanvas.height = 150;
            arcIsRunning = true;
            arcLoopVal = setInterval(updateLocalArcade, 50);
        }

        function updateLocalArcade() {
            if (!arcIsRunning || !arcCtx) return;
            arcCtx.fillStyle = '#020617';
            arcCtx.fillRect(0, 0, arcCanvas.width, arcCanvas.height);
            arcCtx.fillStyle = '#f43f5e';
            arcCtx.beginPath();
            arcCtx.moveTo(arcX + 15, arcCanvas.height - 25);
            arcCtx.lineTo(arcX, arcCanvas.height - 5);
            arcCtx.lineTo(arcX + 30, arcCanvas.height - 5);
            arcCtx.closePath();
            arcCtx.fill();
        }

        async function runPoetryIA() {
            const topic = document.getElementById('poetry-topic').value.trim();
            if (!topic) return;
            toggleWorkspaceLoader(true, "Escribiendo versos...");
            try {
                const result = await fetchGemini("Eres un poeta. Escribe un poema corto de 2 estrofas.", `Tema: "${topic}"`);
                const out = document.getElementById('poetry-output');
                out.innerHTML = result.replace(/\n/g, '<br>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function runIdeasIA() {
            const topic = document.getElementById('ideas-topic').value.trim();
            if (!topic) return;
            toggleWorkspaceLoader(true, "Generando propuestas...");
            try {
                const result = await fetchGemini("Genera 5 propuestas disruptivas.", `Tema: "${topic}"`);
                const out = document.getElementById('ideas-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function runJokeIA() {
            const topic = document.getElementById('joke-topic').value.trim();
            if (!topic) return;
            toggleWorkspaceLoader(true, "Creando comedia...");
            try {
                const result = await fetchGemini("Crea un chiste corto e inteligente de computación.", `Tema: "${topic}"`);
                const out = document.getElementById('joke-output');
                out.innerHTML = result.replace(/\n/g, '<br>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function runTwitterIA() {
            const topic = document.getElementById('twitter-topic').value.trim();
            if (!topic) return;
            toggleWorkspaceLoader(true, "Generando copys...");
            try {
                const result = await fetchGemini("Escribe un hilo viral estructurado de 3 tweets.", `Tema: "${topic}"`);
                const out = document.getElementById('twitter-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        function generatePaletteLocal() {
            const out = document.getElementById('palette-output');
            out.classList.remove('hidden');
            out.innerHTML = '';
            const colors = ['#6366f1', '#a855f7', '#ec4899', '#f43f5e', '#eab308'];
            colors.forEach(col => {
                const block = document.createElement('div');
                block.className = "p-2 rounded-lg border border-slate-800 text-center";
                block.style.backgroundColor = col;
                block.innerHTML = `<span class="bg-black/80 px-1 py-0.5 rounded text-[8px] font-bold">${col}</span>`;
                out.appendChild(block);
            });
        }

        async function runCreativeStoryIA() {
            const premise = document.getElementById('story-premise').value.trim();
            if (!premise) return;
            toggleWorkspaceLoader(true, "Escribiendo micro-historia...");
            try {
                const result = await fetchGemini("Escribe un micro-relato de suspenso de 150 palabras.", `Premisa: "${premise}"`);
                const out = document.getElementById('story-output');
                out.innerHTML = result.replace(/\n/g, '<br>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function runChordsIA() {
            const prompt = document.getElementById('chords-prompt').value.trim();
            if (!prompt) return;
            toggleWorkspaceLoader(true, "Buscando progresión...");
            try {
                const result = await fetchGemini("Genera una progresión armónica de guitarra de 4 acordes.", `Vibra: "${prompt}"`);
                const out = document.getElementById('chords-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        // --- HANDLERS: CATEGORÍA 6 (UTILIDADES) ---
        function generatePasswordLocal() {
            const out = document.getElementById('pass-output');
            out.classList.remove('hidden');
            out.innerText = Math.random().toString(36).slice(-8) + Math.random().toString(36).slice(-8).toUpperCase();
        }

        let pomTimer = null, pomSec = 1500;
        function startPomodoroLocal() {
            if (pomTimer) clearInterval(pomTimer);
            pomTimer = setInterval(() => {
                if (pomSec <= 0) {
                    clearInterval(pomTimer);
                    triggerToast("Pomodoro", "Completado.", "success");
                    return;
                }
                pomSec--;
                document.getElementById('pomodoro-timer').innerText = `${Math.floor(pomSec / 60)}:${(pomSec % 60).toString().padStart(2, '0')}`;
            }, 1000);
        }
        function pausePomodoroLocal() {
            clearInterval(pomTimer);
        }

        function convertUnitsLocal() {
            const val = parseFloat(document.getElementById('unit-val').value) || 0;
            const out = document.getElementById('unit-output');
            out.classList.remove('hidden');
            out.innerHTML = `Resultado: <strong class="text-white">${(val * 2.2).toFixed(2)} Libras</strong>`;
        }

        function generateQrLocal() {
            const link = document.getElementById('qr-link').value.trim();
            const container = document.getElementById('qr-container');
            const img = document.getElementById('qr-output');
            if (!link) return;
            container.classList.remove('hidden');
            img.src = `https://api.qrserver.com/v1/create-qr-code/?size=150x150&data=${encodeURIComponent(link)}`;
        }

        async function runKeywordsIA() {
            const text = document.getElementById('keywords-input').value.trim();
            if (!text) return;
            toggleWorkspaceLoader(true, "Aislando conceptos...");
            try {
                const result = await fetchGemini("Extrae 5 palabras clave del texto.", `Texto:\n\n${text}`);
                const out = document.getElementById('keywords-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function runTtsIA() {
            const text = document.getElementById('tts-input').value.trim();
            if (!text) return;
            toggleWorkspaceLoader(true, "Sintetizando voz nativa...");
            try {
                const synth = window.speechSynthesis;
                const utter = new SpeechSynthesisUtterance(text);
                utter.lang = 'es-ES';
                synth.speak(utter);
                triggerToast("Audio Nativo", "Escuchando síntesis de voz.", "success");
            } catch (err) {
                triggerToast("Error", "Fallo al iniciar el motor de voz.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function runSentimentIA() {
            const text = document.getElementById('sentiment-input').value.trim();
            if (!text) return;
            toggleWorkspaceLoader(true, "Analizando sentimiento...");
            try {
                const result = await fetchGemini("Clasifica el sentimiento en Positivo, Neutro o Negativo.", `Mensaje:\n\n${text}`);
                const out = document.getElementById('sentiment-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        function runRaffleLocal() {
            const list = document.getElementById('raffle-list').value;
            const out = document.getElementById('raffle-output');
            out.classList.remove('hidden');
            const arr = list.split(',').map(n => n.trim()).filter(n => n !== '');
            if (arr.length === 0) return;
            out.innerHTML = `Ganador: <strong class="text-white">${arr[Math.floor(Math.random() * arr.length)]}</strong>`;
        }

        function compareTimesLocal() {
            const out = document.getElementById('timezone-output');
            out.classList.remove('hidden');
            out.innerHTML = '';
            const zones = [
                { name: 'Nueva York', zone: 'America/New_York' },
                { name: 'Londres', zone: 'Europe/London' }
            ];
            zones.forEach(z => {
                const timeStr = new Date().toLocaleTimeString('es-ES', { timeZone: z.zone, hour: '2-digit', minute: '2-digit' });
                const block = document.createElement('div');
                block.className = "bg-slate-900/60 p-2 rounded-lg border border-slate-800 text-center";
                block.innerHTML = `<strong>${z.name}</strong><br>${timeStr}`;
                out.appendChild(block);
            });
        }

        let cartList = [];
        function addCartItemLocal() {
            const name = document.getElementById('cart-item').value.trim();
            if (!name) return;
            cartList.push({ name, checked: false });
            document.getElementById('cart-item').value = '';
            renderCartLocal();
        }
        function toggleCartLocal(idx) {
            cartList[idx].checked = !cartList[idx].checked;
            renderCartLocal();
        }
        function renderCartLocal() {
            const container = document.getElementById('cart-list-container');
            container.innerHTML = '';
            cartList.forEach((item, idx) => {
                const row = document.createElement('div');
                row.className = "flex justify-between items-center text-[10px] bg-slate-900/60 p-3 rounded-xl border border-slate-800";
                row.innerHTML = `
                    <span class="${item.checked ? 'line-through text-slate-500' : ''}">${item.name}</span>
                    <input type="checkbox" ${item.checked ? 'checked' : ''} onchange="toggleCartLocal(${idx})" class="rounded border-slate-800 bg-slate-950 text-teal-500 focus:ring-0">
                `;
                container.appendChild(row);
            });
        }

        // --- HANDLERS: CATEGORÍA 7 (MARKETING & REDES) [NUEVO] ---
        async function runMktCopyIA() {
            const prod = document.getElementById('mkt-product').value.trim();
            if (!prod) return;
            toggleWorkspaceLoader(true, "Escribiendo copys...");
            try {
                const result = await fetchGemini("Escribe 2 copys publicitarios de conversión.", `Producto: "${prod}"`);
                const out = document.getElementById('mkt-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function runMktHashtagsIA() {
            const niche = document.getElementById('mkt-niche').value.trim();
            if (!niche) return;
            toggleWorkspaceLoader(true, "Calculando hashtags...");
            try {
                const result = await fetchGemini("Genera 10 hashtags virales e interactivos.", `Nicho: "${niche}"`);
                const out = document.getElementById('hashtags-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function runSeoMetaIA() {
            const keyword = document.getElementById('seo-keyword').value.trim();
            if (!keyword) return;
            toggleWorkspaceLoader(true, "Optimizando metatags SEO...");
            try {
                const result = await fetchGemini("Genera etiquetas Title (60 chars) y Description (150 chars) SEO.", `Keyword: "${keyword}"`);
                const out = document.getElementById('seo-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function runIgIdeasIA() {
            const topic = document.getElementById('ig-topic').value.trim();
            if (!topic) return;
            toggleWorkspaceLoader(true, "Generando ideas visuales...");
            try {
                const result = await fetchGemini("Genera 3 propuestas creativas de posts de carrusel.", `Nicho: "${topic}"`);
                const out = document.getElementById('ig-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function runTikTokScriptIA() {
            const hook = document.getElementById('tt-hook').value.trim();
            if (!hook) return;
            toggleWorkspaceLoader(true, "Escribiendo guión viral...");
            try {
                const result = await fetchGemini("Escribe un script de video corto con gancho de 3 segundos.", `Gancho inicial: "${hook}"`);
                const out = document.getElementById('tt-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function runNewsletterIA() {
            const nl = document.getElementById('nl-campaign').value.trim();
            if (!nl) return;
            toggleWorkspaceLoader(true, "Redactando boletín informativo...");
            try {
                const result = await fetchGemini("Escribe una campaña informativa con gancho inicial.", `Temática: "${nl}"`);
                const out = document.getElementById('nl-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function runSlogansIA() {
            const desc = document.getElementById('slogan-desc').value.trim();
            if (!desc) return;
            toggleWorkspaceLoader(true, "Escribiendo slogans...");
            try {
                const result = await fetchGemini("Escribe 5 slogans memorables y potentes.", `Negocio: "${desc}"`);
                const out = document.getElementById('slogans-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function runLandingAnalysisIA() {
            const text = document.getElementById('landing-text').value.trim();
            if (!text) return;
            toggleWorkspaceLoader(true, "Evaluando conversión...");
            try {
                const result = await fetchGemini("Analiza la claridad y conversión comercial.", `Texto:\n\n${text}`);
                const out = document.getElementById('landing-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function runStoryQuestionsIA() {
            const topic = document.getElementById('qa-topic').value.trim();
            if (!topic) return;
            toggleWorkspaceLoader(true, "Planteando preguntas...");
            try {
                const result = await fetchGemini("Genera 3 encuestas de alto enganche.", `Tema: "${topic}"`);
                const out = document.getElementById('qa-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        function calculateRoiLocal() {
            const spend = parseFloat(document.getElementById('roi-spend').value) || 0;
            const rev = parseFloat(document.getElementById('roi-rev').value) || 0;
            const out = document.getElementById('roi-output');
            out.classList.remove('hidden');
            if (spend <= 0) return;
            out.innerHTML = `Retorno de Inversión (ROI): <strong class="text-white">${(((rev - spend) / spend) * 100).toFixed(0)}%</strong>`;
        }

        // --- HANDLERS: CATEGORÍA 8 (LIFESTYLE & VIAJES) [NUEVO] ---
        async function runTripPlannerIA() {
            const dest = document.getElementById('trip-dest').value.trim();
            if (!dest) return;
            toggleWorkspaceLoader(true, "Diseñando itinerario...");
            try {
                const result = await fetchGemini("Genera un itinerario estructurado de 3 días.", `Destino: "${dest}"`);
                const out = document.getElementById('trip-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function runPackBuilderIA() {
            const dest = document.getElementById('pack-dest').value.trim();
            if (!dest) return;
            toggleWorkspaceLoader(true, "Generando checklist...");
            try {
                const result = await fetchGemini("Genera una lista de equipaje optimizada.", `Clima/Destino: "${dest}"`);
                const out = document.getElementById('pack-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function runHabit66IA() {
            const habit = document.getElementById('habit-loop-name').value.trim();
            if (!habit) return;
            toggleWorkspaceLoader(true, "Estructurando bucle...");
            try {
                const result = await fetchGemini("Divide la adquisición del hábito en 3 fases de 22 días.", `Hábito: "${habit}"`);
                const out = document.getElementById('habit-loop-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        function calculateReadingPlanLocal() {
            const total = parseInt(document.getElementById('read-total').value) || 0;
            const days = parseInt(document.getElementById('read-days').value) || 0;
            const out = document.getElementById('read-output');
            out.classList.remove('hidden');
            if (total <= 0 || days <= 0) return;
            out.innerHTML = `Meta de lectura: <strong class="text-white">${Math.ceil(total / days)} páginas por día</strong>`;
        }

        function calculateFinances503020Local() {
            const income = parseFloat(document.getElementById('fin-income').value) || 0;
            const out = document.getElementById('fin-output');
            out.classList.remove('hidden');
            if (income <= 0) return;
            out.innerHTML = `
                <p>Gastos Necesarios (50%): <strong class="text-lime-400">${(income * 0.5).toFixed(0)} USD</strong></p>
                <p>Deseos & Ocio (30%): <strong class="text-indigo-400">${(income * 0.3).toFixed(0)} USD</strong></p>
                <p>Ahorro & Inversión (20%): <strong class="text-emerald-400">${(income * 0.2).toFixed(0)} USD</strong></p>
            `;
        }

        async function runSurvivalLangIA() {
            const lang = document.getElementById('lang-target').value.trim();
            if (!lang) return;
            toggleWorkspaceLoader(true, "Estructurando frases de supervivencia...");
            try {
                const result = await fetchGemini("Escribe 5 frases indispensables de viaje con pronunciación fonética.", `Idioma meta: "${lang}"`);
                const out = document.getElementById('lang-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function runCafeSearchIA() {
            const city = document.getElementById('cafe-city').value.trim();
            if (!city) return;
            toggleWorkspaceLoader(true, "Buscando cafeterías...");
            try {
                const result = await fetchGemini("Recomienda teóricamente 3 cafeterías con buena conexión WiFi.", `Ciudad: "${city}"`);
                const out = document.getElementById('cafe-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        async function runMorningRoutineIA() {
            const goal = document.getElementById('morning-goal').value.trim();
            if (!goal) return;
            toggleWorkspaceLoader(true, "Diseñando despertar productivo...");
            try {
                const result = await fetchGemini("Genera una rutina de despertar de 60 minutos.", `Meta: "${goal}"`);
                const out = document.getElementById('morning-output');
                out.innerHTML = result.replace(/\n/g, '<br>').replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                out.classList.remove('hidden');
            } catch (e) {
                triggerToast("Error", "Reintente.", "error");
            } finally {
                toggleWorkspaceLoader(false);
            }
        }

        let gratitudeList = [];
        function saveGratitudeLocal() {
            const text = document.getElementById('gratitude-text').value.trim();
            if (!text) return;
            gratitudeList.push(text);
            document.getElementById('gratitude-text').value = '';
            renderGratitudeLocal();
            triggerToast("Guardado", "Agradecimiento registrado.", "success");
        }
        function renderGratitudeLocal() {
            const container = document.getElementById('gratitude-log-container');
            container.innerHTML = '';
            gratitudeList.slice(-3).reverse().forEach(g => {
                const row = document.createElement('div');
                row.className = "bg-slate-900/60 p-2.5 rounded-xl border border-slate-800 text-[10px] italic text-slate-300";
                row.innerText = `"${g}"`;
                container.appendChild(row);
            });
        }

        let teaTimer = null;
        function startTeaTimerLocal() {
            const val = document.getElementById('tea-type').value;
            const output = document.getElementById('tea-timer-output');
            let sec = val.includes("3") ? 180 : 300;
            if (teaTimer) clearInterval(teaTimer);
            teaTimer = setInterval(() => {
                if (sec <= 0) {
                    clearInterval(teaTimer);
                    output.innerText = "¡Listo!";
                    triggerToast("Infusión", "Tu té está en su punto.", "success");
                    return;
                }
                sec--;
                output.innerText = `${Math.floor(sec / 60)}:${(sec % 60).toString().padStart(2, '0')}`;
            }, 1000);
        }
    </script>
</body>
</html>
Una ia dedicada a la vida diaria-By Maykol Gomez
