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
    font-size: 0.9em;
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


.price {
    font-weight: bold;
    color: #008000; /* Green for positive prices */
    font-size: 1.1em; /* Slightly larger for emphasis */
  }
  
  .old-price {
    text-decoration: line-through;
    color: #808080; /* Gray for old prices */
    font-size: 0.9em;
  }
  
  .discount {
    color: red;
    font-weight: bold; /* Make the discount stand out */
    font-size: 0.9em; /* slightly smaller, but bold */
  }
  
  .currency {
    font-family: monospace; /* Monospace for currency symbols */
    margin-right: 2px; /* Add a little space after the symbol */
  }
  
  /* Optional: Styles for larger numbers */
  .price.large-number {
    letter-spacing: 0.05em; /* Add a little space between digits */
  }
  
  /* Optional: Style for free */
  .price.free {
    color: #00008B; /* Dark blue for "Free" */
    font-style: italic;
  }
  
  /* Optional: Styles for price ranges */
  .price.range-separator {
    margin: 0 5px; /* Add space around the range separator */
  }
  
  /* Optional: style for many decimal places */
  .price.many-decimals {
    font-size: 0.8em;
  }
  
  /* Optional: hover effect */
  .price:hover {
    text-decoration: underline; /* underline on hover */
    cursor: pointer; /* Change cursor to pointer */
  }
  
  /* Optional: style for different currencies */
  .price.euro {
    color: #0000CD; /* medium blue for Euros */
  }
  
  price.pound {
    color: #8B0000; /* dark red for pounds */
  }
  
  price.yen {
    color: #2F4F4F; /* Dark slate gray for yen */
  }


  function formatCurrency(amount, currencySymbol = '$', decimalPlaces = 2, thousandsSeparator = ',', decimalSeparator = '.') {
    if (typeof amount !== 'number') {
      return 'Invalid Amount';
    }
  
    const formattedAmount = amount.toLocaleString('en-US', {
      minimumFractionDigits: decimalPlaces,
      maximumFractionDigits: decimalPlaces,
    });
  
    // Replace default separators if needed
    let result = formattedAmount;
    if (thousandsSeparator !== ',') {
      result = result.replace(/,/g, thousandsSeparator);
    }
    if (decimalSeparator !== '.') {
      result = result.replace(/\./g, decimalSeparator);
    }
  
    return currencySymbol + result;
  }
  
  function displayPrice(elementId, amount, currencySymbol, decimalPlaces, thousandsSeparator, decimalSeparator) {
    const element = document.getElementById(elementId);
    if (element) {
      element.textContent = formatCurrency(amount, currencySymbol, decimalPlaces, thousandsSeparator, decimalSeparator);
    } else {
      console.error(`Element with ID '${elementId}' not found.`);
    }
  }
  
  // Example usage:
  document.addEventListener('DOMContentLoaded', function() {
    const price1 = 19.99;
    const price2 = 1234.56;
    const price3 = 9.95;
    const price4 = 1000000;
    const price5 = 0;
    const price6 = 12.345678;
  
    // Create HTML elements for demonstration
    document.body.innerHTML += `
      <p>Price 1: <span id="price1"></span></p>
      <p>Price 2: <span id="price2"></span></p>
      <p>Price 3 (Euro): <span id="price3"></span></p>
      <p>Price 4 (Large): <span id="price4"></span></p>
      <p>Price 5 (Zero): <span id="price5"></span></p>
      <p>Price 6 (Many decimals): <span id="price6"></span></p>
      <p>Price 7 (Custom): <span id="price7"></span></p>
    `;
  
    displayPrice('price1', price1);
    displayPrice('price2', price2);
    displayPrice('price3', price3, '€');
    displayPrice('price4', price4);
    displayPrice('price5', price5);
    displayPrice('price6', price6, '$', 8);
    displayPrice('price7', 1234.56, 'R$', 2, '.', ','); // Example with Brazilian Real formatting
  });
