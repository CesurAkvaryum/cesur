<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Cesur Akvaryum</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins&display=swap" rel="stylesheet" />
  <style>
    body {
      font-family: 'Poppins', Arial, sans-serif;
      margin: 0;
      background-color: #e0f2f1;
      color: #004d40;
    }
    header {
      background-color: #00796b;
      color: white;
      padding: 15px 30px;
      display: flex;
      align-items: center;
      gap: 15px;
      box-shadow: 0 2px 6px rgba(0,0,0,0.15);
    }
    header img {
      height: 50px;
      width: 50px;
      object-fit: contain;
    }
    header h1 {
      margin: 0;
      font-weight: 700;
      font-size: 1.8rem;
      user-select: none;
    }
    header p {
      margin-left: auto;
      font-size: 1rem;
      font-weight: 500;
      color: #b2dfdb;
      user-select: none;
    }

    nav {
      background-color: #004d40;
      text-align: center;
      padding: 10px 0;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
      position: sticky;
      top: 0;
      z-index: 100;
    }
    nav a {
      color: #b2dfdb;
      margin: 0 18px;
      text-decoration: none;
      font-weight: 600;
      font-size: 1.1rem;
      transition: color 0.3s ease;
      cursor: pointer;
    }
    nav a:hover {
      color: #e0f7fa;
      text-decoration: underline;
    }

    h2 {
      text-align: center;
      margin-top: 40px;
      margin-bottom: 15px;
      color: #00796b;
      user-select: none;
    }
    .scroll-section {
      display: flex;
      overflow-x: auto;
      gap: 20px;
      padding: 0 20px 30px;
      scroll-snap-type: x mandatory;
    }
    .product-card {
      min-width: 280px;
      flex-shrink: 0;
      background-color: white;
      border-radius: 12px;
      box-shadow: 0 3px 10px rgba(0,0,0,0.12);
      padding: 15px;
      scroll-snap-align: start;
      text-align: center;
      cursor: pointer;
      transition: transform 0.25s ease, box-shadow 0.25s ease;
      user-select: none;
    }
    .product-card:hover {
      transform: scale(1.05);
      box-shadow: 0 8px 20px rgba(0,0,0,0.2);
    }
    .product-card img {
      width: 100%;
      height: 180px;
      object-fit: cover;
      border-radius: 10px;
      user-select: none;
    }
    .product-card h3 {
      margin: 12px 0 6px;
      color: #004d40;
      font-weight: 700;
      user-select: text;
    }
    .product-card p {
      color: #555;
      font-size: 14px;
      user-select: text;
    }
    .product-detail {
      display: none;
      padding: 15px 20px;
      background-color: #b2dfdb;
      border-radius: 0 0 12px 12px;
      margin-top: -10px;
      color: #004d40;
      font-size: 14px;
      user-select: text;
    }
    .product-detail.active {
      display: block;
    }

    .contact-section {
      max-width: 600px;
      margin: 40px auto 20px;
      padding: 0 20px;
      color: #004d40;
      font-weight: 600;
      font-size: 15px;
      user-select: text;
      line-height: 1.5;
    }
    .contact-section p {
      margin: 6px 0;
    }

    footer {
      background-color: #004d40;
      text-align: center;
      padding: 18px 20px;
      font-size: 14px;
      color: #b2dfdb;
      user-select: none;
      margin-top: 50px;
    }

    /* Scrollbar styling for scroll-section */
    .scroll-section::-webkit-scrollbar {
      height: 8px;
    }
    .scroll-section::-webkit-scrollbar-track {
      background: #c7ecee;
      border-radius: 10px;
    }
    .scroll-section::-webkit-scrollbar-thumb {
      background-color: #00796b;
      border-radius: 10px;
    }

  </style>
