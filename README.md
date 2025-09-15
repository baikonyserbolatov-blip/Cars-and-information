<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>Атмосферная галерея — 27 машин</title>
<style>
  :root{
    --accent:#ffcc00;
    --bg-overlay: rgba(0,0,0,0.6);
    --card-bg: rgba(255,255,255,0.06);
  }
  *{box-sizing:border-box}
  body{
    margin:0;
    font-family: Inter, Arial, sans-serif;
    background: url('https://img.freepik.com/premium-photo/side-view-asphalt-road-sunny-summer-day_265223-8810.jpg') center/cover fixed no-repeat;
    color:#fff;
    -webkit-font-smoothing:antialiased;
    -moz-osx-font-smoothing:grayscale;
  }

  /* top bar compact: Brands dropdown + About link */
  header{
    position:fixed; left:0; right:0; top:0;
    z-index:2000;
    display:flex;
    justify-content:center;
    padding:10px 16px;
    background: linear-gradient(180deg, rgba(0,0,0,0.6), rgba(0,0,0,0.25));
    backdrop-filter: blur(6px);
  }
  .topbar{
    width:100%;
    max-width:1200px;
    display:flex;
    align-items:center;
    gap:14px;
    justify-content:space-between;
  }
  .brand-btn{
    background:transparent;
    border:1px solid rgba(255,255,255,0.08);
    color:#fff;
    padding:8px 12px;
    border-radius:10px;
    cursor:pointer;
    font-weight:600;
  }
  .brand-btn:hover{ color:var(--accent); border-color:var(--accent); }

  /* dropdown */
  .dropdown{
    position:relative;
    display:inline-block;
  }
  .dropdown-menu{
    position:absolute;
    left:0; top:calc(100% + 10px);
    background:#0f0f0f;
    border-radius:10px;
    padding:10px;
    min-width:220px;
    box-shadow: 0 12px 30px rgba(0,0,0,0.6);
    display:none;
  }
  .dropdown-menu a{
    display:block;
    color:#fff;
    text-decoration:none;
    padding:8px 10px;
    border-radius:8px;
  }
  .dropdown-menu a:hover{ background:rgba(255,255,255,0.03); color:var(--accent); }

  /* page sections */
  main{ padding-top:72px; } /* space for header */
  section{
    padding:80px 20px;
    min-height:100vh;
    background: linear-gradient(180deg, rgba(0,0,0,0.16), rgba(0,0,0,0.6));
  }
  .wrap{ max-width:1200px; margin:0 auto; }

  h1.section-title{
    text-align:center;
    font-size:34px;
    margin:8px 0 26px;
    letter-spacing:1px;
  }

  /* gallery cards */
  .gallery{
    display:grid;
    grid-template-columns: repeat(auto-fit, minmax(260px,1fr));
    gap:20px;
  }
  .card{
    background:var(--card-bg);
    border-radius:12px;
    overflow:hidden;
    cursor:pointer;
    transition: transform .25s ease, box-shadow .25s ease;
    border:1px solid rgba(255,255,255,0.05);
    display:flex;
    flex-direction:column;
    height:100%;
  }
  .card:hover{
    transform: translateY(-8px);
    box-shadow: 0 18px 40px rgba(0,0,0,0.6), 0 0 30px rgba(255,204,0,0.06);
  }
  .card img.thumb{
    width:100%;
    height:180px;
    object-fit:cover;
    display:block;
    filter: saturate(1.02) contrast(1.02);
  }
  .card .card-body{
    padding:12px 14px 18px;
    display:flex;
    flex-direction:column;
    gap:8px;
    flex:1;
  }
  .card h3{ margin:0; font-size:18px; text-align:center; }
  .card p.short{ margin:0; font-size:13px; color:rgba(255,255,255,0.9); text-align:center; }

  /* modal */
  .modal{
    position:fixed; inset:0;
    display:none;
    z-index:3000;
    align-items:center; justify-content:center;
    background: linear-gradient(180deg, rgba(0,0,0,0.6), rgba(0,0,0,0.9));
    padding:20px;
  }
  .modal.show{ display:flex; }
  .modal-card{
    width:100%; max-width:960px;
    background:linear-gradient(180deg,#121212,#0f0f0f);
    border-radius:12px;
    overflow:hidden;
    box-shadow:0 30px 80px rgba(0,0,0,0.7);
  }
  .modal-top img{
    width:100%; height:380px; object-fit:cover; display:block;
  }
  .modal-body{
    padding:18px 20px 26px;
    color:#f2f2f2;
  }
  .modal-title{
    display:flex; align-items:center; gap:12px; margin:0 0 8px;
  }
  .modal-title img.logo{
    width:52px; height:52px; object-fit:contain; border-radius:8px; background:rgba(255,255,255,0.03); padding:6px;
  }
  .modal-desc{ white-space:pre-line; line-height:1.6; color:#e9e9e9; margin:8px 0 12px; }
  .specs{
    display:flex; gap:18px; flex-wrap:wrap; margin-top:6px;
  }
  .spec{
    background: rgba(255,255,255,0.03);
    padding:10px 12px;
    border-radius:8px;
    min-width:140px;
    font-size:14px;
  }
  .modal-close{
    position:absolute; right:14px; top:10px; font-size:28px; color:var(--accent); cursor:pointer;
    z-index:5;
  }

  /* about */
  .about{ text-align:center; font-size:18px; line-height:1.6; max-width:900px; margin:0 auto; color:#f5f5f5; }
  .socials{ margin-top:12px; display:flex; justify-content:center; gap:14px; }
  .socials a{ color:var(--accent); font-weight:700; text-decoration:none; }

  /* responsive */
  @media (max-width:720px){
    .modal-top img{ height:220px; }
    .modal-title img.logo{ width:42px; height:42px; }
    header{ padding:8px; }
  }
</style>
</head>
<body>

<header>
  <div class="topbar wrap">
    <div style="display:flex; gap:12px; align-items:center;">
      <button class="brand-btn" id="brandsBtn">Бренды ▾</button>
      <div class="dropdown" id="brandsDropdown">
        <div class="dropdown-menu" id="brandsMenu">
          <a href="#bmw" data-target="#bmw">BMW</a>
          <a href="#lexus" data-target="#lexus">Lexus</a>
          <a href="#mercedes" data-target="#mercedes">Mercedes</a>
          <a href="#audi" data-target="#audi">Audi</a>
          <a href="#toyota" data-target="#toyota">Toyota</a>
          <a href="#ferrari" data-target="#ferrari">Ferrari</a>
          <a href="#porsche" data-target="#porsche">Porsche</a>
          <a href="#lamborghini" data-target="#lamborghini">Lamborghini</a>
          <a href="#bugatti" data-target="#bugatti">Bugatti</a>
        </div>
      </div>
    </div>

    <div>
      <a href="#about" style="color:#fff; text-decoration:none; font-weight:600;">О нас</a>
    </div>
  </div>
</header>

<main>
  <!-- BMW -->
  <section id="bmw">
    <div class="wrap">
      <h1 class="section-title">BMW</h1>
      <div class="gallery">
        <div class="card" onclick="openModal(
          'BMW M3',
          'https://a.d-cd.net/bb68a76s-1920.jpg',
          'https://upload.wikimedia.org/wikipedia/commons/4/44/BMW.svg',
          'BMW M3 — спортивный седан, сочетающий комфорт и трековые свойства. Культовый M-эмблемой и агрессивной динамикой.',
          '3.0L TwinTurbo I6',
          '≈ 0–100 км/ч за 4.1 с • макс ~250–290 км/ч',
          '$80,000 — $120,000',
          '2021')">
          <img class="thumb" src="https://images.pistonheads.com/nimg/43852/_DSF3440-Edit.jpg" alt="">
          <div class="card-body">
            <h3>BMW M3</h3>
            <p class="short">Культовый спортседан — мощность и управляемость.</p>
          </div>
        </div>

        <div class="card" onclick="openModal(
          'BMW i8',
          'https://autotesla.ru/wp-content/uploads/2015/04/tehnicheskii-vid-bmw-i8.jpg',
          'https://upload.wikimedia.org/wikipedia/commons/4/44/BMW.svg',
          'BMW i8 — гибридный спорткар с футуристичным дизайном и дверьми-бабочками. Экономичность в сочетании со спортивными качествами.',
          'Гибрид: бензин + электромотор',
          '≈ 0–100 км/ч за 4.4 с • макс ~250 км/ч',
          '$140,000 — $170,000',
          '2019')">
          <img class="thumb" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTRppVyTkCHSJ74FM2oKID8y-x1xLuOV9M9YQ&s" alt="">
          <div class="card-body">
            <h3>BMW i8</h3>
            <p class="short">Гибридное спортивное купе с необычным дизайном.</p>
          </div>
        </div>

        <div class="card" onclick="openModal(
          'BMW X6',
          'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQIVW5wsYLJJ0_tKZPiocP9HKIRkQanJY1gHQ&s',
          'https://upload.wikimedia.org/wikipedia/commons/4/44/BMW.svg',
          'BMW X6 — спортивный кроссовер купе-класса. Сочетает мощность, роскошь и внедорожные возможности.',
          'V6 / V8 turbos (в зависимости от версии)',
          'макс ~250–290 км/ч',
          '$70,000 — $130,000',
          '2020')">
          <img class="thumb" src="https://s1.autorating.ru/upload/medialibrary/5a6/5a638c2d68dcda6b991ff1c1b40f5532.jpg" alt="">
          <div class="card-body">
            <h3>BMW X6</h3>
            <p class="short">Спортивный купе-кроссовер — стиль и мощь.</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- LEXUS -->
  <section id="lexus">
    <div class="wrap">
      <h1 class="section-title">Lexus</h1>
      <div class="gallery">
        <div class="card" onclick="openModal(
          'Lexus LFA',
          'https://a.d-cd.net/fc52f6s-960.jpg',
          'https://hdpic.club/uploads/posts/2021-11/1636782491_4-hdpic-club-p-znak-leksus-7.jpg',
          'Lexus LFA — редкий суперкар с V10, выдающий неповторимый звук и высокую отзывчивость двигателя.',
          '4.8L V10',
          'макс ≈ 325 км/ч',
          '$375,000 — $500,000 (все примерные цены для рынка)',
          '2012')">
          <img class="thumb" src="https://blog.consumerguide.com/wp-content/uploads/sites/2/2020/03/3943499_orig.jpg" alt="">
          <div class="card-body">
            <h3>Lexus LFA</h3>
            <p class="short">Японский суперкар — звук и редкость.</p>
          </div>
        </div>

        <div class="card" onclick="openModal(
          'Lexus LC500',
          'https://st.club-lexus.ru/attach/u/250755c43a52ad1a8673c6ec42072516.jpg',
          'https://hdpic.club/uploads/posts/2021-11/1636782491_4-hdpic-club-p-znak-leksus-7.jpg',
          'Lexus LC500 — премиальное купе с атмосферным V8, элегантностью и качеством салона.',
          '5.0L V8',
          '≈ 0–100 км/ч за 4.7 с • макс ~270 км/ч',
          '$92,000 — $110,000',
          '2021')">
          <img class="thumb" src="https://media.ed.edmunds-media.com/lexus/ls-500/2021/oem/2021_lexus_ls-500_sedan_base_fq_oem_3_1600.jpg" alt="">
          <div class="card-body">
            <h3>Lexus LC500</h3>
            <p class="short">Красивое премиум-купе с V8.</p>
          </div>
        </div>

        <div class="card" onclick="openModal(
          'Lexus RX',
          'https://avatars.mds.yandex.net/get-autoru-vos/2179989/df9a4ba27a7906de0acfd18227b45623/456x342',
          'https://hdpic.club/uploads/posts/2021-11/1636782491_4-hdpic-club-p-znak-leksus-7.jpg',
          'Lexus RX — премиальный кроссовер, известный комфортом и надежностью, популярный в семьях.',
          '2.0L / 3.5L / гибридные варианты',
          'макс ~200–230 км/ч (в зависимости от версии)',
          '$45,000 — $75,000',
          '2020')">
          <img class="thumb" src="https://st.club-lexus.ru/attach/u/872adc057268a5bf6b371aa27709454c.jpg" alt="">
          <div class="card-body">
            <h3>Lexus RX</h3>
            <p class="short">Комфортный премиум-кроссовер для семьи.</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- MERCEDES -->
  <section id="mercedes">
    <div class="wrap">
      <h1 class="section-title">Mercedes</h1>
      <div class="gallery">
        <div class="card" onclick="openModal(
          'Mercedes-AMG GT',
          'https://thumbs.dreamstime.com/z/%D0%B4%D0%B2%D0%B8%D0%B3%D0%B0%D1%82%D0%B5%D0%BB%D1%8C-coupe-%D0%BC%D0%B5%D1%80%D1%81%D0%B5%D0%B4%D0%B5%D1%81-amg-gt-c-117239294.jpg',
          'https://upload.wikimedia.org/wikipedia/commons/9/90/Mercedes-Logo.svg',
          'AMG GT — спортивное купе от Mercedes-AMG, ориентированное на драйверов и трек.',
          '4.0L V8 Biturbo',
          '≈ 0–100 км/ч за 3.6–4.0 с • макс ~310 км/ч',
          '$115,000 — $160,000',
          '2020')">
          <img class="thumb" src="https://sales.mercedes-olimp-neva.ru/images/gallery/gallery_model_cars/image_10_11.jpg" alt="">
          <div class="card-body">
            <h3>Mercedes-AMG GT</h3>
            <p class="short">Спорткупе с характером AMG.</p>
          </div>
        </div>

        <div class="card" onclick="openModal(
          'Mercedes G-Class',
          'https://img.mercedes-benz-kiev.com/data/news/325-novi-modeli-mercedes-benz-g-class-ta-mercedes-amg-g-63-2024-roku/novi-modeli-mercedes-benz-g-class-ta-mercedes-amg-g-63-2024-roku-14.jpg',
          'https://upload.wikimedia.org/wikipedia/commons/9/90/Mercedes-Logo.svg',
          'G-Class — легендарный внедорожник, сочетает проходимость и премиум-интерьер.',
          'V8 (в большинстве современных версий)',
          'макс ~210–240 км/ч (в завис. от версии)',
          '$130,000 — $200,000',
          '2021')">
          <img class="thumb" src="https://img.mercedes-benz-kiev.com/data/news/39-novyy-mercedes-benz-g-class-v-kieve-sostoyalas-ofitsialnaya-premera/mercedes-benz-g-63-1.jpg" alt="">
          <div class="card-body">
            <h3>Mercedes G-Class</h3>
            <p class="short">Роскошный и брутальный внедорожник.</p>
          </div>
        </div>

        <div class="card" onclick="openModal(
          'Mercedes C63 AMG',
          'https://avatars.mds.yandex.net/get-autoru-vos/2027711/9489956784fe55f156ee82b490f33437/456x342',
          'https://upload.wikimedia.org/wikipedia/commons/9/90/Mercedes-Logo.svg',
          'C63 AMG — компактный спортивный седан, создаёт много удовольствия у водителя.',
          '4.0L V8 Biturbo',
          '≈ 0–100 км/ч за ~3.9–4.2 с',
          '$70,000 — $90,000',
          '2019')">
          <img class="thumb" src="https://avatars.mds.yandex.net/get-autoru-vos/1981494/5b1d7be6fdf9d113c0822199efdaea98/456x342" alt="">
          <div class="card-body">
            <h3>Mercedes C63 AMG</h3>
            <p class="short">Мал, но свиреп — эмоции и мощь.</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- AUDI -->
  <section id="audi">
    <div class="wrap">
      <h1 class="section-title">Audi</h1>
      <div class="gallery">
        <div class="card" onclick="openModal(
          'Audi R8',
          'https://vvm-auto.ru/images/VVM-AUTO/TEST-REWIEWS/Audi/Audi-R8/Audi-R8-8.jpg',
          'https://avtozaryad.ru/upload/iblock/c15/g73bwu2i50zx2ct3gxsdk5248x1vc15h.png',
          'Audi R8 — суперкар с V10 и системой quattro, отличный баланс технологий и драйва.',
          'V10',
          '≈ 0–100 км/ч за 3.4–3.6 с • макс ~330 км/ч',
          '$170,000 — $210,000',
          '2020')">
          <img class="thumb" src="https://i.infocar.ua/i/12/5834/1200x630.jpg" alt="">
          <div class="card-body">
            <h3>Audi R8</h3>
            <p class="short">Суперкар с V10 и отличной электроникой.</p>
          </div>
        </div>

        <div class="card" onclick="openModal(
          'Audi RS6',
          'https://vvm-auto.ru/images/VVM-AUTO/OPIT_EKSPLYATACI/AUDI/Audi-RS6-C5/Audi-RS6-C5-6.jpg',
          'https://avtozaryad.ru/upload/iblock/c15/g73bwu2i50zx2ct3gxsdk5248x1vc15h.png',
          'RS6 Avant — быстрый универсал, сочетающий практичность и супер-динамику.',
          '4.0L V8 Biturbo',
          '≈ 0–100 км/ч за ~3.6 с',
          '$110,000 — $140,000',
          '2021')">
          <img class="thumb" src="https://gogetcar.ru/upload/uf/e30/vd84e5fsffbegq9ftoztzytc0bmwi0n1/_Audi_RS6_Avant_Header.jpg" alt="">
          <div class="card-body">
            <h3>Audi RS6</h3>
            <p class="short">Универсал-убийца — скорость и практичность.</p>
          </div>
        </div>

        <div class="card" onclick="openModal(
          'Audi TT',
          'https://auto2020.ru/images/Leg/Audi/Audi_TT/Audi_TT_9.jpg',
          'https://avtozaryad.ru/upload/iblock/c15/g73bwu2i50zx2ct3gxsdk5248x1vc15h.png',
          'Audi TT — компактное стильное купе с хорошей управляемостью.',
          '2.0L Turbo / 4-cyl',
          'макс ~250–260 км/ч',
          '$50,000 — $70,000',
          '2019')">
          <img class="thumb" src="https://lh6.googleusercontent.com/proxy/oKeIqnWiXI9DfKZvKpF7bxOfmQ9eB2CHrbC6LxwF5fzQGx3lifOb1CVtUMKUzv6SGoT_XrFcaOO-1JXNXNQ" alt="">
          <div class="card-body">
            <h3>Audi TT</h3>
            <p class="short">Лаконичное купе с фирменным стилем.</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- TOYOTA -->
  <section id="toyota">
    <div class="wrap">
      <h1 class="section-title">Toyota</h1>
      <div class="gallery">
        <div class="card" onclick="openModal(
          'Toyota Supra',
          'https://avatars.mds.yandex.net/get-vertis-journal/4466156/11.jpg_1626941449354/orig',
          'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ6J3ZeasQVcQXVD8UcpziS9swsImjkebATYA&s',
          'Toyota Supra — спортивное купе с японской историей и хорошей динамикой.',
          '3.0L Turbo',
          '≈ 0–100 км/ч за 4.1–4.3 с',
          '$50,000 — $60,000',
          '1995')">
          <img class="thumb" src="https://avatars.mds.yandex.net/get-autoru-vos/1980785/65b98a46458d4c4189767e6c76a81039/456x342" alt="">
          <div class="card-body">
            <h3>Toyota Supra</h3>
            <p class="short">Спортивное купе в духе JDM-легенд.</p>
          </div>
        </div>

        <div class="card" onclick="openModal(
          'Toyota Camry70',
          'https://kolesa-photos.kcdn.online/kolesa-newautomodels/608a85118e5776001b55a6f2/56/full.jpg',
          'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ6J3ZeasQVcQXVD8UcpziS9swsImjkebATYA&s',
          'Camry — один из красивых модели Toyota',
          '3.5L',
          '≈ 0–100 км/ч за ~7-7.5 с',
          '$15,500 - $25,000',
          '2020')">
          <img class="thumb" src="https://bestrental.com.ua/wp-content/uploads/2024/04/7-img_4368_1.jpg" alt="">
          <div class="card-body">
            <h3>Toyota Camry 70</h3>
            <p class="short">Красивый и универсал седан из марки Toyota</p>
          </div>
        </div>

        <div class="card" onclick="openModal(
          'Toyota Land Cruiser',
          'https://auto.ironhorse.ru/wp-content/uploads/2012/04/Land-Cruiser-200-motor-diesel.jpg',
          'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ6J3ZeasQVcQXVD8UcpziS9swsImjkebATYA&s',
          'Land Cruiser — легендарный внедорожник, незаменимый в экспедициях и дальних путешествиях.',
          '4.5L / V8 (в разных версиях)',
          'макс ~180–200 км/ч (зависит от версии)',
          '$60,000 — $90,000',
          '2019')">
          <img class="thumb" src="https://lh3.googleusercontent.com/proxy/biZuaKY6E2-YjviRb-qv7xHjq2ENa6KkiX745OFpoyXM9IZj2uRAbFZVWWtHHClH-cSUivgLC23uw_pabRMdMV-VEpgjR8EfD6uDJZYkTmhw17l8A0RaNUndiLP7xb4142ROkkEWVpFUrU75DY6q2uRt" alt="">
          <div class="card-body">
            <h3>Toyota Land Cruiser</h3>
            <p class="short">Надёжен в любых условиях — выбор для путешествий.</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- FERRARI -->
  <section id="ferrari">
    <div class="wrap">
      <h1 class="section-title">Ferrari</h1>
      <div class="gallery">
        <div class="card" onclick="openModal(
          'Ferrari F8 Tributo',
          'https://i.infocar.ua/img/mats/11448/ins/1641991051901.jpg',
          'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRKe4UxIL8x6Nk2NZp2l5yWkPASZPpcQZc3Tg&s',
          'F8 — динамичный суперкар с итальянским характером и отличной аэродинамикой.',
          '3.9L V8 TwinTurbo',
          '≈ 0–100 км/ч за ~2.9–3.0 с • макс ~340 км/ч',
          '$280,000 — $350,000',
          '2020')">
          <img class="thumb" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRer50z_ft_ug3TLz3qpqWWMlApZYi_IT3j1g&s" alt="">
          <div class="card-body">
            <h3>Ferrari F8</h3>
            <p class="short">Итальянский суперкар — характер и звук V8.</p>
          </div>
        </div>

        <div class="card" onclick="openModal(
          'Ferrari 488',
          'https://hips.hearstapps.com/hmg-prod/images/2019-ferrari-488-pista-inline5-1528489338.jpg',
          'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRKe4UxIL8x6Nk2NZp2l5yWkPASZPpcQZc3Tg&s',
          '488 — турбированная эра Ferrari: мощность и точная управляемость.',
          '3.9L V8 TwinTurbo',
          '≈ 0–100 км/ч за ~3.0 с',
          '$250,000 — $330,000',
          '2018')">
          <img class="thumb" src="https://s0.rbk.ru/v6_top_pics/ampresize/media/img/8/38/755204094731388.jpg" alt="">
          <div class="card-body">
            <h3>Ferrari 488</h3>
            <p class="short">Турбо-эпоха Ferrari — баланс мощности и управляемости.</p>
          </div>
        </div>

        <div class="card" onclick="openModal(
          'Ferrari LaFerrari',
          'https://all-andorra.com/wp-content/uploads/2016/10/ferrari-laferrari-best-car-engine.jpg',
          'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRKe4UxIL8x6Nk2NZp2l5yWkPASZPpcQZc3Tg&s',
          'LaFerrari — гибридный гиперкар, ограниченная серия для коллекционеров.',
          'Гибрид V12 + электромотор',
          'макс очень высокий, более 350+ миль/ч (ограничения), практические значения — экстремальные',
          'несколько миллионов $ (в зависимости от рынка)',
          '2014')">
          <img class="thumb" src="https://hdpic.club/uploads/posts/2021-11/1636459273_8-hdpic-club-p-ferrari-laferrari-14.jpg" alt="">
          <div class="card-body">
            <h3>Ferrari LaFerrari</h3>
            <p class="short">Эксклюзивный гибридный гиперкар — вершина инженерии.</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- PORSCHE -->
  <section id="porsche">
    <div class="wrap">
      <h1 class="section-title">Porsche</h1>
      <div class="gallery">
        <div class="card" onclick="openModal(
          'Porsche 911',
          'https://i.bstr.es/highmotor/2024/07/img_6-1280x720.jpg',
          'https://koleso.ru/articles/wp-content/uploads/2023/11/%D0%9B%D0%BE%D0%B3%D0%BE%D1%82%D0%B8%D0%BF-PORSCHE.jpg',
          '911 — классика Porsche: оппозитный двигатель, идеальная управляемость и длинная история успеха.',
          'Оппозитный 6-цилиндровый',
          'зависит от модификации; трековые версии очень быстры',
          '$100,000 — $250,000',
          '2020')">
          <img class="thumb" src="https://robbreport.com/wp-content/uploads/2024/11/turboremastered06.jpg?w=1024" alt="">
          <div class="card-body">
            <h3>Porsche 911</h3>
            <p class="short">Классика спортивных автомобилей с узнаваемым силуэтом.</p>
          </div>
        </div>

        <div class="card" onclick="openModal(
          'Porsche Taycan',
          'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTWS3bYZJeYBpcDY8Z1O6YL-UnoCqP-3itBLA&s',
          'https://koleso.ru/articles/wp-content/uploads/2023/11/%D0%9B%D0%BE%D0%B3%D0%BE%D1%82%D0%B8%D0%BF-PORSCHE.jpg',
          'Taycan — электрический спорткар Porsche: молниеносный отклик и премиальный салон.',
          'Электродвигатели (полный привод)',
          'быстрая разгонная динамика; макс зависит от версии',
          '$120,000 — $185,000',
          '2021')">
          <img class="thumb" src="https://i.infocar.ua/i/2/5980/114971/1920x.jpg" alt="">
          <div class="card-body">
            <h3>Porsche Taycan</h3>
            <p class="short">Первый полноценный электрокар Porsche с драйверским характером.</p>
          </div>
        </div>

        <div class="card" onclick="openModal(
          'Porsche Panamera',
          'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQgg0T2f8F5c1-mCNckdeDR3L-ubWiKLPzXgA&s',
          'https://koleso.ru/articles/wp-content/uploads/2023/11/%D0%9B%D0%BE%D0%B3%D0%BE%D1%82%D0%B8%D0%BF-PORSCHE.jpg',
          'Panamera — люкс-спортседан, сочетающий комфорт и спортивную динамику.',
          'V6 / V8 / гибридные варианты',
          'динамика высокого уровня для седана',
          '$90,000 — $180,000',
          '2019')">
          <img class="thumb" src="https://avtorinok.ru/cache/storage/photo/pics/porsche/panamera/211992-gthumb-gwdata640-ghdata480-gfitdatacrop.jpg" alt="">
          <div class="card-body">
            <h3>Porsche Panamera</h3>
            <p class="short">Спортивный роскошный седан с драйверским уклоном.</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- LAMBORGHINI -->
  <section id="lamborghini">
    <div class="wrap">
      <h1 class="section-title">Lamborghini</h1>
      <div class="gallery">
        <div class="card" onclick="openModal(
          'Lamborghini Huracan',
          'https://auto.ironhorse.ru/wp-content/uploads/2020/01/huracan-evo-motor.jpg',
          'https://i.pinimg.com/736x/f2/b1/2d/f2b12dfc3534889801734e4518be4356.jpg',
          'Huracan — яркий итальянский суперкар с V10 и острым дизайном.',
          'V10',
          '≈ 0–100 км/ч за ~2.9–3.2 с',
          '$200,000 — $300,000',
          '2020')">
          <img class="thumb" src="https://www.a777aa77.ru/upload/2018-lamborghini-huracan-performante-c.jpg" alt="">
          <div class="card-body">
            <h3>Lamborghini Huracan</h3>
            <p class="short">Агрессивный дизайн и мощный V10.</p>
          </div>
        </div>

        <div class="card" onclick="openModal(
          'Lamborghini Aventador',
          'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT6OvSQ-niLzrWczi8QvHYoHoV01Y-IoQUHPA&s',
          'https://i.pinimg.com/736x/f2/b1/2d/f2b12dfc3534889801734e4518be4356.jpg',
          'Aventador — флагман с V12 и экстремальным обликом.',
          'V12',
          'макс очень высокий; разгон молниеносный',
          '$400,000 — $600,000',
          '2019')">
          <img class="thumb" src="https://autoreview.ru/images/Article/1674/Article_167421_860_575.jpg" alt="">
          <div class="card-body">
            <h3>Lamborghini Aventador</h3>
            <p class="short">Флагманский V12 суперкар — эффект и скорость.</p>
          </div>
        </div>

        <div class="card" onclick="openModal(
          'Lamborghini Urus',
          'https://grandcar.kz/wp-content/uploads/2024/11/key_key21_364234.jpg',
          'https://i.pinimg.com/736x/f2/b1/2d/f2b12dfc3534889801734e4518be4356.jpg',
          'Urus — высокопроизводительный SUV, сочетает комфорт и спортивные качества.',
          'V8 TwinTurbo',
          'макс ~305 км/ч (в зависимости от версии)',
          '$200,000 — $250,000',
          '2021')">
          <img class="thumb" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRBTo8xwsImFhZ14DdVbKnRKDpP_v3m75-koA&s" alt="">
          <div class="card-body">
            <h3>Lamborghini Urus</h3>
            <p class="short">Спортивный ультра-SUV от Lamborghini.</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- BUGATTI -->
  <section id="bugatti">
    <div class="wrap">
      <h1 class="section-title">Bugatti</h1>
      <div class="gallery">
        <div class="card" onclick="openModal(
          'Bugatti Chiron',
          'https://i.redd.it/m51s2dzb7nm21.jpg',
          'https://avatars.mds.yandex.net/i?id=59d115b21438af1cb33e72e89634fd76-4578360-images-thumbs&n=13',
          'Chiron — гиперкар с W16 и невероятными показателями мощности и скорости.',
          'W16',
          'макс свыше 400 км/ч (в зависимости от версии)',
          '$2,500,000 — $3,500,000',
          '2019')">
          <img class="thumb" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcS4DvP15UTfO_lVBAFXSJGpT9ya6OjMy3Wm-A&s" alt="">
          <div class="card-body">
            <h3>Bugatti Chiron</h3>
            <p class="short">Одна из самых мощных и быстрых серийных машин в мире.</p>
          </div>
        </div>

        <div class="card" onclick="openModal(
          'Bugatti Veyron',
          'https://autoiwc.ru/images/bugatti/bugatti-veyron_8.webp',
          'https://avatars.mds.yandex.net/i?id=59d115b21438af1cb33e72e89634fd76-4578360-images-thumbs&n=13',
          'Veyron — легендарный прорывной гиперкар своего времени, ломал рекорды скорости.',
          'W16',
          'макс до ~407+ км/ч (в зависимости от модификации)',
          '$1,700,000+ (в зависимости от редкости)',
          '2010')">
          <img class="thumb" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQcPRRxVdXIZJh8fokGSfqKZPbnkqGP2qTQFg&s" alt="">
          <div class="card-body">
            <h3>Bugatti Veyron</h3>
            <p class="short">Революционный гиперкар — прорыв в скорости и инженерии.</p>
          </div>
        </div>

        <div class="card" onclick="openModal(
          'Bugatti Centodieci',
          'https://auto.vercity.ru/img/news/2018/09/11/1536644303.jpg',
          'https://avatars.mds.yandex.net/i?id=59d115b21438af1cb33e72e89634fd76-4578360-images-thumbs&n=13',
          'Centodieci — очень ограниченная серия, эксклюзив для коллекционеров.',
          'W16',
          'показатели экстремальные, акцент на эксклюзивность',
          'несколько миллионов $',
          '2021')">
          <img class="thumb" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQTa0rOhghU-W6_hv9JTRiMcZ5cZE1Uh9sfYw&s" alt="">
          <div class="card-body">
            <h3>Bugatti Centodieci</h3>
            <p class="short">Эксклюзивный гиперкар ограниченной серии.</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- ABOUT -->
  <section id="about">
    <div class="wrap">
      <h1 class="section-title">О нас</h1>
      <div class="about">
        <p>Привет! Меня зовут <b>Байқоныс</b>.<br>
        Это моя атмосферная мини-галерея автомобилей — здесь собрано 27 моделей от 9 брендов. Я сделал этот проект как практику по веб-дизайну и чтобы делиться любимыми машинами.</p>
        <div class="socials">
          <a href="https://www.instagram.com/ba1kony8__?igsh=cmZwYXZ5NGd3NXNu&utm_source=qr" target="_blank">Instagram — @ba1kony8__</a>
        </div>
      </div>
    </div>
  </section>
