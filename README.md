<!DOCTYPE html>
<html lang="pl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>STERNE FM – Gwiezdna Droga</title>
  <link href="https://fonts.googleapis.com/css2?family=Orbitron&family=Audiowide&display=swap" rel="stylesheet" />
  <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r134/three.min.js"></script>
  <style>
    body {
      margin: 0;
      font-family: 'Orbitron', sans-serif;
      background: radial-gradient(circle at top, #0b0c2a, #000);
      color: white;
      overflow-x: hidden;
    }
    canvas#bg {
      position: fixed;
      top: 0;
      left: 0;
      z-index: -1;
    }
    header {
      padding: 100px 20px;
      text-align: center;
      background: linear-gradient(to bottom, #0b0c2a, #000);
    }
    h1, h2 {
      font-family: 'Audiowide', cursive;
    }<section id="contact">
  <h2>📬 Kontakt</h2>
  <form>
    <input type="text" placeholder="Twoje imię" required>
    <input type="email" placeholder="Twój e-mail" required>
    <textarea placeholder="Wiadomość" required></textarea>
    <button type="submit">Wyślij</button>
  </form>
</section><section id="player">
  <section id="contact">
  <h2>📬 Kontakt</h2>
  <form>
    <input type="text" placeholder="Twoje imię" required>
    <input type="email" placeholder="Twój e-mail" required>
    <textarea placeholder="Wiadomość" required></textarea>
    <button type="submit">Wyślij</button>
  </form>
</section>
  <h2>🔊 Słuchaj nas na żywo</h2>
  <audio controls autoplay style="width: 80%; max-width: 600px; border: 2px solid #fff; border-radius: 10px;">
    <source src="https://s41.myradiostream.com:39624/stream" type="audio/mpeg">
    Twoja przeglądarka nie obsługuje odtwarzacza audio.
  </audio>
  <p>Gramy prosto z orbity – 24/7!</p>
  <div class="live-indicator">🔴 LIVE</div>
  <button class="button" onclick="location.href='#schedule'">Zobacz ramówkę</button> 
  <h2>🔊 Słuchaj nas na żywo</h2>
  <audio controls autoplay style="width: 80%; max-width: 600px; border: 2px solid #fff; border-radius: 10px;">
    <source src="https://s41.myradiostream.com:39624/stream" type="audio/mpeg">
    Twoja przeglądarka nie obsługuje odtwarzacza audio.
  </audio>
  <p>Gramy prosto z orbity – 24/7!</p>
  <div class="live-indicator">🔴 LIVE</div>
  <button class="button" onclick="location.href='#schedule'">Zobacz ramówkę</button>
</section>
  <h2>🧠 Quiz galaktyczny</h2><section id="galaxy-map">
  <h2>🪐 Mapa Galaktyki STERNE</h2>
  <p>Wybierz planetę i odkryj jej dźwięki:</p>
  <button class="button" onclick="location.href='#player'">🎧 Orbita LIVE</button>
  <button class="button" onclick="location.href='#schedule'">📅 Planeta Ramówka</button>
  <button class="button" onclick="location.href='#quiz'">🧠 Gwiazda Quiz</button>
</section>
4. 📻 Podcasty i archiwum audycji (placeholder)
Dodaj sekcję podcastów:

html
<section id="player">
  <h2>🔊 Słuchaj nas na żywo</h2>
  <audio controls autoplay style="width: 80%; max-width: 600px; border: 2px solid #fff; border-radius: 10px;">
    <source src="https://s41.myradiostream.com:39624/stream" type="audio/mpeg">
    Twoja przeglądarka nie obsługuje odtwarzacza audio.
  </audio>
  <p>Gramy prosto z orbity – 24/7!</p>
  <div class="live-indicator">🔴 LIVE</div>
  <button class="button" onclick="location.href='#schedule'">Zobacz ramówkę</button>
</section>
  <h2>📻 Archiwum audycji</h2>
  <p>Wkrótce dodamy nagrania z naszych najlepszych transmisji!</p>
</section>
  <p>Odpowiedz na pytanie i odkryj swoją muzyczną galaktykę!</p>
  <button class="button" onclick="showResult()">Start</button>
  <p id="quiz-result" style="margin-top: 20px;"></p>
</section>

<script>
  function showResult() {
    const galaxies = ["Andromeda Bass", "Orion Chill", "Sirius Synthwave", "Cassiopeia Funk"];
    const result = galaxies[Math.floor(Math.random() * galaxies.length)];
    document.getElementById("quiz-result").textContent = "Twoja galaktyka to: " + result;
  }
</script>
      padding: 60px 20px;
      text-align: center;
    }
    audio {
      width: 80%;
      max-width: 600px;
      border: 2px solid #fff;
      border-radius: 10px;
    }
    ul {
      list-style: none;
      padding: 0;
    }
    li {
      margin: 10px 0;
    }
    a {
      color: #0ff;
      text-decoration: none;
    }
    .live-indicator {
      display: inline-block;
      background-color: red;
      color: white;
      padding: 5px 10px;
      border-radius: 20px;
      animation: pulse 1s infinite;
      font-weight: bold;
      margin-top: 10px;
    }
    @keyframes pulse {
      0% { opacity: 1; }
      50% { opacity: 0.4; }
      100% { opacity: 1; }
    }
    .button {
      background-color: #0ff;
      color: #000;
      padding: 10px 20px;
      border: none;
      border-radius: 20px;
      font-weight: bold;
      cursor: pointer;
      margin-top: 20px;
      transition: background 0.3s;
    }
    .button:hover {
      background-color: #fff;
    }
    footer {
      padding: 40px 20px;
      background-color: #0b0c2a;
      font-size: 0.9em;
      text-align: center;
    }
  </style>
