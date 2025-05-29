<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Cesur Akvaryum</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap" rel="stylesheet" />
  <style>
    /* Temel ayarlar */
    body {
      font-family: 'Poppins', Arial, sans-serif;
      margin: 0;
      background: linear-gradient(135deg, #e0f7fa, #80deea);
      color: #004d40;
      min-height: 100vh;
    }
    header {
      display: flex;
      align-items: center;
      padding: 15px 30px;
      background-color: #00695c;
      color: #e0f2f1;
      box-shadow: 0 4px 8px rgb(0 0 0 / 0.1);
      position: sticky;
      top: 0;
      z-index: 1000;
    }
    header h1 {
      margin: 0;
      font-weight: 600;
      font-size: 1.8rem;
    }
    header p {
      margin: 0 0 0 15px;
      font-weight: 400;
      font-size: 1rem;
      opacity: 0.85;
    }

    /* Başlık bölümü düzeni */
    .header-left {
      display: flex;
      flex-direction: column;
    }

    h2 {
      text-align: center;
      margin: 40px 0 20px;
      color: #004d40;
      font-weight: 600;
      font-size: 1.6rem;
      letter-spacing: 1px;
    }

    /* Kaydırma bölümü */
    .scroll-section {
      display: flex;
      overflow-x: auto;
      gap: 24px;
      padding: 20px 30px;
      scroll-snap-type: x mandatory;
      scrollbar-width: thin;
      scrollbar-color: #004d40 #b2dfdb;
    }
    .scroll-section::-webkit-scrollbar {
      height: 8px;
    }
    .scroll-section::-webkit-scrollbar-track {
      background: #b2dfdb;
      border-radius: 4px;
    }
    .scroll-section::-webkit-scrollbar-thumb {
      background-color: #004d40;
      border-radius: 4px;
    }

    /* Ürün kartları */
    .product-card {
      min-width: 320px;
      flex-shrink: 0;
      background-color: #ffffffcc;
      border-radius: 14px;
      box-shadow: 0 6px 14px rgb(0 0 0 / 0.12);
      padding: 20px;
      scroll-snap-align: start;
      text-align: center;
      cursor: pointer;
      transition: transform 0.3s ease, box-shadow 0.3s ease;
      position: relative;
    }
    .product-card:hover {
      transform: translateY(-6px) scale(1.05);
      box-shadow: 0 12px 24px rgb(0 0 0 / 0.18);
    }
    .product-card img {
      width: 100%;
      height: 180px;
      object-fit: cover;
      border-radius: 12px;
      margin-bottom: 14px;
      box-shadow: 0 4px 8px rgb(0 0 0 / 0.1);
    }
    .product-card h3 {
      margin: 8px 0 6px;
      color: #00796b;
      font-weight: 600;
      font-size: 1.25rem;
    }
    .product-card p {
      color: #333;
      font-size: 15px;
      line-height: 1.4;
      margin-bottom: 12px;
    }

    /* Detay alanı */
    .product-detail {
      display: none;
      padding: 15px;
      margin-top: 12px;
      background-color: #b2dfdbcc;
      border-radius: 0 0 14px 14px;
      font-size: 14px;
      color: #004d40;
      text-align: left;
    }
    .product-detail.active {
      display: block;
    }

    /* İletişim bölümü */
    .contact-section {
      padding: 0 30px 40px;
      color: #004d40dd;
      font-weight: 500;
      font-size: 1rem;
      max-width: 600px;
      margin: 0 auto;
      line-height: 1.5;
    }
    .contact-section p {
      margin: 8px 0;
    }
    .contact-section strong {
      color: #004d40;
    }

    /* Footer */
    footer {
      background-color: #004d40;
      text-align: center;
      padding: 18px 30px;
      font-size: 14px;
      color: #b2dfdb;
      letter-spacing: 0.5px;
      user-select: none;
    }

    /* Responsive */
    @media (max-width: 600px) {
      header {
        flex-direction: column;
        text-align: left;
        gap: 6px;
      }
      header p {
        margin-left: 0;
      }
      .scroll-section {
        padding: 15px 15px;
      }
      .product-card {
        min-width: 260px;
      }
      .contact-section {
        padding: 0 15px 30px;
      }
    }
  </style>
</head>
<body>

  <header>
    <div class="header-left">
      <h1>Cesur Akvaryum</h1>
      <p>Doğal ve Sağlıklı Akvaryumlar İçin Her Şey</p>
    </div>
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

  <section class="contact-section">
    <p><strong>Adres:</strong> İstanbul, Türkiye</p>
    <p><strong>Telefon:</strong> +90 555 123 45 67</p>
    <p><strong>E-posta:</strong> info@cesurakvaryum.com</p>
  </section>

  <footer>
    © 2025 Cesur Akvaryum. Tüm hakları saklıdır.
  </footer>

  <script>
    function toggleDetail(card) {
      const detail = card.querySelector('.product-detail');
      detail.classList.toggle('active');
    }
  </script>
</body>
</html>
