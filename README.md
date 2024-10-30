# World-Fit
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>WOLRD FIT</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f5f5f5;
        }

        header {
            background-color: #333;
            color: #fff;
            padding: 20px;
            text-align: center;
            position: relative;
        }

        nav {
            text-align: center;
            margin: 20px 0;
        }

        nav a {
            margin: 0 15px;
            text-decoration: none;
            color: #333;
        }

        /* Cambia la imagen por el título */
        .logo {
            max-width: 300px; /* Ajusta el tamaño máximo de la imagen */
            height: auto;
        }

        /* Botón de carrito en la esquina superior derecha */
        #cart-icon {
            position: absolute;
            top: 20px;
            right: 20px;
            font-size: 1.2rem;
            background-color: #ffcc00;
            padding: 10px 15px;
            border-radius: 5px;
            cursor: pointer;
        }

        .product-container {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
            margin: 20px;
        }

        .product {
            border: 1px solid #ccc;
            padding: 20px;
            width: 300px;
            margin: 10px;
            text-align: center;
            background-color: white;
        }

        .product img {
            width: 100%;
            height: auto;
        }

        /* Botones alineados al lado del otro */
        .product-buttons {
            display: flex;
            justify-content: space-between;
            margin-top: 10px;
        }

        .add-to-cart, .buy-now {
            background-color: #28a745;
            color: white;
            padding: 10px 15px;
            border: none;
            cursor: pointer;
            flex: 1;
            margin: 0 5px;
        }

        .buy-now {
            background-color: #007bff;
        }

        footer {
            background-color: #333;
            color: white;
            text-align: center;
            padding: 10px 0;
            position: fixed;
            bottom: 0;
            width: 100%;
        }

        /* Estilo para el formulario de contacto */
        .contact-form {
            background-color: white;
            padding: 20px;
            margin: 20px auto;
            width: 50%;
            border: 1px solid #ccc;
            border-radius: 5px;
        }

        .contact-form label {
            display: block;
            margin: 10px 0 5px;
        }

        .contact-form input, .contact-form textarea {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }

        .contact-form button {
            background-color: #333;
            color: white;
            padding: 10px 20px;
            border: none;
            cursor: pointer;
            border-radius: 5px;
        }

        .contact-form button:hover {
            background-color: #555;
        }

        /* Estilo para la sección del carrito */
        #cart-items {
            background-color: white;
            padding: 20px;
            margin: 20px auto;
            width: 80%;
            border: 1px solid #ccc;
            border-radius: 5px;
            display: none;
        }

        #cart-items h2 {
            text-align: center;
        }

        #cart-items ul {
            list-style-type: none;
            padding: 0;
        }

        #cart-items ul li {
            background-color: #f9f9f9;
            padding: 10px;
            margin-bottom: 5px;
            border: 1px solid #ddd;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        #cart-items ul li img {
            width: 50px;
            height: 50px;
            margin-right: 15px;
        }

        .cart-item-info {
            display: flex;
            align-items: center;
        }

        .cart-item-price {
            font-weight: bold;
        }

        /* Estilo para la sección de productos peligrosos */
        .danger-container {
            background-color: #ffe6e6;
            padding: 20px;
            margin: 20px;
            border: 1px solid #ffcccc;
            border-radius: 5px;
        }

        .danger-product {
            border: 1px solid #ff9999;
            padding: 20px;
            width: 300px;
            margin: 10px;
            text-align: center;
            background-color: white;
        }
    </style>
</head>
<body>

<header>
    <img src="imagenes/worldfit.png" alt="Logo de la Tienda" class="logo"> 
    <p>LOS MEJORES PRODUCTOS FITNESS ESTAN AQUI</p>

    <!-- Botón del carrito en la esquina superior derecha -->
    <div id="cart-icon" onclick="viewCart()">
        🛒 Carrito (<span id="cart-count">0</span>)
    </div>
</header>

<nav>
    <a href="#">Inicio</a>
    <a href="#">Productos</a>
    <a href="#contacto">Contacto</a>
</nav>

