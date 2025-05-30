# petshop.kz
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>PetShop — Интернет-магазин для домашних животных | PetShop</title>
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600&display=swap" rel="stylesheet">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Montserrat', sans-serif;
    }
    body {
      background-color: #f9f9f9;
      color: #333;
    }
    header {
      background-color: #ffffff;
      padding: 20px 40px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      box-shadow: 0 2px 8px rgba(0,0,0,0.05);
    }
    header h1 {
      color: #3d8361;
      font-size: 24px;
    }
    nav a {
      margin-left: 20px;
      color: #3d8361;
      text-decoration: none;
      font-weight: 600;
    }
    .hero {
      background: url('c7569cb32bbc4b06f3d72888724955af.gif') center/cover no-repeat;
      height: 60vh;
      display: flex;
      align-items: center;
      justify-content: center;
      color: white;
      text-shadow: 1px 1px 4px rgba(0,0,0,0.7);
      text-align: center;
    }
    .hero h2 {
      font-size: 40px;
    }
    .products {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 20px;
      padding: 40px;
    }
    .product {
      background-color: #fff;
      border-radius: 12px;
      overflow: hidden;
      box-shadow: 0 4px 12px rgba(0,0,0,0.1);
      transition: transform 0.2s;
    }
    .product:hover {
      transform: translateY(-5px);
    }
    .product img {
      width: 70%;
      height: 180px;
      object-fit: cover;
    }
    .product-info {
      padding: 15px;
    }
    .product-info h3 {
      font-size: 18px;
      margin-bottom: 5px;
    }
    .product-info p {
      font-size: 14px;
      color: #666;
      margin-bottom: 5px;
    }
    .product-info .price {
      font-weight: bold;
      color: #3d8361;
      margin-bottom: 10px;
    }
    .product button {
      margin-top: 10px;
      padding: 8px 16px;
      background-color: #3d8361;
      color: white;
      border: none;
      border-radius: 8px;
      cursor: pointer;
    }
    .cart {
      position: fixed;
      top: 80px;
      right: 20px;
      background: #ffffff;
      border: 1px solid #ddd;
      border-radius: 12px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.1);
      padding: 20px;
      width: 300px;
      max-height: 400px;
      overflow-y: auto;
      display: none;
    }
    .cart h3 {
      margin-bottom: 10px;
    }
    footer {
      background-color: #3d8361;
      color: white;
      padding: 20px;
      text-align: center;
    }
    .contact {
      background-color: #fff;
      padding: 40px;
      text-align: center;
    }
    .contact h2 {
      color: #3d8361;
      margin-bottom: 20px;
    }
    .contact p {
      margin: 5px 0;
    }
    .kaspi-qr {
      margin-top: 20px;
    }
    .kaspi-qr img {
      max-width: 200px;
      border: 1px solid #ccc;
      border-radius: 8px;
    }
  </style>