</head>
<body>

  <canvas id="bg"></canvas>
  <script>
    const scene = new THREE.Scene();
    const camera = new THREE.PerspectiveCamera(75, window.innerWidth/window.innerHeight, 0.1, 1000);
    const renderer = new THREE.WebGLRenderer({ canvas: document.getElementById('bg') });
    renderer.setSize(window.innerWidth, window.innerHeight);
    camera.position.z = 5;

    const geometry = new THREE.SphereGeometry(0.1, 24, 24);
    const material = new THREE.MeshBasicMaterial({ color: 0xffffff });

    for (let i = 0; i < 300; i++) {
      const star = new THREE.Mesh(geometry, material);
      star.position.set(
        (Math.random() - 0.5) * 100,
        (Math.random() - 0.5) * 100,
        (Math.random() - 0.5) * 100
      );
      scene.add(star);
    }

    function animate() {
      requestAnimationFrame(animate);
      camera.rotation.y += 0.0005;
      renderer.render(scene, camera);
    }
    animate();
  </script>

  <header>
    <h1>🌠 STERNE FM</h1>
    <p>Gwiezdna muzyczna droga – radio z przyszłości</p>
    <div class="live-indicator">🔴 LIVE</div>
  </header>

  <section id="player"><section id="now-playing">
  <h2>🎶 Aktualnie gramy</h2>
  <p id="track">Ładowanie utworu...</p>
</section>

<script>
  // Przykład: dynamiczna aktualizacja utworu (można podpiąć do API streamu)
  const trackElement = document.getElementById('track');
  setInterval(() => {
    // Tu można podpiąć prawdziwe dane z serwera
    trackElement.textContent = "DJ Nova – Galactic Pulse";
  }, 5000);
</script>
    <h2>🔊 Słuchaj nas na żywo</h2>
    <audio controls autoplay>
      <source src="https://stream.live.vc.bbcmedia.co.uk/bbc_radio_one" type="audio/mpeg">
      Twoja przeglądarka nie obsługuje odtwarzacza audio.
    </audio>
    <p>Gramy prosto z orbity – 24/7!</p>
    <button class="button" onclick="location.href='#schedule'">Zobacz ramówkę</button>
  </section>

  <section id="about">
    <h2>🛰️ Kim jesteśmy?</h2>
    <p>STERNE FM to niezależne radio nadające z galaktyki kreatywności. Nasza misja: dostarczać dźwięki spoza Ziemi, inspirować, łączyć i zaskakiwać. Jesteśmy głosem przyszłości – dla tych, którzy słuchają sercem.</p>
  </section><section id="galactic-journey">
  <h2>🌌 Droga Gwiezdna</h2>
  <p>
    Witaj podróżniku. Trafiłeś na STERNE FM – stację nadawczą dryfującą w przestrzeni międzygwiezdnej, gdzie dźwięk nie zna granic, a rytm pulsuje w rytmie gwiazd.  
    Nasza Droga Gwiezdna to więcej niż transmisja – to podróż przez emocje, wspomnienia i przyszłość, którą tworzymy razem z Tobą.  
    Każda audycja to sygnał wysyłany w eter, każda nuta to fala, która dociera do serc słuchaczy w najdalszych zakątkach galaktyki.  
    Nie jesteśmy zwykłym radiem. Jesteśmy pulsującym rdzeniem muzycznego wszechświata – miejscem, gdzie techno spotyka ambient, a kosmiczny funk tańczy z elektroniczną poezją.  
    Dołącz do naszej załogi. Nadajemy z orbity kreatywności. Lecimy dalej.
  </p>
</section>

  <section id="schedule">
    <h2>🪐 Ramówka</h2>
    <ul>
      <li>🌅 10:00 – Kosmiczne Przebudzenie</li>
      <li>🎶 14:00 – Gwiezdne Brzmienia</li>
      <li>🛸 20:00 – Transmisja z Galaktyki X</li>
    </ul>
  </section>

