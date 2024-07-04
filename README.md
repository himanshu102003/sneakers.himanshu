Product Slider
This project is a dynamic product slider built with HTML, CSS, and JavaScript. It allows users to browse through different products, view their details, select colors and sizes, and proceed to purchase.

Features
Product Browsing: Users can click on menu items to navigate through different products.
Dynamic Content Update: Product details including title, price, and image are updated dynamically based on user selection.
Color Selection: Users can select different colors for the chosen product and see the corresponding product image.
Size Selection: Users can select sizes for the chosen product, with the selected size highlighted.
Payment Modal: Users can proceed to purchase the product, triggering a payment modal.
Installation
Navigate to the project directory:
sh
Copy code

Open the index.html file in your browser to view the product slider.
Click on different menu items to browse through products.
Select colors and sizes as desired.
Click on the "Buy Now" button to open the payment modal.
Code Explanation
HTML Structure
The sliderWrapper contains all product slides.
Each product has its own slide with an image, title, price, color options, and size options.
JavaScript Functionality
Menu Items Event Listeners:

javascript
Copy code
menuItems.forEach((item, index) => {
  item.addEventListener("click", () => {
    wrapper.style.transform = `translateX(${-100 * index}vw)`;
    choosenProduct = products[index];
    currentProductTitle.textContent = choosenProduct.title;
    currentProductPrice.textContent = "$" + choosenProduct.price;
    currentProductImg.src = choosenProduct.colors[0].img;
    currentProductColors.forEach((color, index) => {
      color.style.backgroundColor = choosenProduct.colors[index].code;
    });
  });
});
Changes the displayed product and updates the product details dynamically.
Color Options Event Listeners:

javascript
Copy code
currentProductColors.forEach((color, index) => {
  color.addEventListener("click", () => {
    currentProductImg.src = choosenProduct.colors[index].img;
  });
});
Updates the product image based on the selected color.
Size Options Event Listeners:

javascript
Copy code
currentProductSizes.forEach((size, index) => {
  size.addEventListener("click", () => {
    currentProductSizes.forEach((size) => {
      size.style.backgroundColor = "white";
      size.style.color = "black";
    });
    size.style.backgroundColor = "black";
    size.style.color = "white";
  });
});
Highlights the selected size.
Payment Modal Event Listeners:

javascript
Copy code
productButton.addEventListener("click", () => {
  payment.style.display = "flex";
});

close.addEventListener("click", () => {
  payment.style.display = "none";
});
Displays and hides the payment modal when the corresponding buttons are clicked.
