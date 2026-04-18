<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Authentic Putharekulu Store</title>
    <style>
        body { font-family: Arial, sans-serif; text-align: center; background-color: #fff9f0; }
        .product-card { border: 1px solid #ddd; padding: 20px; margin: 20px auto; width: 300px; background: white; border-radius: 8px; }
        #order-form { display: none; max-width: 400px; margin: 20px auto; text-align: left; background: white; padding: 20px; border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); }
        input, select { width: 100%; padding: 10px; margin: 10px 0; box-sizing: border-box; }
        button { background-color: #e67e22; color: white; border: none; padding: 10px 20px; cursor: pointer; border-radius: 5px; font-size: 16px; }
        button:hover { background-color: #d35400; }
    </style>
</head>
<body>

    <h1>Welcome to Atreyapuram Putharekulu</h1>
    
    <div id="price-section">
        <div class="product-card">
            <h3>Bellam (Jaggery) Putharekulu</h3>
            <p>Price: ₹300 per 10 pieces</p>
            <button onclick="showForm('Bellam')">Buy Now</button>
        </div>
        <div class="product-card">
            <h3>Dry Fruit Putharekulu</h3>
            <p>Price: ₹500 per 10 pieces</p>
            <button onclick="showForm('Dry Fruit')">Buy Now</button>
        </div>
    </div>

    <div id="order-form">
        <h2>Order Details (<span id="selected-item"></span>)</h2>
        <form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
            <input type="hidden" name="Product" id="product-input">
            
            <label>Full Name</label>
            <input type="text" name="name" required placeholder="Enter your name">
            
            <label>Phone Number</label>
            <input type="tel" name="phone" required placeholder="Enter your mobile number">
            
            <label>Email</label>
            <input type="email" name="email" required placeholder="Enter your email">
            
            <label>Address</label>
            <textarea name="address" required style="width:100%; height:80px;" placeholder="Full delivery address"></textarea>
            
            <label>Quantity (Boxes)</label>
            <input type="number" name="quantity" min="1" value="1" required>

            <label>Payment Option</label>
            <select name="payment_method" required>
                <option value="UPI">UPI (Google Pay / PhonePe/ Upi)</option>
                <option value="COD">Cash on Delivery</option>
            </select>

            <button type="submit">Place Order</button>
        </form>
        <button onclick="location.reload()" style="background:gray; margin-top:10px;">Back to Prices</button>
    </div>

    <script>
        function showForm(itemName) {
            document.getElementById('price-section').style.display = 'none';
            document.getElementById('order-form').style.display = 'block';
            document.getElementById('selected-item').innerText = itemName;
            document.getElementById('product-input').value = itemName;
        }
    </script>
</body>
</html>
