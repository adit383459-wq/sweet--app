# sweet--app
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <title>Untuk Kamu 💕</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body{
      margin:0; font-family: Arial, sans-serif;
      background: linear-gradient(135deg,#ff758c,#ff7eb3);
      min-height:100vh; display:flex; align-items:center; justify-content:center;
      color:#fff; text-align:center;
    }
    .card{
      background: rgba(255,255,255,.2);
      backdrop-filter: blur(6px);
      padding:22px; border-radius:18px;
      width:90%; max-width:360px;
      box-shadow:0 10px 30px rgba(0,0,0,.25);
    }
    h1{margin-top:0}
    input,button{
      border:none; border-radius:999px;
      padding:12px 16px; font-size:16px;
    }
    input{width:85%; margin:10px 0}
    button{background:#ff4d6d; color:#fff; margin:8px}
    small{opacity:.9}
  </style>
</head>
<body>

<div class="card" id="gate">
  <h1>🔐 Kode Rahasia</h1>
  <input id="kode" type="password" placeholder="Masukkan kode">
  <br>
  <button onclick="cek()">Buka 💌</button>
  <p><small>Hint: tanggal spesial 😉</small></p>
</div>

<div class="card" id="app" style="display:none">
  <h1 id="judul">Hai ❤️</h1>
  <p id="pesan"></p>
  <p><b>Hari jadian:</b> <span id="hari"></span> hari</p>
  <button onclick="bunyi()">🎵 Putar Musik</button>
  <button onclick="getar()">📳 Getar</button>
</div>

<audio id="music">
  <source src="https://www.soundjay.com/human/sounds/heartbeat-01.mp3" type="audio/mpeg">
</audio>

<script>
  // ====== CUSTOM DI SINI ======
  const KODE = "17";
  const NAMA = "Lilis Karlina Awaliahh";
  const PESAN = "Makasih ya sudah jadi bagian penting di hidupku 💖";
  const TGL_JADIAN = "2025-08-17";
  // ===========================

  function cek(){
    if(document.getElementById('kode').value === KODE){
      document.getElementById('gate').style.display='none';
      document.getElementById('app').style.display='block';
      document.getElementById('judul').innerText = "Hai, " + NAMA + " ❤️";
      document.getElementById('pesan').innerText = PESAN;
      hitungHari();
    } else alert("Kode salah 😝");
  }

  function hitungHari(){
    const start = new Date(TGL_JADIAN);
    const now = new Date();
    const diff = Math.floor((now-start)/(1000*60*60*24));
    document.getElementById('hari').innerText = diff >= 0 ? diff : 0;
  }

  function bunyi(){ document.getElementById('music').play(); }
  function getar(){ if(navigator.vibrate) navigator.vibrate([200,100,200]); }
</script>

</body>
</
