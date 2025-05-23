<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Cadastro de Cliente</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f2f2f2;
      margin: 0;
      padding: 0;
    }

    .container {
      max-width: 400px;
      margin: 50px auto;
      background: #fff;
      padding: 30px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }

    h2 {
      text-align: center;
      margin-bottom: 20px;
    }

    input {
      width: 100%;
      padding: 12px;
      margin: 8px 0 16px 0;
      border: 1px solid #ccc;
      border-radius: 6px;
    }

    button {
      width: 100%;
      background-color: #007bff;
      color: white;
      padding: 12px;
      border: none;
      border-radius: 6px;
      font-size: 16px;
      cursor: pointer;
    }

    button:hover {
      background-color: #0056b3;
    }

    .mensagem {
      margin-top: 15px;
      text-align: center;
      font-weight: bold;
    }

    @media (max-width: 500px) {
      .container {
        margin: 20px;
        padding: 20px;
      }
    }
  </style>
</head>
<body>

  <div class="container">
    <h2>Cadastro de Cliente</h2>
    <form id="formCadastro">
      <input type="text" id="nome" placeholder="Nome completo" required />
      <input type="email" id="email" placeholder="E-mail" required />
      <input type="text" id="usuario" placeholder="Usuário" required />
      <input type="password" id="senha" placeholder="Senha" required />
      <button type="submit">Cadastrar</button>
    </form>
    <div class="mensagem" id="mensagem"></div>
  </div>

  <script>
    const form = document.getElementById("formCadastro");
    const mensagem = document.getElementById("mensagem");

    // Obtém os usuários salvos do localStorage
    function obterUsuarios() {
      return JSON.parse(localStorage.getItem("usuarios") || "[]");
    }

    // Salva o novo usuário no localStorage
    function salvarUsuario(usuarioObj) {
      const usuarios = obterUsuarios();
      usuarios.push(usuarioObj);
      localStorage.setItem("usuarios", JSON.stringify(usuarios));
    }

    form.addEventListener("submit", function(e) {
      e.preventDefault();

      const nome = document.getElementById("nome").value.trim();
      const email = document.getElementById("email").value.trim();
      const usuario = document.getElementById("usuario").value.trim();
      const senha = document.getElementById("senha").value;

      if (!nome || !email || !usuario || !senha) {
        mensagem.textContent = "Preencha todos os campos.";
        mensagem.style.color = "red";
        return;
      }

      const usuarios = obterUsuarios();
      const existe = usuarios.some(u => u.usuario === usuario);

      if (existe) {
        mensagem.textContent = "Usuário já cadastrado.";
        mensagem.style.color = "red";
        return;
      }

      salvarUsuario({ nome, email, usuario, senha });
      mensagem.textContent = "Cadastro realizado com sucesso!";
      mensagem.style.color = "green";
      form.reset();
    });
  </script>

</body>
</html>
