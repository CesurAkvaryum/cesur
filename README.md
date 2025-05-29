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
          <li>Aydınlatma: LED ve UV</li>
        </ul>
        <h4>Yaşam Koşulları:</h4>
        <ul>
          <li>Su Sıcaklığı: 20-28°C</li>
          <li>pH: 6.8-7.8</li>
          <li>Filtrasyon: Zorunlu</li>
        </ul>
        <h4>Akvaryum Boyutu:</h4>
        <p>Minimum hacim: 200 litre</p>
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2016/01/05/13/58/aquarium-1129108_1280.jpg" alt="Yuvarlak Akvaryum" />
      <h3>Yuvarlak Akvaryum</h3>
      <p>Modern ve estetik tasarım.</p>
      <div class="product-detail">
        <h4>Özellikler:</h4>
        <ul>
          <li>Malzeme: Cam</li>
          <li>Kapak: Yok</li>
          <li>Aydınlatma: Harici LED</li>
        </ul>
        <h4>Yaşam Koşulları:</h4>
        <ul>
          <li>Su Sıcaklığı: 22-26°C</li>
          <li>pH: 6.5-7.0</li>
          <li>Filtrasyon: Tavsiye Edilir</li>
        </ul>
        <h4>Akvaryum Boyutu:</h4>
        <p>Minimum hacim: 40 litre</p>
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2015/11/03/08/57/aquarium-1015297_1280.jpg" alt="Dekoratif Akvaryum" />
      <h3>Dekoratif Akvaryum</h3>
      <p>Mobilyaya entegre edilebilir şık model.</p>
      <div class="product-detail">
        <h4>Özellikler:</h4>
        <ul>
          <li>Malzeme: Temperli cam</li>
          <li>Kapak: Var</li>
          <li>Aydınlatma: LED renkli</li>
        </ul>
        <h4>Yaşam Koşulları:</h4>
        <ul>
          <li>Su Sıcaklığı: 20-25°C</li>
          <li>pH: 6.5-7.2</li>
          <li>Filtrasyon: Zorunlu</li>
        </ul>
        <h4>Akvaryum Boyutu:</h4>
        <p>Minimum hacim: 80 litre</p>
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

  </div>
</div>

<!-- Bitki İçeriği -->
<div id="bitki" class="tab-content">
  <div class="scroll-section">

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2016/11/18/15/44/water-plants-1837096_1280.jpg" alt="Amazon Kılıç Bitkisi" />
      <h3>Amazon Kılıç Bitkisi</h3>
      <p>Dayanıklı ve hızlı büyüyen bitki.</p>
      <div class="product-detail">
        <h4>Özellikler:</h4>
        <ul>
          <li>Tip: Canlı bitki</li>
          <li>Uzunluk: 30-50 cm</li>
          <li>Işık İhtiyacı: Orta</li>
        </ul>
        <h4>Yaşam Koşulları:</h4>
        <ul>
          <li>Su sıcaklığı: 22-28°C</li>
          <li>pH: 6.5-7.5</li>
          <li>CO2 takviyesi: Tavsiye edilir</li>
        </ul>
        <h4>Akvaryum Boyutu:</h4>
        <p>Minimum hacim: 50 litre</p>
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2016/04/06/20/44/aquatic-plant-1318573_1280.jpg" alt="Java Moss" />
      <h3>Java Moss</h3>
      <p>Kolay bakımlı, dekoratif yosun.</p>
      <div class="product-detail">
        <h4>Özellikler:</h4>
        <ul>
          <li>Tip: Moss</li>
          <li>Büyüme Hızı: Yavaş</li>
          <li>Işık İhtiyacı: Düşük</li>
        </ul>
        <h4>Yaşam Koşulları:</h4>
        <ul>
          <li>Su sıcaklığı: 20-26°C</li>
          <li>pH: 6.0-7.5</li>
          <li>CO2 takviyesi: Gerekli değil</li>
        </ul>
        <h4>Akvaryum Boyutu:</h4>
        <p>Minimum hacim: 30 litre</p>
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2019/02/04/10/45/aquarium-3978287_1280.jpg" alt="Anubias Nana" />
      <h3>Anubias Nana</h3>
      <p>Düşük ışıkta da yaşayabilen bitki.</p>
      <div class="product-detail">
        <h4>Özellikler:</h4>
        <ul>
          <li>Tip: Rhizome bitki</li>
          <li>Boy: 10-15 cm</li>
          <li>Işık İhtiyacı: Düşük-orta</li>
        </ul>
        <h4>Yaşam Koşulları:</h4>
        <ul>
          <li>Su sıcaklığı: 22-28°C</li>
          <li>pH: 6.0-7.8</li>
          <li>CO2 takviyesi: İsteğe bağlı</li>
        </ul>
        <h4>Akvaryum Boyutu:</h4>
        <p>Minimum hacim: 40 litre</p>
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

  </div>
