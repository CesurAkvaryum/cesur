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
        Küçük boyutlu, minimal alanlarda kullanım için ideal cam akvaryum.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2014/11/21/17/36/aquarium-540461_1280.jpg" alt="Büyük Cam Akvaryum" />
      <h3>Büyük Cam Akvaryum</h3>
      <p>Geniş hacimli gösterişli akvaryum.</p>
      <div class="product-detail">
        200 litrelik bu model, büyük balık grupları için uygundur.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2016/01/05/13/58/aquarium-1129108_1280.jpg" alt="Yuvarlak Akvaryum" />
      <h3>Yuvarlak Akvaryum</h3>
      <p>Modern ve estetik tasarım.</p>
      <div class="product-detail">
        Masa üstü veya dekoratif alanlar için ideal yuvarlak cam akvaryum.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2015/11/03/08/57/aquarium-1015297_1280.jpg" alt="Dekoratif Akvaryum" />
      <h3>Dekoratif Akvaryum</h3>
      <p>Mobilyaya entegre edilebilir şık model.</p>
      <div class="product-detail">
        Şık bir sehpa veya masa içine entegre edilebilir akvaryum modelidir.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2016/11/29/07/16/aquarium-1865159_1280.jpg" alt="Küp Akvaryum" />
      <h3>Küp Akvaryum</h3>
      <p>Kompakt, kolay yerleştirilebilir.</p>
      <div class="product-detail">
        Minimal tasarımı ile küçük alanlara uygun küp şeklinde akvaryum.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

  </div>
</div>

<!-- Bitki İçeriği (Birleştirilen Detaylı Bitkiler) -->
<div id="bitki" class="tab-content">
  <div class="scroll-section">

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2017/07/02/22/04/plant-2475494_1280.jpg" alt="Java Moss" />
      <h3>Java Moss</h3>
      <p>Kolay bakımlı su bitkisi.</p>
      <div class="product-detail" style="display:none;">
        <strong>Tür:</strong> Taxiphyllum barbieri<br />
        <strong>Işık:</strong> Düşük ila orta<br />
        <strong>CO2:</strong> Gerekmez<br />
        <strong>Bakım:</strong> Kolay<br />
        <strong>Açıklama:</strong> Java Moss, akvaryumda dekoratif ve bakımı kolay bir bitkidir. Balıklar için saklanma alanı sağlar.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2017/08/28/20/36/aquatic-plants-2696117_1280.jpg" alt="Anubias" />
      <h3>Anubias</h3>
      <p>Düşük ışık bitkisi.</p>
      <div class="product-detail" style="display:none;">
        <strong>Tür:</strong> Anubias barteri<br />
        <strong>Işık:</strong> Düşük<br />
        <strong>CO2:</strong> Gerekmez<br />
        <strong>Bakım:</strong> Kolay<br />
        <strong>Açıklama:</strong> Anubias, gölgeyi seven dayanıklı bir bitkidir. Genellikle taş veya kök üzerine bağlanarak kullanılır.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2014/04/05/11/39/aquarium-316146_1280.jpg" alt="Amazon Sword" />
      <h3>Amazon Sword</h3>
      <p>Büyük yapraklı bitki.</p>
      <div class="product-detail" style="display:none;">
        <strong>Tür:</strong> Echinodorus amazonicus<br />
        <strong>Işık:</strong> Orta<br />
        <strong>CO2:</strong> Orta seviyede faydalı<br />
        <strong>Bakım:</strong> Orta<br />
        <strong>Açıklama:</strong> Amazon Sword, akvaryuma doğal bir görünüm katar ve balıklar için gizlenme alanı sağlar.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2016/07/22/18/20/aquatic-plants-1533160_1280.jpg" alt="Cryptocoryne" />
      <h3>Cryptocoryne</h3>
      <p>Yavaş büyüyen bitki.</p>
      <div class="product-detail" style="display:none;">
        <strong>Tür:</strong> Cryptocoryne wendtii<br />
        <strong>Işık:</strong> Düşük ila orta<br />
        <strong>CO2:</strong> Gerekmez<br />
        <strong>Bakım:</strong> Kolay<br />
        <strong>Açıklama:</strong> Cryptocoryne, dayanıklı ve az bakım gerektiren bir bitkidir. Farklı renk varyasyonları mevcuttur.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2017/06/14/23/57/aquarium-2401186_1280.jpg" alt="Vallisneria" />
      <h3>Vallisneria</h3>
      <p>Uzun yapraklı su bitkisi.</p>
      <div class="product-detail" style="display:none;">
        <strong>Tür:</strong> Vallisneria spiralis<br />
        <strong>Işık:</strong> Orta<br />
        <strong>CO2:</strong> Gerekmez<br />
        <strong>Bakım:</strong> Kolay<br />
        <strong>Açıklama:</strong> Vallisneria, hızlı büyüyen ve akvaryuma doğal bir görünüm veren uzun yapraklı bir bitkidir.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

  </div>
