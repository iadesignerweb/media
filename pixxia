<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Gerador de Imagens e Vídeos - iaDesigner</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background-color: #f4f4f4;
      color: #333;
    }
    header {
      text-align: center;
      padding: 20px;
      background-color: #fff;
      box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    }
    header h1 {
      margin: 0;
      font-size: 24px;
    }
    main {
      display: flex;
      flex-direction: column;
      align-items: center;
      margin: 20px;
    }
    .prompt-container {
      background: #fff;
      padding: 20px;
      border-radius: 8px;
      box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
      width: 100%;
      max-width: 400px;
    }
    .prompt-container h2 {
      margin-bottom: 15px;
      font-size: 20px;
    }
    .prompt-container label {
      display: block;
      margin-bottom: 10px;
      font-weight: bold;
    }
    .prompt-container input,
    .prompt-container select {
      width: 100%;
      padding: 8px;
      margin-bottom: 15px;
      border: 1px solid #ccc;
      border-radius: 4px;
    }
    .prompt-container button {
      width: 100%;
      padding: 10px;
      border: none;
      background-color: #333;
      color: #fff;
      border-radius: 4px;
      cursor: pointer;
      font-size: 16px;
    }
    .prompt-container button:hover {
      background-color: #555;
    }
    footer {
      margin-top: 20px;
      text-align: center;
      font-size: 14px;
      color: #777;
      padding: 10px;
      background: #fff;
      box-shadow: 0 -2px 4px rgba(0, 0, 0, 0.1);
    }
    .watermark {
      position: fixed;
      bottom: 10px;
      right: 10px;
      font-size: 12px;
      opacity: 0.5;
    }
    .pro-button {
      position: fixed;
      bottom: 70px;
      right: 10px;
      background: black;
      color: white;
      padding: 10px 20px;
      border-radius: 50px;
      font-size: 14px;
      text-decoration: none;
      text-align: center;
    }
    .pro-button:hover {
      background: #444;
    }
    #loading {
      display: none;
      margin-top: 15px;
      color: #333;
      font-size: 14px;
      text-align: center;
    }
  </style>
</head>
<body>
  <header>
    <h1>Gerador de Imagens e Vídeos - iaDesigner</h1>
  </header>
  <main>
    <div class="prompt-container">
      <h2>Gerar Conteúdo</h2>
      <label for="prompt">Digite seu prompt:</label>
      <input type="text" id="prompt" placeholder="Descreva sua imagem ou vídeo...">
      
      <label for="ratio">Escolha a proporção:</label>
      <select id="ratio">
        <option value="1:1">1:1</option>
        <option value="2:3">2:3</option>
        <option value="9:16">9:16</option>
        <option value="16:9">16:9</option>
      </select>
      
      <button onclick="generateImage()">Gerar Imagens</button>
      <button onclick="generateVideo()">Gerar Vídeo</button>

      <div id="loading">Processando... Por favor, aguarde.</div>
    </div>
  </main>
  <footer>
    Copyright 2024 'iaDesigner'
  </footer>
  <div class="watermark">iaDesigner</div>
  <a href="https://wa.me/558799786261" class="pro-button">PRO</a>

  <script>
    const API_URL = "https://sua-api.com"; // Substitua pelo endpoint real da sua API

    async function generateImage() {
      const prompt = document.getElementById('prompt').value;
      const ratio = document.getElementById('ratio').value;
      const loading = document.getElementById('loading');
      const button = document.querySelector('.prompt-container button');

      if (prompt && ratio) {
        button.disabled = true;
        loading.style.display = 'block';

        try {
          const response = await fetch(`${API_URL}/imagem`, {
            method: "POST",
            headers: { "Content-Type": "application/json" },
            body: JSON.stringify({ prompt, ratio })
          });

          if (!response.ok) {
            const errorText = await response.text();
            throw new Error(`Erro da API: ${errorText}`);
          }

          const data = await response.json();
          alert(`Imagem gerada com sucesso! Link: ${data.url}`);
        } catch (error) {
          alert(`Erro ao gerar imagem: ${error.message}`);
        } finally {
          button.disabled = false;
          loading.style.display = 'none';
        }
      } else {
        alert('Preencha todos os campos antes de gerar!');
      }
    }

    async function generateVideo() {
      const prompt = document.getElementById('prompt').value;
      const ratio = document.getElementById('ratio').value;
      const loading = document.getElementById('loading');
      const button = document.querySelector('.prompt-container button');

      if (prompt && ratio) {
        button.disabled = true;
        loading.style.display = 'block';

        try {
          const response = await fetch(`${API_URL}/video`, {
            method: "POST",
            headers: { "Content-Type": "application/json" },
            body: JSON.stringify({ prompt, ratio, duration: 4 })
          });

          if (!response.ok) {
            const errorText = await response.text();
            throw new Error(`Erro da API: ${errorText}`);
          }

          const data = await response.json();
          alert(`Vídeo gerado com sucesso! Link: ${data.url}`);
        } catch (error) {
          alert(`Erro ao gerar vídeo: ${error.message}`);
        } finally {
          button.disabled = false;
          loading.style.display = 'none';
        }
      } else {
        alert('Preencha todos os campos antes de gerar!');
      }
    }
  </script>
</body>
</html>