</head>
<body>
  <header>
    <h1>ZooMarket | PetShop</h1>
    <nav>
      <a href="#">Главная</a>
      <a href="#products">Товары</a>
      <a href="#contact">Контакты</a>
      <a href="#" onclick="toggleCart()">Корзина (<span id="cart-count">0</span>)</a>
    </nav>
  </header>

  <section class="hero">
    <h2>Лучшие товары для ваших питомцев</h2>
  </section>
 <section id="products" class="products">
  <div class="product">
    <img src="https://storage.yandexcloud.net/yac-wh-sb-prod-s3-media-03005/themes/basic/static/home/product_dry.webp" alt="Корм для собак">
    <div class="product-info">
      <h3>Сухой корм для собак Pedigree, 10 кг</h3>
      <p>Полноценный рацион для взрослых собак всех пород.</p>
      <p class="price">12 500 ₸</p>
      <button onclick="addToCart('Сухой корм для собак', 12500)">В корзину</button>
    </div>
  </div>

  <div class="product">
    <img src="https://catalog.detmir.st/media/1zD4fbrR7gUdmRscoRV3Bd3hvIn8vXbg4pw-Bn9S8ys=?preset=site_product_gallery_r450" alt="Наполнитель для кошек">
    <div class="product-info">
      <h3>Наполнитель Cats Way, 6 кг</h3>
      <p>Устраняет запахи, обеспечивает чистоту.</p>
      <p class="price">4 800 ₸</p>
      <button onclick="addToCart('Наполнитель Cats Way', 4800)">В корзину</button>
    </div>
  </div>

  <div class="product">
    <img src="https://images.prom.ua/4044912648_w600_h600_4044912648.jpg" alt="Лежанка для кошек">
    <div class="product-info">
      <h3>Лежак для кошек</h3>
      <p>Комфорт и уют вашему питомцу.</p>
      <p class="price">4 800 ₸</p>
      <button onclick="addToCart('Лежак для кошек', 4800)">В корзину</button>
    </div>
  </div>

  <div class="product">
    <img src="https://zoosfera-nn.ru/images/detailed/678/b67140ff30ab11e0a9b6002618badd88_b4b7edd6d7e911eb80fa00155d331805.jpg" alt="Игрушка для кошек">
    <div class="product-info">
      <h3>Игрушка-мышка для кошек</h3>
      <p>Развивает охотничьи инстинкты.</p>
      <p class="price">1 200 ₸</p>
      <button onclick="addToCart('Игрушка для кошек', 1200)">В корзину</button>
    </div>
  </div>

  <div class="product">
    <img src="https://petplus.com.ua/image/cache/catalog/dogs/aks/Flexi/flexi_black_design_m_cord_5m_blue-min-500x500.jpg" alt="Поводок для собак">
    <div class="product-info">
      <h3>Поводок-рулетка 5 м</h3>
      <p>Прочный, с автоматической намоткой.</p>
      <p class="price">3 000 ₸</p>
      <button onclick="addToCart('Поводок-рулетка', 3000)">В корзину</button>
    </div>
  </div>

  <div class="product">
    <img src="https://static.insales-cdn.com/r/b2LFFLnyp9Y/rs:fit:250:0:1/q:100/plain/images/products/1/576/322708032/Fresh_Nano-Metal_1000x1000.png@png" alt="Миска для животных">
    <div class="product-info">
      <h3>Двойная миска для корма и воды</h3>
      <p>Удобство и простота использования.</p>
      <p class="price">2 500 ₸</p>
      <button onclick="addToCart('Двойная миска', 2500)">В корзину</button>
    </div>
  </div>

  <div class="product">
    <img src="https://storage.yandexcloud.net/yac-wh-sb-prod-s3-media-03002/uploads/product/34/66a2643c597a3_Frame%205-min.jpg" alt="Лакомства для собак">
    <div class="product-info">
      <h3>Лакомства для собак, 500 г</h3>
      <p>Натуральный состав, вкусно и полезно.</p>
      <p class="price">3 200 ₸</p>
      <button onclick="addToCart('Лакомства для собак', 3200)">В корзину</button>
    </div>
  </div>

  <div class="product">
    <img src="https://czv.kz/assets/images/products/24264/biovaks-shampun-dlya-kotyat-i-koshek-ot-bloh-kleshchey-vshey-i-vlasoedov-s-ekstraktom-romashki-i-maslom-evkalipta-250-ml.jpg" alt="Шампунь для животных">
    <div class="product-info">
      <h3>Шампунь для собак и кошек</h3>
      <p>Гипоаллергенный, бережный уход.</p>
      <p class="price">2 800 ₸</p>
      <button onclick="addToCart('Шампунь для животных', 2800)">В корзину</button>
    </div>
  </div>

  <div class="product">
    <img src="https://catalog.detmir.st/media/VNQmNmY9pfxKTL30WJI8278HYS1fjgngYZN93htq1ME=" alt="Когтеточка для кошек">
    <div class="product-info">
      <h3>Когтеточка-столбик</h3>
      <p>Сохраняет мебель и развлекает питомца.</p>
      <p class="price">5 500 ₸</p>
      <button onclick="addToCart('Когтеточка', 5500)">В корзину</button>
    </div>
  </div>
</section>
   
</section>

  <section id="products" class="products">
    <!-- Товары остаются без изменений -->
  </section>

  <div class="cart" id="cart">
    <h3>Корзина</h3>
    <ul id="cart-items"></ul>
    <p><strong>Итого: <span id="total-price">0</span> ₸</strong></p>
  </div>

  <section class="contact" id="contact">
    <h2>Контакты и доставка</h2>
    <p><strong>Адрес:</strong> г. Алматы, ул. Байтурсынова 123</p>
    <p><strong>Телефон:</strong> +7 (777) 123-45-67</p>
    <p><strong>Email:</strong> info@zoomarket.kz</p>
    <p><strong>Оплата:</strong> Kaspi QR, Kaspi перевод, наличные</p>
    <p><strong>Доставка:</strong> По Алматы — 1-2 дня, по Казахстану — 3-5 дней</p>
    <div class="kaspi-qr">
      <p><strong>Отсканируйте для оплаты через Kaspi QR:</strong></p>
      <img src="https://f.nodacdn.net/408120" alt="Kaspi QR">
    </div>
  </section>

  <footer>
    <p>© 2025 ZooMarket | PetShop. Все права защищены.</p>
  </footer>

  <script>
    const cart = [];
    let total = 0;

    function addToCart(item, price) {
      cart.push({ name: item, price });
      document.getElementById('cart-count').innerText = cart.length;
      updateCartDisplay();
    }

    function updateCartDisplay() {
      const cartList = document.getElementById('cart-items');
      cartList.innerHTML = '';
      total = 0;
      cart.forEach((item, index) => {
        const li = document.createElement('li');
        li.textContent = `${index + 1}. ${item.name} — ${item.price} ₸`;
        cartList.appendChild(li);
        total += item.price;
      });
      document.getElementById('total-price').innerText = total;
    }

    function toggleCart() {
      const cartBox = document.getElementById('cart');
      cartBox.style.display = cartBox.style.display === 'block' ? 'none' : 'block';
    }
  </script>
</body>
</html>
