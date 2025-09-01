/* Main SmartShopper layout */
#smartShopperPage {
    max-width: 1200px;
    margin: 30px auto;
    display: none;
}
#productsGridControls {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin: 20px 0;
}
#categories {
    display: flex;
    gap: 15px;
    overflow-x: auto;
    padding-bottom: 8px;
}
#categories button {
    background: #e7e7e7;
    border: none;
    padding: 10px 18px;
    border-radius: 20px;
    cursor: pointer;
    font-weight: bold;
    white-space: nowrap;
}
#categories button.active {
    background: #232f3e;
    color: white;
}
#sortDropdown {
    padding: 8px 12px;
    border-radius: 4px;
    border: 1px solid #ccc;
    font-size: 1em;
}
#productsGrid {
    display: grid;
    grid-template-columns: repeat(auto-fill,minmax(200px,1fr));
    gap: 20px;
}
.productCard {
    border: 1px solid #ddd;
    border-radius: 10px;
    padding: 10px;
    display: flex;
    flex-direction: column;
    background: white;
    transition: box-shadow 0.3s ease;
    cursor: pointer;
}
.productCard:hover {
    box-shadow: 0 2px 10px rgba(0,0,0,0.15);
}
.productImage {
    width: 100%;
    height: 140px;
    object-fit: contain;
    border-radius: 6px;
}
.productName {
    font-weight: 700;
    margin: 12px 0 6px 0;
    flex-grow: 1;
}
.productPrice {
    color: #0a7d01;
    font-weight: bold;
    font-size: 1.1em;
}
.addToCartBtn {
    margin-top: 10px;
    background: #f0c14b;
    border: 1px solid #a88734;
    border-radius: 4px;
    cursor: pointer;
    padding: 6px;
    font-weight: 600;
}
.addToCartBtn:hover {
    background: #ddb347;
}

/* Orders, Cart, and Product Detail Sections */
#ordersSection, #cartPage, #productDetailPage {
    max-width: 1200px;
    margin: 40px auto;
}
#ordersSection h3, #cartPage h2, #productDetailPage h2 {
    margin-bottom: 10px;
}
table {
    width: 100%;
    border-collapse: collapse;
    font-size: 0.9em;
}
th, td {
    border: 1px solid #ccc;
    padding: 8px;
    text-align: center;
}
th {
    background-color: #232f3e;
    color: white;
}

#cartItems {
    display: flex;
    flex-direction: column;
    gap: 15px;
    margin-bottom: 20px;
}
#cartItems > div {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px;
    border: 1px solid #ddd;
    border-radius: 5px;
    background: #f9f9f9;
}
#checkoutBtn, #backToHomeBtn, #addToCartDetailBtn {
    width: 100%;
    padding: 12px;
    font-size: 1.1em;
}
#productDetailContent {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 20px;
    margin-top: 20px;
    padding: 20px;
    border: 1px solid #ddd;
    border-radius: 10px;
    background: #f9f9f9;
}
#detailImage {
    max-width: 300px;
    max-height: 300px;
    object-fit: contain;
}

/* Profile page */
#profilePage {
    max-width: 450px;
    margin: 40px auto;
    background: #f9f9f9;
    padding: 25px;
    border-radius: 8px;
    box-shadow: 0 0 8px rgba(0,0,0,0.1);
    display: none;
}
#profilePage h2 {
    margin-bottom: 15px;
    text-align: center;
}
#profilePage p {
    margin: 10px 0;
    font-weight: 600;
}
#logoutBtn, #logoutBtnProfile {
    background-color: #d9534f;
    color: white;
    border: none;
    padding: 10px;
    width: 100%;
    border-radius: 6px;
    cursor: pointer;
    margin-top: 25px;
    font-weight: bold;
}
#logoutBtn:hover, #logoutBtnProfile:hover {
    background-color: #c9302c;
}
/* Notification Message Box */
#notificationBox {
    position: fixed;
    bottom: 20px;
    right: 20px;
    background-color: #232f3e;
    color: white;
    padding: 15px 25px;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0,0,0,0.2);
    z-index: 1000;
    opacity: 0;
    visibility: hidden;
    transition: opacity 0.5s ease, visibility 0.5s ease;
}
#notificationBox.show {
    opacity: 1;
    visibility: visible;
}
