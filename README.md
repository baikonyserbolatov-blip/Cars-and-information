<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>Атмосферная галерея машин — 27 моделей</title>
<style>
  :root{
    --accent: #ffcc00;
    --glass: rgba(0,0,0,0.6);
    --panel: rgba(255,255,255,0.06);
  }
  *{box-sizing:border-box}
  body {
    margin: 0;
    font-family: Inter, Arial, sans-serif;
    color: #fff;
    background: url('https://images.unsplash.com/photo-1502877338535-766e1452684a?auto=format&fit=crop&w=1920&q=80') center/cover no-repeat fixed;
    -webkit-font-smoothing:antialiased;
    -moz-osx-font-smoothing:grayscale;
  }

  /* Header / меню */
  header {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 2000;
    padding: 14px 20px;
    display:flex;
    align-items:center;
    justify-content:center;
    background: linear-gradient(180deg, rgba(0,0,0,0.6), rgba(0,0,0,0.25));
    backdrop-filter: blur(6px);
    border-bottom: 1px solid rgba(255,255,255,0.04);
  }
  nav {
    display:flex;
    gap: 16px;
    flex-wrap:wrap;
    justify-content:center;
    max-width:1200px;
  }
  nav a {
    color:#fff;
    text-decoration:none;
    font-weight:600;
    padding:8px 10px;
    border-radius:8px;
    position:relative;
    transition: color .25s, transform .15s;
  }
  nav a:hover { color: var(--accent); transform: translateY(-2px); }
  nav a::after {
    content:'';
    display:block;
    height:3px;
    width:0;
    background:var(--accent);
    border-radius:3px;
    margin-top:6px;
    transition: width .25s;
  }
  nav a:hover::after { width:100%; }

  /* Круг подсветки курсора (видимый поверх header) */
  .cursor-light {
    position: fixed;
    pointer-events: none;
    width: 160px;
    height: 160px;
    left: 50%;
    top: 50%;
    transform: translate(-50%,-50%);
    background: radial-gradient(circle, rgba(255,230,160,0.45) 0%, rgba(255,230,160,0.06) 45%, rgba(255,230,160,0) 70%);
    border-radius: 50%;
    mix-blend-mode: screen;
    transition: width .18s ease, height .18s ease, opacity .18s ease;
    z-index:1500;
  }

  /* Основные секции */
  section {
    padding: 120px 28px 80px;
    min-height: 100vh;
    background: linear-gradient(180deg, rgba(0,0,0,0.35), rgba(0,0,0,0.6));
  }
  .wrap {
    max-width: 1200px;
    margin: 0 auto;
  }
  h1.section-title {
    text-align:center;
    margin: 0 0 24px;
    font-size: 36px;
    letter-spacing:1px;
  }

  /* Галерея карточек */
  .gallery {
    display:grid;
    grid-template-columns: repeat(auto-fit,minmax(260px,1fr));
    gap: 22px;
  }
  .car-card {
    background: var(--panel);
    border-radius: 14px;
    overflow:hidden;
    cursor:pointer;
    transition: transform .28s cubic-bezier(.2,.9,.2,1), box-shadow .28s;
    border: 1px solid rgba(255,255,255,0.06);
    display:flex;
    flex-direction:column;
    height:100%;
  }
  .car-card:hover {
    transform: translateY(-10px) scale(1.01);
    box-shadow: 0 12px 40px rgba(0,0,0,0.6), 0 0 30px rgba(255,204,0,0.08);
  }
  .car-card img.thumb {
    width:100%;
    height:180px;
    object-fit:cover;
    display:block;
  }
  .car-card .meta {
    padding:14px;
    display:flex;
    flex-direction:column;
    gap:6px;
    flex:1;
  }
  .car-card .meta h3 {
    margin:0;
    font-size:18px;
    text-align:center;
  }
  .car-card .meta p.short {
    margin:0;
    font-size:13px;
    color: rgba(255,255,255,0.85);
    text-align:center;
  }

  /* Модал */
  .modal {
    display:none;
    position:fixed;
    inset:0;
    z-index:3000;
    align-items:center;
    justify-content:center;
    background: linear-gradient(180deg, rgba(0,0,0,0.6), rgba(0,0,0,0.85));
    padding:20px;
  }
  .modal.show { display:flex; }

  .modal-card {
    width:100%;
    max-width:900px;
    background: linear-gradient(180deg, rgba(30,30,30,0.98), rgba(18,18,18,0.98));
    border-radius:14px;
    overflow:hidden;
    box-shadow: 0 20px 60px rgba(0,0,0,0.7);
    position:relative;
    color:#fff;
  }
  .modal-top {
    position:relative;
  }
  .modal-top img.car-img {
    width:100%;
    height:360px;
    object-fit:cover;
    display:block;
    filter: saturate(1.05) contrast(1.02);
  }
  .modal-body {
    padding:20px 22px 26px;
  }
  .modal-body h2 {
    margin:0 0 8px;
    display:flex;
    align-items:center;
    gap:12px;
    font-size:22px;
  }
  .modal-body h2 img.logo {
    width:46px;
    height:46px;
    object-fit:contain;
    border-radius:8px;
    background:rgba(255,255,255,0.06);
    padding:6px;
  }
  .modal-body p.info {
    margin:8px 0 0;
    line-height:1.6;
    color: #e6e6e6;
    white-space:pre-line;
  }
  .modal-close {
    position:absolute;
    right:14px;
    top:12px;
    font-size:28px;
    color:var(--accent);
    cursor:pointer;
  }

  /* О нас */
  .about {
    text-align:center;
    font-size:18px;
    line-height:1.6;
    max-width:900px;
    margin: 12px auto 0;
  }
  .socials {
    margin-top:14px;
    display:flex;
    justify-content:center;
    gap:18px;
  }
  .socials a {
    color:var(--accent);
    text-decoration:none;
    font-weight:700;
  }

  /* Responsive tweaks */
  @media (max-width:700px){
    .modal-body h2 { font-size:18px; }
    .modal-top img.car-img { height:220px; }
    header { padding:10px; }
  }