</div>

<!-- Canlı İçeriği -->
<div id="canli" class="tab-content">
  <div class="scroll-section">

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2016/03/27/20/22/fish-1284761_1280.jpg" alt="Betta Balığı" />
      <h3>Betta Balığı</h3>
      <p>Renkli ve agresif tür.</p>
      <div class="product-detail">
        Betta balıkları tek başına tutulmalıdır, renkleri oldukça canlıdır.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2014/07/10/17/07/fish-389907_1280.jpg" alt="Neon Tetra" />
      <h3>Neon Tetra</h3>
      <p>Küçük ve sosyal balık.</p>
      <div class="product-detail">
        Neon Tetra, sürü halinde yaşayan ve parlak renkleri olan küçük balıklardır.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2017/06/01/20/42/aquarium-2368376_1280.jpg" alt="Guppy" />
      <h3>Guppy</h3>
      <p>Çoğaltması kolay balık.</p>
      <div class="product-detail">
        Guppyler, renkli ve kolay bakımlı balıklardır. Hızla çoğalırlar.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

  </div>
</div>

<!-- Bilgi Butonu -->
<button id="BilgiBtn">Bilgi</button>

<!-- Modal -->
<div id="infoModal" role="dialog" aria-modal="true" aria-labelledby="modalTitle" aria-describedby="modalDesc">
  <h2 id="modalTitle">Akvaryum Hakkında Bilgi</h2>
  <p id="modalDesc">
    Cesur Akvaryum, geniş ürün yelpazesi ile akvaryum severlere hizmet vermektedir. Akvaryumlar, canlılar ve bitkiler konusunda uzman çözümler sunuyoruz.
  </p>
  <button id="closeModalBtn">Kapat</button>
</div>

<script>
  // Tab açma fonksiyonu
  function openTab(tabId, button) {
    // Tüm tab-contentleri gizle
    document.querySelectorAll('.tab-content').forEach(tc => {
      tc.classList.remove('active');
    });
    // Tüm tab butonlarından active kaldır
    document.querySelectorAll('.tab-button').forEach(btn => {
      btn.classList.remove('active');
    });
    // Seçili tab-content göster
    document.getElementById(tabId).classList.add('active');
    // Butona active ekle
    button.classList.add('active');
  }

  // Detay açma/kapatma fonksiyonu
  function toggleDetail(button) {
    const card = button.parentElement;
    const detail = card.querySelector('.product-detail');
    if (detail.classList.contains('active')) {
      detail.classList.remove('active');
      button.textContent = 'Detayları Göster';
    } else {
      detail.classList.add('active');
      button.textContent = 'Detayları Gizle';
    }
  }

  // Bilgi Modal açma/kapatma
  const infoBtn = document.getElementById('BilgiBtn');
  const modal = document.getElementById('infoModal');
  const closeModalBtn = document.getElementById('closeModalBtn');

  infoBtn.addEventListener('click', () => {
    modal.style.display = 'block';
  });
  closeModalBtn.addEventListener('click', () => {
    modal.style.display = 'none';
  });

  // Modal dışına tıklayınca kapatma
  window.addEventListener('click', (event) => {
    if(event.target === modal) {
      modal.style.display = 'none';
    }
  });
</script>

</body>
</html>
