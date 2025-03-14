<!DOCTYPE html>
<html>
<head>
<title>Money/Price Example</title>
<head>
    <link rel="stylesheet" href="styles.css">
  </head>
<style>
  .price {
    font-weight: bold;
    color: #008000; /* Green for positive prices */
  }
  .old-price {
    text-decoration: line-through;
    color: #808080; /* Gray for old prices */
    font-size: 0.9ng;
  }
  .discount {
    color: red;
  }
  .currency {
    font-family: monospace; /* Monospace for currency symbols */
  }
</style>
</head>
<body>

<h1>Product Prices</h1>

<p>Regular Product: <span class="price"><span class="currency">$</span>19.99</span></p>

<p>On Sale Product: <span class="old-price"><span class="currency">$</span>29.99</span> <span class="price"><span class="currency">$</span>24.99</span> <span class="discount">(Save 16%)</span></p>

<p>Another Product: <span class="price"><span class="currency">€</span>15.50</span></p>

<p>Special Offer: <span class="price"><span class="currency">£</span>9.95</span></p>

<p>Big number: <span class="price"><span class="currency">$</span>1,234,567.89</span></p>

<p>Zero price: <span class="price"><span class="currency">$</span>0.00</span></p>

<p>Free: <span class="price">Free</span></p>

<p>Price range: <span class="price"><span class="currency">$</span>10 - <span class="currency">$</span>20</span></p>

<p>Price with cents: <span class="price"><span class="currency">$</span>12.34</span></p>

<p>Price with many decimal places (for demonstration): <span class="price"><span class="currency">$</span>12.345678</span></p>

<p>Price with different currency symbol: <span class="price"><span class="currency">¥</span>1000</span></p>

</body>
</html>
