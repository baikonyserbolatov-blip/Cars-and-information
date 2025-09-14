<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<title>Car Gallery</title>
<style>
  body {
    margin: 0;
    font-family: Arial, sans-serif;
    background: url('https://images.unsplash.com/photo-1502877338535-766e1452684a?auto=format&fit=crop&w=1920&q=80') no-repeat center center/cover;
    color: #fff;
    overflow-x: hidden;
  }

  /* ===== Главное меню ===== */
  header {
    background: rgba(0,0,0,0.6);
    padding: 20px;
    text-align: center;
    position: fixed;
    width: 100%;
    top: 0;
    z-index: 1000;
    backdrop-filter: blur(6px);
  }
  nav a {
    margin: 0 25px;
    text-decoration: none;
    color: #fff;
    font-size: 22px;
    position: relative;
    transition: color 0.3s;
  }
  nav a:hover {
    color: #ffcc00;
  }
  nav a::after {
    content: '';
    display: block;
    height: 3px;
    background: #ffcc00;
    width: 0;
    transition: width 0.3s;
    margin: 0 auto;
  }
  nav a:hover::after {
    width: 100%;
  }

  /* ===== Секции ===== */
  section {
    min-height: 100vh;
    padding: 120px 60px 60px;
    background: rgba(0,0,0,0.6);
    backdrop-filter: blur(4px);
  }
  h1 {
    text-align: center;
    margin-bottom: 40px;
    font-size: 36px;
    letter-spacing: 2px;
  }

  /* ===== Галерея машин ===== */
  .gallery {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 30px;
  }
  .car-card {
    background: rgba(255,255,255,0.1);
    border-radius: 15px;
    overflow: hidden;
    cursor: pointer;
    transition: transform 0.3s, box-shadow 0.3s;
  }
  .car-card:hover {
    transform: scale(1.05);
    box-shadow: 0 0 25px rgba(255,255,0,0.6);
  }
  .car-card img {
    width: 100%;
    height: 180px;
    object-fit: cover;
  }
  .car-card h3 {
    padding: 15px;
    text-align: center;
  }

  /* ===== Модальное окно ===== */
  .modal {
    display: none;
    position: fixed;
    z-index: 2000;
    left: 0; top: 0;
    width: 100%; height: 100%;
    background: rgba(0,0,0,0.9);
    justify-content: center;
    align-items: center;
  }
  .modal-content {
    background: #222;
    padding: 25px;
    border-radius: 15px;
    max-width: 700px;
    color: #fff;
    text-align: left;
    position: relative;
  }
  .modal-content img.car-img {
    width: 100%;
    border-radius: 10px;
    margin-bottom: 15px;
  }
  .modal-content h2 {
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .modal-content h2 img.logo {
    width: 40px;
    height: 40px;
    object-fit: contain;
  }
  .close {
    position: absolute;
    right: 15px;
    top: 10px;
    font-size: 30px;
    cursor: pointer;
  }

  /* ===== О нас ===== */
  .about {
    text-align: center;
    font-size: 20px;
    line-height: 1.6;
  }
  .socials a {
    margin: 0 15px;
    color: #ffcc00;
    font-weight: bold;
    text-decoration: none;
  }
  .socials a:hover {
    text-decoration: underline;
  }
</style>
</head>
<body>

<header>
  <nav>
    <a href="#bmw">BMW</a>
    <a href="#lexus">Lexus</a>
    <a href="#mercedes">Mercedes</a>
    <a href="#about">О нас</a>
  </nav>
</header>

<!-- ===== BMW ===== -->
<section id="bmw">
  <h1>BMW</h1>
  <div class="gallery">
    <div class="car-card" onclick="openModal('BMW M3','https://cdn.pixabay.com/photo/2016/03/27/19/57/bmw-1281640_1280.jpg','https://upload.wikimedia.org/wikipedia/commons/4/44/BMW.svg','480 л.с., 0-100 км/ч за 4.1 сек, культовый спортседан')">
      <img src="https://cdn.pixabay.com/photo/2016/03/27/19/57/bmw-1281640_1280.jpg" alt="BMW M3">
      <h3>BMW M3</h3>
    </div>
    <div class="car-card" onclick="openModal('BMW i8','https://cdn.pixabay.com/photo/2018/03/01/10/24/bmw-3198826_1280.jpg','https://upload.wikimedia.org/wikipedia/commons/4/44/BMW.svg','Гибридный спорткар будущего, двери-бабочки, ускорение 4.4 сек')">
      <img src="https://cdn.pixabay.com/photo/2018/03/01/10/24/bmw-3198826_1280.jpg" alt="BMW i8">
      <h3>BMW i8</h3>
    </div>
  </div>
</section>

<!-- ===== Lexus ===== -->
<section id="lexus">
  <h1>Lexus</h1>
  <div class="gallery">
    <div class="car-card" onclick="openModal('Lexus LFA','https://cdn.pixabay.com/photo/2016/11/18/16/09/lexus-1835590_1280.jpg','https://upload.wikimedia.org/wikipedia/commons/0/0b/Lexus_division_emblem.svg','Редчайший суперкар, 4.8 V10, звук как у F1, 560 л.с.')">
      <img src="https://cdn.pixabay.com/photo/2016/11/18/16/09/lexus-1835590_1280.jpg" alt="Lexus LFA">
      <h3>Lexus LFA</h3>
    </div>
    <div class="car-card" onclick="openModal('Lexus LC500','https://cdn.pixabay.com/photo/2021/01/23/16/45/lexus-5943392_1280.jpg','https://upload.wikimedia.org/wikipedia/commons/0/0b/Lexus_division_emblem.svg','Атмосферный V8 5.0, 471 л.с., роскошное купе премиум-класса')">
      <img src="https://cdn.pixabay.com/photo/2021/01/23/16/45/lexus-5943392_1280.jpg" alt="Lexus LC500">
      <h3>Lexus LC500</h3>
    </div>
  </div>
</section>

<!-- ===== Mercedes ===== -->
<section id="mercedes">
  <h1>Mercedes</h1>
  <div class="gallery">
    <div class="car-card" onclick="openModal('Mercedes-AMG GT','https://cdn.pixabay.com/photo/2017/03/27/14/56/mercedes-2178774_1280.jpg','https://upload.wikimedia.org/wikipedia/commons/9/90/Mercedes-Logo.svg','4.0 V8 Biturbo, 510 л.с., идеальный баланс стиля и скорости')">
      <img src="https://cdn.pixabay.com/photo/2017/03/27/14/56/mercedes-2178774_1280.jpg" alt="Mercedes AMG GT">
      <h3>Mercedes-AMG GT</h3>
    </div>
    <div class="car-card" onclick="openModal('Mercedes G-Class','https://cdn.pixabay.com/photo/2020/05/28/12/47/mercedes-5233717_1280.jpg','https://upload.wikimedia.org/wikipedia/commons/9/90/Mercedes-Logo.svg','Легендарный G-Wagon: внедорожник-икона, V8, роскошь и мощь')">
      <img src="https://cdn.pixabay.com/photo/2020/05/28/12/47/mercedes-5233717_1280.jpg" alt="Mercedes G-Class">
      <h3>Mercedes G-Class</h3>
    </div>
  </div>
</section>

<!-- ===== О нас ===== -->
<section id="about">
  <h1>О нас</h1>
  <div class="about">
    <p>Привет! 👋 Меня зовут Байқоныс.  
    Я увлекаюсь машинами и веб-дизайном, и этот сайт я сделал для того, чтобы делиться страстью к автомобилям 🚗🔥</p>
    <div class="socials">
      <p>Мои соцсети:</p>
      <a href="#">Instagram:ba1kony8__</a>
      <a href="#">TikTik: @just_bakooo</a>
      <a href="#">YouTube</a>
    </div>
  </div>
</section>

<!-- ===== Модалка ===== -->
<div class="modal" id="modal">
  <div class="modal-content">
    <span class="close" onclick="closeModal()">&times;</span>
    <h2 id="carTitle"><img src="" class="logo"> Название</h2>
    <img src="" class="car-img" id="carImg" alt="car">
    <p id="carInfo"></p>
  </div>
</div>

<script>
function openModal(title, img, logo, info) {
  document.getElementById("modal").style.display = "flex";
  document.getElementById("carTitle").innerHTML = `<img src="${logo}" class="logo"> ${title}`;
  document.getElementById("carImg").src = img;
  document.getElementById("carInfo").innerText = info;
}
function closeModal() {
  document.getElementById("modal").style.display = "none";
}
</script>

</body>
</html>
