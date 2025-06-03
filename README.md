<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Link Único Beat</title>
  <style>
    :root {
      --cor-principal: #ff69b4;
      --imagem-fundo: url('https://exemplo.com/sua-imagem.jpg');
    }

    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: var(--imagem-fundo) no-repeat center center fixed;
      background-size: cover;
      color: #fff;
      text-align: center;
      padding: 20px;
    }

    .container {
      background-color: rgba(0, 0, 0, 0.7);
      border-radius: 20px;
      padding: 30px;
      max-width: 600px;
      margin: auto;
    }

    .foto-perfil {
      width: 120px;
      height: 120px;
      border-radius: 50%;
      object-fit: cover;
      border: 4px solid var(--cor-principal);
    }

    h1 {
      margin-top: 10px;
      color: var(--cor-principal);
    }

    .bio {
      margin: 15px 0;
    }

    .aviso {
      background-color: var(--cor-principal);
      padding: 10px;
      border-radius: 10px;
      margin: 20px 0;
      font-weight: bold;
    }

    .links {
      display: flex;
      flex-direction: column;
      gap: 15px;
    }

    .links a {
      background-color: var(--cor-principal);
      color: #fff;
      text-decoration: none;
      padding: 12px;
      border-radius: 8px;
      font-weight: bold;
      transition: 0.3s;
    }

    .links a:hover {
      background-color: #fff;
      color: var(--cor-principal);
    }

    .menu-admin {
      position: fixed;
      top: 20px;
      right: 20px;
      background-color: rgba(0, 0, 0, 0.7);
      border-radius: 10px;
      padding: 10px;
      cursor: pointer;
    }

    .barras {
      width: 25px;
      height: 3px;
      background-color: var(--cor-principal);
      margin: 4px 0;
    }

    .login-form, .painel-edicao {
      display: none;
      flex-direction: column;
      gap: 10px;
      margin-top: 20px;
      text-align: left;
    }

    .login-form input, .painel-edicao input, .painel-edicao textarea {
      padding: 10px;
      border-radius: 5px;
      border: none;
    }

    .login-form button, .painel-edicao button {
      background-color: var(--cor-principal);
      color: white;
      padding: 10px;
      border: none;
      border-radius: 5px;
      font-weight: bold;
      cursor: pointer;
    }

    .cores-opcoes {
      display: flex;
      gap: 10px;
      flex-wrap: wrap;
    }

    .cor-bolinha {
      width: 25px;
      height: 25px;
      border-radius: 50%;
      border: 2px solid white;
      cursor: pointer;
    }

    footer {
      margin-top: 30px;
      font-size: 12px;
      color: #ccc;
    }
  </style>
