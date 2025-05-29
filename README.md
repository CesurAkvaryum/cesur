<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
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
      display: flex;
      align-items: center;
      gap: 15px;
      padding-left: 30px;
    }
    header img {
      width: 48px;
      height: 48px;
    }
    header h1 {
      margin: 0;
      font-weight: 900;
      font-size: 2rem;
      user-select: none;
    }
    header p {
      margin: 0 0 0 10px;
      font-size: 1rem;
      font-weight: 600;
      color: #b2dfdb;
      user-select: none;
    }
    h2 {
      text-align: center;
      margin-top: 30px;
      color: #00695c;
      font-weight: 800;
      font-size: 1.8rem;
      user-select: none;
    }
    .scroll-section {
      display: flex;
      overflow-x: auto;
      gap: 24px;
      padding: 30px 24px 40px;
      scroll-snap-type: x mandatory;
      background: linear-gradient(135deg, #a8edea, #fed6e3);
      border-radius: 20px;
      margin: 20px;
      box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
    }
    .product-card {
      min-width: 300px;
      flex-shrink: 0;
      background-color: white;
      border-radius: 18px;
      box-shadow:
        0 8px 20px rgba(0, 0, 0, 0.15),
        0 2px 6px rgba(0, 0, 0, 0.08);
      padding: 20px;
      scroll-snap-align: start;
      text-align: center;
      cursor: pointer;
      transition: transform 0.3s ease, box-shadow 0.3s ease;
      user-select: none;
      position: relative;
    }
    .product-card:hover {
      transform: translateY(-10px) scale(1.07);
      box-shadow:
        0 15px 35px rgba(0, 0, 0, 0.25),
        0 6px 12px rgba(0, 0, 0, 0.12);
      z-index: 10;
    }
    .product-card img {
      width: 100%;
      height: 200px;
      object-fit: cover;
      border-radius: 16px;
      user-select: none;
      transition: transform 0.3s ease;
    }
    .product-card:hover img {
      transform: scale(1.05);
    }
    .product-card h3 {
      margin: 18px 0 8px;
      color: #00796b;
      font-weight: 800;
      font-size: 1.3rem;
      user-select: text;
    }
    .product-card p {
      color: #444;
      font-size: 15px;
      margin-bottom: 14px;
      user-select: text;
    }
    .product-detail {
      display: none;
      padding: 12px 18px;
      background-color: #b2dfdb;
      border-radius: 0 0 16px 16px;
      color: #004d40;
      font-size: 14px;
      user-select: text;
      box-shadow: inset 0 2px 6px rgba(0,0,0,0.1);
      line-height: 1.4;
    }
    .product-detail.active {
      display: block;
    }
    .toggle-btn {
      position: absolute;
      bottom: 15px;
      left: 50%;
      transform: translateX(-50%);
      background-color: #00796b;
      border: none;
      color: white;
      padding: 8px 16px;
      border-radius: 30px;
      font-weight: 600;
      font-size: 14px;
      cursor: pointer;
      transition: background-color 0.3s ease;
      user-select: none;
      box-shadow: 0 3px 8px rgba(0,0,0,0.12);
    }
    .toggle-btn:hover {
      background-color: #004d40;
    }
    footer {
      background-color: #eeeeee;
      text-align: center;
      padding: 20px;
      font-size: 14px;
      color: #666;
      margin-top: 40px;
      user-select: none;
    }
  </style>
</head>
<body>

  <header>
    <img src="https://cdn-icons-png.flaticon.com/512/616/616408.png" alt="Logo" />
    <div>
      <h1>Cesur Akvaryum</h1>
      <p>Doğal ve Sağlıklı Akvaryumlar İçin Her Şey</p>
    </div>
  </header>

  <h2>🐠 Akvaryum</h2>
  <div class="scroll-section">
    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2020/02/14/17/59/aquarium-4848120_1280.jpg" alt="Cam Akvaryum" />
      <h3>Cam Akvaryum</h3>
      <p>Şık ve dayanıklı cam akvaryum çeşitleri.</p>
      <div class="product-detail">
        Cam akvaryumlar, net görünüm ve dayanıklılığı ile tercih edilir. Farklı boyut ve şekillerde mevcuttur.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>
    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2017/08/06/13/54/aquarium-2594583_1280.jpg" alt="Başlangıç Seti" />
      <h3>Başlangıç Seti</h3>
      <p>Yeni başlayanlara özel eksiksiz akvaryum setleri.</p>
      <div class="product-detail">
        Filtre, ısıtıcı, dekor, yem ve temel aksesuarlarla dolu başlangıç seti. Akvaryum hobisine kolay başlangıç!
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>
  </div>

  <h2>🌿 Bitki</h2>
  <div class="scroll-section">
    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2016/04/14/20/11/aquarium-1322444_1280.jpg" alt="Bitkili Akvaryum" />
      <h3>Bitkili Akvaryum</h3>
      <p>CO2 gerektirmeyen canlı akvaryum bitkileri.</p>
      <div class="product-detail">
        Canlı bitkiler akvaryumunuzu güzelleştirir ve su kalitesini artırır. Bakımı kolaydır.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>
    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2020/07/12/11/25/aquarium-5396143_1280.jpg" alt="Bitki Dekoru" />
      <h3>Bitki Dekorları</h3>
      <p>Doğal bitkilerle akvaryumunuzu süsleyin.</p>
      <div class="product-detail">
        Estetik ve doğal bitki dekorları ile akvaryumunuz daha canlı ve doğal görünür.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>
    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2017/03/27/14/01/plant-2178750_1280.jpg" alt="Akvaryum Bitkisi" />
      <h3>Akvaryum Bitkisi</h3>
      <p>Canlı ve sağlıklı akvaryum bitkileri.</p>
      <div class="product-detail">
        Doğal ortamı canlandıran akvaryum bitkileri, suyun kalitesini artırır ve balıklar için barınak sağlar. Kolay bakım ve hızlı büyüme özelliklerine sahiptir.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>
  </div>

  <h2>🐟 Canlı</h2>
  <div class="scroll-section">
    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2021/08/05/11/20/fish-6522766_1280.jpg" alt="Neon Tetra" />
      <h3>Neon Tetra</h3>
      <p>Renkli ve uyumlu sürü balıkları.</p>
      <
