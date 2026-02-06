<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<title>Sweet App 💖</title>
<style>
body{
  font-family: Arial, sans-serif;
  background: linear-gradient(135deg,#ff9a9e,#fad0c4);
  text-align:center;
  padding:40px;
}
.card{
  background:#fff;
  padding:20px;
  border-radius:15px;
  max-width:400px;
  margin:auto;
  box-shadow:0 10px 25px rgba(0,0,0,.2);
}
input,button{
  padding:10px;
  width:80%;
  margin:10px;
  border-radius:10px;
  border:1px solid #ccc;
}
button{
  background:#ff5e78;
  color:white;
  border:none;
  font-size:16px;
}
#app{display:none;}
</style>
</head>

<body>

<div class="card" id="gate">
  <h2>🔐 Masukkan Kode Rahasia</h2>
  <input id="kode" placeholder="Kode rahasia">
  <br>
  <button onclick="cek()">Buka 💖</button>
</div>

<div class="card" id="app">
  <h2 id="judul"></h2>
  <p id="pesan"></p>
  <h3>Hari jadian: <span id="hari"></span> hari</h3>

  <button onclick="musik.play()">🎵 Putar Musik</button>
</div>

<audio id="musik" loop>
  <source src="musik.mp3" type="audio/mpeg">
</audio>

<script>
// ======= CUSTOM DI SINI =======
const KODE = "17";
const NAMA = "Lilis Karlina Awaliahh";
const PESAN = "Makasih ya sudah jadi bagian penting di hidupku 💖";
const TGL_JADIAN = "2025-08-17";
// ==============================

const musik = document.getElementById("musik");

function cek(){
  if(document.getElementById("kode").value === KODE){
    document.getElementById("gate").style.display="none";
    document.getElementById("app").style.display="block";
    document.getElementById("judul").innerText = "Hai, " + NAMA + " ❤️";
    document.getElementById("pesan").innerText = PESAN;
    hitungHari();
  }else{
    alert("Kode salah 😝");
  }
}

function hitungHari(){
  const start = new Date(TGL_JADIAN);
  const now = new Date();
  const diff = Math.floor((now-start)/(1000*60*60*24));
  document.getElementById("hari").innerText = diff;
}
</script>

</body>
</html>
