<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8" />
<title>Bitkiler</title>
<style>
  body { font-family: Arial, sans-serif; background: #eef7f7; padding: 20px; }
  .product-card {
    background: white; border-radius: 15px; padding: 15px;
    margin-bottom: 20px; box-shadow: 0 2px 8px rgba(0,0,0,0.1);
    max-width: 400px;
  }
  .product-card img {
    width: 100%; border-radius: 12px;
  }
  .product-detail {
    display: none; margin-top: 10px; padding: 10px;
    background: #dff0f0; border-radius: 10px; color: #005555;
  }
  .toggle-btn {
    margin-top: 10px; padding: 8px 15px;
    background: #008080; color: white; border: none;
    border-radius: 25px; cursor: pointer;
  }
</style>
</head>
<body>

<div class="product-card">
  <img src="https://cdn.pixabay.com/photo/2017/07/02/22/04/plant-2475494_1280.jpg" alt="Java Moss" />
  <h2>Java Moss</h2>
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
  <h2>Anubias</h2>
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

<script>
  function toggleDetail(button) {
    const detail = button.previousElementSibling;
    if (detail.style.display === "block") {
      detail.style.display = "none";
      button.textContent = "Detayları Göster";
    } else {
      detail.style.display = "block";
      button.textContent = "Detayları Gizle";
    }
  }
</script>

</body>
</html>