</style>
</head>
<body>

<header>
  <nav id="mainNav" class="wrap">
    <!-- Меню: 9 брендов + О нас -->
    <a href="#bmw">BMW</a>
    <a href="#lexus">Lexus</a>
    <a href="#mercedes">Mercedes</a>
    <a href="#audi">Audi</a>
    <a href="#toyota">Toyota</a>
    <a href="#ferrari">Ferrari</a>
    <a href="#porsche">Porsche</a>
    <a href="#lamborghini">Lamborghini</a>
    <a href="#bugatti">Bugatti</a>
    <a href="#about">О нас</a>
  </nav>
</header>

<!-- подсветка курсора -->
<div class="cursor-light" id="cursorLight"></div>

<!-- ===== Секция BMW ===== -->
<section id="bmw">
  <div class="wrap">
    <h1 class="section-title">BMW</h1>
    <div class="gallery">
      <div class="car-card" onclick="openModal('BMW M3','https://cdn.pixabay.com/photo/2016/03/27/19/57/bmw-1281640_1280.jpg','https://upload.wikimedia.org/wikipedia/commons/4/44/BMW.svg','Производитель: BMW\nМодель: M3\nДвигатель: 3.0 L TwinTurbo I6\nМощность: ~480 л.с.\n0-100 км/ч: ~4.1 с\nКраткий факт: Спортивный седан, сочетающий комфорт и трековые свойства.')">
        <img class="thumb" src="https://cdn.pixabay.com/photo/2016/03/27/19/57/bmw-1281640_1280.jpg" alt="BMW M3">
        <div class="meta">
          <h3>BMW M3</h3>
          <p class="short">Культовый спортседан — мощность и управляемость.</p>
        </div>
      </div>

      <div class="car-card" onclick="openModal('BMW i8','https://cdn.pixabay.com/photo/2018/03/01/10/24/bmw-3198826_1280.jpg','https://upload.wikimedia.org/wikipedia/commons/4/44/BMW.svg','Производитель: BMW\nМодель: i8\nДвигатель: Гибрид (турбированный бензин + электромотор)\nМощность: ~369 л.с.\nКраткий факт: Футуристичный гибрид с дверями-бабочками — синтетика спорта и экономичности.')">
        <img class="thumb" src="https://cdn.pixabay.com/photo/2018/03/01/10/24/bmw-3198826_1280.jpg" alt="BMW i8">
        <div class="meta">
          <h3>BMW i8</h3>
          <p class="short">Гибридное спортивное купе с необычным дизайном.</p>
        </div>
      </div>

      <div class="car-card" onclick="openModal('BMW X5 M','https://cdn.pixabay.com/photo/2017/01/06/19/15/car-1958457_1280.jpg','https://upload.wikimedia.org/wikipedia/commons/4/44/BMW.svg','Производитель: BMW\nМодель: X5 M\nТип: Высокопроизводительный внедорожник\nМощность: ~600 л.с. (в версиях Competition)\nКраткий факт: Большая семья спортивных SUV с трековыми возможностями.')">
        <img class="thumb" src="https://cdn.pixabay.com/photo/2017/01/06/19/15/car-1958457_1280.jpg" alt="BMW X5 M">
        <div class="meta">
          <h3>BMW X5 M</h3>
          <p class="short">Мощный премиум-SUV для тех, кто любит скорость и комфорт.</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ===== Секция Lexus ===== -->
