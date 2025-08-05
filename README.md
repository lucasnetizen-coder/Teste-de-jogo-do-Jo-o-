<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Como Criar um Jogo + Mini Game</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f2f2f2;
      margin: 0;
      padding: 0;
    }
    header {
      background-color: #222;
      color: white;
      padding: 20px;
      text-align: center;
    }
    main {
      padding: 20px;
      max-width: 900px;
      margin: auto;
    }
    h2 {
      color: #333;
    }
    .game-area {
      margin-top: 40px;
      text-align: center;
    }
    #gameBox {
      width: 400px;
      height: 400px;
      background-color: #ddd;
      position: relative;
      margin: 0 auto;
      border: 2px solid #aaa;
    }
    #target {
      width: 50px;
      height: 50px;
      background-color: red;
      position: absolute;
      cursor: pointer;
      border-radius: 10px;
    }
    #score {
      font-size: 20px;
      margin-top: 15px;
    }
    footer {
      text-align: center;
      padding: 20px;
      background-color: #222;
      color: white;
      margin-top: 40px;
    }
  </style>
</head>
<body>

  <header>
    <h1>Como Criar um Jogo com HTML + JavaScript</h1>
  </header>

  <main>
    <section>
      <h2>Passos para Criar um Jogo</h2>
      <ol>
        <li><strong>Escolha a ideia:</strong> simples, como clicar para ganhar pontos.</li>
        <li><strong>Use HTML:</strong> para estruturar o jogo.</li>
        <li><strong>Use CSS:</strong> para deixar bonito.</li>
        <li><strong>Use JavaScript:</strong> para interatividade.</li>
        <li><strong>Teste e compartilhe!</strong></li>
      </ol>
      <p>Agora, vamos jogar um mini game que você pode criar com poucos códigos!</p>
    </section>

    <div class="game-area">
      <h2>Mini Game: Clique no Quadrado</h2>
      <div id="gameBox">
        <div id="target"></div>
      </div>
      <div id="score">Pontuação: 0</div>
    </div>
  </main>

  <footer>
    Criado por João Lucas | Aprenda, Crie e Jogue!
  </footer>

  <script>
    const target = document.getElementById("target");
    const gameBox = document.getElementById("gameBox");
    const scoreEl = document.getElementById("score");
    let score = 0;

    function moveTarget() {
      const maxX = gameBox.clientWidth - target.clientWidth;
      const maxY = gameBox.clientHeight - target.clientHeight;

      const x = Math.random() * maxX;
      const y = Math.random() * maxY;

      target.style.left = x + "px";
      target.style.top = y + "px";
    }

    target.addEventListener("click", () => {
      score++;
      scoreEl.textContent = "Pontuação: " + score;
      moveTarget();
    });

    // Iniciar o jogo com o quadrado em uma posição aleatória
    moveTarget();
  </script>
</body>
</html>