</head>
<body>

  <header>
    <img src="https://cdn-icons-png.flaticon.com/512/616/616408.png" alt="Logo" />
    <h1>Cesur Akvaryum</h1>
    <p>Doğal ve Sağlıklı Akvaryumlar İçin Her Şey</p>
  </header>

  <nav>
    <a href="#akvaryum">Akvaryum</a>
    <a href="#bitki">Bitki</a>
    <a href="#canli">Canlı</a>
    <a href="#iletisim">İletişim</a>
  </nav>

  <h2 id="akvaryum">🐠 Akvaryum</h2>
  <div class="scroll-section">
    <div class="product-card" onclick="toggleDetail(this)">
      <img src="https://cdn.pixabay.com/photo/2020/02/14/17/59/aquarium-4848120_1280.jpg" alt="Cam Akvaryum" />
      <h3>Cam Akvaryum</h3>
      <p>Şık ve dayanıklı cam akvaryum çeşitleri.</p>
      <div class="product-detail">
        Cam akvaryumlar, net görünüm ve dayanıklılığı ile tercih edilir. Farklı boyut ve şekillerde mevcuttur.
      </div>
    </div>
    <div class="product-card" onclick="toggleDetail(this)">
      <img src="https://cdn.pixabay.com/photo/2017/08/06/13/54/aquarium-2594583_1280.jpg" alt="Başlangıç Seti" />
      <h3>Başlangıç Seti</h3>
      <p>Yeni başlayanlara özel eksiksiz akvaryum setleri.</p>
      <div class="product-detail">
        Filtre, ısıtıcı, dekor, yem ve temel aksesuarlarla dolu başlangıç seti. Akvaryum hobisine kolay başlangıç!
      </div>
    </div>
  </div>

  <h2 id="bitki">🌿 Bitki</h2>
  <div class="scroll-section">
    <div class="product-card" onclick="toggleDetail(this)">
      <img src="https://cdn.pixabay.com/photo/2016/04/14/20/11/aquarium-1322444_1280.jpg" alt="Bitkili Akvaryum" />
      <h3>Bitkili Akvaryum</h3>
      <p>CO2 gerektirmeyen canlı akvaryum bitkileri.</p>
      <div class="product-detail">
        Bakımı kolay, canlı ve doğal bitkilerle akvaryumunuz şenlensin.
      </div>
    </div>
    <div class="product-card" onclick="toggleDetail(this)">
      <img src="https://cdn.pixabay.com/photo/2020/07/12/11/25/aquarium-5396143_1280.jpg" alt="Bitki Dekorları" />
      <h3>Bitki Dekorları</h3>
      <p>Doğal bitkilerle akvaryumunuzu süsleyin.</p>
      <div class="product-detail">
        Akvaryumunuza estetik katmak için doğal bitki dekorları.
      </div>
    </div>
  </div>

  <h2 id="canli">🐟 Canlı</h2>
  <div class="scroll-section">
    <div class="product-card" onclick="toggleDetail(this)">
      <img src="https://cdn.pixabay.com/photo/2021/08/05/11/20/fish-6522766_1280.jpg" alt="Neon Tetra" />
      <h3>Neon Tetra</h3>
      <p>Canlı ve renkli Neon Tetra balıkları.</p>
      <div class="product-detail">
        Neon Tetra, küçük boyutları ve parlak renkleriyle akvaryumunuzu hareketlendirir. Sosyal balıklardır.
      </div>
    </div>
    <div class="product-card" onclick="toggleDetail(this)">
      <img src="https://cdn.pixabay.com/photo/2016/04/07/19/24/fish-1315207_1280.jpg" alt="Beta Balığı" />
      <h3>Beta Balığı</h3>
      <p>Canlı ve gösterişli Beta balıkları.</p>
      <div class="product-detail">
        Beta balıkları canlı renkleri ve gösterişli yüzgeçleriyle akvaryumunuzun yıldızı olur. Tek başına bakılması önerilir.
      </div>
    </div>
  </div>

  <section id="iletisim" class="contact-section">
    <p><strong>Adres:</strong>  Aksaray/Merkez, Türkiye</p>
    <p><strong>Telefon:</strong> +90 501 376 15 33</p>
    <p><strong>E-posta:</strong> info@cesurakvaryum.com</p>
  </section>

  <footer>
    © 2025 Cesur Akvaryum. Tüm hakları saklıdır.
  </footer>

  <script>
    function toggleDetail(card) {
      const detail = card.querySelector('.product-detail');
      if(detail) {
        detail.classList.toggle('active');
      }
    }
  </script>
</body>
</html>
