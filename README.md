# Lilo-hub-animes-
Informações sobre animes
<!DOCTYPE html>
<html lang="pt">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>AnimeStream</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>

  <header>
    <h1>🍥 AnimeStream</h1>
    <nav>
      <a href="#">Início</a>
      <a href="#catalogo">Catálogo</a>
    </nav>
  </header>

  <section class="hero">
    <h2>Assista trailers e descubra seus animes favoritos</h2>
    <p>Uma plataforma estilo Crunchyroll feita para fãs.</p>
  </section>

  <section id="catalogo" class="catalogo">
    <h2>📺 Catálogo de Animes</h2>

    <div class="grid">

      <div class="card" onclick="abrirAnime('Naruto', 'https://www.youtube.com/embed/QczGoCmX-pI')">
        <img src="https://i.imgur.com/Z6f6Fqj.jpg" />
        <h3>Naruto</h3>
      </div>

      <div class="card" onclick="abrirAnime('Attack on Titan', 'https://www.youtube.com/embed/MGRm4IzK1SQ')">
        <img src="https://i.imgur.com/8uZ9XyB.jpg" />
        <h3>Attack on Titan</h3>
      </div>

      <div class="card" onclick="abrirAnime('One Piece', 'https://www.youtube.com/embed/S8_YwFLCh4U')">
        <img src="https://i.imgur.com/7QpQK2G.jpg" />
        <h3>One Piece</h3>
      </div>

    </div>
  </section>

  <footer>
    <p>© 2026 AnimeStream - Projeto estilo Crunchyroll</p>
  </footer>

  <script src="script.js"></script>
</body>
</html>
<!DOCTYPE html>
<html lang="pt">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>AnimeStream - Anime</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>

  <header>
    <h1><a href="index.html">🍥 AnimeStream</a></h1>
  </header>

  <main class="anime-page">
    <h2 id="animeTitulo"></h2>

    <div class="player">
      <iframe id="animeVideo" width="100%" height="400"
        frameborder="0" allowfullscreen>
      </iframe>
    </div>
  </main>

  <script>
    const params = new URLSearchParams(window.location.search);
    document.getElementById("animeTitulo").textContent = params.get("nome");
    document.getElementById("animeVideo").src = params.get("video");
  </script>

</body>
</html>
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: #0b0b0f;
  color: white;
}

header {
  background: #ff6a00;
  padding: 15px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

header h1 {
  margin: 0;
}

header nav a {
  color: white;
  margin-left: 15px;
  text-decoration: none;
}

.hero {
  padding: 50px;
  text-align: center;
  background: linear-gradient(to right, #ff6a00, #ff2a00);
}

.catalogo {
  padding: 30px;
}

.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 20px;
}

.card {
  background: #1a1a22;
  padding: 10px;
  border-radius: 12px;
  cursor: pointer;
  transition: 0.3s;
}

.card:hover {
  transform: scale(1.05);
}

.card img {
  width: 100%;
  border-radius: 10px;
}

.player {
  margin-top: 20px;
}
function abrirAnime(nome, video) {
  window.location.href = `anime.html?nome=${encodeURIComponent(nome)}&video=${encodeURIComponent(video)}`;
}
