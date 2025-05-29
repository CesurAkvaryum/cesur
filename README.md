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
    header img.logo {
      height: 50px;
      width: 50px;
    }
    header h1 {
      margin: 0;
      font-weight: 900;
      font-size: 1.8rem;
    }
    header p {
      margin-left: auto;
      font-size: 1rem;
      font-weight: 600;
      color: #b2dfdb;
    }
    h2 {
      text-align: center;
      margin-top: 40px;
      color: #00695c;
      font-weight: 700;
    }
    .products-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit,minmax(280px,1fr));
      gap: 30px;
      padding: 30px 20px;
      max-width: 1200px;
      margin: 0 auto;
    }
    .product-card {
      background: white;
      border-radius: 16px;
      box-shadow: 0 10px 25px rgba(0,0,0,0.1);
      padding: 20px;
      text-align: center;
      cursor: pointer;
      transition: transform 0.3s ease, box-shadow 0.3s ease;
    }
    .product-card:hover {
      transform: translateY(-10px);
      box-shadow: 0 15px 35px rgba(0,0,0,0.2);
      z-index: 10;
    }
    .product-card img {
      max-width: 100%;
      border-radius: 12px;
      height: 180px;
      object-fit: cover;
      margin-bottom: 15px;
    }
    .product-card h3 {
      margin: 0 0 10px;
      color: #00796b;
      font-weight: 800;
      font-size: 1.25rem;
    }
    .product-card p {
      font-size: 14px;
      color: #444;
      margin-bottom: 12px;
    }
    footer {
      background-color: #eeeeee;
      text-align: center;
      padding: 20px;
      font-size: 14px;
      color: #666;
      margin-top: 60px;
    }
  </style>
</head>
<body>
  <header>
    <img class="logo" src="{{ 'logo.png' | asset_url }}" alt="Cesur Akvaryum Logo" />
    <h1>Cesur Akvaryum</h1>
    <p>Doğal ve Sağlıklı Akvaryumlar İçin Her Şey</p>
  </header>

  <h2>🐠 Ürünlerimiz</h2>
  <div class="products-grid">
    {% for product in collections.all.products %}
      <a href="{{ product.url }}" class="product-card">
        <img src="{{ product.featured_image | img_url: 'medium' }}" alt="{{ product.title }}" />
        <h3>{{ product.title }}</h3>
        <p>{{ product.description | strip_html | truncate: 80 }}</p>
      </a>
    {% endfor %}
  </div>

  <footer>
    &copy; {{ 'now' | date: '%Y' }} Cesur Akvaryum. Tüm hakları saklıdır.
  </footer>
</body>
</html>
<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>{{ product.title }} - Cesur Akvaryum</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0; padding: 20px;
      background-color: #f0f8ff;
      color: #004d40;
    }
    header {
      background-color: #00838f;
      color: white;
      padding: 20px 30px;
      display: flex;
      align-items: center;
      gap: 15px;
    }
    header img.logo {
      height: 50px;
      width: 50px;
    }
    header h1 {
      margin: 0;
      font-weight: 900;
      font-size: 1.8rem;
    }
    main {
      max-width: 900px;
      margin: 40px auto;
      background: white;
      border-radius: 20px;
      padding: 30px;
      box-shadow: 0 12px 30px rgba(0,0,0,0.1);
    }
    img.product-image {
      max-width: 100%;
      border-radius: 18px;
      margin-bottom: 30px;
    }
    h2 {
      margin-top: 0;
      font-weight: 800;
      font-size: 2rem;
      color: #00796b;
    }
    p.description {
      font-size: 16px;
      line-height: 1.5;
      color: #444;
      margin-bottom: 20px;
    }
    .price {
      font-size: 24px;
      font-weight: 900;
      color: #004d40;
      margin-bottom: 30px;
    }
    a.back-link {
      display: inline-block;
      margin-top: 20px;
      color: #00796b;
      text-decoration: none;
      font-weight: 700;
      border: 2px solid #00796b;
      padding: 10px 20px;
      border-radius: 30px;
      transition: background-color 0.3s, color 0.3s;
    }
    a.back-link:hover {
      background-color: #00796b;
      color: white;
    }
  </style>
</head>
<body>
  <header>
    <img class="logo" src="{{ 'logo.png' | asset_url }}" alt="Cesur Akvaryum Logo" />
    <h1>Cesur Akvaryum</h1>
  </header>

  <main>
    <img class="product-image" src="{{ product.featured_image | img_url: 'large' }}" alt="{{ product.title }}" />
    <h2>{{ product.title }}</h2>
    <p class="price">{{ product.price | money }}</p>
    <p class="description">{{ product.description | raw }}</p>

    <a href="/" class="back-link">← Ana Sayfaya Dön</a>
  </main>
</body>
</html>
