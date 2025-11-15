<p align="center">
  <img src="https://github.com/Michael315-mk.png" width="200" height="200" alt="Foto de perfil" />
  <h1 align="center">Michael315-mk</h1>
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/michael315-mk/">
    <img alt="LinkedIn" src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" />
  </a>
  <a href="https://github.com/Michael315-mk">
    <img alt="GitHub" src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white" />
  </a>
</p>

<h3 align="center">Estudante de Ciência da Computação no CEFET-RJ</h3>

<p align="center">
  <img src="https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white" />
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Linux-000000?style=for-the-badge&logo=linux&logoColor=white" />
  <img src="https://img.shields.io/badge/GitHub Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white" />
</p>

<br />

## 📚 Formação Acadêmica

- 🎓 **Ciência da Computação** | CEFET-RJ  
- ⏳ **3º período (Fatorial)**  
- 📚 Estou cursando disciplinas dos **4º, 5º e 6º períodos**  
- 🕒 Faltam aproximadamente **2–3 anos** para graduar-me.

---

## 💻 Habilidades Técnicas

- **Linguagens de Programação:**
  - 🐱‍💻 **C** – Em uso para estudos de Sistemas Operacionais e estruturas de dados.
  - 🐍 **Python** – Em aprendizado para desenvolvimento de projetos, IA e Ciência de Dados.

- **Áreas de Interesse:**
  - 🧠 **Inteligência Artificial**
  - 📊 **Ciência de Dados**
  - 💾 **Sistemas Operacionais**
  - 🔧 **Desenvolvimento de Software**

---

## 🎮 Animação: Jogo da Cobra (Snake Game)

Abaixo está um pequeno jogo da cobra feito em **HTML, CSS e JavaScript**. Você pode incluí-lo diretamente no seu README.md usando o formato `<details>`.

> ⚠️ Lembre-se: GitHub renderiza HTML e JavaScript em README.md, então isso funcionará diretamente!

```html
<details>
<summary>Jogue o Snake Game aqui! 🐍</summary>

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <title>Snake Game</title>
  <style>
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background-color: #111;
      margin: 0;
    }
    #game {
      border: 3px solid white;
      background-color: black;
      width: 400px;
      height: 400px;
      display: grid;
      grid-template-rows: repeat(20, 1fr);
      grid-template-columns: repeat(20, 1fr);
    }
    .snake {
      background-color: lime;
    }
    .food {
      background-color: red;
    }
  </style>
</head>
<body>
  <canvas id="game" width="400" height="400"></canvas>
  <script>
    const canvas = document.getElementById("game");
    const ctx = canvas.getContext("2d");

    const gridSize = 20;
    let snake = [{x: 10, y: 10}];
    let food = {x: Math.floor(Math.random() * gridSize), y: Math.floor(Math.random() * gridSize)};
    let dx = 1, dy = 0;

    document.addEventListener("keydown", changeDirection);

    function changeDirection(e) {
      const LEFT_KEY = 37, RIGHT_KEY = 39, UP_KEY = 38, DOWN_KEY = 40;
      const keyPressed = e.keyCode;
      const canGoLeft = dx === 0;
      const canGoRight = dx === 0;
      const canGoUp = dy === 0;
      const canGoDown = dy === 0;

      if (keyPressed === LEFT_KEY && canGoLeft) { dx = -1; dy = 0; }
      if (keyPressed === RIGHT_KEY && canGoRight) { dx = 1; dy = 0; }
      if (keyPressed === UP_KEY && canGoUp) { dx = 0; dy = -1; }
      if (keyPressed === DOWN_KEY && canGoDown) { dx = 0; dy = 1; }
    }

    function draw() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);

      snake.forEach((segment, index) => {
        ctx.fillStyle = index === 0 ? "lime" : "#0f0";
        ctx.fillRect(segment.x * 20, segment.y * 20, 19, 19);
      });

      ctx.fillStyle = "red";
      ctx.fillRect(food.x * 20, food.y * 20, 19, 19);

      setTimeout(move, 100);
    }

    function move() {
      const head = {x: snake[0].x + dx, y: snake[0].y + dy};
      snake.unshift(head);

      if (head.x === food.x && head.y === food.y) {
        food = {x: Math.floor(Math.random() * gridSize), y: Math.floor(Math.random() * gridSize)};
      } else {
        snake.pop();
      }

      draw();
    }

    draw();
  </script>
</html>