<section id="lexus">
  <div class="wrap">
    <h1 class="section-title">Lexus</h1>
    <div class="gallery">
      <div class="car-card" onclick="openModal('Lexus LFA','https://cdn.pixabay.com/photo/2016/11/18/16/09/lexus-1835590_1280.jpg','https://upload.wikimedia.org/wikipedia/commons/0/0b/Lexus_division_emblem.svg','Производитель: Lexus\nМодель: LFA\nДвигатель: 4.8L V10\nМощность: 552 л.с.\nКраткий факт: Редкий японский суперкар с вдохновляющим звуком двигателя.')">
        <img class="thumb" src="https://cdn.pixabay.com/photo/2016/11/18/16/09/lexus-1835590_1280.jpg" alt="Lexus LFA">
        <div class="meta">
          <h3>Lexus LFA</h3>
          <p class="short">Японский суперкар — звук и редкость.</p>
        </div>
      </div>

      <div class="car-card" onclick="openModal('Lexus LC500','https://cdn.pixabay.com/photo/2021/01/23/16/45/lexus-5943392_1280.jpg','https://upload.wikimedia.org/wikipedia/commons/0/0b/Lexus_division_emblem.svg','Производитель: Lexus\nМодель: LC500\nДвигатель: 5.0L V8\nМощность: 471 л.с.\nКраткий факт: Роскошное купе с акцентом на комфорт и стиль.')">
        <img class="thumb" src="https://cdn.pixabay.com/photo/2021/01/23/16/45/lexus-5943392_1280.jpg" alt="Lexus LC500">
        <div class="meta">
          <h3>Lexus LC500</h3>
          <p class="short">Красивое премиум-купе с V8.</p>
        </div>
      </div>

      <div class="car-card" onclick="openModal('Lexus RX','https://cdn.pixabay.com/photo/2016/11/14/04/25/lexus-1822393_1280.jpg','https://upload.wikimedia.org/wikipedia/commons/0/0b/Lexus_division_emblem.svg','Производитель: Lexus\nМодель: RX\nТип: Премиум-кроссовер\nКраткий факт: Комфорт, надежность и премиальные материалы в салоне.')">
        <img class="thumb" src="https://cdn.pixabay.com/photo/2016/11/14/04/25/lexus-1822393_1280.jpg" alt="Lexus RX">
        <div class="meta">
          <h3>Lexus RX</h3>
          <p class="short">Комфортный премиум-кроссовер для семьи.</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ===== Секция Mercedes ===== -->