</div>

<!-- Canlı İçeriği -->
<div id="canli" class="tab-content">
  <div class="scroll-section">

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2017/02/12/16/39/neon-tetra-2057999_1280.jpg" alt="Neon Tetra" />
      <h3>Neon Tetra</h3>
      <p>Canlı ve renkli küçük balık.</p>
      <div class="product-detail">
        <h4>Özellikler:</h4>
        <ul>
          <li>Boy: 3-4 cm</li>
          <li>Yaşam Süresi: 5 yıl</li>
          <li>Davranış: Sürü balığı</li>
        </ul>
        <h4>Yaşam Koşulları:</h4>
        <ul>
          <li>Su sıcaklığı: 20-26°C</li>
          <li>pH: 6.0-7.0</li>
          <li>Akvaryumda minimum 10 adet önerilir</li>
        </ul>
        <h4>Akvaryum Boyutu:</h4>
        <p>Minimum hacim: 40 litre</p>
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2018/05/31/21/16/goldfish-3441253_1280.jpg" alt="Japon Balığı" />
      <h3>Japon Balığı</h3>
      <p>Uzun ömürlü ve gösterişli balık.</p>
      <div class="product-detail">
        <h4>Özellikler:</h4>
        <ul>
          <li>Boy: 15-20 cm</li>
          <li>Yaşam Süresi: 10-15 yıl</li>
          <li>Davranış: Yavaş yüzücü</li>
        </ul>
        <h4>Yaşam Koşulları:</h4>
        <ul>
          <li>Su sıcaklığı: 18-22°C</li>
          <li>pH: 7.0-8.0</li>
          <li>Akvaryumda tek veya grup</li>
        </ul>
        <h4>Akvaryum Boyutu:</h4>
        <p>Minimum hacim: 80 litre</p>
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2014/11/21/17/36/guppy-540451_1280.jpg" alt="Guppy" />
      <h3>Guppy</h3>
      <p>Hızlı çoğalan küçük balık.</p>
      <div class="product-detail">
        <h4>Özellikler:</h4>
        <ul>
          <li>Boy: 4-6 cm</li>
          <li>Yaşam Süresi: 3-4 yıl</li>
          <li>Davranış: Canlı ve uyumlu</li>
        </ul>
        <h4>Yaşam Koşulları:</h4>
        <ul>
          <li>Su sıcaklığı: 22-28°C</li>
          <li>pH: 7.0-8.0</li>
          <li>Akvaryumda çok sayıda bakılır</li>
        </ul>
        <h4>Akvaryum Boyutu:</h4>
        <p>Minimum hacim: 40 litre</p>
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

  </div>
</div>

<button id="BilgiBtn">Bilgi</button>

<div id="infoModal">
  <h2>Cesur Akvaryum Hakkında</h2>
  <p>Cesur Akvaryum, akvaryum, canlı ve bitki alanlarında uzman bir satış platformudur. En kaliteli ürünleri sizlere sunar ve akvaryum hobinizi daha keyifli hale getirir.</p>
  <button onclick="closeModal()">Kapat</button>
</div>

<div class="contact-section">
  <h2>İletişim</h2>
  <p><strong>Adres:</strong> 123 Akvaryum Sokak, İstanbul</p>
  <p><strong>Telefon:</strong> +90 555 123 4567</p>
  <p><strong>Email:</strong> <a href="mailto:info@cesurakvaryum.com">info@cesurakvaryum.com</a></p>
</div>

<script>
  function openTab(tabId, element) {
    document.querySelectorAll('.tab-button').forEach(btn => btn.classList.remove('active'));
    element.classList.add('active');

    document.querySelectorAll('.tab-content').forEach(tc => {
      tc.classList.remove('active');
    });
    document.getElementById(tabId).classList.add('active');
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

  const infoBtn = document.getElementById('BilgiBtn');
  const infoModal = document.getElementById('infoModal');

  infoBtn.onclick = () => {
    infoModal.style.display = 'block';
  };

  function closeModal() {
    infoModal.style.display = 'none';
  }

  // Modal dışına tıklayınca kapatma
  window.onclick = function(event) {
    if (event.target == infoModal) {
      closeModal();
    }
  }
</script>

</body>
</html>
