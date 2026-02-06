<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<title>Sweet App 💖</title>

<style>
body{
  font-family: Arial, sans-serif;
  background: linear-gradient(135deg,#ff9ecf,#ffd6e8);
  text-align:center;
  padding:40px;
}

.box{
  background:#fff;
  padding:25px;
  border-radius:15px;
  max-width:420px;
  margin:auto;
  box-shadow:0 5px 15px rgba(0,0,0,.2);
}

input, button{
  padding:10px;
  margin-top:10px;
  width:80%;
  border-radius:10px;
  border:1px solid #ccc;
}

button{
  background:#ff4da6;
  color:white;
  border:none;
}

#app{
  display:none;
}
</style>
</head>

<body>

<div class="box" id="gate">
  <h2>🔐 Masukkan Kode Rahasia</h2>
  <input type="password" id="kode" placeholder="Kode rahasia">
  <br>
  <button onclick="cek()">Buka 💖</button>
</div>

<div class="box" id="app">
  <h2>💌 Hai Lilis Karlina Awaliahh</h2>
  <p>Makasih ya sudah jadi bagian penting di hidupku 💖</p>
  <p>📅 Hari jadian kita:</p>
  <b id="hari"></b>
</div>

<audio id="musik" src="lagu.mp3" loop></audio>

<script>
const KODE = "17";
const TGL_JADIAN = "2025-08-17";

const musik = document.getElementById("musik");

function cek(){
  const input = document.getElementById("kode").value;

  if(input === KODE){
    document.getElementById("gate").style.display = "none";
    document.getElementById("app").style.display = "block";

    const hariList = ["Minggu","Senin","Selasa","Rabu","Kamis","Jumat","Sabtu"];
    const tgl = new Date(TGL_JADIAN);

    document.getElementById("hari").innerText =
      hariList[tgl.getDay()] + ", 17 Agustus 2025";

    musik.volume = 0.6;
    musik.play();
  } else {
    alert("Kode salah 😅");
  }
}
</script>

</body>
</html>
