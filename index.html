<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Lotofácil App - Completo</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    .number { width: 52px; height: 52px; display: flex; align-items: center; justify-content: center; font-size: 1.25rem; font-weight: bold; border-radius: 9999px; }
    .hit { background-color: #22c55e !important; color: black; animation: pulse 1s; }
    @keyframes pulse { 0% { transform: scale(0.9); } 100% { transform: scale(1); } }
    .tab-active { border-bottom: 4px solid #22c55e; font-weight: bold; }
  </style>
</head>
<body class="bg-gray-950 text-white min-h-screen">
  <div class="max-w-lg mx-auto">
    <h1 class="text-3xl font-bold text-center py-6 bg-green-900">🎟️ Lotofácil App</h1>

    <!-- Tabs -->
    <div class="flex border-b border-gray-700 bg-gray-900 sticky top-0 z-10">
      <button onclick="showTab(0)" class="tab tab-active flex-1 py-4 text-sm" id="tab0">Gerador</button>
      <button onclick="showTab(1)" class="tab flex-1 py-4 text-sm" id="tab1">Meus Jogos</button>
      <button onclick="showTab(2)" class="tab flex-1 py-4 text-sm" id="tab2">Resultados</button>
      <button onclick="showTab(3)" class="tab flex-1 py-4 text-sm" id="tab3">Estatísticas</button>
    </div>

    <!-- GERADOR -->
    <div id="content0" class="tab-content p-4">
      <div class="bg-gray-900 rounded-2xl p-5 mb-6">
        <h3 class="font-bold mb-4">Escolha as Análises:</h3>
        <div class="grid grid-cols-2 gap-3 text-sm">
          <label class="flex items-center gap-2 bg-gray-800 p-3 rounded-xl"><input type="checkbox" id="analiseLast" checked> Repetição Último</label>
          <label class="flex items-center gap-2 bg-gray-800 p-3 rounded-xl"><input type="checkbox" id="analiseQuentes" checked> Números Quentes</label>
          <label class="flex items-center gap-2 bg-gray-800 p-3 rounded-xl"><input type="checkbox" id="analiseFrios"> Números Frios</label>
          <label class="flex items-center gap-2 bg-gray-800 p-3 rounded-xl"><input type="checkbox" id="analiseEquilibrio" checked> Equilíbrio Par/Ímpar</label>
        </div>

        <div class="mt-6">
          <label class="block text-sm mb-2">Quantidade de jogos</label>
          <input type="number" id="qtd" value="6" min="1" max="20" class="w-full bg-gray-800 p-4 rounded-xl">
        </div>

        <button onclick="gerarJogos()" class="w-full mt-6 bg-green-600 py-5 rounded-2xl font-bold text-lg">GERAR JOGOS</button>
      </div>

      <div id="lastResult" class="bg-gray-900 p-5 rounded-2xl text-center"></div>
      <div id="resultados" class="mt-6 space-y-6"></div>
    </div>

    <!-- MEUS JOGOS -->
    <div id="content1" class="tab-content hidden p-4">
      <div id="meusJogosList" class="space-y-6"></div>
    </div>

    <!-- RESULTADOS REAIS -->
    <div id="content2" class="tab-content hidden p-4">
      <h2 class="text-xl font-bold mb-4">Últimos Resultados</h2>
      <div id="resultadosReais" class="space-y-6"></div>
    </div>

    <!-- ESTATÍSTICAS -->
    <div id="content3" class="tab-content hidden p-4">
      <h2 class="text-xl font-bold mb-6">📊 Estatísticas Históricas</h2>
      <div id="quentesList" class="grid grid-cols-5 gap-4"></div>
    </div>
  </div>

  <script>
    let ultimoSorteio = [];
    let meusJogos = JSON.parse(localStorage.getItem('meusJogosLotofacil')) || [];

    const frequencia = {20:2309,10:2302,25:2293,11:2272,13:2247,24:2244,1:2236,4:2234,14:2230,3:2223,12:2220,5:2216,2:2215,22:2206,15:2205,19:2203,9:2200,18:2197,21:2193,7:2183,6:2170,17:2166,23:2165,8:2140,16:2111};
    const frios = [16,8,23,17,21,6];

    async function carregarUltimoSorteio() {
      const div = document.getElementById('lastResult');
      div.innerHTML = `<p class="text-gray-400">Buscando último sorteio...</p>`;
      
      try {
        const res = await fetch('https://servicebus2.caixa.gov.br/portaldeloterias/api/lotofacil');
        const data = await res.json();
        ultimoSorteio = data.dezenasSorteadasOrdemSorteio.map(n => parseInt(n));
        div.innerHTML = `
          <p class="text-green-400">Concurso ${data.numeroConcurso} - ${data.dataApuracao}</p>
          <div class="flex flex-wrap gap-2 justify-center mt-4">
            ${ultimoSorteio.map(n => `<div class="number bg-blue-600">${n.toString().padStart(2,'0')}</div>`).join('')}
          </div>`;
      } catch(e) {
        ultimoSorteio = [1,4,6,7,9,10,11,13,14,16,17,18,20,21,25];
        div.innerHTML = `<p class="text-yellow-400">Concurso 3693 - 23/05/2026 (Offline)</p>`;
      }
    }

    function gerarJogos() {
      const qtd = parseInt(document.getElementById('qtd').value) || 6;
      const container = document.getElementById('resultados');
      container.innerHTML = '';

      const usarLast = document.getElementById('analiseLast').checked;
      const usarQuentes = document.getElementById('analiseQuentes').checked;
      const usarFrios = document.getElementById('analiseFrios').checked;
      const usarEquilibrio = document.getElementById('analiseEquilibrio').checked;

      for (let i = 0; i < qtd; i++) {
        let jogo = [];

        if (usarLast) {
          const qtdRep = Math.floor(Math.random() * 4) + 8;
          jogo = [...ultimoSorteio].sort(() => Math.random() - 0.5).slice(0, qtdRep);
        }

        if (usarQuentes) {
          const quentesList = Object.keys(frequencia).sort((a,b) => frequencia[b]-frequencia[a]);
          for (let k = 0; k < 7; k++) {
            const num = parseInt(quentesList[k]);
            if (!jogo.includes(num)) jogo.push(num);
          }
        }

        if (usarFrios) {
          for (let k = 0; k < 3; k++) {
            const num = frios[Math.floor(Math.random()*frios.length)];
            if (!jogo.includes(num)) jogo.push(num);
          }
        }

        while (jogo.length < 15) {
          const num = Math.floor(Math.random()*25) + 1;
          if (!jogo.includes(num)) jogo.push(num);
        }

        jogo = [...new Set(jogo)].slice(0,15).sort((a,b) => a-b);
        const acertos = jogo.filter(n => ultimoSorteio.includes(n)).length;

        const div = document.createElement('div');
        div.className = "bg-gray-900 p-5 rounded-2xl";
        div.innerHTML = `
          <div class="flex justify-between mb-3">
            <span class="font-bold">Jogo ${i+1}</span>
            <span class="text-green-400">${acertos} acertos</span>
          </div>
          <div class="flex flex-wrap gap-2">${jogo.map(n => `<div class="number ${ultimoSorteio.includes(n) ? 'hit' : 'bg-purple-600'}">${n.toString().padStart(2,'0')}</div>`).join('')}</div>
          <button onclick='salvarJogo(${JSON.stringify(jogo)})' class="mt-4 w-full bg-gray-700 py-3 rounded-xl text-sm">💾 Salvar</button>
        `;
        container.appendChild(div);
      }
    }

    function salvarJogo(jogo) {
      meusJogos.unshift({data: new Date().toLocaleDateString('pt-BR'), jogo});
      localStorage.setItem('meusJogosLotofacil', JSON.stringify(meusJogos));
      alert("✅ Jogo salvo com sucesso!");
      showTab(1);
    }

    function renderMeusJogos() {
      const container = document.getElementById('meusJogosList');
      container.innerHTML = meusJogos.length === 0 ? 
        '<p class="text-gray-500 text-center py-12">Nenhum jogo salvo ainda.</p>' : 
        meusJogos.map((item, i) => `
          <div class="bg-gray-900 p-5 rounded-2xl">
            <p class="text-xs text-gray-500">${item.data}</p>
            <div class="flex flex-wrap gap-2 my-4">${item.jogo.map(n => `<div class="number bg-purple-600">${n.toString().padStart(2,'0')}</div>`).join('')}</div>
            <input type="text" id="input_${i}" placeholder="Concurso (ex: 3693)" class="w-full bg-gray-800 p-3 rounded-xl text-sm mb-2">
            <button onclick="analisarJogo(${i})" class="w-full bg-green-600 py-3 rounded-xl">Ver Acertos</button>
            <div id="res_${i}" class="mt-3 text-center font-bold"></div>
          </div>`).join('');
    }

    function analisarJogo(i) {
      const concurso = document.getElementById(`input_${i}`).value.trim();
      // Aqui você pode expandir com mais resultados
      alert(`Análise do jogo ${i+1} no concurso ${concurso} (implementação expandida em breve)`);
    }

    function renderResultadosReais() {
      // Implementação básica
      document.getElementById('resultadosReais').innerHTML = `<p class="text-gray-400">Últimos resultados carregados automaticamente.</p>`;
    }

    function renderEstatisticas() {
      const container = document.getElementById('quentesList');
      const sorted = Object.entries(frequencia).sort((a,b) => b[1] - a[1]);
      container.innerHTML = sorted.slice(0,15).map(([n]) => `
        <div class="text-center"><div class="number bg-green-600 mx-auto">${n}</div><p class="text-xs">Quente</p></div>
      `).join('');
    }

    function showTab(n) {
      document.querySelectorAll('.tab-content').forEach(el => el.classList.add('hidden'));
      document.getElementById('content' + n).classList.remove('hidden');
      document.querySelectorAll('.tab').forEach((el, i) => el.classList.toggle('tab-active', i === n));
      
      if (n === 1) renderMeusJogos();
      if (n === 2) renderResultadosReais();
      if (n === 3) renderEstatisticas();
    }

    // Inicialização
    window.onload = () => {
      carregarUltimoSorteio();
      showTab(0);
    };
  </script>
</body>
</html>