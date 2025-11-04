**HTML**
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CINEBOX - Venda de Ingressos</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <header>
    <h1>CINEBOX</h1>
    <nav>
  <nav>
  <a href="#" onclick="mostrarPagina('login')">Home</a>
  <a href="#" onclick="mostrarPagina('perfil')">Perfil</a>
  <a href="#" onclick="mostrarPagina('login')">Sair</a>
</nav>

</nav>

    </nav>
  </header>

  <!-- LOGIN -->
  <section id="login" class="form-container">
    <h2>Login</h2>
    <form onsubmit="return loginUsuario(event)">
      <input type="email" id="email" placeholder="E-mail" required>
      <input type="password" id="senha" placeholder="Senha" required>
      <button type="submit">Entrar</button>
      <p>Não tem conta? <a href="#" onclick="mostrarPagina('cadastro')">Cadastre-se</a></p>
    </form>
  </section>

  <!-- CADASTRO -->
  <section id="cadastro" class="form-container hidden">
    <h2>Cadastrar</h2>
    <form onsubmit="return cadastrarUsuario(event)">
      <input type="email" id="emailCadastro" placeholder="E-mail" required>
      <input type="text" id="telefone" placeholder="Telefone" required>
      <input type="password" id="senhaCadastro" placeholder="Senha" required>
      <button type="submit">Cadastrar</button>
      <button type="button" class="voltar-btn" onclick="voltarPagina()">Voltar</button>
    </form>
  </section>

  <!-- HOME -->
  <section id="emcartaz" class="filmes hidden">
    <h2>Em Cartaz</h2>
    <div class="filmes-container">
      <div class="filme">
        <img src="https://m.media-amazon.com/images/M/MV5BMzczOGVhNzUtNTVhOS00OGE0LWFkODItOTNkNWVkMzc0MTcyXkEyXkFqcGc@._V1_.jpg" alt="The Doll 3">
        <h3>The Doll 3</h3>
        <button onclick="comprarIngresso('The Doll 3')">Comprar Ingresso</button>
      </div>
      <div class="filme">
        <img src="https://br.web.img3.acsta.net/r_1920_1080/pictures/22/12/01/18/05/5068187.jpg" alt="Top Gun Maverick">
        <h3>Top Gun Maverick</h3>
        <button onclick="comprarIngresso('Top Gun Maverick')">Comprar Ingresso</button>
      </div>
      <div class="filme">
        <img src="https://media.fstatic.com/MeS7WOL5PjUJeUwbmLsSmHtrclw=/322x478/smart/filters:format(webp)/media/movies/covers/2020/02/KKK.webp" alt="KKN Di Desa Penari">
        <h3>KKN Di Desa Penari</h3>
        <button onclick="comprarIngresso('KKN Di Desa Penari')">Comprar Ingresso</button>
      </div>
    </div>
  </section>

  <!-- ASSENTOS -->
  <section id="assentos" class="assentos hidden">
    <h2>Selecione seu assento</h2>
    <p id="filmeAssento"></p>

    <div class="tela">TELA</div>

    <div class="grade-assentos" id="gradeAssentos"></div>

    <div class="legenda">
      <span><div class="livre"></div> Livre</span>
      <span><div class="ocupado"></div> Ocupado</span>
      <span><div class="selecionado"></div> Selecionado</span>
    </div>

    <button onclick="confirmarAssentos()">Confirmar Assentos</button>
    <button type="button" class="voltar-btn" onclick="voltarPagina()">Voltar</button>
  </section>

  <!-- PAGAMENTO -->
  <section id="pagamento" class="form-container hidden">
    <h2>Pagamento</h2>
    <p id="filmeSelecionado"></p>
    <form onsubmit="return confirmarPagamento(event)">
      <input type="text" placeholder="Nome no cartão" required>
      <input type="text" placeholder="Número do cartão" required>
      <input type="text" placeholder="Data de vencimento" required>
      <input type="text" placeholder="CVV" required>
      <button type="submit">Pagar</button>
      <button type="button" class="voltar-btn" onclick="voltarPagina()">Voltar</button>
    </form>
  </section>

  <!-- SUCESSO -->
  <section id="sucesso" class="sucesso hidden">
    <h3>PAGAMENTO EFETUADO COM SUCESSO!</h3>
    <p>Seu ingresso foi reservado.</p>
    <button onclick="irParaHome()">Retornar para Home</button>
    <button type="button" class="voltar-btn" onclick="voltarPagina()">Voltar</button>
  </section>

  <!-- PERFIL -->
  <section id="perfil" class="perfil-container hidden">
    <h2>Meu Perfil</h2>
    <input type="text" placeholder="Nome">
    <input type="text" placeholder="Sobrenome">
    <input type="email" placeholder="E-mail">
    <input type="tel" placeholder="Telefone">
    <button>Atualizar Perfil</button>
    <button type="button" class="voltar-btn" onclick="voltarPagina()">Voltar</button>
  </section>

  <script src="script.js"></script>
</body>
</html>



*CSS**

