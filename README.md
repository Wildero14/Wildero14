- 👋 Hi, I’m @Wildero14
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
Wildero14/Wildero14 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
---><!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sklep Internetowy</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <div class="container">
            <h1>Sklep Internetowy</h1>
            <nav>
                <ul>
                    <li><a href="#home">Strona Główna</a></li>
                    <li><a href="#products">Produkty</a></li>
                    <li><a href="#contact">Kontakt</a></li>
                    <li><a href="#cart">Koszyk</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <section id="home">
        <div class="container">
            <h2>Witamy w naszym sklepie!</h2>
            <p>Znajdziesz tutaj najlepsze produkty w najlepszych cenach.</p>
        </div>
    </section>

    <section id="products">
        <div class="container">
            <h2>Nasze Produkty</h2>
            <div class="product-grid">
                <div class="product">
                    <img src="product1.jpg" alt="Produkt 1">
                    <h3>Produkt 1</h3>
                    <p>Opis produktu 1.</p>
                    <p class="price">99,99 zł</p>
                    <button onclick="addToCart('Produkt 1', 99.99)">Dodaj do koszyka</button>
                </div>
                <div class="product">
                    <img src="product2.jpg" alt="Produkt 2">
                    <h3>Produkt 2</h3>
                    <p>Opis produktu 2.</p>
                    <p class="price">149,99 zł</p>
                    <button onclick="addToCart('Produkt 2', 149.99)">Dodaj do koszyka</button>
                </div>
                <div class="product">
                    <img src="product3.jpg" alt="Produkt 3">
                    <h3>Produkt 3</h3>
                    <p>Opis produktu 3.</p>
                    <p class="price">199,99 zł</p>
                    <button onclick="addToCart('Produkt 3', 199.99)">Dodaj do koszyka</button>
                </div>
                <div class="product">
                    <img src="product4.jpg" alt="Produkt 4">
                    <h3>Produkt 4</h3>
                    <p>Opis produktu 4.</p>
                    <p class="price">129,99 zł</p>
                    <button onclick="addToCart('Produkt 4', 129.99)">Dodaj do koszyka</button>
                </div>
                <!-- Dodaj więcej produktów według potrzeb -->
            </div>
        </div>
    </section>

    <section id="cart">
        <div class="container">
            <h2>Koszyk</h2>
            <div id="cart-items">
                <p>Koszyk jest pusty.</p>
            </div>
            <div id="cart-total">
                <p>Suma: <span id="cart-total-value">0,00 zł</span></p>
                <button onclick="checkout()">Zamów</button>
            </div>
        </div>
    </section>

    <section id="contact">
        <div class="container">
            <h2>Kontakt</h2>
            <p>Masz pytania? Skontaktuj się z nami!</p>
            <form action="#" method="post">
                <label for="name">Imię:</label>
                <input type="text" id="name" name="name" required>
                <label for="email">Email:</label>
                <input type="email" id="email" name="email" required>
                <label for="message">Wiadomość:</label>
                <textarea id="message" name="message" required></textarea>
                <button type="submit">Wyślij</button>
            </form>
        </div>
    </section>

    <footer>
        <div class="container">
            <p>&copy; 2024 Sklep Internetowy. Wszelkie prawa zastrzeżone.</p>
        </div>
    </footer>

    <script>
        // Funkcje obsługujące koszyk
        let cart = [];

        function addToCart(productName, productPrice) {
            cart.push({ name: productName, price: productPrice });
            updateCart();
        }

        function updateCart() {
            let cartItemsDiv = document.getElementById('cart-items');
            let cartTotalValue = document.getElementById('cart-total-value');
            cartItemsDiv.innerHTML = '';

            if (cart.length === 0) {
                cartItemsDiv.innerHTML = '<p>Koszyk jest pusty.</p>';
                cartTotalValue.textContent = '0,00 zł';
            } else {
                let totalPrice = 0;
                cart.forEach(item => {
                    totalPrice += item.price;
                    cartItemsDiv.innerHTML += `<div>${item.name} - ${item.price.toFixed(2)} zł</div>`;
                });
                cartTotalValue.textContent = totalPrice.toFixed(2) + ' zł';
            }
        }

        function checkout() {
            // Tu można dodać logikę przetwarzania zamówienia
            alert('Zamówienie złożone! Dziękujemy za zakupy.');
            cart = [];
            updateCart();
        }
    </script>
</body>
</html>

