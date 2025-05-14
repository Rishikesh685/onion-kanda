# onion-kanda<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Onion Price Tracker – Maharashtra</title>
  <style>
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: #f4f4f4;
      margin: 0;
      padding: 20px;
    }
    .container {
      max-width: 700px;
      margin: auto;
      background: #fff;
      padding: 30px;
      border-radius: 8px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }
    h1 {
      text-align: center;
      color: #333;
    }
    select, button {
      padding: 10px;
      font-size: 16px;
      margin-top: 10px;
      width: 100%;
      box-sizing: border-box;
    }
    .price-display {
      margin-top: 20px;
      padding: 15px;
      background: #e0f7fa;
      border-left: 5px solid #00796b;
    }
    .price-display p {
      margin: 5px 0;
    }
    footer {
      text-align: center;
      margin-top: 40px;
      color: #777;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>🧅 Onion Price Tracker – Maharashtra</h1>
    <label for="market">Select Market:</label>
    <select id="market">
      <option value="Pune">Pune</option>
      <option value="Nashik">Nashik</option>
      <option value="Lasalgaon">Lasalgaon</option>
      <option value="Nagpur">Nagpur</option>
      <option value="Kolhapur">Kolhapur</option>
    </select>
    <button onclick="fetchPrice()">Get Latest Price</button>
    <div id="priceDisplay" class="price-display" style="display:none;"></div>
  </div>
  <footer>
    &copy; 2025 Onion Price Tracker. Data sourced from <a href="https://www.commodityonline.com/mandiprices/onion/maharashtra" target="_blank">Commodity Online</a>.
  </footer>

  <script>
    async function fetchPrice() {
      const market = document.getElementById('market').value;
      const priceDisplay = document.getElementById('priceDisplay');
      priceDisplay.style.display = 'none';
      priceDisplay.innerHTML = 'Fetching latest prices...';

      try {
        // Simulated data fetch - Replace this with actual API call if available
        const data = {
          "Pune": { avg: 1000, min: 500, max: 1500 },
          "Nashik": { avg: 1100, min: 600, max: 1600 },
          "Lasalgaon": { avg: 1150, min: 700, max: 1700 },
          "Nagpur": { avg: 1050, min: 550, max: 1550 },
          "Kolhapur": { avg: 950, min: 500, max: 1400 }
        };

        const marketData = data[market];

        priceDisplay.style.display = 'block';
        priceDisplay.innerHTML = `
          <p><strong>Market:</strong> ${market}</p>
          <p><strong>Average Price:</strong> ₹${marketData.avg}/Quintal</p>
          <p><strong>Minimum Price:</strong> ₹${marketData.min}/Quintal</p>
          <p><strong>Maximum Price:</strong> ₹${marketData.max}/Quintal</p>
        `;
      } catch (error) {
        priceDisplay.style.display = 'block';
        priceDisplay.innerHTML = 'Error fetching data. Please try again later.';
        console.error('Error:', error);
      }
    }
  </script>
</body>
</html>