<section id="mercedes">
  <div class="wrap">
    <h1 class="section-title">Mercedes</h1>
    <div class="gallery">
      <div class="car-card" onclick="openModal('Mercedes-AMG GT','https://cdn.pixabay.com/photo/2017/03/27/14/56/mercedes-2178774_1280.jpg','https://upload.wikimedia.org/wikipedia/commons/9/90/Mercedes-Logo.svg','Производитель: Mercedes-Benz\nМодель: AMG GT\nДвигатель: 4.0 V8 Biturbo\nМощность: от 476 до 577 л.с. (в завис. от версии)\nКраткий факт: Спортивное купе от AMG с ярким характером.')">
        <img class="thumb" src="https://cdn.pixabay.com/photo/2017/03/27/14/56/mercedes-2178774_1280.jpg" alt="Mercedes AMG GT">
        <div class="meta">
          <h3>Mercedes-AMG GT</h3>
          <p class="short">Спорткупе с мотором AMG и драйвом.</p>
        </div>
      </div>

      <div class="car-card" onclick="openModal('Mercedes G-Class','https://cdn.pixabay.com/photo/2020/05/28/12/47/mercedes-5233717_1280.jpg','https://upload.wikimedia.org/wikipedia/commons/9/90/Mercedes-Logo.svg','Производитель: Mercedes-Benz\nМодель: G-Class\nТип: Роскошный внедорожник\nКраткий факт: Икона внедорожного класса с презентабельным внешним видом и мощью.')">
        <img class="thumb" src="https://cdn.pixabay.com/photo/2020/05/28/12/47/mercedes-5233717_1280.jpg" alt="Mercedes G-Class">
        <div class="meta">
          <h3>Mercedes G-Class</h3>
          <p class="short">Роскошный и брутальный внедорожник.</p>
        </div>
      </div>

      <div class="car-card" onclick="openModal('Mercedes C63','https://cdn.pixabay.com/photo/2016/11/29/05/58/car-1866500_1280.jpg','https://upload.wikimedia.org/wikipedia/commons/9/90/Mercedes-Logo.svg','Производитель: Mercedes-Benz\nМодель: C63 AMG\nДвигатель: 4.0 V8 Biturbo\nМощность: ~503 л.с.\nКраткий факт: Маленький, но свирепый спортивный седан от AMG.')">
        <img class="thumb" src="https://cdn.pixabay.com/photo/2016/11/29/05/58/car-1866500_1280.jpg" alt="Mercedes C63">
        <div class="meta">
          <h3>Mercedes C63</h3>
          <p class="short">Компактный мощный AMG — эмоции на каждый день.</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ===== Секция Audi ===== -->
<section id="audi">
  <div class="wrap">
    <h1 class="section-title">Audi</h1>
    <div class="gallery">
      <div class="car-card" onclick="openModal('Audi R8','https://cdn.pixabay.com/photo/2016/02/13/12/26/car-1191507_1280.jpg','https://upload.wikimedia.org/wikipedia/commons/6/6b/Audi_logo_2016.svg','Производитель: Audi\nМодель: R8\nДвигатель: V10\nМощность: ~562–602 л.с.\nКраткий факт: Спортивный суперкар с мощью и продуманной электроникой.')">
        <img class="thumb" src="https://cdn.pixabay.com/photo/2016/02/13/12/26/car-1191507_1280.jpg" alt="Audi R8">
        <div class="meta">
          <h3>Audi R8</h3>
          <p class="short">Суперкар с двигателем V10 и quattro-полным приводом.</p>
        </div>
      </div>

      <div class="car-card" onclick="openModal('Audi RS6','https://cdn.pixabay.com/photo/2017/09/02/13/02/audi-2702098_1280.jpg','https://upload.wikimedia.org/wikipedia/commons/6/6b/Audi_logo_2016.svg','Производитель: Audi\nМодель: RS6 Avant\nДвигатель: 4.0 V8 Biturbo\nМощность: ~600+ л.с.\nКраткий факт: Универсал-убийца — сочетание практичности и дикой скорости.')">
        <img class="thumb" src="https://cdn.pixabay.com/photo/2017/09/02/13/02/audi-2702098_1280.jpg" alt="Audi RS6">
        <div class="meta">
          <h3>Audi RS6</h3>
          <p class="short">Быстрый практичный универсал от Audi Sport.</p>
        </div>
      </div>

      <div class="car-card" onclick="openModal('Audi TT','https://cdn.pixabay.com/photo/2017/01/27/14/05/car-2017501_1280.jpg','https://upload.wikimedia.org/wikipedia/commons/6/6b/Audi_logo_2016.svg','Производитель: Audi\nМодель: TT\nТип: Компактное купе\nКраткий факт: Стильный компакт с хорошей управляемостью.')">
        <img class="thumb" src="https://cdn.pixabay.com/photo/2017/01/27/14/05/car-2017501_1280.jpg" alt="Audi TT">
        <div class="meta">
          <h3>Audi TT</h3>
          <p class="short">Лаконичное купе с фирменным стилем Audi.</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ===== Секция Toyota ===== -->
