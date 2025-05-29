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
    #bittiBtn {
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
  <img src="https://cdn-icons-png.flaticon.com/512/616/616408.png" alt="Logo">
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
      <img src="https://cdn.pixabay.com/photo/2017/03/27/14/01/plant-2178750_1280.jpg" alt="Bitki" />
      <h3>Akvaryum Bitkisi</h3>
      <p>Canlı ve sağlıklı akvaryum bitkileri.</p>
      <div class="product-detail">
        Doğal ortamı canlandıran bitkilerle su kalitesi artar, estetik zenginleşir.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>
  </div>
</div>

<!-- Canlı İçeriği -->
<div id="canli" class="tab-content">
  <div class="scroll-section">
    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2021/08/05/11/20/fish-6522766_1280.jpg" alt="Neon Tetra" />
      <h3>Neon Tetra</h3>
      <p>Renkli ve uyumlu sürü balıkları.</p>
      <div class="product-detail">
        Neon tetra, barışçıl doğası ve canlı renkleriyle en çok tercih edilen balıklardandır.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>
    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2022/08/30/17/36/betta-7421979_1280.jpg" alt="Beta Balığı" />
      <h3>Beta Balığı</h3>
      <p>Tek başına bakılabilen görkemli balık.</p>
      <div class="product-detail">
        Renkli yüzgeçleriyle dikkat çeken beta balığı, agresif yapısıyla bilinir ve yalnız bakılması önerilir.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>
    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2021/02/28/17/04/fish-6059249_1280.jpg" alt="Lepistes" />
      <h3>Lepistes</h3>
      <p>Kolay bakımı ile sevilen balık.</p>
      <div class="product-detail">
        Lepistesler dayanıklı ve hızlı çoğalan balıklardır. 22-28°C arasında iyi yaşar.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>
    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2017/12/11/14/28/pleco-3019951_1280.jpg" alt="Çöpçü Balığı" />
      <h3>Çöpçü Balığı</h3>
      <p>Dip temizleyici ve uyumlu canlı.</p>
      <div class="product-detail">
        Çöpçü balıkları tankın dip kısmını temizler, 23-28°C sıcaklık arası tercih eder.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>
    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2014/06/11/18/38/apple-snail-365696_1280.jpg" alt="Elma Salyangozu" />
      <h3>Elma Salyangozu</h3>
      <p>Yosunlarla beslenen temizlikçi.</p>
      <div class="product-detail">
        Elma salyangozları, tankın yosunlarını temizleyerek doğal denge sağlar.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>
  </div>
</div>

<!-- Bitti Butonu -->
<button id="bittiBtn">Bitti</button>

<!-- Bilgi Modal -->
<div id="infoModal">
  <h2>Bilgi</h2>
  <div id="infoContent"></div>
  <button onclick="closeModal()">Kapat</button>
</div>

<script>
  // Tablar arası geçiş
  function openTab(tabId, btn) {
    document.querySelectorAll('.tab-content').forEach(tab => {
      tab.classList.remove('active');
    });
    document.querySelectorAll('.tab-button').forEach(button => {
      button.classList.remove('active');
    });
    document.getElementById(tabId).classList.add('active');
    btn.classList.add('active');
  }

  // Detay göster/gizle butonu
  function toggleDetail(button) {
    const detail = button.previousElementSibling;
    const isActive = detail.classList.contains('active');
    if (isActive) {
      detail.classList.remove('active');
      button.textContent = 'Detayları Göster';
    } else {
      detail.classList.add('active');
      button.textContent = 'Detayları Gizle';
    }
  }

  // Bitti butonu işlevi
  document.getElementById('bittiBtn').addEventListener('click', function() {
    const activeTab = document.querySelector('.tab-content.active');
    if (!activeTab) return;

    const tabId = activeTab.id;
    let bilgi = '';

    if(tabId === 'akvaryum') {
      bilgi = `
        <strong>Akvaryum Çeşitleri ve Yaşam Koşulları:</strong><br><br>
        <ul>
          <li><strong>Küçük Cam Akvaryum:</strong> Küçük hacimlerde, küçük balıklar için uygundur. Sık temizlik gerekir.</li>
          <li><strong>Büyük Cam Akvaryum:</strong> Geniş hacim, büyük balıklar ve bitkiler için ideal. Filtrasyon önemli.</li>
          <li><strong>Yuvarlak Akvaryum:</strong> Dekoratif, küçük balıklar için uygun. Yüzgeçleri zarar görebilir.</li>
          <li><strong>Dekoratif Akvaryum:</strong> Mobilyaya entegre, küçük balıklar için uygundur. Su kalitesi takip edilmeli.</li>
          <li><strong>Küp Akvaryum:</strong> Kare şekilli, küçük ila orta balıklar için ideal. Bitki çeşitleriyle desteklenmeli.</li>
        </ul>
      `;
    } else if(tabId === 'bitki') {
      bilgi = `
        <strong>Akvaryum Bitkileri ve Yaşam Koşulları:</strong><br><br>
        <ul>
          <li><strong>Akvaryum Bitkisi:</strong> Doğal ortam sağlar. Işık, CO₂ ve uygun sıcaklık gerekir.</li>
          <li><em>Genel Koşullar:</em> 22-28°C arası sıcaklık, yeterli aydınlatma ve düzenli gübreleme bitkiler için önemlidir.</li>
        </ul>
      `;
    } else if(tabId === 'canli') {
      bilgi = `
        <strong>Canlılar ve Yaşam Koşulları:</strong><br><br>
        <ul>
          <li><strong>Neon Tetra:</strong> Sürüler halinde barışçıl, 20-26°C sıcaklık ve yumuşak su sever.</li>
          <li><strong>Beta Balığı:</strong> Tek başına bakılmalı, 24-30°C sıcaklık ve temiz su gerekir.</li>
          <li><strong>Lepistes:</strong> Kolay bakılır, 22-28°C sıcaklık ve dengeli beslenme ister.</li>
          <li><strong>Çöpçü Balığı:</strong> Dip temizleyici, 23-28°C arası sıcaklıkta aktif olur.</li>
          <li><strong>Elma Salyangozu:</strong> Yosunlarla beslenir, su kalitesi yüksek olmalı.</li>
        </ul>
      `;
    } else {
      bilgi = 'Aktif sekme bulunamadı veya bilgi yok.';
    }

    document.getElementById('infoContent').innerHTML = bilgi;
    document.getElementById('infoModal').style.display = 'block';
  });

  // Modal kapatma
  function closeModal() {
    document.getElementById('infoModal').style.display = 'none';
  }
</script>

</body>
</html>
