<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>R PERFUME</title>

<style>
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    background: #090909;
    color: white;
    font-family: Arial, sans-serif;
}

header {
    background: #151515;
    text-align: center;
    padding: 22px 10px;
    border-bottom: 2px solid #d71920;
}

header h1 {
    color: #e6e6e6;
    letter-spacing: 5px;
    margin: 0;
}

header h1 span {
    color: #e31b23;
}

header p {
    color: #aaa;
    font-size: 12px;
}

nav {
    display: flex;
    justify-content: space-around;
    padding: 15px 5px;
    background: #202020;
}

nav a {
    color: white;
    text-decoration: none;
    font-size: 14px;
}

.hero {
    text-align: center;
    padding: 45px 15px;
    background: linear-gradient(135deg, #31090b, #101010, #292929);
}

.hero h2 {
    font-size: 27px;
    color: #f0f0f0;
}

.hero p {
    color: #ccc;
}

button {
    border: none;
    padding: 12px 16px;
    background: #d71920;
    color: white;
    font-weight: bold;
    border-radius: 5px;
    cursor: pointer;
}

.section {
    padding: 22px 12px;
}

.section h2 {
    text-align: center;
    color: #e31b23;
    margin-bottom: 22px;
}

.products {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 12px;
}

.card {
    background: #191919;
    border: 1px solid #444;
    border-radius: 9px;
    text-align: center;
    overflow: hidden;
    padding-bottom: 15px;
}

.card img {
    width: 100%;
    height: 145px;
    object-fit: contain;
    background: #eee;
}

.card h3 {
    font-size: 15px;
    margin: 12px 4px;
}

.price {
    color: #ddd;
    font-weight: bold;
}

.card button {
    font-size: 11px;
    padding: 10px;
}

#cart {
    background: #171717;
    margin: 12px;
    padding: 18px;
    border: 1px solid #d71920;
    border-radius: 8px;
}

#cart h2 {
    color: #e31b23;
}

.cart-row {
    padding: 10px 0;
    border-bottom: 1px solid #444;
}

input, textarea {
    width: 100%;
    padding: 12px;
    margin: 7px 0;
    background: #262626;
    border: 1px solid #555;
    border-radius: 5px;
    color: white;
}

footer {
    background: #050505;
    text-align: center;
    padding: 22px 10px;
    color: #aaa;
    border-top: 2px solid #d71920;
}
</style>
</head>

<body>

<header>
    <h1>R <span>PERFUME</span></h1>
    <p>YOUR STYLE. YOUR FRAGRANCE.</p>
</header>

<nav>
    <a href="#home">Home</a>
    <a href="#shop">Shop</a>
    <a href="#cart">Cart 🛒 <span id="count">0</span></a>
</nav>

<section class="hero" id="home">
    <h2>SMELL DIFFERENT.</h2>
    <p>Discover fragrances that define you.</p>
    <button onclick="document.getElementById('shop')
    .scrollIntoView({behavior:'smooth'})">
        EXPLORE COLLECTION
    </button>
</section>

<section class="section" id="shop">
    <h2>OUR COLLECTION</h2>
    <div class="products" id="products"></div>
</section>

<section id="cart">
    <h2>YOUR SHOPPING CART</h2>
    <div id="items">Your cart is empty.</div>
    <h3>Total: ₹<span id="total">0</span></h3>

    <h3>Delivery Details</h3>
    <input id="name" placeholder="Your Full Name">
    <input id="phone" type="tel" maxlength="10"
           placeholder="Your Phone Number">
    <textarea id="address" placeholder="Delivery Address"></textarea>

    <button onclick="placeOrder()">ORDER ON WHATSAPP</button>
</section>

<footer>
    <h3>R PERFUME</h3>
    <p>Luxury Fragrances | Online Perfume Store</p>
    <p>© 2026 R PERFUME</p>
</footer>