<section id="toyota">
  <div class="wrap">
    <h1 class="section-title">Toyota</h1>
    <div class="gallery">
      <div class="car-card" onclick="openModal('Toyota Supra','https://cdn.pixabay.com/photo/2016/03/27/21/16/car-1284514_1280.jpg','https://upload.wikimedia.org/wikipedia/commons/9/9d/Toyota_logo.png','Производитель: Toyota\nМодель: Supra\nДвигатель: 3.0 Turbo\nМощность: ~335–382 л.с.\nКраткий факт: Легенда спортивных купе, ожившая в современных версиях.')">
        <img class="thumb" src="https://cdn.pixabay.com/photo/2016/03/27/21/16/car-1284514_1280.jpg" alt="Toyota Supra">
        <div class="meta">
          <h3>Toyota Supra</h3>
          <p class="short">Спортивное купе в духе классических JDM-легенд.</p>
        </div>
      </div>

      <div class="car-card" onclick="openModal('Toyota GR Yaris','https://cdn.pixabay.com/photo/2021/04/11/09/12/toyota-6176224_1280.jpg','https://upload.wikimedia.org/wikipedia/commons/9/9d/Toyota_logo.png','Производитель: Toyota\nМодель: GR Yaris\nДвигатель: 1.6 Turbo\nМощность: ~257 л.с.\nКраткий факт: Раллийный малютка с невероятной управляемостью.')">
        <img class="thumb" src="https://cdn.pixabay.com/photo/2021/04/11/09/12/toyota-6176224_1280.jpg" alt="Toyota GR Yaris">
        <div class="meta">
          <h3>Toyota GR Yaris</h3>
          <p class="short">Ралли-генетика в компактном кузове.</p>
        </div>
      </div>

      <div class="car-card" onclick="openModal('Toyota Land Cruiser','https://cdn.pixabay.com/photo/2016/11/19/14/00/toyota-1835407_1280.jpg','https://upload.wikimedia.org/wikipedia/commons/9/9d/Toyota_logo.png','Производитель: Toyota\nМодель: Land Cruiser\nТип: Внедорожник\nКраткий факт: Легендарная проходимость и надежность в долгих путешествиях.')">
        <img class="thumb" src="https://cdn.pixabay.com/photo/2016/11/19/14/00/toyota-1835407_1280.jpg" alt="Toyota Land Cruiser">
        <div class="meta">
          <h3>Toyota Land Cruiser</h3>
          <p class="short">Надёжный внедорожник для бездорожья и экспедиций.</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ===== Секция Ferrari ===== -->
<section id="ferrari">
  <div class="wrap">
    <h1 class="section-title">Ferrari</h1>
    <div class="gallery">
      <div class="car-card" onclick="openModal('Ferrari F8 Tributo','https://images.unsplash.com/photo-1549921296-3f1b1f6bcd99?crop=entropy&cs=tinysrgb&fit=max&w=1280&q=80','https://upload.wikimedia.org/wikipedia/en/1/10/Ferrari-Logo.png','Производитель: Ferrari\nМодель: F8 Tributo\nДвигатель: 3.9L V8 TwinTurbo\nМощность: 710 л.с.\nКраткий факт: Динамичный суперкар с итальянским характером.')">
        <img class="thumb" src="https://images.unsplash.com/photo-1549921296-3f1b1f6bcd99?crop=entropy&cs=tinysrgb&fit=max&w=1280&q=80" alt="Ferrari F8">
        <div class="meta">
          <h3>Ferrari F8</h3>
          <p class="short">Итальянский суперкар с V8 и характерным звуком.</p>
        </div>
      </div>

      <div class="car-card" onclick="openModal('Ferrari 488 GTB','https://images.unsplash.com/photo-1549921296-3f1b1f6bcd99?crop=entropy&cs=tinysrgb&fit=max&w=1280&q=80','https://upload.wikimedia.org/wikipedia/en/1/10/Ferrari-Logo.png','Производитель: Ferrari\nМодель: 488 GTB\nДвигатель: 3.9L V8 TwinTurbo\nМощность: ~660 л.с.\nКраткий факт: Один из ключевых этапов в развитии современных Ferrari с турбонаддувом.')">
        <img class="thumb" src="https://images.unsplash.com/photo-1549921296-3f1b1f6bcd99?crop=entropy&cs=tinysrgb&fit=max&w=1280&q=80" alt="Ferrari 488">
        <div class="meta">
          <h3>Ferrari 488</h3>
          <p class="short">Сбалансированный динамический суперкар Ferrari.</p>
        </div>
      </div>

      <div class="car-card" onclick="openModal('Ferrari LaFerrari','https://cdn.pixabay.com/photo/2015/03/27/13/16/car-694098_1280.jpg','https://upload.wikimedia.org/wikipedia/en/1/10/Ferrari-Logo.png','Производитель: Ferrari\nМодель: LaFerrari\nДвигатель: Гибрид V12 + электромотор\nМощность: ~950+ л.с.\nКраткий факт: Ограниченная серия, вершина инженерной мысли Ferrari на момент выпуска.')">
        <img class="thumb" src="https://cdn.pixabay.com/photo/2015/03/27/13/16/car-694098_1280.jpg" alt="Ferrari LaFerrari">
        <div class="meta">
          <h3>Ferrari LaFerrari</h3>
          <p class="short">Гибридный гиперкар — эксклюзив и топ-производительность.</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ===== Секция Porsche ===== -->