<!-- Sección de productos -->
<section class="product-container">
    <div class="product">
        <img src="imagenes/proteina bipro.png" alt="Producto 1">
        <h3>Proteina Bipro</h3>
        <p>BiPro es una proteína de suero ultra pura, sin grasas, carbohidratos ni lactosa. Ideal para una recuperación muscular óptima, ofrece alta biodisponibilidad y se adapta a cualquier rutina de entrenamiento.</p>
        <p><strong>Precio: $175.000</strong></p>
        <div class="product-buttons">
            <button class="add-to-cart" onclick="addToCart('Proteina Bipro', 'imagenes/proteina bipro.png', 175.000)">Añadir al carrito</button>
            <button class="buy-now" onclick="buyNow('Proteina Bipro')">Comprar</button>
        </div>
    </div>
    
    <div class="product">
        <img src="imagenes/proteina star.png" alt="Producto 2">
        <h3>Proteina Star Nutrition</h3>
        <p>Star Nutrition ofrece una proteína de suero de alta calidad, rica en aminoácidos esenciales y de fácil disolución. Diseñada para maximizar el desarrollo y la recuperación muscular, es ideal para quienes buscan resultados efectivos en sus entrenamientos.</p>
        <p><strong>Precio: $35.000</strong></p>
        <div class="product-buttons">
            <button class="add-to-cart" onclick="addToCart('Proteina Star Nutrition', 'imagenes/proteina star.png', 35.000)">Añadir al carrito</button>
            <button class="buy-now" onclick="buyNow('Proteina Star Nutrition')">Comprar</button>
        </div>
    </div>

    <div class="product">
        <img src="imagenes/proteina pulver.png" alt="Producto 3">
        <h3>Proteina Pulver</h3>
        <p>Pulver es una proteína de suero de alta calidad, destacada por su pureza y rápida absorción. Ideal para la recuperación y el crecimiento muscular, es baja en carbohidratos y grasas, perfecta para optimizar el rendimiento físico en cualquier rutina de entrenamiento.</p>
        <p><strong>Precio: $33.000</strong></p>
        <div class="product-buttons">
            <button class="add-to-cart" onclick="addToCart('Proteina Pulver', 'imagenes/producto2.jpg', 33.000)">Añadir al carrito</button>
            <button class="buy-now" onclick="buyNow('Proteina Pulver')">Comprar</button>
        </div>
    </div>

    <div class="product">
        <img src="imagenes/gentech.png" alt="Producto 4">
        <h3>Proteina Gentech</h3>
        <p>Gentech es una proteína de suero de alta calidad, rica en aminoácidos esenciales y de rápida absorción, ideal para la recuperación y el crecimiento muscular. Perfecta para complementar cualquier rutina de entrenamiento.        </p>
        <p><strong>Precio: $30.000</strong></p>
        <div class="product-buttons">
            <button class="add-to-cart" onclick="addToCart('Proteina Gentech', 'imagenes/gentech.png', 30.000)">Añadir al carrito</button>
            <button class="buy-now" onclick="buyNow('Proteina Gentech')">Comprar</button>
        </div>
    </div>

    <div class="product">
        <img src="imagenes/creatinaxtrenght.png" alt="Producto 5">
        <h3>Creatina Xtrenght</h3>
        <p>Creatina Xtrenght es un suplemento de alta pureza que mejora el rendimiento físico y aumenta la fuerza muscular. Optimiza la energía durante entrenamientos intensos y favorece la recuperación, ideal para atletas que buscan maximizar sus resultados.</p>
        <p><strong>Precio: $27.000</strong></p>
        <div class="product-buttons">
            <button class="add-to-cart" onclick="addToCart('Creatina Xtrenght', 'imagenes/creatinaxtrenght.png', 27.000)">Añadir al carrito</button>
            <button class="buy-now" onclick="buyNow('Creatina Xtrenght')">Comprar</button>
        </div>
    </div>

    <div class="product">
        <img src="imagenes/creatina+growth.png" alt="Producto 6">
        <h3>Creatina +growth</h3>
        <p>  Creatina +Growth es un suplemento que combina creatina con ingredientes diseñados para potenciar el crecimiento muscular. Ayuda a mejorar el rendimiento en entrenamientos intensos y favorece la recuperación, ideal para quienes buscan maximizar su masa muscular y fuerza.</p>
        <p><strong>Precio: $15.000</strong></p>
        <div class="product-buttons">
            <button class="add-to-cart" onclick="addToCart('Creatina +growth', 'imagenes/creatina+growth.png', 33.000)">Añadir al carrito</button>
            <button class="buy-now" onclick="buyNow('Creatina +growth')">Comprar</button>
        </div>
    </div>
    
    <div class="product">
        <img src="imagenes/creatinastarnutrition.png" alt="Producto 7">
        <h3>Creatina Star Nutrition</h3>
        <p>
            Creatina Star Nutrition es un suplemento de creatina pura que mejora el rendimiento físico y aumenta la fuerza muscular. Ideal para potenciar la energía durante entrenamientos intensos y acelerar la recuperación, ayudando a alcanzar tus objetivos de fitness de manera efectiva.</p>
        <p><strong>Precio: $29.999</strong></p>
        <div class="product-buttons">
            <button class="add-to-cart" onclick="addToCart('Creatina Star Nutrition', 'imagenes/creatinastarnutrition.png', 33.000)">Añadir al carrito</button>
            <button class="buy-now" onclick="buyNow('Creatina Star Nutrition')">Comprar</button>
        </div>
    </div>

</section>

