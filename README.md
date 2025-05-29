<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Cesur Akvaryum</title>
  <link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;700;900&display=swap" rel="stylesheet">
  <style>
    * {
      box-sizing: border-box;
    }
    body {
      font-family: 'Nunito', sans-serif;
      margin: 0;
      background-color: #f4fdfd;
      color: #003d40;
    }
    header {
      background-color: #006064;
      color: white;
      padding: 20px 30px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      box-shadow: 0 4px 10px rgba(0,0,0,0.15);
    }
    header h1 {
      margin: 0;
      font-weight: 900;
      font-size: 2rem;
    }
    nav {
      display: flex;
      gap: 20px;
    }
    nav a {
      color: white;
      text-decoration: none;
      font-weight: bold;
    }
    nav a:hover {
      text-decoration: underline;
    }
    .hero {
      background: url('https://images.unsplash.com/photo-1607082349250-f7c6c629b3d1') no-repeat center center/cover;
      height: 300px;
      display: flex;
      align-items: center;
      justify-content: center;
      color: white;
      font-size: 2.5rem;
      font-weight: 900;
      text-shadow: 2px 2px 6px rgba(0,0,0,0.6);
    }
    .products-section {
      padding: 40px 20px;
      max-width: 1200px;
      margin: 0 auto;
    }
    .products-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 24px;
    }
    .product-card {
      background-color: white;
      border-radius: 16px;
      box-shadow: 0 6px 18px rgba(0, 0, 0, 0.1);
      overflow: hidden;
      transition: transform 0.3s;
    }
    .product-card:hover {
      transform: translateY(-5px);
    }
    .product-card img {
      width: 100%;
      height: 180px;
      object-fit: cover;
    }
    .product-card .content {
      padding: 20px;
    }
    .product-card h3 {
      margin: 0 0 10px;
      color: #00695c;
    }
    .product-card p {
      font-size: 14px;
      color: #444;
    }
    .product-card button {
      margin-top: 15px;
      background-color: #00796b;
      color: white;
      border: none;
      padding: 10px 20px;
      border-radius: 25px;
      font-weight: bold;
      cursor: pointer;
    }
    .info-section {
      text-align: center;
      padding: 60px 20px;
      background-color: #e0f7fa;
    }
    .info-section h2 {
      font-size: 2rem;
      margin-bottom: 20px;
      color: #004d40;
    }
    .info-section p {
      font-size: 1.1rem;
      max-width: 800px;
      margin: 0 auto;
      line-height: 1.6;
    }
    .contact-section {
      background-color: #004d40;
      color: white;
      padding: 40px 20px;
      text-align: center;
      font-size: 1rem;
      border-top-left-radius: 20px;
      border-top-right-radius: 20px;
    }
    .contact-section h2 {
      margin-bottom: 20px;
    }
    .contact-section a {
      color: #80cbc4;
      text-decoration: none;
    }
  </style>
</head>
<body>
  <header>
    <h1>Cesur Akvaryum</h1>
    <nav>
      <a href="#">Anasayfa</a>
      <a href="#products">Ürünler</a>
      <a href="#hakkimizda">Hakkımızda</a>
      <a href="#iletisim">İletişim</a>
    </nav>
  </header>

  <div class="hero">Doğanın Güzelliğini Evinize Taşıyın</div>

  <section class="products-section" id="products">
    <h2 style="text-align:center; color:#00695c; font-weight:900;">Popüler Ürünler</h2>
    <div class="products-grid">
      <div class="product-card">
        <img src="https://images.unsplash.com/photo-1614019512475-c9f6a0eb98d5" alt="Akvaryum 1">
        <div class="content">
          <h3>Akvaryum</h3>
          <p>Farklı boyutlarda kaliteli cam akvaryumlar.</p>
          <button id="BilgiBtn">Detaylar</button>
        </div>
      </div>
      <div class="product-card">
        <img src="https://images.unsplash.com/photo-1592229505780-dc361b2cfa9c" alt="Dekor">
        <div class="content">
          <h3>Akvaryum Dekorları</h3>
          <p>Estetik ve doğal görünümlü dekor seçenekleri.</p>
          <button>Detaylar</button>
        </div>
      </div>
      <div class="product-card">
        <img src="https://images.unsplash.com/photo-1529156069898-49953e39b3ac" alt="Bitki">
        <div class="content">
          <h3>Bitki</h3>
          <p>Canlı ve yapay bitkilerle doğal bir ortam yaratın.</p>
          <button>Detaylar</button>
        </div>
      </div>
      <div class="product-card">
        <img src="https://images.unsplash.com/photo-1615193470313-bdd2523cc4db" alt="Canlı">
        <div class="content">
          <h3>Canlı</h3>
          <p>Sağlıklı ve çeşitli akvaryum balıkları.</p>
          <button>Detaylar</button>
        </div>
      </div>
      <div class="product-card">
        <img src="https://images.unsplash.com/photo-1610279721635-4a2e8f142cc1" alt="Filtre">
        <div class="content">
          <h3>Filtreler</h3>
          <p>Temiz ve sağlıklı su için güçlü filtre çözümleri.</p>
          <button>Detaylar</button>
        </div>
      </div>
    </div>
  </section>

  <section class="info-section" id="hakkimizda">
    <h2>Biz Kimiz?</h2>
    <p>Cesur Akvaryum olarak yıllardır en kaliteli akvaryum ürünlerini sizlerle buluşturuyoruz. Doğayı yaşam alanınıza taşıyan çözümler sunuyor, hem balıklarınız hem de sizin için estetik ve sağlıklı ortamlar yaratıyoruz.</p>
  </section>

  <section class="contact-section" id="iletisim">
    <h2>Bize Ulaşın</h2>
    <p>Telefon: <a href="tel:+905013761533">+90 501 376 15 33</a><br>E-posta: <a href="mailto:info@cesurakvaryum.com">info@cesurakvaryum.com</a></p>
    <p>Adres: İstanbul, Türkiye</p>
  </section>

  <script>
    document.addEventListener("DOMContentLoaded", function () {
      const bilgiBtn = document.getElementById("BilgiBtn");
      if (bilgiBtn) {
        bilgiBtn.addEventListener("click", function () {
          alert("Ürün hakkında daha fazla bilgi yakında eklenecek!");
        });
      }
    });
  </script>
</body>
</html>
