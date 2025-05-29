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
    .tab-button.active,
    .tab-button[aria-selected="true"] {
      background-color: #00796b;
      color: white;
    }
    .tab-button:hover,
    .tab-button:focus {
      outline: none;
      opacity: 0.85;
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
      transition: background-color 0.3s;
    }
    .toggle-btn:hover,
    .toggle-btn:focus {
      background-color: #004d40;
      outline: none;
      opacity: 0.9;
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
      transition: opacity 0.3s;
    }
    #BilgiBtn:hover,
    #BilgiBtn:focus {
      opacity: 0.85;
      outline: none;
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
    #infoModal:focus {
      outline: none;
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
      transition: opacity 0.3s;
    }
    #infoModal button:hover,
    #infoModal button:focus {
      opacity: 0.85;
      outline: none;
    }

    /* Responsive */
    @media (max-width: 600px) {
      .product-card {
        min-width: 250px;
      }
      .scroll-section {
        padding: 20px 12px 30px;
        gap: 16px;
        margin: 0 10px 30px;
      }
    }
  </style>
</head>
<body>

<header>
  <img src="https://cdn-icons-png.flaticon.com/512/616/616408.png" alt="Logo" />
  <h1>Cesur Akvaryum</h1>
</header>

<div class="tabs" role="tablist" aria-label="Ürün Kategorileri">
  <button
    class="tab-button active"
    role="tab"
    aria-selected="true"
    id="tab-akvaryum"
    aria-controls="akvaryum"
    tabindex="0"
    onclick="openTab('akvaryum', this)">🐠 Akvaryum</button>
  <button
    class="tab-button"
    role="tab"
    aria-selected="false"
    id="tab-bitki"
    aria-controls="bitki"
    tabindex="-1"
    onclick="openTab('bitki', this)">🌿 Bitki</button>
  <button
    class="tab-button"
    role="tab"
    aria-selected="false"
    id="tab-canli"
    aria-controls="canli"
    tabindex="-1"
    onclick="openTab('canli', this)">🐟 Canlı</button>
</div>

<!-- Akvaryum İçeriği -->
<div
  id="akvaryum"
  class="tab-content active"
  role="tabpanel"
  aria-labelledby="tab-akvaryum"
  tabindex="0">
  <div class="scroll-section">

    <div class="product-card" tabindex="0">
      <img src="https://cdn.pixabay.com/photo/2016/11/29/12/54/fish-tank-1866863_1280.jpg" alt="Küçük Cam Akvaryum" />
      <h3>Küçük Cam Akvaryum</h3>
      <p>Kompakt tasarımıyla her alana uygun.</p>
      <div class="product-detail">
        Küçük boyutlu, minimal alanlarda kullanım için ideal cam akvaryum.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this, event)">Detayları Göster</button>
    </div>

    <div class="product-card" tabindex="0">
      <img src="https://cdn.pixabay.com/photo/2014/11/21/17/36/aquarium-540461_1280.jpg" alt="Büyük Cam Akvaryum" />
      <h3>Büyük Cam Akvaryum</h3>
      <p>Geniş hacimli gösterişli akvaryum.</p>
      <div class="product-detail">
        200 litrelik bu model, büyük balık grupları için uygundur.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this, event)">Detayları Göster</button>
    </div>

  </div>
</div>

<!-- Bitki İçeriği -->
<div
  id="bitki"
  class="tab-content"
  role="tabpanel"
  aria-labelledby="tab-bitki"
  tabindex="0">
  <div class="scroll-section">

    <div class="product-card" tabindex="0">
      <img src="https://cdn.pixabay.com/photo/2015/03/17/12/38/water-67516_1280.jpg" alt="Canlı Su Bitkisi" />
      <h3>Canlı Su Bitkisi</h3>
      <p>Doğal görünüm ve oksijen sağlar.</p>
      <div class="product-detail">
        Akvaryumunuzda doğal dengeyi sağlar ve estetik görünüm katar.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this, event)">Detayları Göster</button>
    </div>

    <div class="product-card" tabindex="0">
      <img src="https://cdn.pixabay.com/photo/2017/08/06/09/26/water-plants-2588387_1280.jpg" alt="Dekoratif Bitki" />
      <h3>Dekoratif Bitki</h3>
      <p>Renkli ve bakımı kolay.</p>
      <div class="product-detail">
        Canlı renkleriyle akvaryumunuza şıklık katar.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this, event)">Detayları Göster</button>
    </div>

  </div>
