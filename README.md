<h1> Agrinho 2026      Pietro Vinicius n22
<div class="container">
  <header>
    <h2>Agro Forte, Futuro Sustentável</h2>
    <p>Conectando tecnologia e preservação ambiental</p>
  </header>

  <main class="dashboard">
    <div class="card" id="card-umidade">
      <h3>Umidade do Solo</h3>
      <div class="sensor-value"><span id="umidade">45</span>%</div>
      <p id="status-solo">Status: Carregando...</p>
    </div>

    <div class="card">
      <h3>Temperatura do Campo</h3>
      <div class="sensor-value"><span id="temperatura">26</span>°C</div>
      <p>Clima ideal para plantio</p>
    </div>
  </main>

  <section class="actions">
    <button onclick="irrigar()">Ativar Irrigação Inteligente 💧</button>
    <button onclick="atualizarSensores()">Simular Novas Leituras 🔄</button>
  </section>

  <div id="alerta" class="alerta escondido"></div>
</div
}body {
  margin: 0;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background-color: #f4f9f4;
  color: #2c3e50;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
}

.container {
  background: #ffffff;
  border-radius: 15px;
  padding: 30px;
  box-shadow: 0 10px 20px rgba(0,0,0,0.05);
  max-width: 600px;
  width: 100%;
  text-align: center;
  border-top: 8px solid #2ecc71;
}

header h1 {
  color: #27ae60;
  margin-bottom: 5px;
}

header h2 {
  font-size: 1.2rem;
  color: #7f8c8d;
  margin-top: 0;
}

.dashboard {
  display: flex;
  gap: 20px;
  margin: 30px 0;
}

.card {
  flex: 1;
  background: #f9fbf9;
  border: 1px solid #e2eee2;
  border-radius: 10px;
  padding: 20px;
  transition: transform 0.2s;
}

.card:hover {
  transform: translateY(-5px);
}

.sensor-value {
  font-size: 2.5rem;
  font-weight: bold;
  color: #2c3e50;
  margin: 10px 0;
}

button {
  background-color: #27ae60;
  color: white;
  border: none;
  padding: 12px 20px;
  font-size: 1rem;
  border-radius: 25px;
  cursor: pointer;
  margin: 5px;
  font-weight: bold;
  transition: background 0.3s;
}

button:hover {
  background-color: #219653;
}

.alerta {
  margin-top: 20px;
  padding: 15px;
  background-color: #3498db;
  color: white;
  border-radius: 8px;
  font-weight: bold;
}

.escondido {
  display: none;
}
document.getElementsByTagName("h1")[0].style.fontSize = "6vw";// Função para simular a mudança dos sensores no campo
function atualizarSensores() {
  // Gera valores aleatórios realistas
  const novaUmidade = Math.floor(Math.random() * (80 - 30) + 30);
  const novaTemperatura = Math.floor(Math.random() * (35 - 18) + 18);

  // Atualiza o texto na tela
  document.getElementById('umidade').innerText = novaUmidade;
  document.getElementById('temperatura').innerText = novaTemperatura;

  // Analisa o status do solo baseado na umidade
  const statusSolo = document.getElementById('status-solo');
  if (novaUmidade < 40) {
    statusSolo.innerText = "Status: Solo Seco! Precisa de água.";
    statusSolo.style.color = "#e74c3c";
  } else if (novaUmidade > 70) {
    statusSolo.innerText = "Status: Solo Encharcado!";
    statusSolo.style.color = "#f39c12";
  } else {
    statusSolo.innerText = "Status: Umidade Ideal ✅";
    statusSolo.style.color = "#27ae60";
  }
}

// Função executada ao clicar no botão de irrigação
function irrigar() {
  const alerta = document.getElementById('alerta');
  alerta.classList.remove('escondido');
  alerta.innerText = "💧 Irrigadores ativados! Economizando água com base nos dados do sensor.";

  // Força a umidade a subir após a irrigação
  setTimeout(() => {
    document.getElementById('umidade').innerText = "65";
    document.getElementById('status-solo').innerText = "Status: Umidade Ideal ✅";
    document.getElementById('status-solo').style.color = "#27ae60";
  }, 1500);

  // Esconde a mensagem depois de 4 segundos
  setTimeout(() => {
    alerta.classList.add('escondido');
  }, 4000);
}

// Executa uma vez ao abrir a página para definir os valores iniciais
atualizarSensores();
