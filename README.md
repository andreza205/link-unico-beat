
<html lang="pt-BR">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Link Único Beat - Painel & Página</title>
<style>
  :root {
    --cor-principal: #ff69b4;
    --cor-fundo: #222;
    --cor-texto: #fff;
  }

  body {
    margin: 0; font-family: Arial, sans-serif;
    background-color: var(--cor-fundo);
    color: var(--cor-texto);
    text-align: center;
    padding: 20px;
  }

  .hidden { display: none; }

  /* Login */
  #login-container {
    max-width: 300px;
    margin: 80px auto;
    background: #333;
    padding: 25px;
    border-radius: 12px;
  }
  #login-container h2 {
    margin-bottom: 15px;
    color: var(--cor-principal);
  }
  #login-container input {
    width: 90%;
    padding: 10px;
    margin: 8px 0;
    border-radius: 6px;
    border: none;
    font-size: 1rem;
  }
  #login-container button {
    background: var(--cor-principal);
    color: white;
    border: none;
    padding: 10px 15px;
    border-radius: 6px;
    font-weight: bold;
    cursor: pointer;
  }
  #login-error {
    color: #f55;
    margin-top: 10px;
  }

  /* Painel */
  #painel {
    max-width: 600px;
    margin: auto;
    background: rgba(0,0,0,0.8);
    border-radius: 15px;
    padding: 20px;
    text-align: left;
  }
  #painel h2 {
    color: var(--cor-principal);
    margin-bottom: 15px;
  }
  #painel label {
    display: block;
    margin-top: 15px;
    font-weight: bold;
  }
  #painel input[type="text"],
  #painel input[type="url"],
  #painel textarea,
  #painel input[type="color"] {
    width: 100%;
    padding: 8px;
    margin-top: 5px;
    border-radius: 6px;
    border: none;
    font-size: 1rem;
  }
  #painel textarea {
    resize: vertical;
    height: 80px;
  }
  #painel button {
    margin-top: 20px;
    background: var(--cor-principal);
    color: white;
    border: none;
    padding: 12px 20px;
    border-radius: 10px;
    font-weight: bold;
    cursor: pointer;
  }
  #logout-btn {
    background: #f33;
    margin-top: 10px;
  }

  /* Página pública */
  #pagina-publica {
    max-width: 600px;
    margin: 40px auto;
    background: rgba(0,0,0,0.7);
    border-radius: 20px;
    padding: 30px;
    text-align: center;
  }
  #pagina-publica img.foto-perfil {
    width: 120px;
    height: 120px;
    border-radius: 50%;
    object-fit: cover;
    border: 4px solid var(--cor-principal);
  }
  #pagina-publica h1 {
    margin: 10px 0 5px 0;
    color: var(--cor-principal);
  }
  #pagina-publica .bio {
    margin: 15px 0;
  }
  #pagina-publica .aviso {
    background-color: var(--cor-principal);
    padding: 10px;
    border-radius: 10px;
    margin: 20px 0;
    font-weight: bold;
  }
  #pagina-publica .links {
    display: flex;
    flex-direction: column;
    gap: 12px;
  }
  #pagina-publica .links a {
    background-color: var(--cor-principal);
    color: #fff;
    text-decoration: none;
    padding: 12px;
    border-radius: 8px;
    font-weight: bold;
    transition: 0.3s;
  }
  #pagina-publica .links a:hover {
    background-color: #fff;
    color: var(--cor-principal);
  }
  #pagina-publica footer {
    margin-top: 30px;
    font-size: 12px;
    color: #ccc;
  }
</style>
</head>
<body>

<!-- LOGIN -->
<div id="login-container">
  <h2>Login</h2>
  <input id="usuario" type="text" placeholder="Usuário" autocomplete="off" />
  <input id="senha" type="password" placeholder="Senha" autocomplete="off" />
  <button onclick="login()">Entrar</button>
  <div id="login-error"></div>
</div>

<!-- PAINEL -->
<div id="painel" class="hidden">
  <h2>Painel de Controle</h2>

  <label for="inputNome">Nome:</label>
  <input type="text" id="inputNome" placeholder="Nome da pessoa" />

  <label for="inputFoto">URL da Foto de Perfil:</label>
  <input type="url" id="inputFoto" placeholder="Link da imagem da foto de perfil" />

  <label for="inputBio">Biografia:</label>
  <textarea id="inputBio" placeholder="Ex: 22 anos | Criador de conteúdo..."></textarea>

  <label for="inputAviso">Avisos (use emojis e quebre linha com Enter):</label>
  <textarea id="inputAviso" placeholder="Ex: 🚨 Live no TikTok dia 10/06 às 20h"></textarea>

  <label for="inputInstagram">Link Instagram:</label>
  <input type="url" id="inputInstagram" placeholder="https://instagram.com/usuario" />

  <label for="inputTikTok">Link TikTok:</label>
  <input type="url" id="inputTikTok" placeholder="https://tiktok.com/@usuario" />

  <label for="inputSpotify">Link Spotify:</label>
  <input type="url" id="inputSpotify" placeholder="https://spotify.com/usuario" />

  <label for="inputFacebook">Link Facebook:</label>
  <input type="url" id="inputFacebook" placeholder="https://facebook.com/usuario" />

  <label for="inputYouTube">Link YouTube:</label>
  <input type="url" id="inputYouTube" placeholder="https://youtube.com/seucanal" />

  <label for="inputCorPrincipal">Cor principal (links, bordas):</label>
  <input type="color" id="inputCorPrincipal" value="#ff69b4" />

  <label for="inputCorFundo">Cor do fundo da página:</label>
  <input type="color" id="inputCorFundo" value="#222222" />

  <button onclick="salvar()">Salvar alterações</button>
  <button id="logout-btn" onclick="logout()">Sair</button>
