<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Cesur Akvaryum</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      background: #f0f8ff;
    }
    header {
      background-color: #00838f;
      color: white;
      padding: 20px;
      text-align: center;
    }
    nav {
      background-color: #004d40;
      display: flex;
      justify-content: center;
      gap: 30px;
      padding: 10px 0;
    }
    nav a {
      color: white;
      text-decoration: none;
      font-weight: bold;
    }
    nav a:hover {
      text-decoration: underline;
    }
    .products {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      padding: 20px;
      gap: 20px;
    }
    .product-card {
      background-color: white;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      width: 280px;
      padding: 15px;
      text-align: center;
    }
    .product-card img {
      max-width: 100%;
      border-radius: 8px;
      height: 160px;
      object-fit: cover;
    }
    .product-card h3 {
      margin-top: 10px;
      font-size: 18px;
      color: #00695c;
    }
    .product-card p {
      font-size: 15px;
      color: #444;
    }
    section {
      padding: 20px;
      max-width: 800px;
      margin: auto;
    }
    h2 {
      color: #00796B;
      border-bottom: 1px solid #00796B;
      padding-bottom: 5px;
    }
    footer {
      text-align: center;
      padding: 20px;
      background: #eeeeee;
      font-size: 14px;
      color: #666;
      margin-top: 40px;
    }
  </style>
</head>
<body>

  <header>
    <h1>Cesur Akvaryum</h1>
    <p>Doğal ve Sağlıklı Akvaryumlar İçin</p>
  </header>

  <nav>
    <a href="#akvaryum">Akvaryum</a>
    <a href="#bitki">Bitki</a>
    <a href="#canli">Canlı</a>
    <a href="#iletisim">İletişim</a>
  </nav>

  <section id="akvaryum">
    <h2>🐠 Akvaryum</h2>
    <div class="products">
      <div class="product-card">
        <img src="https://images.unsplash.com/photo-1506744038136-46273834b3fb?auto=format&fit=crop&w=400&q=80" alt="Akvaryum" />
        <h3>60x40 Cam Akvaryum</h3>
        <p>Dayanıklı cam yapısı ile sızdırmaz akvaryum.</p>
      </div>
    </div>
  </section>

  <section id="bitki">
    <h2>🌿 Bitki</h2>
    <div class="products">
      <div class="product-card">
        <img src="https://cdn.pixabay.com/photo/2019/12/10/16/10/aquarium-4686324_1280.jpg" alt="Akvaryum Bitkisi" />
        <h3>Bitkili Akvaryum</h3>
        <p>CO2 gerektirmeyen canlı bitkilerle dekore edilmiş.</p>
      </div>
    </div>
  </section>

  <section id="canli">
    <h2>🐟 Canlı</h2>
    <div class="products">
      <div class="product-card">
        <img src="https://cdn.pixabay.com/photo/2016/04/14/20/11/aquarium-1322444_1280.jpg" alt="Balık" />
        <h3>Neon Tetra</h3>
        <p>Canlı renkleriyle akvaryumunuzu süsleyen sürü balıkları.</p>
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