<section id="porsche">
  <div class="wrap">
    <h1 class="section-title">Porsche</h1>
    <div class="gallery">
      <div class="car-card" onclick="openModal('Porsche 911','https://images.unsplash.com/photo-1502877338535-766e1452684a?crop=entropy&cs=tinysrgb&fit=max&w=1280&q=80','https://upload.wikimedia.org/wikipedia/commons/0/0a/Porsche.svg','Производитель: Porsche\nМодель: 911\nДвигатель: Оппозитный 6-цилиндровый (разные версии)\nКраткий факт: Классика спортивных автомобилей — узнаваемый силуэт и точная управляемость.')">
        <img class="thumb" src="https://images.unsplash.com/photo-1502877338535-766e1452684a?crop=entropy&cs=tinysrgb&fit=max&w=1280&q=80" alt="Porsche 911">
        <div class="meta">
          <h3>Porsche 911</h3>
          <p class="short">Классическое спортивное купе с богатой историей.</p>
        </div>
      </div>

      <div class="car-card" onclick="openModal('Porsche Taycan','https://images.unsplash.com/photo-1549921296-3f1b1f6bcd99?crop=entropy&cs=tinysrgb&fit=max&w=1280&q=80','https://upload.wikimedia.org/wikipedia/commons/0/0a/Porsche.svg','Производитель: Porsche\nМодель: Taycan\nТип: Электрокар\nКраткий факт: Первые электромобили Porsche — сочетание производительности и шинной культуры бренда.')">
        <img class="thumb" src="https://images.unsplash.com/photo-1549921296-3f1b1f6bcd99?crop=entropy&cs=tinysrgb&fit=max&w=1280&q=80" alt="Porsche Taycan">
        <div class="meta">
          <h3>Porsche Taycan</h3>
          <p class="short">Электрический спорткар от Porsche — быстрая и плавная езда.</p>
        </div>
      </div>

      <div class="car-card" onclick="openModal('Porsche Panamera','https://cdn.pixabay.com/photo/2016/01/19/17/48/porsche-1149900_1280.jpg','https://upload.wikimedia.org/wikipedia/commons/0/0a/Porsche.svg','Производитель: Porsche\nМодель: Panamera\nТип: Люкс-спортседан\nКраткий факт: Комфорт + спортивная динамика в кузове седан/универсал.')">
        <img class="thumb" src="https://cdn.pixabay.com/photo/2016/01/19/17/48/porsche-1149900_1280.jpg" alt="Porsche Panamera">
        <div class="meta">
          <h3>Porsche Panamera</h3>
          <p class="short">Спортивный роскошный седан с драйверским уклоном.</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ===== Секция Lamborghini ===== -->