</div>

<!-- PÁGINA PÚBLICA -->
<div id="pagina-publica" class="hidden">
  <img id="fotoPerfil" class="foto-perfil" src="" alt="Foto de perfil" />
  <h1 id="nomePessoa"></h1>
  <p id="bioPessoa" class="bio"></p>
  <div id="avisoPessoa" class="aviso"></div>

  <div class="links" id="linksContainer"></div>

  <footer>© 2025 • Feito com 💖 por você</footer>
</div>

<script>
  // Dados padrão
  const dadosDefault = {
    nome: "Beat Lee",
    foto: "https://exemplo.com/foto-perfil.jpg",
    bio: "22 anos | Criador de conteúdo, artista e empreendedor. Aqui você encontra todos os meus links, novidades e lançamentos!",
    aviso: "🚨 Live especial no TikTok dia 10/06 às 20h!\n🎧 Nova playlist no Spotify!",
    instagram: "https://instagram.com/seuusuario",
    tiktok: "https://tiktok.com/@seuusuario",
    spotify: "https://spotify.com/seuusuario",
    facebook: "https://facebook.com/seuusuario",
    youtube: "https://youtube.com/seucanal",
    corPrincipal: "#ff69b4",
    corFundo: "#222222"
  };

  const loginUser = "Beat Lee";
  const loginPass = "11.11.2005";

  // Elementos
  const loginContainer = document.getElementById("login-container");
  const painel = document.getElementById("painel");
  const paginaPublica = document.getElementById("pagina-publica");

  const inputNome = document.getElementById("inputNome");
  const inputFoto = document.getElementById("inputFoto");
  const inputBio = document.getElementById("inputBio");
  const inputAviso = document.getElementById("inputAviso");
  const inputInstagram = document.getElementById("inputInstagram");
  const inputTikTok = document.getElementById("inputTikTok");
  const inputSpotify = document.getElementById("inputSpotify");
  const inputFacebook = document.getElementById("inputFacebook");
  const inputYouTube = document.getElementById("inputYouTube");
  const inputCorPrincipal = document.getElementById("inputCorPrincipal");
  const inputCorFundo = document.getElementById("inputCorFundo");

  const fotoPerfilEl = document.getElementById("fotoPerfil");
  const nomePessoaEl = document.getElementById("nomePessoa");
  const bioPessoaEl = document.getElementById("bioPessoa");
  const avisoPessoaEl = document.getElementById("avisoPessoa");
  const linksContainer = document.getElementById("linksContainer");

  const loginError = document.getElementById("login-error");

  // Função login
  function login() {
    const user = document.getElementById("usuario").value.trim();
    const pass = document.getElementById("senha").value.trim();

    if(user === loginUser && pass === loginPass) {
      loginContainer.classList.add("hidden");
      painel.classList.remove("hidden");
      paginaPublica.classList.remove("hidden");
      loginError.textContent = "";
      carregarDados();
    } else {
      loginError.textContent = "Usuário ou senha incorretos!";
    }
  }

  // Função logout
  function logout() {
    painel.classList.add("hidden");
    paginaPublica.classList.add("hidden");
    loginContainer.classList.remove("hidden");
    document.getElementById("usuario").value = "";
    document.getElementById("senha").value = "";
  }

  // Salvar dados no localStorage
  function salvar() {
    const dados = {
      nome: inputNome.value.trim() || dadosDefault.nome,
      foto: inputFoto.value.trim() || dadosDefault.foto,
      bio: inputBio.value.trim() || dadosDefault.bio,
      aviso: inputAviso.value.trim() || dadosDefault.aviso,
      instagram: inputInstagram.value.trim() || dadosDefault.instagram,
      tiktok: inputTikTok.value.trim() || dadosDefault.tiktok,
      spotify: inputSpotify.value.trim() || dadosDefault.spotify,
      facebook: inputFacebook.value.trim() || dadosDefault.facebook,
      youtube: inputYouTube.value.trim() || dadosDefault.youtube,
      corPrincipal: inputCorPrincipal.value || dadosDefault.corPrincipal,
      corFundo: inputCorFundo.value || dadosDefault.corFundo
    };
    localStorage.setItem("dadosLinkUnico", JSON.stringify(dados));
    carregarDados();
    alert("Dados salvos com sucesso!");
  }

  // Carregar dados do localStorage ou padrão
  function carregarDados() {
    const dadosSalvos = JSON.parse(localStorage.getItem("dadosLinkUnico"));
    const d = dadosSalvos || dadosDefault;

    // Atualiza inputs painel
    inputNome.value = d.nome;
    inputFoto.value = d.foto;
    inputBio.value = d.bio;
    inputAviso.value = d.aviso;
    inputInstagram.value = d.instagram;
    inputTikTok.value = d.tiktok;
    inputSpotify.value = d.spotify;
    inputFacebook.value = d.facebook;
    inputYouTube.value = d.youtube;
    inputCorPrincipal.value = d.corPrincipal;
    inputCorFundo.value = d.corFundo;

    // Atualiza página pública
    document.documentElement.style.setProperty('--cor-principal', d.corPrincipal);
    document.documentElement.style.setProperty('--cor-fundo', d.corFundo);
    document.body.style.backgroundColor = d.corFundo;

    fotoPerfilEl.src = d.foto;
    fotoPerfilEl.alt = "Foto de perfil de " + d.nome;
    nomePessoaEl.textContent = d.nome;
    bioPessoaEl.text
```
