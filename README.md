<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Trilhos Mortos [Alfa] - Script Premium</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        .glow {
            text-shadow: 0 0 10px #00ff00, 0 0 20px #00ff00;
        }
        .gradient-bg {
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
        }
        .btn-hover:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 20px rgba(0, 255, 0, 0.2);
        }
        .tab-content {
            display: none;
        }
        .tab-content.active {
            display: block;
            animation: fadeIn 0.5s ease-in-out;
        }
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        .status-indicator {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            display: inline-block;
            margin-right: 8px;
        }
        .status-active {
            background-color: #00ff00;
            box-shadow: 0 0 10px #00ff00;
        }
        .status-inactive {
            background-color: #ff0000;
        }
        .bypass-badge {
            position: absolute;
            top: 10px;
            right: 10px;
            background-color: #ff0000;
            color: white;
            padding: 3px 8px;
            border-radius: 10px;
            font-size: 12px;
            font-weight: bold;
        }
    </style>
</head>
<body class="gradient-bg text-gray-100 min-h-screen font-sans">
    <div class="container mx-auto px-4 py-8 max-w-4xl">
        <!-- Header -->
        <header class="text-center mb-8 relative">
            <div class="bypass-badge">BYPASS ATIVO</div>
            <h1 class="text-4xl font-bold mb-2 glow text-green-400">TRILHOS MORTOS [ALFA]</h1>
            <p class="text-xl text-gray-300">Script Premium - Auto Farm & Bypass</p>
            <div class="flex justify-center mt-4">
                <span class="status-indicator status-active"></span>
                <span class="text-green-400">Script Ativo</span>
            </div>
        </header>

        <!-- Main Content -->
        <div class="bg-gray-800 bg-opacity-70 rounded-xl shadow-2xl overflow-hidden">
            <!-- Tabs -->
            <div class="flex border-b border-gray-700">
                <button class="tab-btn py-4 px-6 font-medium text-green-400 border-b-2 border-green-400" data-tab="auto-farm">
                    <i class="fas fa-robot mr-2"></i>Auto Farm
                </button>
                <button class="tab-btn py-4 px-6 font-medium text-gray-400 hover:text-green-400" data-tab="bypass">
                    <i class="fas fa-shield-alt mr-2"></i>Sistema Bypass
                </button>
                <button class="tab-btn py-4 px-6 font-medium text-gray-400 hover:text-green-400" data-tab="utilities">
                    <i class="fas fa-tools mr-2"></i>Utilities
                </button>
                <button class="tab-btn py-4 px-6 font-medium text-gray-400 hover:text-green-400" data-tab="settings">
                    <i class="fas fa-cog mr-2"></i>Configurações
                </button>
            </div>

            <!-- Tab Contents -->
            <div class="p-6">
                <!-- Auto Farm Tab -->
                <div id="auto-farm" class="tab-content active">
                    <h2 class="text-2xl font-bold mb-4 text-green-400"><i class="fas fa-robot mr-2"></i>Auto Farm Configurações</h2>
                    
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-6">
                        <div class="bg-gray-900 p-4 rounded-lg">
                            <h3 class="text-lg font-semibold mb-3 text-green-300">Configurações Básicas</h3>
                            <div class="space-y-4">
                                <div class="flex items-center">
                                    <input type="checkbox" id="enable-autofarm" class="w-5 h-5 text-green-500 rounded focus:ring-green-400" checked>
                                    <label for="enable-autofarm" class="ml-2 text-gray-300">Ativar Auto Farm</label>
                                </div>
                                <div class="flex items-center">
                                    <input type="checkbox" id="collect-coins" class="w-5 h-5 text-green-500 rounded focus:ring-green-400" checked>
                                    <label for="collect-coins" class="ml-2 text-gray-300">Coletar Moedas</label>
                                </div>
                                <div class="flex items-center">
                                    <input type="checkbox" id="collect-items" class="w-5 h-5 text-green-500 rounded focus:ring-green-400" checked>
                                    <label for="collect-items" class="ml-2 text-gray-300">Coletar Itens</label>
                                </div>
                            </div>
                        </div>

                        <div class="bg-gray-900 p-4 rounded-lg">
                            <h3 class="text-lg font-semibold mb-3 text-green-300">Configurações Avançadas</h3>
                            <div class="space-y-4">
                                <div>
                                    <label for="farm-speed" class="block text-gray-300 mb-1">Velocidade de Farm</label>
                                    <input type="range" id="farm-speed" min="1" max="10" value="5" class="w-full h-2 bg-gray-700 rounded-lg appearance-none cursor-pointer">
                                    <div class="flex justify-between text-xs text-gray-400 mt-1">
                                        <span>Lento</span>
                                        <span>Rápido</span>
                                    </div>
                                </div>
                                <div>
                                    <label for="search-radius" class="block text-gray-300 mb-1">Raio de Busca</label>
                                    <select id="search-radius" class="w-full bg-gray-700 border border-gray-600 text-gray-300 rounded-lg p-2 focus:ring-green-400 focus:border-green-400">
                                        <option value="50">50 studs</option>
                                        <option value="100" selected>100 studs</option>
                                        <option value="150">150 studs</option>
                                        <option value="200">200 studs</option>
                                    </select>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="bg-gray-900 p-4 rounded-lg mb-6">
                        <h3 class="text-lg font-semibold mb-3 text-green-300">Estatísticas</h3>
                        <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
                            <div class="bg-gray-800 p-3 rounded-lg text-center">
                                <p class="text-gray-400 text-sm">Moedas Coletadas</p>
                                <p class="text-2xl font-bold text-green-400" id="coins-collected">0</p>
                            </div>
                            <div class="bg-gray-800 p-3 rounded-lg text-center">
                                <p class="text-gray-400 text-sm">Itens Coletados</p>
                                <p class="text-2xl font-bold text-green-400" id="items-collected">0</p>
                            </div>
                            <div class="bg-gray-800 p-3 rounded-lg text-center">
                                <p class="text-gray-400 text-sm">Tempo Ativo</p>
                                <p class="text-2xl font-bold text-green-400" id="uptime">00:00:00</p>
                            </div>
                            <div class="bg-gray-800 p-3 rounded-lg text-center">
                                <p class="text-gray-400 text-sm">Eficiência</p>
                                <p class="text-2xl font-bold text-green-400" id="efficiency">95%</p>
                            </div>
                        </div>
                    </div>

                    <div class="flex justify-center">
                        <button id="start-farm" class="bg-green-600 hover:bg-green-700 text-white font-bold py-3 px-8 rounded-lg transition-all duration-300 btn-hover flex items-center">
                            <i class="fas fa-play mr-2"></i> Iniciar Auto Farm
                        </button>
                    </div>
                </div>

                <!-- Bypass Tab -->
                <div id="bypass" class="tab-content">
                    <h2 class="text-2xl font-bold mb-4 text-green-400"><i class="fas fa-shield-alt mr-2"></i>Sistema Bypass</h2>
                    
                    <div class="bg-gray-900 p-4 rounded-lg mb-6">
                        <h3 class="text-lg font-semibold mb-3 text-green-300">Status do Bypass</h3>
                        <div class="grid grid-cols-1 md:grid-cols-3 gap-4 mb-4">
                            <div class="bg-gray-800 p-3 rounded-lg">
                                <div class="flex items-center mb-2">
                                    <span class="status-indicator status-active"></span>
                                    <span class="text-green-400">Bypass Ativo</span>
                                </div>
                                <p class="text-gray-300 text-sm">Protegendo contra detecção</p>
                            </div>
                            <div class="bg-gray-800 p-3 rounded-lg">
                                <p class="text-gray-400 text-sm">Última Verificação</p>
                                <p class="text-green-400 font-semibold" id="last-check">Agora mesmo</p>
                            </div>
                            <div class="bg-gray-800 p-3 rounded-lg">
                                <p class="text-gray-400 text-sm">Tempo de Atividade</p>
                                <p class="text-green-400 font-semibold" id="bypass-uptime">00:00:00</p>
                            </div>
                        </div>
                        
                        <div class="bg-blue-900 bg-opacity-30 p-3 rounded-lg border border-blue-400">
                            <div class="flex items-start">
                                <i class="fas fa-info-circle text-blue-300 mt-1 mr-2"></i>
                                <p class="text-blue-300 text-sm">
                                    O sistema de bypass está atualmente mascarando todas as atividades do script para evitar detecção pelo anti-cheat do jogo.
                                </p>
                            </div>
                        </div>
                    </div>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-6">
                        <div class="bg-gray-900 p-4 rounded-lg">
                            <h3 class="text-lg font-semibold mb-3 text-green-300">Configurações de Bypass</h3>
                            <div class="space-y-4">
                                <div class="flex items-center">
                                    <input type="checkbox" id="anti-detection" class="w-5 h-5 text-green-500 rounded focus:ring-green-400" checked>
                                    <label for="anti-detection" class="ml-2 text-gray-300">Anti-Detecção</label>
                                </div>
                                <div class="flex items-center">
                                    <input type="checkbox" id="random-patterns" class="w-5 h-5 text-green-500 rounded focus:ring-green-400" checked>
                                    <label for="random-patterns" class="ml-2 text-gray-300">Padrões Aleatórios</label>
                                </div>
                                <div class="flex items-center">
                                    <input type="checkbox" id="fake-inputs" class="w-5 h-5 text-green-500 rounded focus:ring-green-400">
                                    <label for="fake-inputs" class="ml-2 text-gray-300">Inputs Falsos</label>
                                </div>
                            </div>
                        </div>

                        <div class="bg-gray-900 p-4 rounded-lg">
                            <h3 class="text-lg font-semibold mb-3 text-green-300">Métodos de Bypass</h3>
                            <div class="space-y-4">
                                <div>
                                    <label for="bypass-method" class="block text-gray-300 mb-1">Método Principal</label>
                                    <select id="bypass-method" class="w-full bg-gray-700 border border-gray-600 text-gray-300 rounded-lg p-2 focus:ring-green-400 focus:border-green-400">
                                        <option value="memory">Injeção de Memória</option>
                                        <option value="hook" selected>Hook de Funções</option>
                                        <option value="packet">Manipulação de Pacotes</option>
                                    </select>
                                </div>
                                <div>
                                    <label for="security-level" class="block text-gray-300 mb-1">Nível de Segurança</label>
                                    <select id="security-level" class="w-full bg-gray-700 border border-gray-600 text-gray-300 rounded-lg p-2 focus:ring-green-400 focus:border-green-400">
                                        <option value="low">Baixo (Performance)</option>
                                        <option value="medium" selected>Médio (Recomendado)</option>
                                        <option value="high">Alto (Segurança Máxima)</option>
                                    </select>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="bg-gray-900 p-4 rounded-lg">
                        <h3 class="text-lg font-semibold mb-3 text-green-300">Teste de Bypass</h3>
                        <div class="grid grid-cols-2 gap-4">
                            <button id="test-bypass" class="bg-yellow-600 hover:bg-yellow-700 text-white py-2 px-4 rounded transition-all duration-300 btn-hover flex items-center justify-center">
                                <i class="fas fa-vial mr-2"></i> Testar Bypass
                            </button>
                            <button id="update-bypass" class="bg-purple-600 hover:bg-purple-700 text-white py-2 px-4 rounded transition-all duration-300 btn-hover flex items-center justify-center">
                                <i class="fas fa-sync-alt mr-2"></i> Atualizar Bypass
                            </button>
                        </div>
                    </div>
                </div>

                <!-- Utilities Tab -->
                <div id="utilities" class="tab-content">
                    <h2 class="text-2xl font-bold mb-4 text-green-400"><i class="fas fa-tools mr-2"></i>Ferramentas Úteis</h2>
                    
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-6">
                        <div class="bg-gray-900 p-4 rounded-lg">
                            <h3 class="text-lg font-semibold mb-3 text-green-300">Jogador</h3>
                            <div class="space-y-4">
                                <div class="flex items-center">
                                    <input type="checkbox" id="anti-afk" class="w-5 h-5 text-green-500 rounded focus:ring-green-400" checked>
                                    <label for="anti-afk" class="ml-2 text-gray-300">Anti-AFK</label>
                                </div>
                                <div class="flex items-center">
                                    <input type="checkbox" id="auto-sprint" class="w-5 h-5 text-green-500 rounded focus:ring-green-400">
                                    <label for="auto-sprint" class="ml-2 text-gray-300">Auto Sprint</label>
                                </div>
                                <div class="flex items-center">
                                    <input type="checkbox" id="no-clip" class="w-5 h-5 text-green-500 rounded focus:ring-green-400">
                                    <label for="no-clip" class="ml-2 text-gray-300">No Clip</label>
                                </div>
                            </div>
                        </div>

                        <div class="bg-gray-900 p-4 rounded-lg">
                            <h3 class="text-lg font-semibold mb-3 text-green-300">Visual</h3>
                            <div class="space-y-4">
                                <div class="flex items-center">
                                    <input type="checkbox" id="esp-players" class="w-5 h-5 text-green-500 rounded focus:ring-green-400">
                                    <label for="esp-players" class="ml-2 text-gray-300">ESP Jogadores</label>
                                </div>
                                <div class="flex items-center">
                                    <input type="checkbox" id="esp-items" class="w-5 h-5 text-green-500 rounded focus:ring-green-400" checked>
                                    <label for="esp-items" class="ml-2 text-gray-300">ESP Itens</label>
                                </div>
                                <div class="flex items-center">
                                    <input type="checkbox" id="fullbright" class="w-5 h-5 text-green-500 rounded focus:ring-green-400" checked>
                                    <label for="fullbright" class="ml-2 text-gray-300">FullBright</label>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="bg-gray-900 p-4 rounded-lg mb-6">
                        <h3 class="text-lg font-semibold mb-3 text-green-300">Teleportes</h3>
                        <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
                            <button class="bg-blue-600 hover:bg-blue-700 text-white py-2 px-4 rounded transition-all duration-300 btn-hover">
                                Estação Central
                            </button>
                            <button class="bg-blue-600 hover:bg-blue-700 text-white py-2 px-4 rounded transition-all duration-300 btn-hover">
                                Mina Abandonada
                            </button>
                            <button class="bg-blue-600 hover:bg-blue-700 text-white py-2 px-4 rounded transition-all duration-300 btn-hover">
                                Floresta Sombria
                            </button>
                            <button class="bg-blue-600 hover:bg-blue-700 text-white py-2 px-4 rounded transition-all duration-300 btn-hover">
                                Cemitério
                            </button>
                        </div>
                    </div>

                    <div class="bg-gray-900 p-4 rounded-lg">
                        <h3 class="text-lg font-semibold mb-3 text-green-300">Outras Utilidades</h3>
                        <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                            <button class="bg-purple-600 hover:bg-purple-700 text-white py-2 px-4 rounded transition-all duration-300 btn-hover flex items-center justify-center">
                                <i class="fas fa-coins mr-2"></i> Auto Vender
                            </button>
                            <button class="bg-purple-600 hover:bg-purple-700 text-white py-2 px-4 rounded transition-all duration-300 btn-hover flex items-center justify-center">
                                <i class="fas fa-shopping-cart mr-2"></i> Auto Comprar
                            </button>
                            <button class="bg-purple-600 hover:bg-purple-700 text-white py-2 px-4 rounded transition-all duration-300 btn-hover flex items-center justify-center">
                                <i class="fas fa-ghost mr-2"></i> Anti-Zumbi
                            </button>
                        </div>
                    </div>
                </div>

                <!-- Settings Tab -->
                <div id="settings" class="tab-content">
                    <h2 class="text-2xl font-bold mb-4 text-green-400"><i class="fas fa-cog mr-2"></i>Configurações do Script</h2>
                    
                    <div class="bg-gray-900 p-4 rounded-lg mb-6">
                        <h3 class="text-lg font-semibold mb-3 text-green-300">Configurações Gerais</h3>
                        <div class="space-y-4">
                            <div>
                                <label for="ui-theme" class="block text-gray-300 mb-1">Tema da Interface</label>
                                <select id="ui-theme" class="w-full bg-gray-700 border border-gray-600 text-gray-300 rounded-lg p-2 focus:ring-green-400 focus:border-green-400">
                                    <option value="dark">Escuro (Padrão)</option>
                                    <option value="darker">Mais Escuro</option>
                                    <option value="green">Verde Neon</option>
                                    <option value="blue">Azul</option>
                                </select>
                            </div>
                            <div class="flex items-center">
                                <input type="checkbox" id="save-settings" class="w-5 h-5 text-green-500 rounded focus:ring-green-400" checked>
                                <label for="save-settings" class="ml-2 text-gray-300">Salvar configurações automaticamente</label>
                            </div>
                            <div class="flex items-center">
                                <input type="checkbox" id="notifications" class="w-5 h-5 text-green-500 rounded focus:ring-green-400" checked>
                                <label for="notifications" class="ml-2 text-gray-300">Ativar notificações</label>
                            </div>
                        </div>
                    </div>

                    <div class="bg-gray-900 p-4 rounded-lg mb-6">
                        <h3 class="text-lg font-semibold mb-3 text-green-300">Configurações de Segurança</h3>
                        <div class="space-y-4">
                            <div class="flex items-center">
                                <input type="checkbox" id="auto-disable" class="w-5 h-5 text-green-500 rounded focus:ring-green-400" checked>
                                <label for="auto-disable" class="ml-2 text-gray-300">Desativar automaticamente se detectado</label>
                            </div>
                            <div>
                                <label for="detection-level" class="block text-gray-300 mb-1">Nível de Detecção</label>
                                <select id="detection-level" class="w-full bg-gray-700 border border-gray-600 text-gray-300 rounded-lg p-2 focus:ring-green-400 focus:border-green-400">
                                    <option value="low">Baixo (Mais rápido)</option>
                                    <option value="medium" selected>Médio (Recomendado)</option>
                                    <option value="high">Alto (Mais seguro)</option>
                                </select>
                            </div>
                            <div>
                                <label for="random-delay" class="block text-gray-300 mb-1">Atraso Aleatório</label>
                                <select id="random-delay" class="w-full bg-gray-700 border border-gray-600 text-gray-300 rounded-lg p-2 focus:ring-green-400 focus:border-green-400">
                                    <option value="0">Desativado</option>
                                    <option value="1">1-3 segundos</option>
                                    <option value="2" selected>2-5 segundos</option>
                                    <option value="5">5-10 segundos</option>
                                </select>
                            </div>
                        </div>
                    </div>

                    <div class="flex justify-between">
                        <button class="bg-gray-600 hover:bg-gray-700 text-white font-bold py-2 px-6 rounded-lg transition-all duration-300 btn-hover">
                            <i class="fas fa-redo mr-2"></i> Redefinir
                        </button>
                        <button class="bg-green-600 hover:bg-green-700 text-white font-bold py-2 px-6 rounded-lg transition-all duration-300 btn-hover">
                            <i class="fas fa-save mr-2"></i> Salvar Configurações
                        </button>
                    </div>
                </div>
            </div>
        </div>

        <!-- Footer -->
        <footer class="mt-8 text-center text-gray-400 text-sm">
            <p>Script Trilhos Mortos [Alfa] Premium © 2023 - Todos os direitos reservados</p>
            <p class="mt-1">Sistema de bypass integrado - v2.5.1</p>
        </footer>
    </div>

    <script>
        // Tab switching functionality
        document.querySelectorAll('.tab-btn').forEach(btn => {
            btn.addEventListener('click', () => {
                // Remove active class from all buttons and contents
                document.querySelectorAll('.tab-btn').forEach(b => {
                    b.classList.remove('text-green-400', 'border-b-2', 'border-green-400');
                    b.classList.add('text-gray-400');
                });
                
                // Add active class to clicked button
                btn.classList.remove('text-gray-400');
                btn.classList.add('text-green-400', 'border-b-2', 'border-green-400');
                
                // Show corresponding content
                const tabId = btn.getAttribute('data-tab');
                document.querySelectorAll('.tab-content').forEach(content => {
                    content.classList.remove('active');
                });
                document.getElementById(tabId).classList.add('active');
            });
        });

        // Auto Farm statistics simulation
        let coins = 0;
        let items = 0;
        let seconds = 0;
        let bypassSeconds = 0;
        
        document.getElementById('start-farm').addEventListener('click', function() {
            this.innerHTML = '<i class="fas fa-sync-alt mr-2 animate-spin"></i> Farmeando...';
            this.classList.remove('bg-green-600', 'hover:bg-green-700');
            this.classList.add('bg-yellow-600', 'hover:bg-yellow-700');
            
            // Simulate farming
            const coinInterval = setInterval(() => {
                coins += Math.floor(Math.random() * 5) + 1;
                document.getElementById('coins-collected').textContent = coins;
            }, 3000);
            
            const itemInterval = setInterval(() => {
                items += Math.floor(Math.random() * 2) + 1;
                document.getElementById('items-collected').textContent = items;
            }, 5000);
            
            const timeInterval = setInterval(() => {
                seconds++;
                const hours = Math.floor(seconds / 3600);
                const minutes = Math.floor((seconds % 3600) / 60);
                const secs = seconds % 60;
                document.getElementById('uptime').textContent = 
                    `${hours.toString().padStart(2, '0')}:${minutes.toString().padStart(2, '0')}:${secs.toString().padStart(2, '0')}`;
            }, 1000);
            
            // Stop button functionality
            const stopBtn = document.createElement('button');
            stopBtn.id = 'stop-farm';
            stopBtn.className = 'bg-red-600 hover:bg-red-700 text-white font-bold py-3 px-8 rounded-lg transition-all duration-300 btn-hover flex items-center ml-4';
            stopBtn.innerHTML = '<i class="fas fa-stop mr-2"></i> Parar';
            
            stopBtn.addEventListener('click', function() {
                clearInterval(coinInterval);
                clearInterval(itemInterval);
                clearInterval(timeInterval);
                document.getElementById('start-farm').innerHTML = '<i class="fas fa-play mr-2"></i> Iniciar Auto Farm';
                document.getElementById('start-farm').classList.remove('bg-yellow-600', 'hover:bg-yellow-700');
                document.getElementById('start-farm').classList.add('bg-green-600', 'hover:bg-green-700');
                this.remove();
            });
            
            this.parentNode.appendChild(stopBtn);
        });

        // Bypass system simulation
        const bypassInterval = setInterval(() => {
            bypassSeconds++;
            const hours = Math.floor(bypassSeconds / 3600);
            const minutes = Math.floor((bypassSeconds % 3600) / 60);
            const secs = bypassSeconds % 60;
            document.getElementById('bypass-uptime').textContent = 
                `${hours.toString().padStart(2, '0')}:${minutes.toString().padStart(2, '0')}:${secs.toString().padStart(2, '0')}`;
            
            // Update last check time
            const now = new Date();
            document.getElementById('last-check').textContent = `${now.getHours().toString().padStart(2, '0')}:${now.getMinutes().toString().padStart(2, '0')}:${now.getSeconds().toString().padStart(2, '0')}`;
        }, 1000);

        // Test bypass button
        document.getElementById('test-bypass').addEventListener('click', function() {
            this.innerHTML = '<i class="fas fa-spinner mr-2 animate-spin"></i> Testando...';
            
            setTimeout(() => {
                this.innerHTML = '<i class="fas fa-check-circle mr-2"></i> Bypass Funcionando';
                this.classList.remove('bg-yellow-600', 'hover:bg-yellow-700');
                this.classList.add('bg-green-600', 'hover:bg-green-700');
                
                setTimeout(() => {
                    this.innerHTML = '<i class="fas fa-vial mr-2"></i> Testar Bypass';
                    this.classList.remove('bg-green-600', 'hover:bg-green-700');
                    this.classList.add('bg-yellow-600', 'hover:bg-yellow-700');
                }, 2000);
            }, 1500);
        });

        // Update bypass button
        document.getElementById('update-bypass').addEventListener('click', function() {
            this.innerHTML = '<i class="fas fa-spinner mr-2 animate-spin"></i> Atualizando...';
            
            setTimeout(() => {
                this.innerHTML = '<i class="fas fa-check-circle mr-2"></i> Bypass Atualizado';
                this.classList.remove('bg-purple-600', 'hover:bg-purple-700');
                this.classList.add('bg-green-600', 'hover:bg-green-700');
                
                setTimeout(() => {
                    this.innerHTML = '<i class="fas fa-sync-alt mr-2"></i> Atualizar Bypass';
                    this.classList.remove('bg-green-600', 'hover:bg-green-700');
                    this.classList.add('bg-purple-600', 'hover:bg-purple-700');
                }, 2000);
            }, 2000);
        });

        // Theme switcher simulation
        document.getElementById('ui-theme').addEventListener('change', function() {
            const theme = this.value;
            const body = document.body;
            
            // Remove all theme classes
            body.classList.remove('theme-dark', 'theme-darker', 'theme-green', 'theme-blue');
            
            // Add selected theme class
            if (theme !== 'dark') {
                body.classList.add(`theme-${theme}`);
            }
            
            // Show notification
            if (document.getElementById('notifications').checked) {
                alert(`Tema alterado para: ${this.options[this.selectedIndex].text}`);
            }
        });

        // Settings save simulation
        document.querySelector('#settings button.bg-green-600').addEventListener('click', function() {
            if (document.getElementById('notifications').checked) {
                alert('Configurações salvas com sucesso!');
            }
        });
    </script>
</body>
</html>
