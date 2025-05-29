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
      padding: 20px 30px;
      display: flex;
      align-items: center;
      gap: 15px;
    }
    header img {
      width: 48px;
      height: 48px;
    }
    header h1 {
      margin: 0;
      font-weight: 900;
      font-size: 2rem;
    }
    .tabs {
      display: flex;
      justify-content: center;
      gap: 20px;
      margin: 20px 0;
    }
    .tab-button {
      padding: 10px 20px;
      border: none;
      border-radius: 30px;
      background-color: #b2ebf2;
      color: #006064;
      font-weight: bold;
      cursor: pointer;
      transition: background-color 0.3s;
    }
    .tab-button.active {
      background-color: #00796b;
      color: white;
    }
    .tab-content {
      display: none;
    }
    .tab-content.active {
      display: block;
    }
    .scroll-section {
      display: flex;
      overflow-x: auto;
      overflow-y: hidden;
      gap: 24px;
      padding: 30px 24px 40px;
      scroll-snap-type: x mandatory;
      background: linear-gradient(135deg, #a8edea, #fed6e3);
      border-radius: 20px;
      margin: 0 20px 40px;
      box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
    }
    .product-card {
      min-width: 300px;
      flex-shrink: 0;
      background-color: white;
      border-radius: 18px;
      box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15),
                  0 2px 6px rgba(0, 0, 0, 0.08);
      padding: 20px;
      scroll-snap-align: start;
      text-align: center;
      cursor: pointer;
      transition: transform 0.3s ease, box-shadow 0.3s ease;
      position: relative;
    }
    .product-card:hover {
      transform: translateY(-10px) scale(1.07);
    }
    .product-card img {
      width: 100%;
      height: 200px;
      object-fit: cover;
      border-radius: 16px;
      transition: transform 0.3s ease;
    }
    .product-card:hover img {
      transform: scale(1.05);
    }
    .product-card h3 {
      margin: 18px 0 8px;
      color: #00796b;
    }
    .product-detail {
      display: none;
      padding: 12px 18px;
      background-color: #b2dfdb;
      border-radius: 0 0 16px 16px;
      color: #004d40;
      font-size: 14px;
      line-height: 1.4;
      text-align: left;
      margin-top: 12px;
    }
    .product-detail.active {
      display: block;
    }
    .product-detail h4 {
      margin: 10px 0 6px;
      color: #004d40;
      border-bottom: 1px solid #00796b;
      padding-bottom: 3px;
    }
    .product-detail ul {
      margin: 0 0 10px 18px;
      padding: 0;
      list-style-type: disc;
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
      cursor: pointer;
    }
    /* Bilgi Butonu */
    #BilgiBtn {
      background-color: #00796b;
      color: white;
      border: none;
      padding: 12px 24px;
      border-radius: 30px;
      cursor: pointer;
      font-weight: bold;
      font-size: 16px;
      margin: 0 auto 40px;
      display: block;
      width: 150px;
    }
    /* Modal */
    #infoModal {
      display: none;
      position: fixed;
      top: 50%; left: 50%;
      transform: translate(-50%, -50%);
      background: white;
      padding: 30px;
      border-radius: 15px;
      box-shadow: 0 10px 25px rgba(0,0,0,0.3);
      max-width: 90%;
      max-height: 80%;
      overflow-y: auto;
      z-index: 9999;
    }
    #infoModal h2 {
      margin-top: 0;
      color: #00796b;
    }
    #infoModal button {
      margin-top: 20px;
      background: #00796b;
      color: white;
      border: none;
      padding: 8px 20px;
      border-radius: 30px;
      cursor: pointer;
      font-weight: bold;
    }
    /* İletişim Bölümü */
    .contact-section {
      background-color: #004d40;
      color: white;
      padding: 30px 20px;
      text-align: center;
      font-size: 1rem;
      font-weight: 600;
      border-top-left-radius: 20px;
      border-top-right-radius: 20px;
      box-shadow: 0 -5px 20px rgba(0, 0, 0, 0.2);
      margin-top: 40px;
    }
    .contact-section h2 {
      margin-bottom: 16px;
      font-weight: 900;
    }
    .contact-section a {
      color: #80cbc4;
      text-decoration: none;
    }
  </style>
</head>
<body>

<header>
  <img src="https://cdn-icons-png.flaticon.com/512/616/616408.png" alt="Logo" />
  <h1>Cesur Akvaryum</h1>
</header>

