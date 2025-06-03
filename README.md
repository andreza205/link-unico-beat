<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Painel Admin Teste</title>
<style>
  :root {
    --cor-principal: #000000;
    --cor-bio: #000000;
    --imagem-fundo: none;
  }
  body {
    background: var(--imagem-fundo) no-repeat center center fixed;
    background-size: cover;
    color: var(--cor-principal);
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 20px;
  }
  #pagina-principal {
    max-width: 500px;
    margin: 0 auto 40px auto;
    padding: 15px;
    border: 2px solid var(--cor-principal);
    border-radius: 8px;
    background: #f9f9f9;
  }
  #pagina-principal img {
    display: block;
    margin: 10px 0;
    max-width: 100%;
    border-radius: 8px;
  }
  #pagina-principal h2 {
    margin-bottom: 5px;
  }
  #pagina-principal p {
    margin: 5px 0;
  }
  #bio {
    color: var(--cor-bio);
  }

  #painel {
    max-width: 500px;
    margin: 0 auto;
    padding: 20px;
    border: 2px solid var(--cor-principal);
    border-radius: 8px;
    background: #eee;
  }
  #painel h3 {
    margin-top: 0;
  }
  #painel label {
    display: block;
    margin-bottom: 10px;
    font-weight: bold;
  }
  #painel input[type="text"],
  #painel textarea,
  #painel input[type="color"] {
    width: 100%;
    padding: 6px;
    margin-top: 4px;
    box-sizing: border-box;
    border: 1px solid #ccc;
    border-radius: 4px;
    font-size: 14px;
  }
  #painel textarea {
    resize: vertical;
  }
  #painel button {
    background-color: var(--cor-principal);
    color: white;
    border: none;
    padding: 10px 15px;
    font-size: 16px;
    border-radius: 5px;
    cursor: pointer;
    margin-top: 10px;
  }
  #painel button:hover {
    opacity: 0.9;
  }
</style>
</head>
<body>

<div id="pagina-principal">
  <h2 id="nome">Seu Nome Aqui</h2>
  <img id="perfil" src="https://via.placeholder.com/150" alt="Foto Perfil" />
  <p id="bio">Essa é a biografia padrão, que não pode ficar em branco.</p>
  <p id="aviso">Avisos aparecerão aqui.</p>
</div>

<div id="painel">
  <h3>Painel Administrativo</h3>

  <label for="input-nome">Nome:</label>
  <input type="text" id="input-nome" placeholder="Digite o nome" />

  <label for="input-foto">Foto (URL):</label>
  <input type="text" id="input-foto" placeholder="Cole a URL da foto" />

  <label for="input-bio">Biografia:</label>
  <textarea id="input-bio" rows="3" placeholder="Digite a biografia"></textarea>

  <label for="input-cor-bio">Cor da Biografia:</label>
  <input type="color" id="input-cor-bio" value="#000000" />

  <label for="input-aviso">Aviso:</label>
  <input type="text" id="input-aviso" placeholder="Digite um aviso" />

  <label for="input-cor">Cor do painel:</label>
  <input type="color" id="input-cor" value="#000000" />

  <label for="input-fundo">Imagem de Fundo (URL):</label>
  <input type="text" id="input-fundo" placeholder="Cole a URL da imagem de fundo" />

  <button onclick="atualizarDados()">Salvar e Atualizar</button>
</div>

<script>
  window.onload = () => {
    // Inicializa os inputs com os dados da página
    document.getElementById('input-nome').value = document.getElementById('nome').innerText;
    document.getElementById('input-bio').value = document.getElementById('bio').innerText;
    document.getElementById('input-aviso').value = document.getElementById('aviso').innerText;
    document.getElementById('input-cor').value = '#000000';
    document.getElementById('input-cor-bio').value = '#000000';
  };

  function atualizarDados() {
    // Nome
    const nomeValor = document.getElementById('input-nome').value.trim();
    if (nomeValor) {
      document.getElementById('nome').innerText = nomeValor;
    }

    // Foto
    const urlFoto = document.getElementById('input-foto').value.trim();
    if (urlFoto) {
      document.getElementById('perfil').src = urlFoto;
    }

    // Biografia (não pode ficar vazia)
    const bioValor = document.getElementById('input-bio').value.trim();
    if (bioValor) {
      document.getElementById('bio').innerText = bioValor;
    }

    // Cor da Biografia
    const corBio = document.getElementById('input-cor-bio').value;
    if (corBio) {
      document.documentElement.style.setProperty('--cor-bio', corBio);
    }

    // Aviso (pode ficar vazio)
    const avisoValor = document.getElementById('input-aviso').value.trim();
    document.getElementById('aviso').innerText = avisoValor;

    // Cor do painel
    const cor = document.getElementById('input-cor').value;
    if (cor) {
      document.documentElement.style.setProperty('--cor-principal', cor);
    }

    // Imagem de fundo
    const fundoURL = document.getElementById('input-fundo').value.trim();
    if (fundoURL) {
      document.documentElement.style.setProperty('--imagem-fundo', `url('${fundoURL}')`);
    } else {
      document.documentElement.style.setProperty('--imagem-fundo', 'none');
    }
  }
</script>

</body>
</html>
