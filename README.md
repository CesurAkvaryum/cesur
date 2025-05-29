<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Cesur Akvaryum</title>
  <link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;700;900&display=swap" rel="stylesheet" />
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

    /* Modal stilleri */
    .modal {
      display: none;
      position: fixed;
      z-index: 9999;
      left: 0;
      top: 0;
      width: 100vw;
      height: 100vh;
      overflow: auto;
      background-color: rgba(0,0,0,0.6);
      align-items: center;
      justify-content: center;
      padding: 20px;
    }
    .modal-content {
      background-color: white;
      border-radius: 12px;
      max-width: 700px;
      width: 100%;
      padding: 30px 20px;
      box-shadow: 0 8px 30px rgba(0,0,0,0.3);
      position: relative;
      animation: fadeIn 0.3s ease forwards;
    }
    @keyframes fadeIn {
      from {opacity: 0; transform: translateY(-20px);}
      to {opacity: 1; transform: translateY(0);}
    }
    .modal-content h3 {
      margin-top: 0;
      color: #00695c;
      font-weight: 900;
    }
    .modal-content p {
      line-height: 1.5;
      color: #444;
    }
    .modal-content img {
      max-width: 100%;
      border-radius: 12px;
      margin: 20px 0;
    }
    .close-btn {
      position: absolute;
      top: 15px;
      right: 15px;
      font-size: 24px;
      color: #666;
      cursor: pointer;
      border: none;
      background: none;
      font-weight: bold;
    }
    .close-btn:hover {
      color: #00796b;
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
        <img src="https://images.unsplash.com/photo-1614019512475-c9f6a0eb98d5" alt="Akvaryum 1" />
        <div class="content">
          <h3>Akvaryum</h3>
          <p>Farklı boyutlarda kaliteli cam akvaryumlar.</p>
          <button class="detail-btn" data-product="Akvaryum">Detaylar</button>
        </div>
      </div>
      <div class="product-card">
        <img src="https://images.unsplash.com/photo-1592229505780-dc361b2cfa9c" alt="Dekor" />
        <div class="content">
          <h3>Akvaryum Dekorları</h3>
          <p>Estetik ve doğal görünümlü dekor seçenekleri.</p>
          <button class="detail-btn" data-product="Akvaryum Dekorları">Detaylar</button>
        </div>
      </div>
      <div class="product-card">
        <img src="https://images.unsplash.com/photo-1529156069898-49953e39b3ac" alt="Bitki" />
        <div class="content">
          <h3>Bitki</h3>
          <p>Canlı ve yapay bitkilerle doğal bir ortam yaratın.</p>
          <button class="detail-btn" data-product="Bitki">Detaylar</button>
        </div>
      </div>
      <div class="product-card">
        <img src="https://images.unsplash.com/photo-1615193470313-bdd2523cc4db" alt="Canlı" />
        <div class="content">
          <h3>Canlı</h3>
          <p>Sağlıklı ve çeşitli akvaryum balıkları.</p>
          <button class="detail-btn" data-product="Canlı">Detaylar</button>
        </div>
      </div>
      <div class="product-card">
        <img src="https://images.unsplash.com/photo-1610279721635-4a2e8f142cc1" alt="Filtre" />
        <div class="content">
          <h3>Filtreler</h3>
          <p>Temiz ve sağlıklı su için güçlü filtreler.</p>
          <button class="detail-btn" data-product="Filtreler">Detaylar</button>
        </div>
      </div>
    </div>
  </section>

  <section class="info-section" id="hakkimizda">
    <h2>Hakkımızda</h2>
    <p>Cesur Akvaryum olarak doğanın en güzel parçalarını evinize getiriyoruz. Uzun yıllardır sektörde edindiğimiz tecrübe ile kaliteli ve güvenilir ürünleri sizlere sunmaktan gurur duyuyoruz. Doğal, sağlıklı ve estetik akvaryum ortamları yaratmak için buradayız.</p>
  </section>

  <section class="contact-section" id="iletisim">
    <h2>İletişim</h2>
    <p>Adres: Örnek Mah. Akvaryum Sok. No:12, İstanbul</p>
    <p>Telefon: (0212) 123 45 67</p>
    <p>Email: <a href="mailto:info@cesurakvaryum.com">info@cesurakvaryum.com</a></p>
  </section>

  <!-- Modal -->
  <div class="modal" id="productModal">
    <div class="modal-content">
      <button class="close-btn" id="closeModal">&times;</button>
      <h3 id="modalTitle"></h3>
      <img id="modalImage" src="" alt="" />
      <p id="modalDescription"></p>
    </div>
  </div>

  <script>
    // Ürün detayları bilgisi
    const productDetails = {
      "Akvaryum": {
        description: "Farklı boyutlarda kaliteli camdan yapılmış, dayanıklı ve şık tasarımlı akvaryumlarımız ile evinizin dekorasyonunu tamamlayın.",
        image: "https://images.unsplash.com/photo-1614019512475-c9f6a0eb98d5"
      },
      "Akvaryum Dekorları": {
        description: "Doğal görünümlü taşlar, bitkiler ve diğer dekoratif ürünlerle akvaryumunuzu güzelleştirin ve balıklarınıza daha doğal bir ortam sağlayın.",
        image: "https://images.unsplash.com/photo-1592229505780-dc361b2cfa9c"
      },
      "Bitki": {
        description: "Canlı veya yapay bitkilerimizle akvaryumunuzu daha canlı ve sağlıklı hale getirin. Doğal ortamın keyfini çıkarın.",
        image: "https://images.unsplash.com/photo-1529156069898-49953e39b3ac"
      },
      "Canlı": {
        description: "Sağlıklı, dayanıklı ve çeşitli balık türleri ile akvaryumunuzu renklendirin. Uzman ekibimiz her zaman yanınızda.",
        image: "https://images.unsplash.com/photo-1615193470313-bdd2523cc4db"
      },
      "Filtreler": {
        description: "Akvaryumunuzun suyunu temiz ve sağlıklı tutmak için çeşitli kapasite ve modellerde güçlü filtre sistemlerimiz mevcuttur.",
        image: "https://images.unsplash.com/photo-1610279721635-4a2e8f142cc1"
      }
    };

    // Modal ve butonları seç
    const modal = document.getElementById('productModal');
    const modalTitle = document.getElementById('modalTitle');
    const modalImage = document.getElementById('modalImage');
    const modalDescription = document.getElementById('modalDescription');
    const closeModalBtn = document.getElementById('closeModal');

    // Detay butonlarına event listener ekle
    document.querySelectorAll('.detail-btn').forEach(button => {
      button.addEventListener('click', () => {
        const productName = button.getAttribute('data-product');
        const details = productDetails[productName];
        if(details) {
          modalTitle.textContent = productName;
          modalImage.src = details.image;
          modalImage.alt = productName;
          modalDescription.textContent = details.description;
          modal.style.display = 'flex';
          document.body.style.overflow = 'hidden'; // scroll kilitle
        }
      });
    });

    // Modal kapatma
    closeModalBtn.addEventListener('click', () => {
      modal.style.display = 'none';
      document.body.style.overflow = 'auto';
    });

    // Modal dışına tıklayınca kapatma
    window.addEventListener('click', (e) => {
      if(e.target === modal) {
        modal.style.display = 'none';
        document.body.style.overflow = 'auto';
      }
    });
  </script>
</body>
</html>
