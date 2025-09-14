<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<title>Галерея машин</title>
<style>
  body {
    margin: 0;
    font-family: Arial, sans-serif;
    background: #222;
    color: #fff;
    text-align: center;
  }

  h1 {
    margin-top: 20px;
  }

  .cars-container {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 20px;
    margin-top: 30px;
  }

  .car {
    cursor: pointer;
    transition: transform 0.2s;
    border: 2px solid #fff;
    border-radius: 10px;
    overflow: hidden;
    width: 200px;
  }

  .car img {
    width: 100%;
  }

  .car:hover {
    transform: scale(1.05);
  }

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
</style>
</head>
<body>

<h1>Выберите машину</h1>

<div class="cars-container">
  <div class="car" data-name="Ferrari F8" data-info="Производитель: Ferrari\nМаксимальная скорость: 340 км/ч\nМощность: 710 л.с.">
    <img src="https://i.imgur.com/2yG0XbC.png" alt="Ferrari">
    <p>Ferrari F8</p>
  </div>

  <div class="car" data-name="Lamborghini Huracan" data-info="Производитель: Lamborghini\nМаксимальная скорость: 325 км/ч\nМощность: 640 л.с.">
    <img src="https://i.imgur.com/0bJ2ySx.png" alt="Lamborghini">
    <p>Lamborghini Huracan</p>
  </div>

  <div class="car" data-name="Porsche 911" data-info="Производитель: Porsche\nМаксимальная скорость: 310 км/ч\nМощность: 450 л.с.">
    <img src="https://i.imgur.com/1MZfZT0.png" alt="Porsche">
    <p>Porsche 911</p>
  </div>
</div>

<div class="info" id="infoBox">
  <span class="close-btn" id="closeBtn">×</span>
  <h2 id="carName"></h2>
  <p id="carInfo"></p>
</div>

<script>
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
</script>

</body>
</html># Cars-and-information
