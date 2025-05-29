<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Cesur Akvaryum | Petshop</title>
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      background-color: #f9f9f9;
    }
    header {
      background-color: #00796B;
      color: white;
      padding: 20px;
      text-align: center;
    }
    nav {
      background-color: #004D40;
      display: flex;
      justify-content: center;
      gap: 20px;
      padding: 10px 0;
    }
    nav a {
      color: white;
      text-decoration: none;
      font-weight: bold;
    }
    section {
      padding: 40px 20px;
      max-width: 1000px;
      margin: auto;
    }
    h2 {
      color: #00796B;
      border-bottom: 2px solid #00796B;
      padding-bottom: 10px;
    }
    .product {
      display: flex;
      gap: 20px;
      margin-top: 20px;
      flex-wrap: wrap;
    }
    .product-card {
      flex: 1 1 300px;
      background: white;
      border-radius: 8px;
      box-shadow: 0 2px 10px rgba(0,0,0,0.1);
      padding: 20px;
      text-align: center;
    }
    .product-card img {
      max-width: 100%;
      border-radius: 6px;
    }
    footer {
      text-align: center;
      background-color: #eeeeee;
      padding: 20px;
      color: #666;
      margin-top: 40px;
    }
  </style>
</head>
<body>

  <header>
    <h1>Cesur Akvaryum</h1>
    <p>Doğal ve Sağlıklı Akvaryumlar İçin Her Şey</p>
  </header>

  <nav>
    <a href="#akvaryum">Akvaryum</a>
    <a href="#bitki">Bitki</a>
    <a href="#canli">Canlı</a>
    <a href="#iletisim">İletişim</a>
  </nav>

  <section id="akvaryum">
    <h2>🐠 Akvaryum</h2>
    <div class="product">
      <div class="product-card">
        <img src="co2-gerekmeyen-1.webp" alt="Akvaryum" />
        <h3>Cam Akvaryum 60x40</h3>
        <p>Dayanıklı, sızdırmaz ve modern cam akvaryumlar.</p>
      </div>
    </div>
  </section>

  <section id="bitki">
    <h2>🌿 Bitki</h2>
    <div class="product">
      <div class="product-card">
        <img src="co2-gerekmeyen-1.webp" alt="Bitkili Akvaryum" />
        <h3>Bitkili Akvaryum</h3>
        <p>CO2 gerektirmeyen canlı akvaryum bitkileriyle dekore edilmiş.</p>
      </div>
    </div>
  </section>

  <section id="canli">
    <h2>🐟 Canlı</h2>
    <div class="product">
      <div class="product-card">
        <img src="https://cdn.pixabay.com/photo/2016/04/14/20/11/aquarium-1322444_1280.jpg" alt="Balık" />
        <h3>Neon Tetra</h3>
        <p>Renkli ve uyumlu sürü balıkları.</p>
      </div>
    </div>
  </section>

  <section id="iletisim">
    <h2>📞 İletişim</h2>
    <p><strong>Adres:</strong> Cesur Akvaryum, Aksaray</p>
    <p><strong>Telefon:</strong> 0501 376 15 33</p>
    <p><strong>E-Posta:</strong> info@cesurakvaryum.com</p>
  </section>

  <footer>
    &copy; 2025 Cesur Akvaryum. Tüm hakları saklıdır.
  </footer>

</body>
</html>