</div>

<!-- Canlı İçeriği -->
<div
  id="canli"
  class="tab-content"
  role="tabpanel"
  aria-labelledby="tab-canli"
  tabindex="0">
  <div class="scroll-section">

    <div class="product-card" tabindex="0">
      <img src="https://cdn.pixabay.com/photo/2017/03/13/11/26/fish-2136480_1280.jpg" alt="Beta Balığı" />
      <h3>Beta Balığı</h3>
      <p>Canlı renkleriyle popüler tür.</p>
      <div class="product-detail">
        Kolay bakım ve dayanıklı tür, küçük akvaryumlar için ideal.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this, event)">Detayları Göster</button>
    </div>

    <div class="product-card" tabindex="0">
      <img src="https://cdn.pixabay.com/photo/2015/10/23/13/10/fish-1002226_1280.jpg" alt="Guppy Balığı" />
      <h3>Guppy Balığı</h3>
      <p>Hızlı çoğalan sevimli balık.</p>
      <div class="product-detail">
        Çeşitli renk seçenekleri ve aktif yapısıyla akvaryumunuzu canlandırır.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this, event)">Detayları Göster</button>
    </div>

  </div>
</div>

<button id="BilgiBtn" aria-haspopup="dialog" aria-controls="infoModal">Bilgi</button>

<div
  id="infoModal"
  role="dialog"
  aria-modal="true"
  aria-labelledby="modalTitle"
  aria-describedby="modalDesc"
  tabindex="-1">
  <h2 id="modalTitle">Cesur Akvaryum Hakkında</h2>
  <p id="modalDesc">
    Cesur Akvaryum, akvaryum tutkunları için geniş ürün yelpazesi sunar. Canlılar,
    bitkiler ve akvaryumlar için kaliteli ürünler.
  </p>
  <button onclick="closeModal()">Kapat</button>
</div>

<script>
  function openTab(tabId, button) {
    // Tüm tab butonlarını ve içeriklerini temizle
    document.querySelectorAll('.tab-button').forEach(btn => {
      btn.classList.remove('active');
      btn.setAttribute('aria-selected', 'false');
      btn.setAttribute('tabindex', '-1');
    });
    document.querySelectorAll('.tab-content').forEach(tab => {
      tab.classList.remove('active');
      tab.setAttribute('tabindex', '-1');
    });

    // Seçilen tab aktif yap
    button.classList.add('active');
    button.setAttribute('aria-selected', 'true');
    button.setAttribute('tabindex', '0');
    button.focus();

    const tab = document.getElementById(tabId);
    tab.classList.add('active');
    tab.setAttribute('tabindex', '0');
  }

  function toggleDetail(button, event) {
    event.stopPropagation();
    const card = button.parentElement;
    const detail = card.querySelector('.product-detail');
    if (detail.classList.contains('active')) {
      detail.classList.remove('active');
      button.textContent = "Detayları Göster";
    } else {
      detail.classList.add('active');
      button.textContent = "Detayları Kapat";
    }
  }

  const infoBtn = document.getElementById('BilgiBtn');
  const modal = document.getElementById('infoModal');

  infoBtn.addEventListener('click', () => {
    modal.style.display = 'block';
    modal.focus();
  });

  function closeModal() {
    modal.style.display = 'none';
    infoBtn.focus();
  }

  // Modal dışına tıklayınca veya ESC ile kapatma
  window.addEventListener('click', (e) => {
    if (e.target === modal) {
      closeModal();
    }
  });

  window.addEventListener('keydown', (e) => {
    if (e.key === "Escape" && modal.style.display === 'block') {
      closeModal();
    }
  });

</script>

</body>
<section aria-label="İletişim Bilgileri" style="
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
">
  <h2 style="margin-bottom: 16px; font-weight: 900;">İletişim</h2>
  <p>Telefon: <a href="tel:+905013761533" style="color: #80cbc4; text-decoration: none;">0 501 376 15 33</a></p>
  <p>E-posta: <a href="mailto:info@cesurakvaryum.com" style="color: #80cbc4; text-decoration: none;">info@cesurakvaryum.com</a></p>
  <p>Adres: Aksaray / Merkez, Türkiye</p>
</section>
</html>
