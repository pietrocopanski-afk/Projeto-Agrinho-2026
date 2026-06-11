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
