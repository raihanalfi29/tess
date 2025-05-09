<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1" />
  <title>Selamat Ulang Tahun, Sayang!</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Great+Vibes&family=Poppins:wght@300;700&display=swap');
    /* Reset dan dasar */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    body {
      background: linear-gradient(135deg, #ffe1e8 0%, #ffcad4 50%, #ffb3c1 100%);
      font-family: 'Poppins', sans-serif;
      color: #4a2c3b;
      padding: 20px;
      text-align: center;
      min-height: 100vh;
    }
    h1 {
      font-family: 'Great Vibes', cursive;
      font-size: 3.5rem;
      color: #9e3050;
      text-shadow: 0 0 10px #e75480aa;
      margin-bottom: 10px;
    }
    h2 {
      font-weight: 300;
      font-size: 1.8rem;
      margin-top: 0;
      color: #7f4057;
    }
    .container, .album-container {
      background: rgba(255, 255, 255, 0.85);
      border-radius: 25px;
      padding: 30px 40px;
      max-width: 480px;
      box-shadow: 0 10px 25px rgba(209, 91, 123, 0.3);
      margin: 20px auto;
      position: relative;
      z-index: 2;
    }
    p.pesan {
      margin: 20px 0 30px;
      font-size: 1.2rem;
      line-height: 1.5;
      color: #702c42;
    }
    .gambar-romantis {
      width: 100%;
      height: auto;
      border-radius: 20px;
      box-shadow: 0 8px 18px rgba(161, 81, 115, 0.4);
      margin-top: 20px;
    }
    .audio-control {
      margin-top: 15px;
      text-align: center;
    }
    .audio-control button, .toggle-album-btn {
      background: #e75480;
      border: none;
      color: white;
      padding: 10px 24px;
      border-radius: 25px;
      font-size: 1rem;
      cursor: pointer;
      box-shadow: 0 4px 8px rgba(231, 84, 128, 0.5);
      transition: background-color 0.3s ease;
      margin-top: 10px;
      display: inline-block;
    }
    .audio-control button:hover, .toggle-album-btn:hover {
      background: #d04875;
    }
    .album-container {
      display: none;
    }
    .album-title {
      font-family: 'Great Vibes', cursive;
      font-size: 2.6rem;
      color: #9e3050;
      text-align: center;
      margin-bottom: 20px;
    }
    .gallery {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 15px;
    }
    .gallery div {
      width: calc(50% - 10px);
      border-radius: 10px;
    }
    .gallery img, .gallery video {
      width: 100%;
      border-radius: 10px;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
      cursor: pointer;
      transition: transform 0.3s ease;
      max-height: 250px;
      object-fit: cover;
    }
    .gallery img:hover, .gallery video:hover {
      transform: scale(1.05);
    }
    .gallery p {
      margin-top: 6px;
      color: #7f4057;
      font-size: 0.9rem;
    }
    /* Kontainer hati mengapung */
    .hati {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      overflow: hidden;
      z-index: 1;
    }
    .hati-bentuk {
      position: absolute;
      bottom: -40px;
      width: 20px;
      height: 20px;
      background: #e75480;
      transform: rotate(-45deg);
      animation-name: mengapungKeAtas;
      animation-timing-function: linear;
      animation-iteration-count: infinite;
      filter: drop-shadow(0 0 2px #f37ea7);
    }
    .hati-bentuk::before,
    .hati-bentuk::after {
      content: "";
      position: absolute;
      width: 20px;
      height: 20px;
      background: #e75480;
      border-radius: 50%;
    }
    .hati-bentuk::before {
      top: -10px;
      left: 0;
    }
    .hati-bentuk::after {
      top: 0;
      left: 10px;
    }
    @keyframes mengapungKeAtas {
      0% {transform: translateY(0) rotate(-45deg);opacity: 1;}
      100% {transform: translateY(-600px) rotate(-45deg);opacity: 0;}
    }
    /* Responsif untuk mobile */
    @media (max-width: 600px) {
      body {
        padding: 12px;
      }
      h1 {
        font-size: 2.8rem;
      }
      h2 {
        font-size: 1.4rem;
      }
      .container, .album-container {
        max-width: 90vw;
        padding: 25px;
      }
      .gallery div {
        width: 100%;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Selamat Ulang Tahun, Sayangku!</h1>
    <h2 id="tanggalHariIni"></h2>
    <p class="pesan">
      Semoga hari ulang tahunmu dipenuhi dengan kebahagiaan, cinta, dan harapan yang indah.<br>
      Aku sangat beruntung memilikimu di hidupku. Terima kasih sudah menjadi cahaya dalam duniaku.<br>
      Aku mencintaimu selamanya. ❤️
    </p>
    <img class="gambar-romantis" loading="lazy" alt="Bunga Romantis" src="https://images.unsplash.com/photo-1465188162913-8fb18a7f4c6e?auto=format&fit=crop&w=600&q=80" />
    <div class="audio-control">
      <button type="button" id="toggleAudio">Putar Lagu: You'll Be In My Heart ❤️</button>
      <br />
      <button class="toggle-album-btn" id="showAlbumBtn">Tampilkan Album Foto & Video 📸🎥</button>
      <audio id="music" loop preload="auto">
        <source src="audio/lagu1.mp3.mp3" type="audio/mpeg" />
        Browser Anda tidak mendukung audio.
      </audio>
    </div>
  </div>

  <div class="album-container">
    <h2 class="album-title">Album Kenangan Foto & Video</h2>
    <div class="gallery">
      <div>
        <img src="foto/foto1.jpg" alt="Kenangan 1" />
        <p>poto paling fav</p>
      </div>
      <div>
        <img src="foto/foto2.jpg" alt="Kenangan 2" />
        <p>miror nya gacorr habiss</p>
      </div>
      <div>
        <img src="foto/foto3.jpg" alt="Kenangan 3" />
        <p>animasi dari orang tersayangg</p>
      </div>
      <div>
        <img src="foto/foto4.jpg" alt="Kenangan 4" />
        <p>poto best di kampus</p>
      </div>
      <div>
        <video controls alt="Video Kenangan 1">
          <source src="foto/vidio1.mp4" type="video/mp4" />
          Browser Anda tidak mendukung video.
        </video>
        <p>seseru itu hujan"an di pantai</p>
      </div>
      <div>
        <video controls alt="Video Kenangan 2">
          <source src="foto/vidio2.mp4" type="video/mp4" />
          Browser Anda tidak mendukung video.
        </video>
        <p>omagaa</p>
      </div>
    </div>
    <button class="toggle-album-btn" id="backBtn">Kembali ke Halaman Utama</button>
  </div>

  <div class="hati" aria-hidden="true"></div>

<script>
  // Tampilkan tanggal hari ini
  const tanggalHariIni = new Date();
  const opsiTanggal = { day: '2-digit', month: '2-digit', year: 'numeric' };
  document.getElementById('tanggalHariIni').textContent =
    "Hari ini tanggal " + tanggalHariIni.toLocaleDateString('id-ID', opsiTanggal);

  // Efek hati mengapung
  const containerHati = document.querySelector('.hati');
  function buatHati() {
    const hati = document.createElement('div');
    hati.classList.add('hati-bentuk');
    hati.style.left = Math.random() * 100 + 'vw';
    const ukuran = Math.random() * 15 + 10;
    hati.style.width = ukuran + 'px';
    hati.style.height = ukuran + 'px';
    hati.style.animationDuration = (Math.random() * 3 + 3) + 's';
    hati.style.opacity = Math.random();
    containerHati.appendChild(hati);
    setTimeout(() => { hati.remove(); }, 6000);
  }
  setInterval(buatHati, 300);

  // Kontrol audio
  const audio = document.getElementById('music');
  const toggleBtn = document.getElementById('toggleAudio');
  let playing = false;
  toggleBtn.addEventListener('click', () => {
    if (!playing) {
      audio.play();
      toggleBtn.textContent = "Jeda Lagu 🎵";
      playing = true;
    } else {
      audio.pause();
      toggleBtn.textContent = "Putar Lagu: You'll Be In My Heart ❤️";
      playing = false;
    }
  });

  // Kontrol tampilkan album dan halaman utama
  const showAlbumBtn = document.getElementById('showAlbumBtn');
  const backBtn = document.getElementById('backBtn');
  const container = document.querySelector('.container');
  const album = document.querySelector('.album-container');

  showAlbumBtn.addEventListener('click', () => {
    album.style.display = 'block';
    container.style.display = 'none';
  });

  backBtn.addEventListener('click', () => {
    album.style.display = 'none';
    container.style.display = 'block';
  });
</script>
