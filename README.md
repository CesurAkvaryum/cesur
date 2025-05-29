 <style>
    /* ... diğer stiller aynı kalacak ... */

    /* Orta bölüm için daha şık görünüm */
    .scroll-section {
      display: flex;
      overflow-x: auto;
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
    /* Buton tarzı detay gösterme/kapatma */
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
  </style>

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
    <!-- Diğer kartlar aynı şekilde -->
  </div>

  <script>
    function toggleDetail(btn) {
      const card = btn.closest('.product-card');
      const detail = card.querySelector('.product-detail');
      if(detail.classList.contains('active')) {
        detail.classList.remove('active');
        btn.textContent = 'Detayları Göster';
      } else {
        // Aynı anda sadece bir detay açılması için
        document.querySelectorAll('.product-detail.active').forEach(d => {
          d.classList.remove('active');
          d.parentElement.querySelector('.toggle-btn').textContent = 'Detayları Göster';
        });
        detail.classList.add('active');
        btn.textContent = 'Kapat';
      }
    }
  </script>
