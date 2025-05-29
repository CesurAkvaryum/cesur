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

<!-- Bitki İçeriği -->
<div id="bitki" class="tab-content">
  <div class="scroll-section">
    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2017/07/02/22/04/plant-2475494_1280.jpg" alt="Java Moss" />
      <h3>Java Moss</h3>
      <p>Kolay bakımlı su bitkisi.</p>
      <div class="product-detail">
        Havadar yapısıyla akvaryum dekorasyonunda tercih edilir.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2016/02/12/11/00/plant-1192544_1280.jpg" alt="Anubias" />
      <h3>Anubias</h3>
      <p>Dayanıklı ve dekoratif bitki.</p>
      <div class="product-detail">
        Düşük ışıkta da yaşayabilen yavaş büyüyen bitki türü.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2018/09/07/23/29/plant-3669950_1280.jpg" alt="Cryptocoryne" />
      <h3>Cryptocoryne</h3>
      <p>Gölge seven akvaryum bitkisi.</p>
      <div class="product-detail">
        Sakin sularda ve düşük ışıkta iyi gelişir.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>
  </div>
</div>

<!-- Canlı İçeriği -->
<div id="canli" class="tab-content">
  <div class="scroll-section">

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2016/03/27/19/48/fish-1285401_1280.jpg" alt="Neon Tetrafish" />
      <h3>Neon Tetrafish</h3>
      <p>Canlı renkleriyle popüler küçük balık.</p>
      <div class="product-detail">
        <strong>Tür:</strong> Paracheirodon innesi<br />
        <strong>Boy:</strong> 3-4 cm<br />
        <strong>Yaşam Süresi:</strong> 5 yıl<br />
        <strong>Beslenme:</strong> Omnivor, küçük canlı yem ve pul yem<br />
        <strong>Davranış:</strong> Barışçıl, sürü halinde yaşar<br /><br />
        <strong>Genel Canlı Özellikleri:</strong><br />
        Tüm canlılar hücrelerden oluşur, metabolizmaya sahiptir, büyür, çoğalır ve çevrelerine uyum sağlarlar. Neon Tetrafish, solungaçlarıyla solunum yapar ve sürü halinde yaşayarak sosyal davranışlar sergiler.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2018/01/30/18/57/fish-3120607_1280.jpg" alt="Guppy" />
      <h3>Guppy</h3>
      <p>Canlı renkleri ve hareketli yapısı.</p>
      <div class="product-detail">
        <strong>Tür:</strong> Poecilia reticulata<br />
        <strong>Boy:</strong> 4-6 cm<br />
        <strong>Yaşam Süresi:</strong> 3-5 yıl<br />
        <strong>Beslenme:</strong> Omnivor, pul yem ve küçük canlı yem<br />
        <strong>Davranış:</strong> Barışçıl, sürü halinde yaşar<br /><br />
        <strong>Genel Canlı Özellikleri:</strong><br />
        Canlılar hücrelerden oluşur, metabolizma yapar ve çevresine uyum sağlar. Guppy, hızlı çoğalan türlerdendir ve renkli yapısıyla akvaryumlarda popülerdir.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2016/10/04/22/39/fish-1714686_1280.jpg" alt="Betta" />
      <h3>Betta</h3>
      <p>Güçlü ve gösterişli yüzgeçlere sahip balık.</p>
      <div class="product-detail">
        <strong>Tür:</strong> Betta splendens<br />
        <strong>Boy:</strong> 6-7 cm<br />
        <strong>Yaşam Süresi:</strong> 3-4 yıl<br />
        <strong>Beslenme:</strong> Etçil, canlı yem tercih eder<br />
        <strong>Davranış:</strong> Tek başına veya küçük gruplar halinde yaşar<br /><br />
        <strong>Genel Canlı Özellikleri:</strong><br />
        Canlılar solunum, beslenme, üreme gibi temel fonksiyonları yerine getirir. Betta, agresif olabilir, bu yüzden akvaryumda dikkatli beslenmelidir.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

    <div class="product-card">
      <img src="https://cdn.pixabay.com/photo/2016/04/28/23/23/fish-1352561_1280.jpg" alt="Moli Balığı" />
      <h3>Moli Balığı</h3>
      <p>Dayanıklı ve uyumlu tatlı su balığı.</p>
      <div class="product-detail">
        <strong>Tür:</strong> Poecilia sphenops<br />
        <strong>Boy:</strong> 6-7 cm<br />
        <strong>Yaşam Süresi:</strong> 3-5 yıl<br />
        <strong>Beslenme:</strong> Omnivor, çeşitli yemler<br />
        <strong>Davranış:</strong> Barışçıl, sosyal balık<br /><br />
        <strong>Genel Canlı Özellikleri:</strong><br />
        Canlılar metabolizma ile enerji üretir ve çevresel değişimlere adapte olur. Moli, akvaryumlarda kolay bakımı ile tercih edilir.
      </div>
      <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
    </div>

  </div>
</div>

<button id="BilgiBtn" onclick="showInfo()">Bilgi</button>

<!-- Modal -->
<div id="infoModal">
  <h2>Genel Canlı Özellikleri</h2>
  <p>
    Canlılar; hücrelerden oluşur, metabolizma ile enerji üretir, büyür, çevresine uyum sağlar ve çoğalır. Solunum, beslenme, hareket ve üreme gibi temel yaşamsal faaliyetleri gerçekleştirirler. Suda yaşayan canlılar genellikle solungaçlarıyla nefes alır, beslenme şekilleri türlere göre değişir ve ekosistemde önemli roller üstlenirler.
  </p>
  <button onclick="closeInfo()">Kapat</button>
</div>

<script>
  function openTab(tabName, el) {
    document.querySelectorAll('.tab-button').forEach(btn => btn.classList.remove('active'));
    el.classList.add('active');

    document.querySelectorAll('.tab-content').forEach(tab => {
      tab.classList.remove('active');
    });
    document.getElementById(tabName).classList.add('active');
  }

  function toggleDetail(btn) {
    const detail = btn.previousElementSibling;
    detail.classList.toggle('active');
    btn.textContent = detail.classList.contains('active') ? 'Detayları Gizle' : 'Detayları Göster';
  }

  // Modal açma
  function showInfo() {
    document.getElementById('infoModal').style.display = 'block';
  }

  // Modal kapama
  function closeInfo() {
    document.getElementById('infoModal').style.display = 'none';
  }
</script>

</body>
</html>