<!-- Sección de productos peligrosos -->
<section class="danger-container">
    <h2>Productos Peligrosos</h2>
    <div class="product-container">
        <div class="danger-product">
            <img src="imagenes/trembo.png" alt="Producto Peligroso 1">
            <h3>Producto Peligroso 1</h3>
            <p>Descripción breve del producto peligroso.</p>
            <p><strong>Precio: $59.99</strong></p>
            <div class="product-buttons">
                <button class="add-to-cart" onclick="addToCart('Producto Peligroso 1', 'imagenes/peligroso1.jpg', 59.99)">Añadir al carrito</button>
                <button class="buy-now" onclick="buyNow('Producto Peligroso 1')">Comprar</button>
            </div>
        </div>
        
        <div class="danger-product">
            <img src="imagenes/clembuterol.png" alt="Producto Peligroso 2">
            <h3>Producto Peligroso 2</h3>
            <p>Descripción breve del producto peligroso.</p>
            <p><strong>Precio: $69.99</strong></p>
            <div class="product-buttons">
                <button class="add-to-cart" onclick="addToCart('Producto Peligroso 2', 'imagenes/peligroso2.jpg', 69.99)">Añadir al carrito</button>
                <button class="buy-now" onclick="buyNow('Producto Peligroso 2')">Comprar</button>
            </div>
        </div>
        
        <div class="danger-product">
            <img src="imagenes/dianabol.png" alt="Producto Peligroso 3">
            <h3>Producto Peligroso 3</h3>
            <p>Descripción breve del producto peligroso.</p>
            <p><strong>Precio: $79.99</strong></p>
            <div class="product-buttons">
                <button class="add-to-cart" onclick="addToCart('Producto Peligroso 3', 'imagenes/peligroso3.jpg', 79.99)">Añadir al carrito</button>
                <button class="buy-now" onclick="buyNow('Producto Peligroso 3')">Comprar</button>
            </div>
        </div>
    </div>
</section>

<!-- Sección de información -->
<section class="info-section">
    <h2>Información Importante</h2>
    <p>En esta sección puedes agregar información relevante sobre tu tienda, políticas de envío, devoluciones, o cualquier otro dato que consideres útil para tus clientes.</p>
</section>

<!-- Sección del carrito de compras -->
<section id="cart-items">
    <h2>Tu carrito de compras</h2>
    <ul id="cart-list">
        <!-- Aquí se mostrarán los productos añadidos al carrito -->
    </ul>
</section>

<!-- Sección de formulario de contacto -->
<section id="contacto" class="contact-form">
    <h2>Contacto</h2>
    <form action="https://formspree.io/f/tu_codigo" method="POST">
        <label for="name">Nombre:</label>
        <input type="text" id="name" name="name" required>
        
        <label for="email">Correo Electrónico:</label>
        <input type="email" id="email" name="email" required>
        
        <label for="message">Mensaje:</label>
        <textarea id="message" name="message" rows="5" required></textarea>
        
        <button type="submit">Enviar Mensaje</button>
    </form>
</section>

<footer>
    <p>© 2024 WORLD FIT | Todos los derechos reservados</p>
</footer>

<!-- JavaScript para simular carrito de compras -->
<script>
let cart = [];
let cartCount = 0;

function addToCart(product, image, price) {
    cart.push({ name: product, img: image, price: price });
    cartCount++;
    document.getElementById('cart-count').textContent = cartCount;
    alert(product + ' ha sido añadido al carrito.');
}

function viewCart() {
    const cartSection = document.getElementById('cart-items');
    const cartList = document.getElementById('cart-list');
    
    // Limpiamos la lista de productos antes de agregar los nuevos
    cartList.innerHTML = '';
    
    // Si no hay productos en el carrito
    if (cart.length === 0) {
        cartList.innerHTML = '<li>No hay productos en el carrito</li>';
    } else {
        // Añadir productos al carrito con imagen y precio
        cart.forEach(item => {
            const listItem = document.createElement('li');
            
            const itemInfo = document.createElement('div');
            itemInfo.classList.add('cart-item-info');
            
            const imgElement = document.createElement('img');
            imgElement.src = item.img;
            
            const textNode = document.createTextNode(item.name + ' - $' + item.price.toFixed(2));
            
            const priceElement = document.createElement('span');
            priceElement.classList.add('cart-item-price');
            
            itemInfo.appendChild(imgElement);
            itemInfo.appendChild(textNode);
            listItem.appendChild(itemInfo);
            listItem.appendChild(priceElement);
            
            cartList.appendChild(listItem);
        });
    }
    
    // Mostramos la sección del carrito
    cartSection.style.display = 'block';
}

function buyNow(product) {
    alert('Comprando ' + product);
    // Redirigir a la página de pago, si lo deseas
    window.location.href = 'pagina-de-pago.html';
}
</script>

</body>
</html>
