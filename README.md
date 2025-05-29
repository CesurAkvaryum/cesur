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
      <p>Temiz çizgilerle modern akvaryum keyfi.</p>
      <div class="product-detail">
        Kare yapılı küp akvaryumlar küçük alanlar için tercih edilir.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

  </div>
</div>

<!-- Bitki İçeriği -->
<div id="bitki" class="tab-content">
  <div class="scroll-section">

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2017/06/08/17/42/aquarium-2380972_1280.jpg" alt="Java Fern" />
      <h3>Java Fern (Microsorum pteropus)</h3>
      <p>Az ışıkta dayanıklı, bakımı kolay.</p>
      <div class="product-detail">
        <strong>Tür:</strong> Eğrelti otu ailesinden <br />
        <strong>Yerleşim:</strong> Kaya veya kök üzerine bağlanmalı <br />
        <strong>Bakım:</strong> Düşük ila orta ışık, az besin gerektirir <br />
        <strong>Boy:</strong> 12-15 cm <br />
        Java Fern, az ışıklı akvaryumlarda başarılı olur. Yapraklarını çürüten balıklara karşı dayanıklıdır.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2016/11/19/12/58/plant-1836993_1280.jpg" alt="Anubias" />
      <h3>Anubias (Anubias barteri)</h3>
      <p>Yavaş büyüyen, dayanıklı.</p>
      <div class="product-detail">
        <strong>Tür:</strong> Araceae ailesinden <br />
        <strong>Yerleşim:</strong> Kök veya kaya üstüne bağlanmalı <br />
        <strong>Bakım:</strong> Düşük ışık, yavaş büyüme <br />
        <strong>Boy:</strong> 10-20 cm <br />
        Anubias, dayanıklı yapısıyla akvaryumlarda popülerdir. Balıkların yaprakları yemesinden az etkilenir.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2016/07/14/15/05/aquarium-1512306_1280.jpg" alt="Amazon Sword" />
      <h3>Amazon Sword (Echinodorus amazonicus)</h3>
      <p>Geniş yapraklı, orta ışıkta iyi gelişir.</p>
      <div class="product-detail">
        <strong>Tür:</strong> Alismataceae ailesinden <br />
        <strong>Yerleşim:</strong> Substrat içinde köklenmeli <br />
        <strong>Bakım:</strong> Orta ışık ve besinler gerektirir <br />
        <strong>Boy:</strong> 20-50 cm <br />
        Amazon Sword, akvaryum tabanına zenginlik katar ve balıklar için iyi saklanma alanı sağlar.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2015/05/25/17/02/plant-783189_1280.jpg" alt="Cryptocoryne" />
      <h3>Cryptocoryne</h3>
      <p>Farklı renk ve yaprak formları.</p>
      <div class="product-detail">
        <strong>Tür:</strong> Araceae ailesinden <br />
        <strong>Yerleşim:</strong> Substrat içinde köklenmeli <br />
        <strong>Bakım:</strong> Orta ışık, düzenli besin <br />
        <strong>Boy:</strong> 15-30 cm <br />
        Cryptocoryne, değişik renk tonları ile akvaryuma estetik katar. Adaptasyon süreci bazen yavaştır.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2014/11/21/17/36/aquarium-540461_1280.jpg" alt="Vallisneria" />
      <h3>Vallisneria</h3>
      <p>Uzun yapraklarıyla arka plan bitkisi.</p>
      <div class="product-detail">
        <strong>Tür:</strong> Hydrocharitaceae ailesinden <br />
        <strong>Yerleşim:</strong> Substrat içinde köklenmeli <br />
        <strong>Bakım:</strong> Orta ila yüksek ışık <br />
        <strong>Boy:</strong> 30-60 cm <br />
        Vallisneria, hızlı büyüyen ve akvaryumun arka planında güzel görsel oluşturur.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

  </div>
</div>

<!-- Canlı İçeriği -->
<div id="canli" class="tab-content">
  <div class="scroll-section">

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2017/06/20/18/08/fish-2422507_1280.jpg" alt="Neon Tetrafish" />
      <h3>Neon Tetrafish</h3>
      <p>Canlı renkleriyle popüler küçük balık.</p>
      <div class="product-detail">
        Neon Tetrafish, barışçıl sürü balığıdır ve düşük bakım gerektirir.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2016/03/27/20/51/fish-1283654_1280.jpg" alt="Betta Balığı" />
      <h3>Betta Balığı</h3>
      <p>Tek başına yaşayan, renkli yüzgeçli.</p>
      <div class="product-detail">
        Betta, agresif olabilir; tek başına beslenmelidir.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2014/11/21/17/36/aquarium-540461_1280.jpg" alt="Guppy" />
      <h3>Guppy</h3>
      <p>Kolay üreyen, renkli küçük balık.</p>
      <div class="product-detail">
        Guppy, hızlı çoğalan ve canlı renkli akvaryum balığıdır.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2015/12/09/20/02/fish-1082164_1280.jpg" alt="Corydoras" />
      <h3>Corydoras</h3>
      <p>Dip temizleyici ve barışçıl.</p>
      <div class="product-detail">
        Corydoras, akvaryum tabanını temizler ve sosyal balıktır.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

  </div>
</div>

<button id="BilgiBtn">Bilgi</button>

<!-- Modal -->
<div id="infoModal">
  <h2>Cesur Akvaryum Bilgileri</h2>
  <p>
    Bu web sitesi, akvaryum, bitki ve canlı çeşitleri hakkında detaylı bilgiler sunar. Her sekmede ürün kartları bulunmaktadır. Kartların altında "Detayları Göster" butonuna tıklayarak ürün hakkında daha fazla bilgi alabilirsiniz.
  </p>
  <button onclick="closeModal()">Kapat</button>
</div>

<script>
  function openTab(tabId, el) {
    const tabs = document.querySelectorAll('.tab-content');
    const buttons = document.querySelectorAll('.tab-button');
    tabs.forEach(tab => tab.classList.remove('active'));
    buttons.forEach(btn => btn.classList.remove('active'));
    document.getElementById(tabId).classList.add('active');
    el.classList.add('active');
  }

  function toggleDetail(button) {
    const detail = button.previousElementSibling;
    if(detail.classList.contains('active')) {
      detail.classList.remove('active');
      button.textContent = "Detayları Göster";
    } else {
      detail.classList.add('active');
      button.textContent = "Detayları Gizle";
    }
  }

  const bilgiBtn = document.getElementById('BilgiBtn');
  const infoModal = document.getElementById('infoModal');

  bilgiBtn.addEventListener('click', () => {
    infoModal.style.display = 'block';
  });

  function closeModal() {
    infoModal.style.display = 'none';
  }

  window.onclick = function(event) {
    if(event.target == infoModal) {
      closeModal();
    }
  };
</script>

</body>
</html>
