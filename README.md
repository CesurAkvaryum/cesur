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
      background-color: #f0f8ff;
    }
    header {
      background-color: #00838f;
      color: white;
      padding: 20px;
      text-align: center;
    }
    h2 {
      text-align: center;
      margin-top: 30px;
      color: #00695c;
    }
    .scroll-section {
      display: flex;
      overflow-x: auto;
      gap: 20px;
      padding: 20px;
      scroll-snap-type: x mandatory;
    }
    .product-card {
      min-width: 300px;
      flex-shrink: 0;
      background-color: white;
      border-radius: 10px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.1);
      padding: 15px;
      scroll-snap-align: start;
      text-align: center;
      cursor: pointer;
      transition: transform 0.2s;
      position: relative;
    }
    .product-card:hover {
      transform: scale(1.03);
    }
    .product-card img {
      width: 100%;
      height: 180px;
      object-fit: cover;
      border-radius: 8px;
    }
    .product-card h3 {
      margin: 10px 0 5px;
      color: #00796b;
    }
    .product-card p {
      color: #444;
      font-size: 14px;
    }
    .product-detail {
      display: none;
      padding: 15px;
      margin-top: 10px;
      background-color: #e0f2f1;
      border-top: 1px solid #b2dfdb;
      border-radius: 0 0 10px 10px;
      font-size: 14px;
      color: #004d40;
      text-align: left;
    }
    .product-detail.active {
      display: block;
    }
    footer {
      background-color: #eeeeee;
      text-align: center;
      padding: 20px;
      font-size: 14px;
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

  <h2>🐠 Akvaryum</h2>
  <div class="scroll-section">
    <div class="product-card" onclick="toggleDetail(this)">
      <img src="https://cdn.pixabay.com/photo/2020/02/14/17/59/aquarium-4848120_1280.jpg" alt="Cam Akvaryum" />
      <h3>Cam Akvaryum</h3>
      <p>Şık ve dayanıklı cam akvaryum çeşitleri.</p>
      <div class="product-detail">
        Cam akvaryumlar dayanıklılık ve şıklığı bir arada sunar. Farklı boyut ve tasarımlarda mevcuttur.
      </div>
    </div>
    <div class="product-card" onclick="toggleDetail(this)">
      <img src="https://cdn.pixabay.com/photo/2017/08/06/13/54/aquarium-2594583_1280.jpg" alt="Başlangıç Seti" />
      <h3>Başlangıç Seti</h3>
      <p>Yeni başlayanlara özel eksiksiz akvaryum setleri.</p>
      <div class="product-detail">
        Yeni başlayanlar için tasarlanmış bu set, filtre, ısıtıcı, dekor, yem ve temel aksesuarlarla birlikte gelir. Akvaryum hobisine kolay bir adımla giriş yapın!
      </div>
    </div>
  </div>

  <h2>🌿 Bitki</h2>
  <div class="scroll-section">
    <div class="product-card" onclick="toggleDetail(this)">
      <img src="https://cdn.pixabay.com/photo/2016/04/14/20/11/aquarium-1322444_1280.jpg" alt="Bitkili Akvaryum" />
      <h3>Bitkili Akvaryum</h3>
      <p>CO2 gerektirmeyen canlı akvaryum bitkileri.</p>
      <div class="product-detail">
        Canlı bitkiler ile akvaryumunuzu doğal ve sağlıklı hale getirin. CO2 takviyesi gerektirmeyen türler mevcuttur.
      </div>
    </div>
    <div class="product-card" onclick="toggleDetail(this)">
      <img src="https://cdn.pixabay.com/photo/2020/07/12/11/25/aquarium-5396143_1280.jpg" alt="Bitki Dekoru" />
      <h3>Bitki Dekorları</h3>
      <p>Doğal bitkilerle akvaryumunuzu süsleyin.</p>
      <div class="product-detail">
        Akvaryumunuz için doğal ve estetik bitki dekorları. Farklı renk ve boyut seçenekleri ile.
      </div>
    </div>
  </div>

  <h2>🐟 Canlı</h2>
  <div class="scroll-section">
    <div class="product-card" onclick="toggleDetail(this)">
      <img src="https://cdn.pixabay.com/photo/2021/08/05/11/20/fish-6522766_1280.jpg" alt="Neon Tetra" />
      <h3>Neon Tetra</h3>
      <p>Renkli ve uyumlu sürü balıkları.</p>
      <div class="product-detail">
        Neon Tetra, sürü halinde uyumlu yaşayan ve akvaryuma renk katan küçük balık türüdür.
      </div>
    </div>
    <div class="product-card" onclick="toggleDetail(this)">
      <img src="https://cdn.pixabay.com/photo/2022/07/20/13/35/guppy-7334925_1280.jpg" alt="Guppy" />
      <h3>Guppy</h3>
      <p>Kolay bakımlı, canlı renkli balık türleri.</p>
      <div class="product-detail">
        Guppy, bakımı kolay, renkli ve aktif hareket eden popüler bir akvaryum balığıdır.
      </div>
    </div>
  </div>

  <h2>📞 İletişim</h2>
  <div style="padding: 0 20px; margin-bottom: 40px;">
    <p><strong>Adres:</strong> Aksaray, Türkiye</p>
    <p><strong>Telefon:</strong> +90 501 376 15 33</p>
    <p><strong>E-Posta:</strong> info@cesurakvaryum.com</p>
  </div>

  <footer>
    &copy; 2025 Cesur Akvaryum. Tüm hakları saklıdır.
  </footer>

  <script>
    function toggleDetail(card) {
      const detail = card.querySelector('.product-detail');
      detail.classList.toggle('active');
    }
  </script>

</body>
</html>
  </script>

</body>
</html>