</main>

<!-- Modal -->
<div id="modal" class="modal" onclick="if(event.target===this) closeModal()">
  <div class="modal-card" role="dialog" aria-modal="true">
    <div style="position:relative;">
      <span class="modal-close" onclick="closeModal()">×</span>
      <div class="modal-top">
        <img id="modalImg" src="" alt="car image">
      </div>
    </div>
    <div class="modal-body">
      <h2 class="modal-title"><img id="modalLogo" class="logo" src="" alt="logo"><span id="modalTitle">Название</span></h2>
      <div id="modalDesc" class="modal-desc">Описание...</div>
      <div class="specs">
        <div class="spec"><strong>Двигатель:</strong> <span id="specEngine"></span></div>
        <div class="spec"><strong>Разгон/скорость:</strong> <span id="specSpeed"></span></div>
        <div class="spec"><strong>Цена:</strong> <span id="specPrice"></span></div>
        <div class="spec"><strong>Год:</strong> <span id="specYear"></span></div>
      </div>
    </div>
  </div>
</div>

<script>
  // dropdown brands toggle
  const btn = document.getElementById('brandsBtn');
  const menu = document.getElementById('brandsMenu');
  btn.addEventListener('click', ()=> {
    menu.style.display = menu.style.display === 'block' ? 'none' : 'block';
  });
  // close dropdown clicking outside
  document.addEventListener('click', (e)=>{
    if(!btn.contains(e.target) && !menu.contains(e.target)) menu.style.display = 'none';
  });
  // smooth scroll from dropdown links
  document.querySelectorAll('#brandsMenu a').forEach(a=>{
    a.addEventListener('click', (e)=>{
      e.preventDefault();
      const target = document.querySelector(a.getAttribute('data-target'));
      if(target){
        const y = target.getBoundingClientRect().top + window.scrollY - 70;
        window.scrollTo({top:y, behavior:'smooth'});
        menu.style.display='none';
      }
    });
  });

  // modal open/close
  function openModal(title, img, logo, desc, engine, speed, price, year){
    document.getElementById('modalImg').src = img;
    document.getElementById('modalLogo').src = logo;
    document.getElementById('modalTitle').textContent = title;
    document.getElementById('modalDesc').textContent = desc;
    document.getElementById('specEngine').textContent = engine;
    document.getElementById('specSpeed').textContent = speed;
    document.getElementById('specPrice').textContent = price;
    document.getElementById('specYear').textContent = year;
    document.getElementById('modal').classList.add('show');
    document.body.style.overflow = 'hidden';
  }
  function closeModal(){
    document.getElementById('modal').classList.remove('show');
    document.body.style.overflow = '';
  }
  document.addEventListener('keydown', (e)=> {
    if(e.key === 'Escape') closeModal();
  });

  // ensure images are visible in modal (preload minimal)
  // (nothing extra needed; setting src before showing modal is enough)
</script>

</body>
</html>