<section id="lamborghini">
  <div class="wrap">
    <h1 class="section-title">Lamborghini</h1>
    <div class="gallery">
      <div class="car-card" onclick="openModal('Lamborghini Huracan','https://images.unsplash.com/photo-1470418048257-7e7c6e74f2f3?crop=entropy&cs=tinysrgb&fit=max&w=1280&q=80','https://upload.wikimedia.org/wikipedia/commons/3/31/Lamborghini_Logo.svg','Производитель: Lamborghini\nМодель: Huracan\nДвигатель: V10\nМощность: ~602 л.с.\nКраткий факт: Яркий итальянский суперкар с агрессивным дизайном.')">
        <img class="thumb" src="https://images.unsplash.com/photo-1470418048257-7e7c6e74f2f3?crop=entropy&cs=tinysrgb&fit=max&w=1280&q=80" alt="Lamborghini Huracan">
        <div class="meta">
          <h3>Lamborghini Huracan</h3>
          <p class="short">Агрессивный дизайн и мощный V10.</p>
        </div>
      </div>

      <div class="car-card" onclick="openModal('Lamborghini Aventador','https://images.unsplash.com/photo-1542367597-1a5f9d3a1d46?crop=entropy&cs=tinysrgb&fit=max&w=1280&q=80','https://upload.wikimedia.org/wikipedia/commons/3/31/Lamborghini_Logo.svg','Производитель: Lamborghini\nМодель: Aventador\nДвигатель: V12\nМощность: ~730+ л.с.\nКраткий факт: Флагманский V12 суперкар с экстремальным дизайном.')">
        <img class="thumb" src="https://images.unsplash.com/photo-1542367597-1a5f9d3a1d46?crop=entropy&cs=tinysrgb&fit=max&w=1280&q=80" alt="Lamborghini Aventador">
        <div class="meta">
          <h3>Lamborghini Aventador</h3>
          <p class="short">V12-громила — эффект и скорость.</p>
        </div>
      </div>

      <div class="car-card" onclick="openModal('Lamborghini Urus','https://cdn.pixabay.com/photo/2019/11/25/05/50/automobile-4657549_1280.jpg','https://upload.wikimedia.org/wikipedia/commons/3/31/Lamborghini_Logo.svg','Производитель: Lamborghini\nМодель: Urus\nТип: Высокопроизводительный SUV\nКраткий факт: Самый быстрый SUV марки — спорт и практичность в одном.')">
        <img class="thumb" src="https://cdn.pixabay.com/photo/2019/11/25/05/50/automobile-4657549_1280.jpg" alt="Lamborghini Urus">
        <div class="meta">
          <h3>Lamborghini Urus</h3>
          <p class="short">Спортивный ультра-SUV от Lamborghini.</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ===== Секция Bugatti ===== -->
<section id="bugatti">
  <div class="wrap">
    <h1 class="section-title">Bugatti</h1>
    <div class="gallery">
      <div class="car-card" onclick="openModal('Bugatti Chiron','https://cdn.pixabay.com/photo/2017/01/31/20/42/auto-2029173_1280.jpg','https://upload.wikimedia.org/wikipedia/commons/6/69/Bugatti_logo.png','Производитель: Bugatti\nМодель: Chiron\nДвигатель: W16\nМощность: до 1500 л.с.\nКраткий факт: Одни из самых мощных и быстрых серийных автомобилей в мире.')">
        <img class="thumb" src="https://cdn.pixabay.com/photo/2017/01/31/20/42/auto-2029173_1280.jpg" alt="Bugatti Chiron">
        <div class="meta">
          <h3>Bugatti Chiron</h3>
          <p class="short">Топовое ускорение и невероятная скорость.</p>
        </div>
      </div>

      <div class="car-card" onclick="openModal('Bugatti Veyron','https://cdn.pixabay.com/photo/2014/12/15/13/40/bugatti-569223_1280.jpg','https://upload.wikimedia.org/wikipedia/commons/6/69/Bugatti_logo.png','Производитель: Bugatti\nМодель: Veyron\nДвигатель: W16\nКраткий факт: Революционный гиперкар своего времени — многократно ломал рекорды скорости.')">
        <img class="thumb" src="https://cdn.pixabay.com/photo/2014/12/15/13/40/bugatti-569223_1280.jpg" alt="Bugatti Veyron">
        <div class="meta">
          <h3>Bugatti Veyron</h3>
          <p class="short">Легенда гиперкаров — прорыв в скорости и инженерии.</p>
        </div>
      </div>

      <div class="car-card" onclick="openModal('Bugatti Centodieci','https://cdn.pixabay.com/photo/2021/08/10/12/09/car-6539008_1280.jpg','https://upload.wikimedia.org/wikipedia/commons/6/69/Bugatti_logo.png','Производитель: Bugatti\nМодель: Centodieci\nКраткий факт: Очень ограниченная серия — эксклюзив и коллекционная ценность.')">
        <img class="thumb" src="https://cdn.pixabay.com/photo/2021/08/10/12/09/car-6539008_1280.jpg" alt="Bugatti Centodieci">
        <div class="meta">
          <h3>Bugatti Centodieci</h3>
          <p class="short">Эксклюзивный гиперкар ограниченной серии.</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ===== Секция About ===== -->