<div class="tabs">
  <button class="tab-button active" onclick="openTab('akvaryum', this)">🐠 Akvaryum</button>
  <button class="tab-button" onclick="openTab('bitki', this)">🌿 Bitki</button>
  <button class="tab-button" onclick="openTab('canli', this)">🐟 Canlı</button>
</div>

<!-- Akvaryum İçeriği -->
<div id="akvaryum" class="tab-content active">
  <div class="scroll-section">

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2016/11/29/12/54/fish-tank-1866863_1280.jpg" alt="Küçük Cam Akvaryum" />
      <h3>Küçük Cam Akvaryum</h3>
      <p>Kompakt tasarımıyla her alana uygun.</p>
      <div class="product-detail">
        <h4>Özellikler:</h4>
        <ul>
          <li>Malzeme: Temperli cam</li>
          <li>Kapak: Var</li>
          <li>Aydınlatma: LED</li>
        </ul>
        <h4>Yaşam Koşulları:</h4>
        <ul>
          <li>Su Sıcaklığı: 22-26°C</li>
          <li>pH: 6.5-7.5</li>
          <li>Filtrasyon: Zorunlu</li>
        </ul>
        <h4>Akvaryum Boyutu:</h4>
        <p>Minimum hacim: 30 litre</p>
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2014/11/21/17/36/aquarium-540461_1280.jpg" alt="Büyük Cam Akvaryum" />
      <h3>Büyük Cam Akvaryum</h3>
      <p>Geniş hacimli gösterişli akvaryum.</p>
      <div class="product-detail">
        <h4>Özellikler:</h4>
        <ul>
          <li>Malzeme: Temperli cam</li>
          <li>Kapak: Var</li>
          <li>Aydınlatma: LED</li>
        </ul>
        <h4>Yaşam Koşulları:</h4>
        <ul>
          <li>Su Sıcaklığı: 20-28°C</li>
          <li>pH: 6.8-7.8</li>
          <li>Filtrasyon: Zorunlu</li>
        </ul>
        <h4>Akvaryum Boyutu:</h4>
        <p>Minimum hacim: 100 litre</p>
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

  </div>
</div>

<!-- Bitki İçeriği -->
<div id="bitki" class="tab-content">
  <div class="scroll-section">

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2018/05/22/16/06/aquarium-3428380_1280.jpg" alt="Anubias Bitkisi" />
      <h3>Anubias Bitkisi</h3>
      <p>Bakımı kolay, dayanıklı bir su bitkisi.</p>
      <div class="product-detail">
        <h4>Özellikler:</h4>
        <ul>
          <li>Ortam: Tatlı su</li>
          <li>Işık: Düşük-orta</li>
          <li>Yayılma: Yavaş</li>
        </ul>
        <h4>Yaşam Koşulları:</h4>
        <ul>
          <li>Su Sıcaklığı: 22-28°C</li>
          <li>pH: 6.0-7.5</li>
          <li>Besin: Yeterli CO2</li>
        </ul>
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2017/09/24/18/46/water-2779367_1280.jpg" alt="Java Moss Bitkisi" />
      <h3>Java Moss Bitkisi</h3>
      <p>Yosun görünümlü popüler su bitkisi.</p>
      <div class="product-detail">
        <h4>Özellikler:</h4>
        <ul>
          <li>Ortam: Tatlı su</li>
          <li>Işık: Düşük</li>
          <li>Yayılma: Hızlı</li>
        </ul>
        <h4>Yaşam Koşulları:</h4>
        <ul>
          <li>Su Sıcaklığı: 20-26°C</li>
          <li>pH: 6.0-7.0</li>
          <li>Besin: Az CO2</li>
        </ul>
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

  </div>
</div>

