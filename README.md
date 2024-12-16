# Kuis-lucu  
HTML (index.html)
```
<!DOCTYPE html>
<html>
<head>
 <title>Kuis Cinta Lucu Denny dan Dessy</title>
 <link rel="stylesheet" href="style.css">
</head>
<body>
 <h1>Kuis Cinta Lucu</h1>
 <form id="kuis-cinta">
 <label for="jawab1">Apa yang membuatmu tertawa saat bersama Dessy?</label>
 <input type="text" id="jawab1" required>

 <label for="jawab2">Kebiasaan Dessy yang paling menggemaskan?</label>
 <input type="text" id="jawab2" required>

 <label for="jawab3">Apa yang kamu sukai dari Dessy?</label>
 <input type="text" id="jawab3" required>

 <label for="jawab4">Bagaimana kamu menunjukkan cinta kepada Dessy?</label>
 <input type="text" id="jawab4" required>

 <label for="jawab5">Momen paling lucu bersama Dessy?</label>
 <input type="text" id="jawab5" required>

 <button id="submit">Cek Hasil</button>
 </form>
 <div id="hasil"></div>

 <script src="script.js"></script>
</body>
</html>
```

CSS (style.css)
```
body {
 background-color: #87CEEB; /* Biru */
 font-family: Arial, sans-serif;
}

h1 {
 color: #34C759; /* Hijau */
 text-align: center;
}

form {
 width: 50%;
 margin: 40px auto;
 padding: 20px;
 background-color: #fff;
 border: 1px solid #ddd;
 box-shadow: 0 0 10px rgba(0,0,0,0.1);
}

label {
 display: block;
 margin-bottom: 10px;
}

input[type="text"] {
 width: 100%;
 height: 40px;
 margin-bottom: 20px;
 padding: 10px;
 border: 1px solid #ccc;
}

button {
 width: 100%;
 height: 40px;
 background-color: #34C759; /* Hijau */
 color: #fff;
 border: none;
 cursor: pointer;
}

button:hover {
 background-color: #3e8e41;
}

#hasil {
 font-size: 24px;
 font-weight: bold;
 text-align: center;
 margin-top: 20px;
}
```

JavaScript (script.js)
```
const form = document.getElementById('kuis-cinta');
const hasil = document.getElementById('hasil');

form.addEventListener('submit', (e) => {
 e.preventDefault();
 const jawab1 = document.getElementById('jawab1').value;
 const jawab2 = document.getElementById('jawab2').value;
 const jawab3 = document.getElementById('jawab3').value;
 const jawab4 = document.getElementById('jawab4').value;
 const jawab5 = document.getElementById('jawab5').value;
 const skor = hitungSkor(jawab1, jawab2, jawab3, jawab4, jawab5);
 tampilkanHasil(skor);
});

function hitungSkor(jawab1, jawab2, jawab3, jawab4, jawab5) {
 let skor = 0;
 if (jawab1.toLowerCase().includes('dessy')) skor += 20;
 if (jawab2.toLowerCase().includes('baik')) skor += 20;
 if (jawab3.toLowerCase().includes('cinta')) skor += 20;
 if (jawab4.toLowerCase().includes('sayang')) skor += 20;
 if (jawab5.toLowerCase().includes('lucu')) skor += 20;
 return skor;
}

function tampilkanHasil(skor) {
 if (skor >= 100) {
 hasil.innerHTML = 'Kamu sangat mencintai Dessy!';
 } else if (skor >= 60) {
 hasil.innerHTML = 'Kamu mencintai Dessy!';
 } else {
 hasil.innerHTML = 'Kamu perlu lebih mencintai Dessy!'