body {
  font-family: 'Poppins', sans-serif;
  background: linear-gradient(180deg, #0f1c5d, #7b1fa2);
  color: white;
  margin: 0;
  padding: 0;
}

header {
  background-color: #0d1647;
  padding: 20px;
  text-align: center;
}

header h1 {
  margin: 0;
  color: #00bcd4;
}

nav a {
  color: white;
  margin: 0 10px;
  text-decoration: none;
}

.hidden {
  display: none;
}

/* Seção filmes */
.filmes {
  padding: 20px;
  text-align: center;
}

.filmes-container {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 20px;
}

.filme {
  background: #1c267a;
  border-radius: 15px;
  padding: 10px;
  width: 200px;
}

.filme img {
  width: 100%;
  height: 300px;          /* Altura fixa para todas as imagens */
  object-fit: cover;      /* Corta proporcionalmente sem distorcer */
  border-radius: 10px;
}

button {
  background-color: #00bcd4;
  color: white;
  border: none;
  border-radius: 10px;
  padding: 10px 15px;
  cursor: pointer;
  width: 100%;
  margin-top: 10px;
  font-weight: bold;
}

button:hover {
  background-color: #0097a7;
}

/* Formulários */
.form-container, .perfil-container {
  max-width: 350px;
  margin: 50px auto;
  background: #1c267a;
  border-radius: 15px;
  padding: 25px;
  text-align: center;
}

input {
  width: 90%;
  padding: 10px;
  margin: 10px 0;
  border-radius: 10px;
  border: none;
}

h2 {
  margin-bottom: 10px;
}

a {
  color: #00bcd4;
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}

/* Mensagem de sucesso */
.sucesso {
  background: linear-gradient(180deg, #7b1fa2, #00bcd4);
  padding: 30px;
  border-radius: 15px;
  text-align: center;
  max-width: 350px;
  margin: 80px auto;
}

.voltar-btn {
  background-color: #ff9800;
  margin-top: 15px;
}

.voltar-btn:hover {
  background-color: #e68900;
}

/* Página de assentos */
.assentos {
  text-align: center;
  padding: 20px;
}

.tela {
  background-color: #fff;
  color: #000;
  padding: 8px;
  border-radius: 10px;
  width: 60%;
  margin: 10px auto 20px;
  font-weight: bold;
}

.grade-assentos {
  display: grid;
  grid-template-columns: repeat(10, 30px);
  gap: 8px;
  justify-content: center;
  margin-bottom: 15px;
}

.assento {
  width: 30px;
  height: 30px;
  border-radius: 6px;
  background-color: #e91e63;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  font-size: 12px;
}

.assento.ocupado {
  background-color: #3f51b5;
  cursor: not-allowed;
}

.assento.selecionado {
  background-color: #ff9800;
}

.legenda {
  display: flex;
  justify-content: center;
  gap: 15px;
  margin-bottom: 20px;
}

.legenda span {
  display: flex;
  align-items: center;
  gap: 5px;
}

.legenda div {
  width: 15px;
  height: 15px;
  border-radius: 4px;
}

.livre { background-color: #e91e63; }
.ocupado { background-color: #3f51b5; }
.selecionado { background-color: #ff9800; }


**SCRIPT**

let paginaAnterior = 'login';
let filmeSelecionado = '';
let assentosSelecionados = [];

function mostrarPagina(pagina) {
  document.querySelectorAll('section').forEach(sec => sec.classList.add('hidden'));
  document.getElementById(pagina).classList.remove('hidden');
  if (pagina !== 'sucesso') paginaAnterior = pagina;
}

function voltarPagina() {
  mostrarPagina(paginaAnterior);
}

function loginUsuario(e) {
  e.preventDefault();
  alert('Login realizado com sucesso!');
  paginaAnterior = 'login';
  mostrarPagina('emcartaz');
}

function cadastrarUsuario(e) {
  e.preventDefault();
  alert('Cadastro realizado com sucesso!');
  paginaAnterior = 'cadastro';
  mostrarPagina('login');
}

function comprarIngresso(filme) {
  filmeSelecionado = filme;
  document.getElementById('filmeAssento').textContent = `Filme: ${filme}`;
  criarAssentos();
  paginaAnterior = 'emcartaz';
  mostrarPagina('assentos');
}

function criarAssentos() {
  const grade = document.getElementById('gradeAssentos');
  grade.innerHTML = '';
  assentosSelecionados = [];
  for (let i = 1; i <= 100; i++) {
    const assento = document.createElement('div');
    assento.classList.add('assento');
    assento.textContent = i;
    if (Math.random() < 0.2) assento.classList.add('ocupado'); // 20% ocupados
    assento.onclick = () => selecionarAssento(assento);
    grade.appendChild(assento);
  }
}

function selecionarAssento(assento) {
  if (assento.classList.contains('ocupado')) return;
  assento.classList.toggle('selecionado');
  const numero = assento.textContent;
  if (assento.classList.contains('selecionado')) {
    assentosSelecionados.push(numero);
  } else {
    assentosSelecionados = assentosSelecionados.filter(a => a !== numero);
  }
}

function confirmarAssentos() {
  if (assentosSelecionados.length === 0) {
    alert('Selecione pelo menos um assento!');
    return;
  }
  document.getElementById('filmeSelecionado').textContent =
    `Filme: ${filmeSelecionado} | Assentos: ${assentosSelecionados.join(', ')}`;
  paginaAnterior = 'assentos';
  mostrarPagina('pagamento');
}

function confirmarPagamento(e) {
  e.preventDefault();
  paginaAnterior = 'pagamento';
  mostrarPagina('sucesso');
}

mostrarPagina('login');

function irParaHome() {
  assentosSelecionados = []; // Limpa os assentos selecionados
  filmeSelecionado = '';     // Limpa o filme selecionado
  paginaAnterior = 'login';  // Reseta o histórico
  mostrarPagina('login');     // volta para a tela inicial de login
}