<!-- Canlı İçeriği -->
<div id="canli" class="tab-content">
  <div class="scroll-section">

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2015/06/24/15/45/fish-820051_1280.jpg" alt="Kırmızı Plati" />
      <h3>Kırmızı Plati</h3>
      <p>Canlı renkleri ve dayanıklı yapısıyla sevilen.</p>
      <div class="product-detail">
        <h4>Özellikler:</h4>
        <ul>
          <li>Boy: 5-6 cm</li>
          <li>Davranış: Barışçıl, sürü balığı</li>
          <li>Renk: Kırmızı tonları</li>
        </ul>
        <h4>Yaşam Koşulları:</h4>
        <ul>
          <li>Su sıcaklığı: 22-26°C</li>
          <li>pH: 7.0-8.0</li>
          <li>Filtrasyon: Orta seviyede</li>
        </ul>
        <h4>Akvaryum Boyutu:</h4>
        <p>Minimum hacim: 40 litre</p>
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <!-- Yeni Ürünler Başlangıcı -->

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2017/01/06/17/05/shark-1958651_1280.jpg" alt="Pengasus Köpek Balığı" />
      <h3>Pengasus Köpek Balığı</h3>
      <p>Şık görünümü ve sakin yapısı ile popüler.</p>
      <div class="product-detail">
        <h4>Özellikler:</h4>
        <ul>
          <li>Boy: 12-15 cm</li>
          <li>Davranış: Barışçıl, gececi</li>
          <li>Renk: Gri ve beyaz</li>
        </ul>
        <h4>Yaşam Koşulları:</h4>
        <ul>
          <li>Su sıcaklığı: 22-28°C</li>
          <li>pH: 6.5-7.5</li>
          <li>Filtrasyon: İyi seviyede</li>
        </ul>
        <h4>Akvaryum Boyutu:</h4>
        <p>Minimum hacim: 100 litre</p>
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2017/05/30/23/11/shark-2351467_1280.jpg" alt="Challenger Köpek Balığı" />
      <h3>Challenger Köpek Balığı</h3>
      <p>Güçlü yapısı ve dikkat çekici görünümü.</p>
      <div class="product-detail">
        <h4>Özellikler:</h4>
        <ul>
          <li>Boy: 20-25 cm</li>
          <li>Davranış: Agresif, korumacı</li>
          <li>Renk: Siyah ve gri tonları</li>
        </ul>
        <h4>Yaşam Koşulları:</h4>
        <ul>
          <li>Su sıcaklığı: 24-28°C</li>
          <li>pH: 7.0-7.8</li>
          <li>Filtrasyon: Yüksek performans</li>
        </ul>
        <h4>Akvaryum Boyutu:</h4>
        <p>Minimum hacim: 150 litre</p>
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2017/11/08/21/17/tetra-2936644_1280.jpg" alt="Genetik Tetra" />
      <h3>Genetik Tetra</h3>
      <p>Canlı renkleri ve dayanıklılığı ile tercih edilir.</p>
      <div class="product-detail">
        <h4>Özellikler:</h4>
        <ul>
          <li>Boy: 3-5 cm</li>
          <li>Davranış: Sosyal, sürü balığı</li>
          <li>Renk: Parlak mavi ve kırmızı</li>
        </ul>
        <h4>Yaşam Koşulları:</h4>
        <ul>
          <li>Su sıcaklığı: 22-26°C</li>
          <li>pH: 6.0-7.0</li>
          <li>Filtrasyon: Orta seviyede</li>
        </ul>
        <h4>Akvaryum Boyutu:</h4>
        <p>Minimum hacim: 40 litre</p>
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <!-- Yeni Ürünler Sonu -->

  </div>
</div>

<button id="BilgiBtn">Bilgi</button>

<div id="infoModal">
  <h2>Cesur Akvaryum Bilgileri</h2>
  <p>
    Akvaryum hobisi, doğal yaşamı evimize taşımak ve su altı dünyasının güzelliklerini keşfetmek için harika bir yoldur.
    Cesur Akvaryum olarak, her seviyeden hobiciye kaliteli ürün ve bilgi sunmayı amaçlıyoruz.
  </p>
  <button onclick="closeModal()">Kapat</button>
</div>

<div class="contact-section">
  <h2>İletişim</h2>
  <p>Email: <a href="mailto:iletisim@cesurakvaryum.com">iletisim@cesurakvaryum.com</a></p>
  <p>Telefon: +90 501 376 15 33</p>
</div>

<script>
  function openTab(tabName, elem) {
    document.querySelectorAll('.tab-button').forEach(btn => btn.classList.remove('active'));
    elem.classList.add('active');
    document.querySelectorAll('.tab-content').forEach(tc => tc.classList.remove('active'));
    document.getElementById(tabName).classList.add('active');
  }

  function toggleDetail(button) {
    const detail = button.previousElementSibling;
    if (detail.classList.contains('active')) {
      detail.classList.remove('active');
      button.textContent = 'Detayları Göster';
    } else {
      detail.classList.add('active');
      button.textContent = 'Detayları Gizle';
    }
  }

  document.getElementById('BilgiBtn').addEventListener('click', () => {
    document.getElementById('infoModal').style.display = 'block';
  });

  function closeModal() {
    document.getElementById('infoModal').style.display = 'none';
  }
</script>

</body>
</html>
