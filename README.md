<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Cesur Akvaryum</title>
  <style>
    /* Genel Stil */
    * {
      box-sizing: border-box;
    }
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      margin: 0;
      background-color: #f4fdfd;
      color: #003d40;
    }
    header {
      background-color: #006064;
      color: white;
      padding: 20px 30px;
      display: flex;
      align-items: center;
      gap: 15px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.15);
    }
    header img {
      width: 50px;
      height: 50px;
    }
    header h1 {
      margin: 0;
      font-weight: 900;
      font-size: 2.2rem;
    }
    .tabs {
      display: flex;
      justify-content: center;
      gap: 20px;
      margin: 30px 0 20px;
    }
    .tab-button {
      padding: 10px 25px;
      border: none;
      border-radius: 50px;
      background-color: #b2ebf2;
      color: #004d40;
      font-weight: bold;
      cursor: pointer;
      transition: all 0.3s;
    }
    .tab-button:hover {
      background-color: #4dd0e1;
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
      box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
      padding: 20px;
      scroll-snap-align: start;
      text-align: center;
      cursor: pointer;
      position: relative;
      transition: transform 0.3s, box-shadow 0.3s;
    }
    .product-card:hover {
      transform: translateY(-10px) scale(1.05);
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
      margin: 16px 0 8px;
      color: #00695c;
    }
    .product-detail {
      display: none;
      padding: 12px 18px;
      background-color: #e0f2f1;
      border-radius: 0 0 16px 16px;
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
      border-bottom: 1px solid #00796b;
      padding-bottom: 3px;
    }
    .product-detail ul {
      margin: 0 0 10px 18px;
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
      font-weight: bold;
    }
    #BilgiBtn {
      background-color: #004d40;
      color: white;
      border: none;
      padding: 12px 24px;
      border-radius: 30px;
      cursor: pointer;
      font-weight: bold;
      font-size: 16px;
      margin: 0 auto 40px;
      display: block;
    }
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
    .contact-section {
      background-color: #004d40;
      color: white;
      padding: 40px 20px;
      text-align: center;
      font-size: 1.1rem;
      font-weight: 600;
      border-top-left-radius: 20px;
      border-top-right-radius: 20px;
      box-shadow: 0 -5px 20px rgba(0, 0, 0, 0.2);
    }
    .contact-section h2 {
      margin-bottom: 20px;
      font-weight: 900;
    }
    .contact-section a {
      color: #80cbc4;
      text-decoration: none;
    }
  </style>
</head>
<body>
  <!-- HTML içeriği burada aynı şekilde devam eder -->
  <!-- İçeriği görmek için yukarıdaki HTML'i kopyalayabilirsiniz -->
  <script>
    function openTab(tabName, elem) {
      document.querySelectorAll('.tab-button').forEach(btn => btn.classList.remove('active'));
      elem.classList.add('active');
      document.querySelectorAll('.tab-content').forEach(tc => tc.classList.remove('active'));
      document.getElementById(tabName).classList.add('active');
    }
    function toggleDetail(button) {
      const detail = button.previousElementSibling;
      detail.classList.toggle('active');
      button.textContent = detail.classList.contains('active') ? 'Detayları Gizle' : 'Detayları Göster';
    }
    document.getElementById('BilgiBtn').addEventListener('click', () => {
      document.getElementById('infoModal').style.display = 'block';
    });
    function closeModal() {
      document.getElementById('infoModal').style.display = 'none';
    }
  </script>
</body>
</html>