</head>
<body>
  <div class="menu-admin" onclick="toggleLogin()">
    <div class="barras"></div>
    <div class="barras"></div>
    <div class="barras"></div>
    <div style="font-size: 12px; color: white; margin-top: 5px;">Login do Administrador</div>
  </div>

  <div class="container">
    <img id="perfil" class="foto-perfil" src="https://exemplo.com/foto-perfil.jpg" alt="Foto de perfil">
    <h1 id="nome">Beat Lee</h1>
    <p class="bio" id="bio">22 anos | Criador de conteúdo, artista e empreendedor. Aqui você encontra todos os meus links, novidades e lançamentos!</p>
    <div class="aviso" id="aviso">
      🚨 Live especial no TikTok dia 10/06 às 20h!<br>
      🎧 Nova playlist no Spotify!
    </div>
    <div class="links" id="links">
      <a id="link-instagram" href="https://instagram.com/seuusuario" target="_blank">Instagram</a>
      <a id="link-tiktok" href="https://tiktok.com/@seuusuario" target="_blank">TikTok</a>
      <a id="link-spotify" href="https://spotify.com/seuusuario" target="_blank">Spotify</a>
      <a id="link-facebook" href="https://facebook.com/seuusuario" target="_blank">Facebook</a>
      <a id="link-youtube" href="https://youtube.com/seucanal" target="_blank">YouTube</a>
    </div>

    <div id="login-form" class="login-form">
      <input type="text" id="usuario" placeholder="Usuário">
      <input type="password" id="senha" placeholder="Senha">
      <button onclick="logar()">Entrar</button>
      <div id="mensagem"></div>
    </div>

    <div id="painel-edicao" class="painel-edicao">
      <input id="input-nome" placeholder="Nome">
      <input id="input-foto" placeholder="URL da foto (opcional)">
      <input type="file" id="upload-foto" accept="image/*">
      <textarea id="input-bio" placeholder="Biografia"></textarea>
      <textarea id="input-aviso" placeholder="Aviso"></textarea>
      <input id="input-instagram" placeholder="Link do Instagram">
      <input id="input-tiktok" placeholder="Link do TikTok">
      <input id="input-spotify" placeholder="Link do Spotify">
      <input id="input-facebook" placeholder="Link do Facebook">
      <input id="input-youtube" placeholder="Link do YouTube">
      <input id="input-fundo" placeholder="URL da imagem de fundo (opcional)">
      <input type="file" id="upload-fundo" accept="image/*">
      <input id="input-cor" placeholder="Cor principal (hex)">
      <div class="cores-opcoes">
        <div class="cor-bolinha" style="background-color: #ff69b4;" onclick="setCor('#ff69b4')"></div>
        <div class="cor-bolinha" style="background-color: #3498db;" onclick="setCor('#3498db')"></div>
        <div class="cor-bolinha" style="background-color: #2ecc71;" onclick="setCor('#2ecc71')"></div>
        <div class="cor-bolinha" style="background-color: #e74c3c;" onclick="setCor('#e74c3c')"></div>
        <div class="cor-bolinha" style="background-color: #f1c40f;" onclick="setCor('#f1c40f')"></div>
        <div class="cor-bolinha" style="background-color: #9b59b6;" onclick="setCor('#9b59b6')"></div>
      </div>
      <button onclick="atualizarDados()">Salvar Alterações</button>
    </div>

    <footer>
      © 2025 • Feito com 💖 por você
    </footer>
  </div>

  <script>
    function toggleLogin() {
      const form = document.getElementById('login-form');
      form.style.display = form.style.display === 'flex' ? 'none' : 'flex';
    }

    function logar() {
      const usuario = document.getElementById('usuario').value;
      const senha = document.getElementById('senha').value;
      const mensagem = document.getElementById('mensagem');

      if (usuario === 'Beat Lee' && senha === '11.11.2005') {
        mensagem.innerHTML = '<p style="color:lightgreen">Acesso liberado!</p>';
        document.getElementById('painel-edicao').style.display = 'flex';
        document.getElementById('login-form').style.display = 'none';
      } else {
        mensagem.innerHTML = '<p style="color:red">Usuário ou senha incorretos!</p>';
      }
    }

    document.getElementById('upload-foto').addEventListener('change', function(e) {
      const file = e.target.files[0];
      if (file) {
        const url = URL.createObjectURL(file);
        document.getElementById('perfil').src = url;
      }
    });

    document.getElementById('upload-fundo').addEventListener('change', function(e) {
      const file = e.target.files[0];
      if (file) {
        const url = URL.createObjectURL(file);
        document.documentElement.style.setProperty('--imagem-fundo', `url('${url}')`);
      }
    });

    function atualizarDados() {
      document.getElementById('nome').innerText = document.getElementById('input-nome').value;
      const urlFoto = document.getElementById('input-foto').value;
      if (urlFoto) document.getElementById('perfil').src = urlFoto;
      document.getElementById('bio').innerText = document.getElementById('input-bio').value;
      document.getElementById('aviso').innerText = document.getElementById('input-aviso').value;
      document.getElementById('link-instagram').href = document.getElementById('input-instagram').value;
      document.getElementById('link-tiktok').href = document.getElementById('input-tiktok').value;
      document.getElementById('link-spotify').href = document.getElementById('input-spotify').value;
      document.getElementById('link-facebook').href = document.getElementById('input-facebook').value;
      document.getElementById('link-youtube').href = document.getElementById('input-youtube').value;
      const cor = document.getElementById('input-cor').value;
      if (cor) document.documentElement.style.setProperty('--cor-principal', cor);
      const fundoURL = document.getElementById('input-fundo').value;
      if (fundoURL) document.documentElement.style.setProperty('--imagem-fundo', `url('${fundoURL}')`);
    }

    function setCor(cor) {
      document.documentElement.style.setProperty('--cor-principal', cor);
      document.getElementById('input-cor').value = cor;
    }
  </script>
</body>
</html>
