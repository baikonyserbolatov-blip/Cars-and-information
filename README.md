<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<title>Галерея машин</title>
<style>
  body {
    margin: 0;
    font-family: Arial, sans-serif;
    background: #111;
    color: #fff;
    overflow-x: hidden;
  }

  /* Главный экран */
  #mainMenu {
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
    flex-direction: column;
    background: #222;
  }

  /* Меню */
  .menu {
    display: flex;
    gap: 50px;
    font-size: 32px;
    position: relative;
    z-index: 1;
  }

  .menu-item {
    cursor: pointer;
    transition: color 0.2s;
  }

  .menu-item:hover {
    color: #ffcc00;
  }

  /* Круг подсветки */
  .cursor-light {
    position: absolute;
    width: 150px;
    height: 150px;
    background: radial-gradient(circle, rgba(255,255,200,0.5) 0%, rgba(255,255,200,0) 60%);
    border-radius: 50%;
    pointer-events: none;
    transform: translate(-50%, -50%);
    transition: width 0.2s, height 0.2s;
  }

  /* Галерея машин */
  #carsPage {
    display: none;
    padding: 20px;
    text-align: center;
    background: #111;
    min-height: 100vh;
  }

  .cars-container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
    justify-items: center;
    margin-top: 30px;
  }

  .car {
    cursor: pointer;
    border: 2px solid #fff;
    border-radius: 10px;
    overflow: hidden;
    width: 200px;
    transition: transform 0.2s;
  }

  .car img {
    width: 100%;
  }

  .car:hover {
    transform: scale(1.05);
  }

  /* Блок с информацией */
  .info {
    display: none;
    margin-top: 20px;
    background: #333;
    padding: 20px;
    border-radius: 10px;
    width: 400px;
    margin-left: auto;
    margin-right: auto;
    text-align: left;
  }

  .close-btn {
    cursor: pointer;
    color: yellow;
    float: right;
    font-weight: bold;
  }

  .back-btn {
    margin-top: 20px;
    cursor: pointer;
    color: #ffcc00;
    font-size: 20px;
  }
</style>
</head>
<body>

<!-- Главный экран -->
<div id="mainMenu">
  <h1>Главное меню</h1>
  <div class="menu">
    <div class="menu-item" id="menuCars">Машины</div>
    <div class="menu-item">Контакты</div>
    <div class="menu-item">О нас</div>
  </div>
  <div class="cursor-light" id="cursorLight"></div>
</div>

