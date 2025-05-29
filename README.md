<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Bitkiler Tab Örneği</title>
<style>
  body { font-family: Arial, sans-serif; background:#f0f8ff; margin:0; }
  .tabs { display:flex; justify-content:center; margin:20px; gap:20px; }
  .tab-button {
    padding:10px 20px; border:none; border-radius:30px;
    background:#b2ebf2; color:#006064; cursor:pointer; font-weight:bold;
  }
  .tab-button.active { background:#00796b; color:#fff; }
  .tab-content { display:none; padding:20px; }
  .tab-content.active { display:block; }
  .product-card {
    background:#fff; border-radius:15px; padding:15px; margin-bottom:20px;
    box-shadow:0 4px 8px rgba(0,0,0,0.1);
  }
  .product-card img {
    width:100%; border-radius:12px;
  }
  .product-detail {
    display:none; background:#b2dfdb; margin-top:10px; padding:10px;
    border-radius:10px; color:#004d40;
  }
  .toggle-btn {
    margin-top:10px; padding:8px 15px;
    background:#00796b; color:#fff; border:none; border-radius:30px;
    cursor:pointer;
  }
</style>
</head>
<body>

<div class="tabs">
  <button class="tab-button active" onclick="openTab('bitki', this)">Bitkiler</button>
  <button class="tab-button" onclick="openTab('canli', this)">Canlılar</button>
</div>

<div id="bitki" class="tab-content active">
  <div class="product-card">
    <img src="https://cdn.pixabay.com/photo/2017/07/02/22/04/plant-2475494_1280.jpg" alt="Java Moss" />
    <h3>Java Moss</h3>
    <p>Kolay bakımlı su bitkisi.</p>
    <div class="product-detail">
      <strong>Tür:</strong> Taxiphyllum barbieri<br />
      <strong>Işık:</strong> Düşük ila orta<br />
      <strong>CO2:</strong> Gerekmez<br />
      <strong>Bakım:</strong> Kolay<br />
      Java Moss, akvaryumda dekoratif ve bakımı kolay bir bitkidir. Balıklar için saklanma alanı sağlar.
    </div>
    <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
  </div>

  <div class="product-card">
    <img src="https://cdn.pixabay.com/photo/2017/08/28/20/36/aquatic-plants-2696117_1280.jpg" alt="Anubias" />
    <h3>Anubias</h3>
    <p>Düşük ışık bitkisi.</p>
    <div class="product-detail">
      <strong>Tür:</strong> Anubias barteri<br />
      <strong>Işık:</strong> Düşük<br />
      <strong>CO2:</strong> Gerekmez<br />
      <strong>Bakım:</strong> Kolay<br />
      Anubias, gölgeyi seven dayanıklı bir bitkidir. Genellikle taş veya kök üzerine bağlanarak kullanılır.
    </div>
    <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
  </div>
</div>

<div id="canli" class="tab-content">
  <div class="product-card">
    <img src="https://cdn.pixabay.com/photo/2016/03/27/20/22/fish-1284761_1280.jpg" alt="Betta Balığı" />
    <h3>Betta Balığı</h3>
    <p>Renkli ve agresif tür.</p>
    <div class="product-detail">
      Betta balıkları tek başına tutulmalıdır, renkleri oldukça canlıdır.
    </div>
    <button class="toggle-btn" onclick="toggleDetail(this)">Detayları Göster</button>
  </div>
</div>

<script>
  function openTab(tabId, button) {
    document.querySelectorAll('.tab-content').forEach(tc => {
      tc.classList.remove('active');
    });
    document.querySelectorAll('.tab-button').forEach(btn => {
      btn.classList.remove('active');
    });
    document.getElementById(tabId).classList.add('active');
    button.classList.add('active');
  }
  function toggleDetail(btn) {
    const detail = btn.previousElementSibling;
    if (detail.style.display === 'block') {
      detail.style.display = 'none';
      btn.textContent = 'Detayları Göster';
    } else {
      detail.style.display = 'block';
      btn.textContent = 'Detayları Gizle';
    }
  }
</script>

</body>
</html>