<script>
const products = [
    {
        id: 1,
        name: "Dior Sauvage",
        price: 8500,
        image: "https://www.sephora.com.mx/on/demandware.static/-/Sites-masterCatalog_Sephora/es_MX/dwdefc1b76/images/hi-res/eau-de-toilette-dior-dior-sauvage-eau-de-toilette-100ml3348901250146A.jpg"
    },
    {
        id: 2,
        name: "Bleu de Chanel",
        price: 9500,
        image: "https://media.ulta.com/i/ulta/2227849?fmt=auto&h=1080&w=1080"
    },
    {
        id: 3,
        name: "Versace Eros",
        price: 6500,
        image: "https://cdn.media.amplience.net/i/frasersdev/75195069_o.jpg?v=20240417082012"
    },
    {
        id: 4,
        name: "Royal Musk",
        price: 1499,
        image: "https://amfragrances.com/cdn/shop/files/50ml_black_bottle_square.png?v=1784228002&width=1445"
    },
    {
        id: 5,
        name: "Premium Oud",
        price: 1999,
        image: "https://fizzywhiz.com/cdn/shop/files/rose_oud_fragrance_oil.jpg?v=1770472524"
    },
    {
        id: 6,
        name: "Silver Night",
        price: 999,
        image: "https://mocemsa.com/cdn/shop/files/4_4_2048x2048.jpg?v=1683993671"
}     
];

let cart = [];

function displayProducts() {
    document.getElementById("products").innerHTML =
    products.map(p => `
        <div class="card">
            <img src="${p.image}" alt="${p.name}">
            <h3>${p.name}</h3>
            <p class="price">₹${p.price.toLocaleString("en-IN")}</p>
            <button onclick="addToCart(${p.id})">
                ADD TO CART
            </button>
        </div>
    `).join("");
}

function addToCart(id) {
    let item = cart.find(p => p.id === id);

    if (item) {
        item.qty++;
    } else {
        let product = products.find(p => p.id === id);
        cart.push({...product, qty: 1});
    }

    displayCart();
}

function removeFromCart(id) {
    let item = cart.find(p => p.id === id);

    if (item) {
        item.qty--;

        if (item.qty <= 0) {
            cart = cart.filter(p => p.id !== id);
        }
    }

    displayCart();
}

function displayCart() {
    document.getElementById("count").textContent =
        cart.reduce((sum, p) => sum + p.qty, 0);

    document.getElementById("items").innerHTML =
        cart.length ? cart.map(p => `
            <div class="cart-row">
                ${p.name} × ${p.qty}
                — ₹${(p.price * p.qty).toLocaleString("en-IN")}
                <button onclick="removeFromCart(${p.id})">−</button>
            </div>
        `).join("") : "Your cart is empty.";

    document.getElementById("total").textContent =
        cart.reduce((sum, p) => sum + p.price * p.qty, 0)
        .toLocaleString("en-IN");
}

function placeOrder() {
    const name = document.getElementById("name").value.trim();
    const phone = document.getElementById("phone").value.trim();
    const address = document.getElementById("address").value.trim();

    if (!cart.length) {
        alert("Please add a perfume to your cart.");
        return;
    }

    if (!name || !/^[0-9]{10}$/.test(phone) || !address) {
        alert("Enter your name, valid 10-digit phone number and address.");
        return;
    }

    const orderDetails = cart.map(p =>
        `${p.name} x ${p.qty} = Rs. ${p.price * p.qty}`
    ).join("\n");

    const total = cart.reduce(
        (sum, p) => sum + p.price * p.qty, 0
    );

    const message =
        `New R PERFUME Order\n\n` +
        `Customer: ${name}\n` +
        `Phone: ${phone}\n` +
        `Address: ${address}\n\n` +
        `${orderDetails}\n\n` +
        `Total: Rs. ${total}`;

    const whatsappNumber = "919699955142";

    window.open(
        "https://wa.me/" + whatsappNumber +
        "?text=" + encodeURIComponent(message),
        "_blank"
    );
}

displayProducts();
displayCart();
</script>

</body>
</html>