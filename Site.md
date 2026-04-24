# Site   
  
g9-motos  
 ├── index.html  
 ├── style.css  
 ├── script.js  
 └── logo.png   (seu logo)  
  
<!DOCTYPE html>  
<html lang="pt-BR">  
<head>  
<meta charset="UTF-8">  
<meta name="viewport" content="width=device-width, initial-scale=1.0">  
<title>G9 Motos</title>  
  
<link rel="stylesheet" href="style.css">  
</head>  
  
<body>  
  
<header>  
  <img src="logo.png">  
  <nav>  
    <a href="#">Início</a>  
    <a href="#motos">Motos</a>  
    <a href="#contato">Contato</a>  
  </nav>  
</header>  
  
<section class="banner">  
  <div>  
    <h1>G9 MOTOS</h1>  
    <p>Qualidade, procedência e confiança</p>  
    <a href="https://wa.me/5511915629892" class="btn">Falar no WhatsApp</a>  
  </div>  
</section>  
  
<section class="info">  
  <a href="https://www.instagram.com/g9.motos" target="_blank">Instagram</a>  
  <a href="https://maps.google.com/maps/place//data=!4m2!3m1!1s0x94cf016216362821:0x1540c74598c80037" target="_blank">Ver localização</a>  
</section>  
  
<section class="filtro">  
  <input type="text" id="busca" placeholder="Buscar moto...">  
</section>  
  
<section id="motos" class="motos"></section>  
  
<footer id="contato">  
  <p>WhatsApp: (11) 91562-9892</p>  
  <p>© 2026 G9 Motos</p>  
</footer>  
  
<script src="script.js"></script>  
</body>  
</html>  
  
body {  
  margin: 0;  
  font-family: Arial;  
  background: #000;  
  color: #fff;  
}  
  
header {  
  display: flex;  
  justify-content: space-between;  
  align-items: center;  
  padding: 15px 30px;  
  border-bottom: 2px solid #FFD700;  
}  
  
header img {  
  height: 55px;  
}  
  
nav a {  
  color: #FFD700;  
  margin-left: 20px;  
  text-decoration: none;  
  font-weight: bold;  
}  
  
.banner {  
  height: 450px;  
  background: url('https://images.unsplash.com/photo-1558981806-ec527fa84c39') center/cover;  
  display: flex;  
  align-items: center;  
  justify-content: center;  
  text-align: center;  
}  
  
.banner h1 {  
  font-size: 60px;  
  color: #FFD700;  
}  
  
.btn {  
  background: #FFD700;  
  color: #000;  
  padding: 12px 25px;  
  text-decoration: none;  
  font-weight: bold;  
  border-radius: 5px;  
}  
  
.info {  
  text-align: center;  
  padding: 15px;  
}  
  
.info a {  
  color: #FFD700;  
  margin: 0 15px;  
  text-decoration: none;  
}  
  
.filtro {  
  padding: 20px;  
  text-align: center;  
}  
  
.filtro input {  
  padding: 12px;  
  width: 300px;  
  border-radius: 5px;  
  border: none;  
}  
  
.motos {  
  display: grid;  
  grid-template-columns: repeat(auto-fit, minmax(250px,1fr));  
  gap: 25px;  
  padding: 20px;  
}  
  
.card {  
  background: #111;  
  border: 1px solid #FFD700;  
  border-radius: 12px;  
  overflow: hidden;  
  transition: 0.3s;  
}  
  
.card:hover {  
  transform: scale(1.03);  
}  
  
.card img {  
  width: 100%;  
  height: 180px;  
  object-fit: cover;  
}  
  
.card h3, .card p {  
  padding: 10px;  
}  
  
.whatsapp {  
  display: block;  
  background: #25D366;  
  text-align: center;  
  padding: 10px;  
  margin: 10px;  
  color: white;  
  text-decoration: none;  
  border-radius: 5px;  
}  
  
footer {  
  text-align: center;  
  padding: 20px;  
  border-top: 1px solid #FFD700;  
}  
  
const motos = [  
  {  
    nome: "Honda Fan 160",  
    preco: "R$ 13.900",  
    imagem: "https://images.unsplash.com/photo-1580310614729-ccd69652491d"  
  },  
  {  
    nome: "Yamaha Fazer 250",  
    preco: "R$ 18.500",  
    imagem: "https://images.unsplash.com/photo-1609630875171-b1321377ee65"  
  }  
];  
  
const container = document.querySelector(".motos");  
const busca = document.getElementById("busca");  
  
function mostrarMotos(lista) {  
  container.innerHTML = "";  
  
  lista.forEach(moto => {  
    container.innerHTML += `  
      <div class="card">  
        <img src="${moto.imagem}">  
        <h3>${moto.nome}</h3>  
        <p>${moto.preco}</p>  
        <a class="whatsapp"   
        href="https://wa.me/5511915629892?text=Tenho interesse na ${moto.nome}">  
        Tenho interesse  
        </a>  
      </div>  
    `;  
  });  
}  
  
busca.addEventListener("input", () => {  
  const valor = busca.value.toLowerCase();  
  const filtrado = motos.filter(m => m.nome.toLowerCase().includes(valor));  
  mostrarMotos(filtrado);  
});  
  
mostrarMotos(motos);  
  
