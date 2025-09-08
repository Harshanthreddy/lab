<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Smart Shopper</title>
    <!-- Inter font -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f0f2f5;
        }
    </style>
</head>
<body class="min-h-screen">

    <!-- Header Navigation -->
    <header class="bg-[#232f3e] text-white p-4">
        <nav class="flex items-center justify-between max-w-7xl mx-auto">
            <div class="flex items-center gap-4">
                <a href="#" id="homeNav" class="text-xl font-bold hover:text-gray-300">Smart Shopper</a>
                <button id="cartNav" class="relative hover:text-gray-300">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M3 3h2l.4 2M7 13h10l4-8H5.4M7 13L5.4 5M7 13v10h10v-10m-2 0V7m-4 0v6" />
                    </svg>
                    <span id="cartCount" class="absolute -top-2 -right-2 bg-red-500 text-xs text-white font-bold rounded-full h-4 w-4 flex items-center justify-center">0</span>
                </button>
            </div>
            <div class="flex items-center gap-4">
                <button id="ordersNav" class="hover:text-gray-300">Orders</button>
                <button id="profileNav" class="hover:text-gray-300">Profile</button>
            </div>
        </nav>
    </header>

    <!-- Main Content Sections -->
    <main class="container mx-auto px-4 mt-8">

        <!-- SmartShopper Page -->
        <section id="smartShopperPage" class="max-w-7xl mx-auto p-4 bg-white rounded-lg shadow-md">
            <div id="productsGridControls" class="flex flex-col md:flex-row md:items-center justify-between mb-6 gap-4">
                <div id="categories" class="flex flex-wrap gap-2 overflow-x-auto pb-2">
                    <!-- Categories will be added here dynamically -->
                </div>
                <div class="flex items-center gap-2">
                    <label for="sortDropdown" class="text-sm font-medium text-gray-700">Sort by:</label>
                    <select id="sortDropdown" class="p-2 border border-gray-300 rounded-md text-sm shadow-sm focus:ring-blue-500 focus:border-blue-500">
                        <option value="name">Name</option>
                        <option value="priceLowToHigh">Price (Low to High)</option>
                        <option value="priceHighToLow">Price (High to Low)</option>
                    </select>
                </div>
            </div>

            <div id="productsGrid" class="grid grid-cols-2 sm:grid-cols-3 lg:grid-cols-4 gap-4">
                <!-- Product cards will be added here dynamically -->
            </div>
        </section>

        <!-- Product Detail Page -->
        <section id="productDetailPage" class="hidden max-w-3xl mx-auto p-6 bg-white rounded-lg shadow-lg">
            <button id="backToHomeBtn" class="mb-4 text-blue-600 hover:underline flex items-center">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4 mr-1" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M15 19l-7-7 7-7" />
                </svg>
                Back to Products
            </button>
            <div id="productDetailContent" class="flex flex-col md:flex-row items-center md:items-start gap-6">
                <img id="detailImage" class="w-full h-auto md:max-w-sm rounded-lg shadow-md object-contain" src="" alt="Product Image">
                <div class="flex flex-col flex-1 w-full">
                    <h2 id="detailName" class="text-3xl font-bold text-gray-800 mb-2">Product Name</h2>
                    <p id="detailDescription" class="text-gray-600 mb-4 flex-grow">Product Description</p>
                    <div class="flex items-center justify-between mb-4">
                        <p id="detailPrice" class="text-2xl font-bold text-green-600">$99.99</p>
                        <span id="detailCategory" class="text-sm text-gray-500 bg-gray-100 px-3 py-1 rounded-full">Category</span>
                    </div>
                    <button id="addToCartDetailBtn" class="bg-[#f0c14b] text-[#111827] font-semibold py-3 px-6 rounded-lg hover:bg-[#ddb347] transition-colors duration-200">
                        Add to Cart
                    </button>
                </div>
            </div>
        </section>

        <!-- Cart Page -->
        <section id="cartPage" class="hidden max-w-3xl mx-auto p-6 bg-white rounded-lg shadow-lg">
            <h2 class="text-2xl font-bold mb-4">Your Shopping Cart</h2>
            <div id="cartItems" class="space-y-4 mb-6">
                <!-- Cart items will be rendered here -->
            </div>
            <div class="flex justify-between items-center text-lg font-semibold mb-6 border-t border-gray-200 pt-4">
                <span>Total:</span>
                <span id="cartTotal">$0.00</span>
            </div>
            <button id="checkoutBtn" class="w-full bg-blue-600 text-white font-semibold py-3 px-6 rounded-lg hover:bg-blue-700 transition-colors duration-200">
                Proceed to Checkout
            </button>
        </section>

        <!-- Orders Section -->
        <section id="ordersSection" class="hidden max-w-3xl mx-auto p-6 bg-white rounded-lg shadow-lg">
            <h2 class="text-2xl font-bold mb-4">Your Orders</h2>
            <div id="ordersList" class="space-y-4">
                <!-- Orders history will be shown here -->
                <p class="text-center text-gray-500">No orders found.</p>
            </div>
        </section>

        <!-- Profile Page -->
        <section id="profilePage" class="hidden max-w-sm mx-auto p-6 bg-white rounded-lg shadow-lg">
            <h2 class="text-2xl font-bold text-center mb-6">User Profile</h2>
            <div class="space-y-4">
                <div>
                    <p class="text-sm font-semibold text-gray-600">User ID:</p>
                    <p id="profileUserId" class="bg-gray-100 p-2 rounded-md font-mono text-xs break-all"></p>
                </div>
                <div>
                    <p class="text-sm font-semibold text-gray-600">Email:</p>
                    <p id="profileEmail" class="bg-gray-100 p-2 rounded-md font-mono text-xs break-all">Not available</p>
                </div>
            </div>
            <button id="logoutBtnProfile" class="w-full bg-red-500 text-white font-semibold py-3 px-6 rounded-lg hover:bg-red-600 transition-colors duration-200 mt-6">
                Log Out
            </button>
        </section>

    </main>

    <!-- Notification Message Box -->
    <div id="notificationBox" class="fixed bottom-4 right-4 bg-gray-800 text-white py-3 px-6 rounded-lg shadow-xl opacity-0 transition-opacity duration-300 pointer-events-none">
        Item added to cart!
    </div>
    
    <script>
        const products = [
            { id: 1, name: 'Wireless Ergonomic Mouse', price: 29.99, image: 'https://placehold.co/150x150/EAEAEA/333333?text=Mouse', category: 'Electronics' },
            { id: 2, name: 'HD Webcam 1080p', price: 45.50, image: 'https://placehold.co/150x150/F2F2F2/333333?text=Webcam', category: 'Electronics' },
            { id: 3, name: 'Noise-Cancelling Headphones', price: 199.00, image: 'https://placehold.co/150x150/DCDCDC/333333?text=Headphones', category: 'Electronics' },
            { id: 4, name: 'Portable Bluetooth Speaker', price: 59.99, image: 'https://placehold.co/150x150/E6E6E6/333333?text=Speaker', category: 'Electronics' },
            { id: 5, name: 'Stainless Steel Water Bottle', price: 15.00, image: 'https://placehold.co/150x150/F5F5F5/333333?text=Bottle', category: 'Home & Kitchen' },
            { id: 6, name: 'Microfiber Cleaning Cloths (12-pack)', price: 9.99, image: 'https://placehold.co/150x150/EAEAEA/333333?text=Cloths', category: 'Home & Kitchen' },
            { id: 7, name: 'Digital Air Fryer', price: 89.99, image: 'https://placehold.co/150x150/DCDCDC/333333?text=Fryer', category: 'Home & Kitchen' },
            { id: 8, name: 'Organic Coffee Beans', price: 12.50, image: 'https://placehold.co/150x150/E6E6E6/333333?text=Coffee', category: 'Grocery' },
            { id: 9, name: 'Resistance Bands Set', price: 24.99, image: 'https://placehold.co/150x150/F2F2F2/333333?text=Bands', category: 'Sports & Outdoors' },
            { id: 10, name: 'Yoga Mat', price: 35.00, image: 'https://placehold.co/150x150/F5F5F5/333333?text=Yoga+Mat', category: 'Sports & Outdoors' },
        ];

        let cart = [];
        let currentPage = 'smartShopperPage';
        let currentProduct = null;
        let userId = 'user_001'; // Mock user ID

        const elements = {
            smartShopperPage: document.getElementById('smartShopperPage'),
            productDetailPage: document.getElementById('productDetailPage'),
            cartPage: document.getElementById('cartPage'),
            ordersSection: document.getElementById('ordersSection'),
            profilePage: document.getElementById('profilePage'),
            
            productsGrid: document.getElementById('productsGrid'),
            categoriesContainer: document.getElementById('categories'),
            sortDropdown: document.getElementById('sortDropdown'),
            
            homeNav: document.getElementById('homeNav'),
            cartNav: document.getElementById('cartNav'),
            ordersNav: document.getElementById('ordersNav'),
            profileNav: document.getElementById('profileNav'),
            cartCount: document.getElementById('cartCount'),
            
            backToHomeBtn: document.getElementById('backToHomeBtn'),
            addToCartDetailBtn: document.getElementById('addToCartDetailBtn'),
            
            cartItems: document.getElementById('cartItems'),
            cartTotal: document.getElementById('cartTotal'),
            checkoutBtn: document.getElementById('checkoutBtn'),
            
            detailImage: document.getElementById('detailImage'),
            detailName: document.getElementById('detailName'),
            detailDescription: document.getElementById('detailDescription'),
            detailPrice: document.getElementById('detailPrice'),
            detailCategory: document.getElementById('detailCategory'),
            
            notificationBox: document.getElementById('notificationBox'),
            profileUserId: document.getElementById('profileUserId'),
            profileEmail: document.getElementById('profileEmail'),
            logoutBtnProfile: document.getElementById('logoutBtnProfile'),
        };

        const showNotification = (message) => {
            const notificationBox = elements.notificationBox;
            notificationBox.textContent = message;
            notificationBox.classList.add('opacity-100', 'pointer-events-auto');
            setTimeout(() => {
                notificationBox.classList.remove('opacity-100', 'pointer-events-auto');
            }, 2000);
        };

        const renderProducts = (filteredProducts) => {
            elements.productsGrid.innerHTML = '';
            filteredProducts.forEach(product => {
                const productCard = document.createElement('div');
                productCard.className = 'productCard bg-white p-4 rounded-lg shadow-md hover:shadow-lg transition-shadow cursor-pointer flex flex-col';
                productCard.innerHTML = `
                    <img src="${product.image}" alt="${product.name}" class="productImage w-full h-36 object-contain rounded-md">
                    <div class="productName font-semibold text-lg mt-3 flex-grow">${product.name}</div>
                    <div class="productPrice text-green-600 font-bold text-xl">$${product.price.toFixed(2)}</div>
                    <button class="addToCartBtn w-full mt-3 bg-yellow-400 text-gray-800 font-semibold py-2 rounded-lg hover:bg-yellow-500 transition-colors duration-200">
                        Add to Cart
                    </button>
                `;
                
                // Add click event for product detail view
                productCard.querySelector('.productImage, .productName').addEventListener('click', () => showProductDetail(product.id));
                productCard.querySelector('.addToCartBtn').addEventListener('click', (e) => {
                    e.stopPropagation(); // Prevents the detail view from opening
                    addToCart(product);
                    showNotification('Item added to cart!');
                });
                elements.productsGrid.appendChild(productCard);
            });
        };

        const renderCategories = () => {
            const categories = ['All', ...new Set(products.map(p => p.category))];
            elements.categoriesContainer.innerHTML = categories.map(cat => `
                <button class="categoryBtn bg-gray-200 text-gray-800 font-semibold py-2 px-4 rounded-full hover:bg-gray-300 transition-colors duration-200" data-category="${cat}">${cat}</button>
            `).join('');

            document.querySelectorAll('.categoryBtn').forEach(button => {
                button.addEventListener('click', () => {
                    document.querySelectorAll('.categoryBtn').forEach(btn => btn.classList.remove('bg-gray-800', 'text-white'));
                    button.classList.add('bg-gray-800', 'text-white');
                    filterAndSortProducts(button.dataset.category, elements.sortDropdown.value);
                });
            });
        };

        const filterAndSortProducts = (category, sortBy) => {
            let filtered = products;
            if (category && category !== 'All') {
                filtered = products.filter(p => p.category === category);
            }

            switch(sortBy) {
                case 'name':
                    filtered.sort((a, b) => a.name.localeCompare(b.name));
                    break;
                case 'priceLowToHigh':
                    filtered.sort((a, b) => a.price - b.price);
                    break;
                case 'priceHighToLow':
                    filtered.sort((a, b) => b.price - a.price);
                    break;
            }

            renderProducts(filtered);
        };

        const renderCart = () => {
            elements.cartItems.innerHTML = '';
            let total = 0;
            if (cart.length === 0) {
                elements.cartItems.innerHTML = `<p class="text-center text-gray-500">Your cart is empty.</p>`;
                elements.checkoutBtn.disabled = true;
                elements.checkoutBtn.classList.add('opacity-50', 'cursor-not-allowed');
            } else {
                elements.checkoutBtn.disabled = false;
                elements.checkoutBtn.classList.remove('opacity-50', 'cursor-not-allowed');
                cart.forEach(item => {
                    const cartItem = document.createElement('div');
                    cartItem.className = 'flex items-center justify-between p-4 bg-gray-50 rounded-lg shadow-sm';
                    cartItem.innerHTML = `
                        <div class="flex items-center gap-4">
                            <img src="${item.image}" alt="${item.name}" class="w-16 h-16 object-contain rounded-md">
                            <div>
                                <h3 class="font-semibold text-gray-800">${item.name}</h3>
                                <p class="text-gray-500 text-sm">Qty: ${item.quantity}</p>
                            </div>
                        </div>
                        <div class="flex items-center gap-4">
                            <p class="font-bold text-green-600">$${(item.price * item.quantity).toFixed(2)}</p>
                            <button class="remove-from-cart-btn text-red-500 hover:text-red-700 transition-colors duration-200" data-id="${item.id}">
                                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
                                    <path fill-rule="evenodd" d="M9 2a1 1 0 00-.894.553L7.382 4H4a1 1 0 000 2v10a2 2 0 002 2h8a2 2 0 002-2V6a1 1 0 100-2h-3.382l-.724-1.447A1 1 0 0011 2H9zM7 8a1 1 0 012 0v6a1 1 0 11-2 0V8zm6 0a1 1 0 11-2 0v6a1 1 0 112 0V8z" clip-rule="evenodd" />
                                </svg>
                            </button>
                        </div>
                    `;
                    total += item.price * item.quantity;
                    elements.cartItems.appendChild(cartItem);
                });
                document.querySelectorAll('.remove-from-cart-btn').forEach(button => {
                    button.addEventListener('click', (e) => {
                        removeFromCart(parseInt(e.currentTarget.dataset.id));
                    });
                });
            }
            elements.cartTotal.textContent = `$${total.toFixed(2)}`;
            elements.cartCount.textContent = cart.reduce((acc, item) => acc + item.quantity, 0);
        };
        
        const showPage = (pageName) => {
            const pages = [elements.smartShopperPage, elements.productDetailPage, elements.cartPage, elements.ordersSection, elements.profilePage];
            pages.forEach(page => page.classList.add('hidden'));
            const targetPage = elements[pageName];
            if (targetPage) {
                targetPage.classList.remove('hidden');
                currentPage = pageName;
            }
        };

        const showProductDetail = (productId) => {
            currentProduct = products.find(p => p.id === productId);
            if (currentProduct) {
                elements.detailImage.src = currentProduct.image;
                elements.detailName.textContent = currentProduct.name;
                elements.detailDescription.textContent = "A simple product description for the " + currentProduct.name + ". This item is of high quality and great value.";
                elements.detailPrice.textContent = `$${currentProduct.price.toFixed(2)}`;
                elements.detailCategory.textContent = currentProduct.category;
                elements.addToCartDetailBtn.onclick = () => {
                    addToCart(currentProduct);
                    showNotification('Item added to cart!');
                };
                showPage('productDetailPage');
            }
        };

        const addToCart = (product) => {
            const existingItem = cart.find(item => item.id === product.id);
            if (existingItem) {
                existingItem.quantity++;
            } else {
                cart.push({ ...product, quantity: 1 });
            }
            renderCart();
        };

        const removeFromCart = (productId) => {
            cart = cart.filter(item => item.id !== productId);
            renderCart();
        };

        // Event Listeners for Navigation
        elements.homeNav.addEventListener('click', () => {
            showPage('smartShopperPage');
            filterAndSortProducts('All', 'name');
            document.querySelectorAll('.categoryBtn').forEach(btn => btn.classList.remove('bg-gray-800', 'text-white'));
            document.querySelector('.categoryBtn[data-category="All"]').classList.add('bg-gray-800', 'text-white');
        });
        elements.cartNav.addEventListener('click', () => {
            showPage('cartPage');
            renderCart();
        });
        elements.ordersNav.addEventListener('click', () => showPage('ordersSection'));
        elements.profileNav.addEventListener('click', () => {
            showPage('profilePage');
            elements.profileUserId.textContent = userId;
        });
        elements.backToHomeBtn.addEventListener('click', () => showPage('smartShopperPage'));
        elements.sortDropdown.addEventListener('change', (e) => {
            const activeCategoryBtn = document.querySelector('.categoryBtn.bg-gray-800');
            const category = activeCategoryBtn ? activeCategoryBtn.dataset.category : 'All';
            filterAndSortProducts(category, e.target.value);
        });
        
        // Initial setup
        document.addEventListener('DOMContentLoaded', () => {
            renderCategories();
            document.querySelector('.categoryBtn[data-category="All"]').classList.add('bg-gray-800', 'text-white');
            filterAndSortProducts('All', 'name');
            showPage('smartShopperPage');
        });

    </script>
</body>
</html>
