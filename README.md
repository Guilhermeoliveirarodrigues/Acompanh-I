<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>EduOcorrência</title>

  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f6f9;
      margin: 0;
      padding: 0;
    }

    header {
      background: #1e3a8a;
      color: white;
      padding: 20px;
      text-align: center;
    }

    .container {
      max-width: 600px;
      margin: 30px auto;
      background: white;
      padding: 25px;
      border-radius: 10px;
      box-shadow: 0px 0px 10px rgba(0,0,0,0.1);
    }

    h2 {
      text-align: center;
      color: #1e3a8a;
    }

    label {
      font-weight: bold;
      display: block;
      margin-top: 15px;
    }

    input, textarea, select {
      width: 100%;
      padding: 10px;
      margin-top: 5px;
      border-radius: 5px;
      border: 1px solid #ccc;
      box-sizing: border-box;
    }

    textarea {
      resize: none;
      height: 120px;
    }

    button {
      width: 100%;
      padding: 12px;
      margin-top: 20px;
      background: #2563eb;
      color: white;
      border: none;
      border-radius: 5px;
      font-size: 16px;
      cursor: pointer;
    }

    button:hover {
      background: #1d4ed8;
    }

    .resultado {
      margin-top: 20px;
      background: #dcfce7;
      color: #166534;
      padding: 15px;
      border-radius: 5px;
      display: none;
    }
  </style>
</head>
<body>

  <header>
    <h1>EduOcorrência</h1>
    <p>Sistema de Ocorrência Escolar</p>
  </header>

  <div class="container">
    <h2>Registrar Ocorrência</h2>

    <label>Nome do Professor</label>
    <input type="text" id="professor" placeholder="Digite o nome do professor">

    <label>Nome do Aluno</label>
    <input type="text" id="aluno" placeholder="Digite o nome do aluno">

    <label>Turma</label>
    <input type="text" id="turma" placeholder="Ex: 2º Ano A">

    <label>Tipo de Ocorrência</label>
    <select id="tipo">
      <option>Atraso</option>
      <option>Falta</option>
      <option>Desrespeito</option>
      <option>Tarefa não entregue</option>
      <option>Uso de celular</option>
    </select>

    <label>Descrição</label>
    <textarea id="descricao" placeholder="Digite os detalhes da ocorrência"></textarea>

    <label>Email do Responsável</label>
    <input type="email" id="email" placeholder="responsavel@email.com">

    <button onclick="enviarOcorrencia()">Enviar Ocorrência</button>

    <div class="resultado" id="resultado"></div>
  </div>

  <script>
    function enviarOcorrencia() {

      let professor = document.getElementById("professor").value;
      let aluno = document.getElementById("aluno").value;
      let turma = document.getElementById("turma").value;
      let tipo = document.getElementById("tipo").value;
      let descricao = document.getElementById("descricao").value;
      let email = document.getElementById("email").value;

      if(professor === "" || aluno === "" || turma === "" || descricao === "" || email === ""){
        alert("Preencha todos os campos!");
        return;
      }

      let mensagem = `
        Ocorrência enviada com sucesso!<br><br>

        <strong>Professor:</strong> ${professor}<br>
        <strong>Aluno:</strong> ${aluno}<br>
        <strong>Turma:</strong> ${turma}<br>
        <strong>Tipo:</strong> ${tipo}<br>
        <strong>Descrição:</strong> ${descricao}<br><br>

        Uma notificação foi enviada para o responsável no email:
        <strong>${email}</strong>
      `;

      let resultado = document.getElementById("resultado");
      resultado.style.display = "block";
      resultado.innerHTML = mensagem;

      // Simulação de envio
      console.log("Ocorrência enviada para:", email);
    }
  </script>

</body>
</html>