<section id="about">
  <div class="wrap">
    <h1 class="section-title">О нас</h1>
    <div class="about">
      <p>Привет! 👋 Я — [ТВОЁ ИМЯ]. Этот сайт — моя мини-галерея и проект по веб-дизайну, где я собрал любимые марки и модели автомобилей. Здесь можно просмотреть 27 автомобилей — по 3 модели от каждой из 9 брендов.</p>
      <p>Если хочешь, я могу добавить больше моделей, ссылки на видеообзоры, характеристики в виде таблиц или страницу контактов.</p>

      <div class="socials">
        <a href="#" target="_blank">Instagram</a>
        <a href="#" target="_blank">Telegram</a>
        <a href="#" target="_blank">YouTube</a>
      </div>
    </div>
  </div>
</section>

<!-- ===== Модалка (универсальная) ===== -->
<div id="modal" class="modal" onclick="if(event.target===this) closeModal()">
  <div class="modal-card" role="dialog" aria-modal="true">
    <div class="modal-top">
      <span class="modal-close" onclick="closeModal()">×</span>
      <img id="modalImg" class="car-img" src="" alt="car image">
    </div>
    <div class="modal-body">
      <h2 id="modalTitle"><img class="logo" id="modalLogo" src="" alt="logo"> Название</h2>
      <p id="modalInfo" class="info"></p>
    </div>
  </div>
</div>

<script>
  // подсветка курсора
  const cursor = document.getElementById('cursorLight');
  document.addEventListener('mousemove', e => {
    cursor.style.left = e.clientX + 'px';
    cursor.style.top  = e.clientY + 'px';
  });
  // увеличить свет при наведении на меню элементы
  const menuLinks = document.querySelectorAll('header nav a');
  menuLinks.forEach(a=>{
    a.addEventListener('mouseenter', ()=> { cursor.style.width='220px'; cursor.style.height='220px'; });
    a.addEventListener('mouseleave', ()=> { cursor.style.width='160px'; cursor.style.height='160px'; });
  });

  // Модал
  function openModal(title, img, logo, info){
    document.getElementById('modal').classList.add('show');
    document.getElementById('modalImg').src = img;
    document.getElementById('modalLogo').src = logo;
    document.getElementById('modalTitle').innerHTML = `<img class="logo" id="modalLogoInner" src="${logo}" alt="logo"> ${title}`;
    document.getElementById('modalInfo').innerText = info;
    // блокируем прокрутку страницы при открытой модалке
    document.body.style.overflow = 'hidden';
  }
  function closeModal(){
    document.getElementById('modal').classList.remove('show');
    document.body.style.overflow = '';
  }

  // Плавный скролл по ссылкам меню
  document.querySelectorAll('header nav a[href^="#"]').forEach(link=>{
    link.addEventListener('click', evt=>{
      evt.preventDefault();
      const target = document.querySelector(link.getAttribute('href'));
      if(target){
        const y = target.getBoundingClientRect().top + window.scrollY - 90; // учёт фикс. шапки
        window.scrollTo({top:y, behavior:'smooth'});
      }
    });
  });

  // Закрывать модал по Esc
  document.addEventListener('keydown', (e)=>{
    if(e.key==='Escape') closeModal();
  });
</script>

</body>
</html>