<!-- Страница с машинами -->
<div id="carsPage">
  <h1>Выберите машину</h1>
  <div class="cars-container">
    <!-- Примеры 9 машин -->
    <div class="car" data-name="Ferrari F8" data-info="Производитель: Ferrari\nМаксимальная скорость: 340 км/ч\nМощность: 710 л.с.\nЦена: $280,000" >
      <img src="https://unsplash.com/photos/1zYd3v9Q8J4/download?force=true&w=400" alt="Ferrari">
      <p>Ferrari F8</p>
    </div>
    <div class="car" data-name="Lamborghini Huracan" data-info="Производитель: Lamborghini\nМаксимальная скорость: 325 км/ч\nМощность: 640 л.с.\nЦена: $260,000">
      <img src="https://unsplash.com/photos/8uK0FzVJ4Vg/download?force=true&w=400" alt="Lamborghini">
      <p>Lamborghini Huracan</p>
    </div>
    <div class="car" data-name="Porsche 911" data-info="Производитель: Porsche\nМаксимальная скорость: 310 км/ч\nМощность: 450 л.с.\nЦена: $150,000">
      <img src="https://unsplash.com/photos/1zYd3v9Q8J4/download?force=true&w=400" alt="Porsche">
      <p>Porsche 911</p>
    </div>
    <!-- Добавляем ещё 6 машин по аналогии -->
    <div class="car" data-name="McLaren 720S" data-info="Производитель: McLaren\nМаксимальная скорость: 341 км/ч\nМощность: 710 л.с.\nЦена: $300,000">
      <img src="https://unsplash.com/photos/G4LwHSI14eQ/download?force=true&w=400" alt="McLaren">
      <p>McLaren 720S</p>
    </div>
    <div class="car" data-name="Aston Martin DB11" data-info="Производитель: Aston Martin\nМаксимальная скорость: 322 км/ч\nМощность: 600 л.с.\nЦена: $200,000">
      <img src="https://unsplash.com/photos/E2psl9xU1iQ/download?force=true&w=400" alt="Aston Martin">
      <p>Aston Martin DB11</p>
    </div>
    <div class="car" data-name="Bugatti Chiron" data-info="Производитель: Bugatti\nМаксимальная скорость: 420 км/ч\nМощность: 1500 л.с.\nЦена: $3,000,000">
      <img src="https://unsplash.com/photos/qjZ8r0-J5qI/download?force=true&w=400" alt="Bugatti">
      <p>Bugatti Chiron</p>
    </div>
    <div class="car" data-name="Chevrolet Corvette" data-info="Производитель: Chevrolet\nМаксимальная скорость: 312 км/ч\nМощность: 495 л.с.\nЦена: $90,000">
      <img src="https://unsplash.com/photos/2xX8vJx9G3Q/download?force=true&w=400" alt="Corvette">
      <p>Chevrolet Corvette</p>
    </div>
    <div class="car" data-name="Ford Mustang" data-info="Производитель: Ford\nМаксимальная скорость: 250 км/ч\nМощность: 450 л.с.\nЦена: $60,000">
      <img src="https://unsplash.com/photos/lrQPTQs7nQQ/download?force=true&w=400" alt="Mustang">
      <p>Ford Mustang</p>
    </div>
    <div class="car" data-name="Nissan GT-R" data-info="Производитель: Nissan\nМаксимальная скорость: 315 км/ч\nМощность: 565 л.с.\nЦена: $115,000">
      <img src="https://unsplash.com/photos/3MnJG0h_XQo/download?force=true&w=400" alt="Nissan">
      <p>Nissan GT-R</p>
    </div>
  </div>

  <!-- Информационный блок -->
  <div class="info" id="infoBox">
    <span class="close-btn" id="closeBtn">×</span>
    <h2 id="carName"></h2>
    <p id="carInfo"></p>
  </div>

  <div class="back-btn" id="backBtn">← Назад в меню</div>
</div>

<script>
  // Подсветка курсора на главном меню
  const cursor = document.getElementById("cursorLight");
  document.addEventListener("mousemove", e => {
    cursor.style.left = e.clientX + "px";
    cursor.style.top = e.clientY + "px";
  });

  const menuItems = document.querySelectorAll(".menu-item");
  menuItems.forEach(item => {
    item.addEventListener("mouseenter", () => {
      cursor.style.width = "200px";
      cursor.style.height = "200px";
    });
    item.addEventListener("mouseleave", () => {
      cursor.style.width = "150px";
      cursor.style.height = "150px";
    });
  });

  // Переход к странице с машинами
  const menuCars = document.getElementById("menuCars");
  const mainMenu = document.getElementById("mainMenu");
  const carsPage = document.getElementById("carsPage");

  menuCars.addEventListener("click", () => {
    mainMenu.style.display = "none";
    carsPage.style.display = "block";
  });

  // Открытие информации о машине
  const cars = document.querySelectorAll(".car");
  const infoBox = document.getElementById("infoBox");
  const carNameEl = document.getElementById("carName");
  const carInfoEl = document.getElementById("carInfo");
  const closeBtn = document.getElementById("closeBtn");

  cars.forEach(car => {
    car.addEventListener("click", () => {
      carNameEl.textContent = car.getAttribute("data-name");
      carInfoEl.textContent = car.getAttribute("data-info").replace(/\\n/g, "\n");
      infoBox.style.display = "block";
    });
  });

  closeBtn.addEventListener("click", () => {
    infoBox.style.display = "none";
  });

  // Назад в главное меню
  const backBtn = document.getElementById("backBtn");
  backBtn.addEventListener("click", () => {
    carsPage.style.display = "none";
    mainMenu.style.display = "flex";
  });
</script>

</body>
</html>
