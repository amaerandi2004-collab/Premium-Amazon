<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PrimeShop - Premium Amazon Affiliate Store</title>
    <meta name="description" content="Discover curated Amazon products with exclusive deals. Shop now for the best prices.">
    <style>
        /* ==== GLOBAL STYLES ==== */
        :root {
            --black: #0a0a0a;
            --navy: #0f172a;
            --navy-light: #1e293b;
            --ice-grey: #e2e8f0;
            --iris: #5b5bff;
            --iris-dark: #4a4ae0;
            --white: #ffffff;
            --gradient: linear-gradient(135deg, var(--navy) 0%, var(--iris) 100%);
            --radius: 12px;
            --shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--black);
            color: var(--ice-grey);
            line-height: 1.6;
        }

        a {
            text-decoration: none;
            color: inherit;
        }

        img {
            max-width: 100%;
            height: auto;
        }

        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* ==== BUTTON STYLES ==== */
        .btn {
            display: inline-block;
            padding: 12px 24px;
            background: var(--gradient);
            color: var(--white);
            border: none;
            border-radius: var(--radius);
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
            box-shadow: var(--shadow);
        }

        .btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 12px rgba(91, 91, 255, 0.25);
        }

        .btn:active {
            transform: translateY(0);
        }

        /* ==== HEADER & NAVIGATION ==== */
        header {
            background-color: var(--navy);
            padding: 20px 0;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
        }

        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 24px;
            font-weight: 700;
            color: var(--white);
        }

        .logo span {
            color: var(--iris);
        }

        .nav-menu {
            display: flex;
            list-style: none;
        }

        .nav-menu li {
            margin-left: 30px;
        }

        .nav-menu a {
            font-weight: 500;
            transition: var(--transition);
            position: relative;
        }

        .nav-menu a:hover {
            color: var(--iris);
        }

        .nav-menu a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background-color: var(--iris);
            transition: var(--transition);
        }

        .nav-menu a:hover::after {
            width: 100%;
        }

        .hamburger {
            display: none;
            cursor: pointer;
            width: 30px;
            height: 20px;
            flex-direction: column;
            justify-content: space-between;
        }

        .hamburger span {
            display: block;
            width: 100%;
            height: 3px;
            background-color: var(--white);
            transition: var(--transition);
        }

        /* ==== HERO SECTION ==== */
        .hero {
            background: var(--gradient);
            padding: 80px 0;
            text-align: center;
            margin-bottom: 40px;
        }

        .hero-content {
            max-width: 800px;
            margin: 0 auto;
        }

        .hero h1 {
            font-size: 48px;
            margin-bottom: 20px;
            color: var(--white);
        }

        .hero p {
            font-size: 20px;
            margin-bottom: 30px;
            opacity: 0.9;
        }

        /* ==== SEARCH SECTION ==== */
        .search-section {
            padding: 30px 0;
            background-color: var(--navy-light);
            border-radius: var(--radius);
            margin-bottom: 40px;
        }

        .search-container {
            max-width: 800px;
            margin: 0 auto;
        }

        .search-bar {
            display: flex;
            background-color: var(--navy);
            border-radius: var(--radius);
            overflow: hidden;
            box-shadow: var(--shadow);
        }

        .search-bar input {
            flex: 1;
            padding: 15px;
            border: none;
            background-color: transparent;
            color: var(--ice-grey);
            font-size: 16px;
        }

        .search-bar input::placeholder {
            color: var(--ice-grey);
            opacity: 0.7;
        }

        .search-bar button {
            padding: 0 20px;
            background-color: var(--iris);
            color: var(--white);
            border: none;
            cursor: pointer;
            transition: var(--transition);
        }

        .search-bar button:hover {
            background-color: var(--iris-dark);
        }

        /* ==== PRODUCT GRID ==== */
        .products-section {
            padding: 40px 0;
        }

        .section-title {
            text-align: center;
            margin-bottom: 40px;
            font-size: 32px;
            color: var(--white);
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 30px;
        }

        .product-card {
            background-color: var(--navy);
            border-radius: var(--radius);
            overflow: hidden;
            transition: var(--transition);
            box-shadow: var(--shadow);
        }

        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
        }

        .product-image {
            height: 200px;
            background-color: var(--navy-light);
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
        }

        .product-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }

        .product-card:hover .product-image img {
            transform: scale(1.05);
        }

        .product-info {
            padding: 20px;
        }

        .product-title {
            font-size: 18px;
            margin-bottom: 10px;
            color: var(--white);
        }

        .product-price {
            font-size: 22px;
            font-weight: 700;
            color: var(--iris);
            margin-bottom: 15px;
        }

        .product-description {
            margin-bottom: 20px;
            font-size: 14px;
            opacity: 0.8;
        }

        /* ==== AD OVERLAY ==== */
        .overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.9);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 1000;
            opacity: 0;
            visibility: hidden;
            transition: opacity 0.3s ease;
        }

        .overlay.active {
            opacity: 1;
            visibility: visible;
        }

        .ad-container {
            width: 90%;
            max-width: 800px;
            height: 80vh;
            background-color: var(--navy);
            border-radius: var(--radius);
            padding: 20px;
            display: flex;
            flex-direction: column;
        }

        .ad-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }

        .ad-title {
            font-size: 18px;
            color: var(--white);
        }

        .close-ad {
            background: none;
            border: none;
            color: var(--ice-grey);
            font-size: 24px;
            cursor: pointer;
            transition: var(--transition);
        }

        .close-ad:hover {
            color: var(--iris);
        }

        .ad-content {
            flex: 1;
            background-color: var(--navy-light);
            border-radius: var(--radius);
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
        }

        .ad-content iframe {
            width: 100%;
            height: 100%;
            border: none;
        }

        .redirect-message {
            margin-top: 20px;
            text-align: center;
            font-size: 14px;
            opacity: 0.7;
        }

        /* ==== FOOTER ==== */
        footer {
            background-color: var(--navy);
            padding: 60px 0 20px;
            margin-top: 60px;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-column h3 {
            font-size: 20px;
            margin-bottom: 20px;
            color: var(--white);
        }

        .footer-column p {
            margin-bottom: 15px;
            opacity: 0.8;
        }

        .footer-links {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 10px;
        }

        .footer-links a {
            transition: var(--transition);
            opacity: 0.8;
        }

        .footer-links a:hover {
            opacity: 1;
            color: var(--iris);
        }

        .social-links {
            display: flex;
            gap: 15px;
        }

        .social-links a {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background-color: var(--navy-light);
            border-radius: 50%;
            transition: var(--transition);
        }

        .social-links a:hover {
            background-color: var(--iris);
            transform: translateY(-3px);
        }

        .copyright {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid var(--navy-light);
            opacity: 0.7;
            font-size: 14px;
        }

        /* ==== RESPONSIVE STYLES ==== */
        @media (max-width: 992px) {
            .hero h1 {
                font-size: 36px;
            }
        }

        @media (max-width: 768px) {
            .nav-menu {
                position: fixed;
                top: 80px;
                left: -100%;
                width: 100%;
                height: calc(100vh - 80px);
                background-color: var(--navy);
                flex-direction: column;
                align-items: center;
                justify-content: flex-start;
                padding-top: 40px;
                transition: var(--transition);
            }

            .nav-menu.active {
                left: 0;
            }

            .nav-menu li {
                margin: 15px 0;
            }

            .hamburger {
                display: flex;
            }

            .hamburger.active span:nth-child(1) {
                transform: translateY(8px) rotate(45deg);
            }

            .hamburger.active span:nth-child(2) {
                opacity: 0;
            }

            .hamburger.active span:nth-child(3) {
                transform: translateY(-8px) rotate(-45deg);
            }

            .hero h1 {
                font-size: 32px;
            }

            .hero p {
                font-size: 18px;
            }
        }

        @media (max-width: 576px) {
            .hero {
                padding: 60px 0;
            }

            .hero h1 {
                font-size: 28px;
            }

            .section-title {
                font-size: 26px;
            }

            .product-card {
                max-width: 100%;
            }
        }
    </style>
</head>
<body>
    <!-- Header Section -->
    <header>
        <div class="container header-container">
            <a href="#" class="logo">Prime<span>Shop</span></a>
            <div class="hamburger">
                <span></span>
                <span></span>
                <span></span>
            </div>
            <ul class="nav-menu">
                <li><a href="#">Home</a></li>
                <li><a href="#categories">Categories</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container hero-content">
            <h1>Discover Premium Products</h1>
            <p>Curated selection of the best Amazon products with exclusive deals</p>
            <a href="#products" class="btn">Shop Now</a>
        </div>
    </section>

    <!-- Search Section -->
    <section class="search-section">
        <div class="container search-container">
            <div class="search-bar">
                <input type="text" id="search-input" placeholder="Search products...">
                <button id="search-button">
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <circle cx="11" cy="11" r="8"></circle>
                        <line x1="21" y1="21" x2="16.65" y2="16.65"></line>
                    </svg>
                </button>
            </div>
        </div>
    </section>

    <!-- Products Section -->
    <section class="products-section" id="products">
        <div class="container">
            <h2 class="section-title">Featured Products</h2>
            <div class="products-grid" id="products-grid">
                <!-- Products will be dynamically inserted here -->
            </div>
        </div>
    </section>

    <!-- Ad Overlay -->
    <div class="overlay" id="ad-overlay">
        <div class="ad-container">
            <div class="ad-header">
                <h3 class="ad-title">Sponsored Content</h3>
                <button class="close-ad" id="close-ad">&times;</button>
            </div>
            <div class="ad-content">
                <!-- Ad will be loaded here -->
                <iframe id="ad-iframe" frameborder="0" scrolling="no"></iframe>
            </div>
            <p class="redirect-message">You will be redirected to the product page shortly...</p>
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>About PrimeShop</h3>
                    <p>We curate the best products from Amazon to help you make informed purchasing decisions.</p>
                    <div class="social-links">
                        <a href="#" aria-label="Facebook">
                            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                                <path d="M18 2h-3a5 5 0 0 0-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 0 1 1-1h3z"></path>
                            </svg>
                        </a>
                        <a href="#" aria-label="Twitter">
                            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                                <path d="M23 3a10.9 10.9 0 0 1-3.14 1.53 4.48 4.48 0 0 0-7.86 3v1A10.66 10.66 0 0 1 3 4s-4 9 5 13a11.64 11.64 0 0 1-7 2c9 5 20 0 20-11.5a4.5 4.5 0 0 0-.08-.83A7.72 7.72 0 0 0 23 3z"></path>
                            </svg>
                        </a>
                        <a href="#" aria-label="Instagram">
                            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                                <rect x="2" y="2" width="20" height="20" rx="5" ry="5"></rect>
                                <path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"></path>
                                <line x1="17.5" y1="6.5" x2="17.51" y2="6.5"></line>
                            </svg>
                        </a>
                    </div>
                </div>
                <div class="footer-column">
                    <h3>Quick Links</h3>
                    <ul class="footer-links">
                        <li><a href="#">Home</a></li>
                        <li><a href="#categories">Categories</a></li>
                        <li><a href="#about">About Us</a></li>
                        <li><a href="#contact">Contact</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Information</h3>
                    <ul class="footer-links">
                        <li><a href="#">Privacy Policy</a></li>
                        <li><a href="#">Terms of Service</a></li>
                        <li><a href="#">Affiliate Disclosure</a></li>
                        <li><a href="#">Shipping Info</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Contact Us</h3>
                    <p>Email: info@primeshop.com</p>
                    <p>Phone: (123) 456-7890</p>
                    <p>Address: 123 Store St, City, Country</p>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2023 PrimeShop. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <script>
        // ===== CONFIGURATION =====
        // Change these values as needed
        const config = {
            adLink: "https://www.profitableratecpm.com/mxwvpffp0n?key=fc7e79075620650c6d87", // Adsterra ad link
            redirectDelay: 8000, // Delay in milliseconds (8000ms = 8 seconds)
            products: [
                {
                    id: 1,
                    title: "Wireless Bluetooth Earbuds",
                    description: "Premium sound quality with noise cancellation and 24hr battery life.",
                    price: "$59.99",
                    image: "https://m.media-amazon.com/images/I/61SUj2aKoEL._AC_UL320_.jpg",
                    amazonLink: "https://www.amazon.com/dp/B08C5HYHB2?tag=yourtag-20", // Replace with your affiliate link
                    category: "electronics"
                },
                {
                    id: 2,
                    title: "Smart Fitness Tracker",
                    description: "Track your heart rate, steps, sleep and more with this advanced fitness band.",
                    price: "$39.95",
                    image: "https://m.media-amazon.com/images/I/71Swqqe7XAL._AC_UL320_.jpg",
                    amazonLink: "https://www.amazon.com/dp/B08DFPZG71?tag=yourtag-20", // Replace with your affiliate link
                    category: "fitness"
                },
                {
                    id: 3,
                    title: "Stainless Steel Water Bottle",
                    description: "Keep your drinks cold for 24 hours or hot for 12 hours with this durable bottle.",
                    price: "$24.99",
                    image: "https://m.media-amazon.com/images/I/71gGPRRlyTL._AC_UL320_.jpg",
                    amazonLink: "https://www.amazon.com/dp/B01N4SAD60?tag=yourtag-20", // Replace with your affiliate link
                    category: "home"
                },
                {
                    id: 4,
                    title: "Organic Cotton T-Shirt",
                    description: "Comfortable and eco-friendly t-shirt made from 100% organic cotton.",
                    price: "$19.99",
                    image: "https://m.media-amazon.com/images/I/61-jBuhtgZL._AC_UL320_.jpg",
                    amazonLink: "https://www.amazon.com/dp/B07P5BNB3F?tag=yourtag-20", // Replace with your affiliate link
                    category: "clothing"
                },
                {
                    id: 5,
                    title: "Portable Bluetooth Speaker",
                    description: "Waterproof speaker with 20hr playtime and rich bass sound.",
                    price: "$45.50",
                    image: "https://m.media-amazon.com/images/I/71HOV3yQ3AL._AC_UL320_.jpg",
                    amazonLink: "https://www.amazon.com/dp/B07VX4BWRW?tag=yourtag-20", // Replace with your affiliate link
                    category: "electronics"
                },
                {
                    id: 6,
                    title: "Memory Foam Pillow",
                    description: "Ergonomic pillow for neck pain relief and better sleep.",
                    price: "$34.99",
                    image: "https://m.media-amazon.com/images/I/61XxJ9t3VBL._AC_UL320_.jpg",
                    amazonLink: "https://www.amazon.com/dp/B07QK1CW5Q?tag=yourtag-20", // Replace with your affiliate link
                    category: "home"
                }
            ]
        };

        // ===== GLOBAL VARIABLES =====
        let currentProductLink = "";
        let redirectTimer = null;

        // ===== DOM ELEMENTS =====
        const hamburger = document.querySelector('.hamburger');
        const navMenu = document.querySelector('.nav-menu');
        const productsGrid = document.getElementById('products-grid');
        const searchInput = document.getElementById('search-input');
        const searchButton = document.getElementById('search-button');
        const adOverlay = document.getElementById('ad-overlay');
        const closeAd = document.getElementById('close-ad');
        const adIframe = document.getElementById('ad-iframe');

        // ===== EVENT LISTENERS =====
        document.addEventListener('DOMContentLoaded', () => {
            // Load products when page loads
            displayProducts(config.products);
            
            // Mobile menu toggle
            hamburger.addEventListener('click', () => {
                hamburger.classList.toggle('active');
                navMenu.classList.toggle('active');
            });
            
            // Close mobile menu when clicking a link
            document.querySelectorAll('.nav-menu a').forEach(link => {
                link.addEventListener('click', () => {
                    hamburger.classList.remove('active');
                    navMenu.classList.remove('active');
                });
            });
            
            // Search functionality
            searchButton.addEventListener('click', filterProducts);
            searchInput.addEventListener('keyup', (e) => {
                if (e.key === 'Enter') {
                    filterProducts();
                }
            });
            
            // Close ad overlay
            closeAd.addEventListener('click', closeAdOverlay);
        });

        // ===== FUNCTIONS =====
        
        /**
         * Display products in the grid
         * @param {Array} products - Array of product objects
         */
        function displayProducts(products) {
            productsGrid.innerHTML = '';
            
            if (products.length === 0) {
                productsGrid.innerHTML = '<p class="no-products">No products found. Try a different search.</p>';
                return;
            }
            
            products.forEach(product => {
                const productCard = document.createElement('div');
                productCard.className = 'product-card';
                productCard.innerHTML = `
                    <div class="product-image">
                        <img src="${product.image}" alt="${product.title}" loading="lazy">
                    </div>
                    <div class="product-info">
                        <h3 class="product-title">${product.title}</h3>
                        <div class="product-price">${product.price}</div>
                        <p class="product-description">${product.description}</p>
                        <button class="btn shop-now" data-id="${product.id}">Shop Now</button>
                    </div>
                `;
                
                productsGrid.appendChild(productCard);
            });
            
            // Add event listeners to all "Shop Now" buttons
            document.querySelectorAll('.shop-now').forEach(button => {
                button.addEventListener('click', (e) => {
                    const productId = parseInt(e.target.getAttribute('data-id'));
                    const product = config.products.find(p => p.id === productId);
                    if (product) {
                        showAdOverlay(product.amazonLink);
                    }
                });
            });
        }
        
        /**
         * Filter products based on search input
         */
        function filterProducts() {
            const searchTerm = searchInput.value.toLowerCase();
            const filteredProducts = config.products.filter(product => {
                return (
                    product.title.toLowerCase().includes(searchTerm) ||
                    product.description.toLowerCase().includes(searchTerm) ||
                    product.category.toLowerCase().includes(searchTerm)
                );
            });
            
            displayProducts(filteredProducts);
        }
        
        /**
         * Show ad overlay and set up redirect
         * @param {string} productLink - Amazon affiliate link to redirect to
         */
        function showAdOverlay(productLink) {
            currentProductLink = productLink;
            adIframe.src = config.adLink;
            adOverlay.classList.add('active');
            
            // Start the redirect timer
            redirectTimer = setTimeout(() => {
                redirectToProduct();
            }, config.redirectDelay);
        }
        
        /**
         * Close ad overlay and cancel redirect
         */
        function closeAdOverlay() {
            adOverlay.classList.remove('active');
            adIframe.src = '';
            
            // Clear the redirect timer
            if (redirectTimer) {
                clearTimeout(redirectTimer);
                redirectTimer = null;
            }
            
            // Redirect immediately when user closes the ad
            redirectToProduct();
        }
        
        /**
         * Redirect to the Amazon product page
         */
        function redirectToProduct() {
            window.location.href = currentProductLink;
        }
    </script>
</body>
</html>
