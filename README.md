# smart_intventary_hackathon
Smart inventory management system built for the Odoo Hackathon.
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>StockSense - Login</title>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, sans-serif;
        }

        body {
            min-height: 100vh;
            background: #f4f7fb;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .container {
            width: 900px;
            max-width: 95%;
            min-height: 520px;
            background: white;
            border-radius: 20px;
            overflow: hidden;
            display: flex;
            box-shadow: 0 10px 35px rgba(0, 0, 0, 0.12);
        }

        /* Left Section */
        .left-section {
            width: 50%;
            background: #1e3a8a;
            color: white;
            padding: 60px 45px;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        .logo {
            font-size: 32px;
            font-weight: bold;
            margin-bottom: 20px;
        }

        .left-section h1 {
            font-size: 38px;
            margin-bottom: 20px;
        }

        .left-section p {
            font-size: 17px;
            line-height: 1.6;
            opacity: 0.9;
        }

        .stock-icon {
            font-size: 70px;
            margin-top: 35px;
        }

        /* Right Section */
        .right-section {
            width: 50%;
            padding: 60px 50px;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        .right-section h2 {
            font-size: 30px;
            color: #1f2937;
            margin-bottom: 10px;
        }

        .subtitle {
            color: #6b7280;
            margin-bottom: 30px;
        }

        label {
            display: block;
            margin-bottom: 8px;
            color: #374151;
            font-weight: bold;
        }

        input {
            width: 100%;
            padding: 13px;
            border: 1px solid #d1d5db;
            border-radius: 8px;
            margin-bottom: 20px;
            font-size: 15px;
            outline: none;
        }

        input:focus {
            border-color: #1e3a8a;
        }

        .forgot {
            text-align: right;
            margin-top: -10px;
            margin-bottom: 20px;
        }

        .forgot a {
            color: #1e3a8a;
            text-decoration: none;
            font-size: 14px;
        }

        .login-btn {
            width: 100%;
            padding: 14px;
            background: #1e3a8a;
            color: white;
            border: none;
            border-radius: 8px;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
        }

        .login-btn:hover {
            background: #172e6b;
        }

        .signup {
            text-align: center;
            margin-top: 25px;
            color: #6b7280;
        }

        .signup a {
            color: #1e3a8a;
            font-weight: bold;
            text-decoration: none;
        }

        /* Mobile */
        @media (max-width: 700px) {
            .container {
                flex-direction: column;
            }

            .left-section,
            .right-section {
                width: 100%;
            }

            .left-section {
                padding: 35px;
            }

            .right-section {
                padding: 40px 30px;
            }

            .stock-icon {
                display: none;
            }
        }
    </style>
</head>

<body>

    <div class="container">

        <!-- Left Side -->
        <div class="left-section">

            <div class="logo">📦 StockSense</div>

            <h1>Smart Inventory Management</h1>

            <p>
                Manage your products, stock, receipts, deliveries
                and warehouse operations from one simple dashboard.
            </p>

            <div class="stock-icon">
                📊 📦
            </div>

        </div>

        <!-- Right Side -->
        <div class="right-section">

            <h2>Welcome Back!</h2>

            <p class="subtitle">
                Login to your StockSense account
            </p>

            <form onsubmit="login(event)">

                <label for="email">Email</label>

                <input
                    type="email"
                    id="email"
                    placeholder="Enter your email"
                    required
                >

                <label for="password">Password</label>

                <input
                    type="password"
                    id="password"
                    placeholder="Enter your password"
                    required
                >

                <div class="forgot">
                    <a href="#">Forgot Password?</a>
                </div>

                <button class="login-btn" type="submit">
                    Login
                </button>

            </form>

            <p class="signup">
                Don't have an account?
                <a href="#">Sign Up</a>
            </p>

        </div>

    </div>

    <script>

        function login(event) {

            event.preventDefault();

            const email = document.getElementById("email").value;
            const password = document.getElementById("password").value;

            if (email && password) {

                alert("Login successful!");

                // Later we will redirect to dashboard here.
                window.location.href = "dashboard.html";

            }
        }

    </script>

</body>

<!DOCTYPE html>
<html lang="en">

<head>

    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>StockSense - Dashboard</title>

    <style>

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: Arial, sans-serif;
        }

        body {
            background: #f4f7fb;
            color: #1f2937;
        }

        /* SIDEBAR */

        .sidebar {
            position: fixed;
            left: 0;
            top: 0;
            width: 240px;
            height: 100vh;
            background: #172033;
            color: white;
            padding: 25px 15px;
        }

        .logo {
            font-size: 27px;
            font-weight: bold;
            padding: 0 15px;
            margin-bottom: 40px;
        }

        .logo span {
            color: #4f8cff;
        }

        .menu a {
            display: block;
            text-decoration: none;
            color: #dbe5f5;
            padding: 14px 15px;
            margin: 6px 0;
            border-radius: 9px;
        }

        .menu a:hover,
        .menu a.active {
            background: #33415f;
            color: white;
        }

        /* MAIN */

        .main {
            margin-left: 240px;
            padding: 35px;
        }

        .topbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
        }

        h1 {
            font-size: 30px;
        }

        .subtitle {
            color: #6b7280;
            margin-top: 6px;
        }

        .profile {
            background: white;
            padding: 12px 18px;
            border-radius: 10px;
            box-shadow: 0 3px 12px rgba(0,0,0,0.06);
        }

        /* CARDS */

        .cards {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 20px;
            margin-bottom: 30px;
        }

        .card {
            background: white;
            padding: 22px;
            border-radius: 13px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.06);
        }

        .card h3 {
            font-size: 15px;
            color: #6b7280;
            margin-bottom: 12px;
        }

        .number {
            font-size: 30px;
            font-weight: bold;
            color: #2563eb;
        }

        .warning {
            color: #dc2626;
        }

        /* CONTENT */

        .content {
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 20px;
        }

        .panel {
            background: white;
            padding: 25px;
            border-radius: 13px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.06);
        }

        .panel h2 {
            margin-bottom: 20px;
        }

        table {
            width: 100%;
            border-collapse: collapse;
        }

        th {
            background: #f1f5f9;
            text-align: left;
            padding: 13px;
        }

        td {
            padding: 13px;
            border-bottom: 1px solid #e5e7eb;
        }

        .action {
            display: block;
            text-decoration: none;
            color: #1f2937;
            background: #f1f5f9;
            padding: 14px;
            border-radius: 8px;
            margin-bottom: 10px;
        }

        .action:hover {
            background: #dbeafe;
        }

    </style>

</head>

<body>

    <!-- SIDEBAR -->

    <div class="sidebar">

        <div class="logo">
            Stock<span>Sense</span>
        </div>

        <div class="menu">

            <a href="dashboard.html" class="active">
                🏠 Dashboard
            </a>

            <a href="products.html">
                📦 Products
            </a>

            <a href="receipts.html">
                📥 Receipts
            </a>

            <a href="deliveries.html">
                📤 Deliveries
            </a>

            <a href="#">
                🔄 Transfers
            </a>

            <a href="#">
                📝 Adjustments
            </a>

            <a href="#">
                📊 Stock Ledger
            </a>

            <a href="#">
                🏭 Warehouse
            </a>

        </div>

    </div>


    <!-- MAIN -->

    <div class="main">

        <div class="topbar">

            <div>
                <h1>Dashboard</h1>
                <p class="subtitle">
                    Welcome back! Here's your inventory overview.
                </p>
            </div>

            <div class="profile">
                👤 Inventory Manager
            </div>

        </div>


        <!-- KPI CARDS -->

        <div class="cards">

            <div class="card">
                <h3>Total Products in Stock</h3>
                <div class="number">1,250</div>
            </div>

            <div class="card">
                <h3>Low / Out of Stock</h3>
                <div class="number warning">8</div>
            </div>

            <div class="card">
                <h3>Pending Receipts</h3>
                <div class="number">12</div>
            </div>

            <div class="card">
                <h3>Pending Deliveries</h3>
                <div class="number">7</div>
            </div>

        </div>


        <!-- CONTENT -->

        <div class="content">

            <div class="panel">

                <h2>Recent Stock Activity</h2>

                <table>

                    <tr>
                        <th>Product</th>
                        <th>Type</th>
                        <th>Quantity</th>
                        <th>Status</th>
                    </tr>

                    <tr>
                        <td>Steel Rods</td>
                        <td>Receipt</td>
                        <td>+100 kg</td>
                        <td>Done</td>
                    </tr>

                    <tr>
                        <td>Office Chairs</td>
                        <td>Delivery</td>
                        <td>-10 pcs</td>
                        <td>Done</td>
                    </tr>

                    <tr>
                        <td>Wooden Tables</td>
                        <td>Receipt</td>
                        <td>+25 pcs</td>
                        <td>Waiting</td>
                    </tr>

                </table>

            </div>


            <div class="panel">

                <h2>Quick Actions</h2>

                <a class="action" href="products.html">
                    📦 Manage Products
                </a>

                <a class="action" href="receipts.html">
                    📥 New Receipt
                </a>

                <a class="action" href="#">
                    📤 New Delivery
                </a>

            </div>

        </div>

    </div>

</body>
</html>
</html>
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>StockSense - Products</title>

    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: Arial, sans-serif;
        }

        body {
            background: #f5f7fb;
            color: #1f2937;
        }

        /* Sidebar */
        .sidebar {
            position: fixed;
            left: 0;
            top: 0;
            width: 230px;
            height: 100vh;
            background: #172033;
            color: white;
            padding: 25px 15px;
        }

        .logo {
            font-size: 25px;
            font-weight: bold;
            text-align: center;
            margin-bottom: 35px;
        }

        .logo span {
            color: #4f8cff;
        }

        .menu a {
            display: block;
            color: #cbd5e1;
            text-decoration: none;
            padding: 13px 15px;
            margin: 6px 0;
            border-radius: 8px;
        }

        .menu a:hover,
        .menu .active {
            background: #2d3b55;
            color: white;
        }

        /* Main area */
        .main {
            margin-left: 230px;
            padding: 35px;
        }

        .topbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
        }

        .topbar h1 {
            font-size: 30px;
        }

        .add-btn {
            background: #4f8cff;
            color: white;
            border: none;
            padding: 12px 20px;
            border-radius: 8px;
            cursor: pointer;
            font-size: 15px;
        }

        .add-btn:hover {
            background: #3575df;
        }

        /* Search */
        .search-box {
            background: white;
            padding: 20px;
            border-radius: 12px;
            margin-bottom: 25px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.06);
        }

        .search-box input {
            width: 100%;
            padding: 12px;
            border: 1px solid #d8dee9;
            border-radius: 7px;
            font-size: 14px;
        }

        /* Table */
        .table-card {
            background: white;
            border-radius: 12px;
            padding: 20px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.06);
            overflow-x: auto;
        }

        table {
            width: 100%;
            border-collapse: collapse;
        }

        th {
            background: #f1f5f9;
            text-align: left;
            padding: 15px;
            font-size: 14px;
        }

        td {
            padding: 15px;
            border-bottom: 1px solid #edf0f5;
            font-size: 14px;
        }

        tr:hover {
            background: #f8fafc;
        }

        .stock {
            font-weight: bold;
        }

        .good {
            color: #16a34a;
        }

        .low {
            color: #f59e0b;
        }

        /* Responsive */
        @media (max-width: 700px) {
            .sidebar {
                width: 180px;
            }

            .main {
                margin-left: 180px;
                padding: 20px;
            }
        }
    </style>
</head>

<body>

    <!-- Sidebar -->
    <div class="sidebar">

        <div class="logo">
            Stock<span>Sense</span>
        </div>

        <div class="menu">

            <a href="dashboard.html">🏠 Dashboard</a>

            <a href="products.html">
                📦 Products
            </a>

            <a href="receipts.html>">📥 Receipts</a>

            <a href="#">📤 Deliveries</a>

            <a href="#">🔄 Transfers</a>

            <a href="#">📝 Adjustments</a>

            <a href="#">📊 Stock Ledger</a>

            <a href="#">🏭 Warehouse</a>

        </div>

    </div>


    <!-- Main Content -->
    <div class="main">

        <div class="topbar">

            <div>
                <h1>Products</h1>
                <p>Manage your inventory products</p>
            </div>

            <button class="add-btn">
                + Add Product
            </button>

        </div>


        <!-- Search -->
        <div class="search-box">

            <input
                type="text"
                placeholder="🔍 Search products by name or SKU..."
            >

        </div>


        <!-- Product Table -->
        <div class="table-card">

            <table>

                <thead>

                    <tr>
                        <th>Product Name</th>
                        <th>SKU</th>
                        <th>Category</th>
                        <th>Unit</th>
                        <th>Stock</th>
                        <th>Status</th>
                    </tr>

                </thead>

                <tbody>

                    <tr>
                        <td>Steel Rods</td>
                        <td>ST-001</td>
                        <td>Raw Material</td>
                        <td>kg</td>
                        <td class="stock">100</td>
                        <td class="good">● In Stock</td>
                    </tr>

                    <tr>
                        <td>Office Chairs</td>
                        <td>CH-001</td>
                        <td>Furniture</td>
                        <td>pcs</td>
                        <td class="stock">50</td>
                        <td class="good">● In Stock</td>
                    </tr>

                    <tr>
                        <td>Wooden Tables</td>
                        <td>TB-001</td>
                        <td>Furniture</td>
                        <td>pcs</td>
                        <td class="stock">25</td>
                        <td class="low">● Low Stock</td>
                    </tr>

                </tbody>

            </table>

        </div>

    </div>

</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>StockSense - Products</title>

    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: Arial, sans-serif;
        }

        body {
            background: #f5f7fb;
            color: #1f2937;
        }

        /* SIDEBAR */
        .sidebar {
            position: fixed;
            left: 0;
            top: 0;
            width: 230px;
            height: 100vh;
            background: #172033;
            color: white;
            padding: 25px 15px;
        }

        .logo {
            font-size: 25px;
            font-weight: bold;
            text-align: center;
            margin-bottom: 35px;
        }

        .logo span {
            color: #4f8cff;
        }

        .menu a {
            display: block;
            color: #cbd5e1;
            text-decoration: none;
            padding: 13px 15px;
            margin: 6px 0;
            border-radius: 8px;
        }

        .menu a:hover,
        .menu .active {
            background: #2d3b55;
            color: white;
        }

        /* MAIN */
        .main {
            margin-left: 230px;
            padding: 35px;
        }

        .topbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
        }

        .topbar h1 {
            font-size: 30px;
        }

        .topbar p {
            margin-top: 7px;
            color: #6b7280;
        }

        /* ADD BUTTON */
        .add-btn {
            background: #4f8cff;
            color: white;
            border: none;
            padding: 12px 20px;
            border-radius: 8px;
            cursor: pointer;
            font-size: 15px;
        }

        .add-btn:hover {
            background: #3575df;
        }

        /* ADD PRODUCT FORM */
        .form-card {
            display: none;
            background: white;
            padding: 25px;
            border-radius: 12px;
            margin-bottom: 25px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.06);
        }

        .form-card h2 {
            margin-bottom: 20px;
        }

        .form-grid {
            display: grid;
            grid-template-columns: repeat(5, 1fr);
            gap: 15px;
        }

        .form-group label {
            display: block;
            font-size: 14px;
            font-weight: bold;
            margin-bottom: 7px;
        }

        .form-group input,
        .form-group select {
            width: 100%;
            padding: 11px;
            border: 1px solid #d8dee9;
            border-radius: 7px;
            font-size: 14px;
        }

        .form-buttons {
            margin-top: 20px;
        }

        .save-btn {
            background: #4f8cff;
            color: white;
            border: none;
            padding: 11px 20px;
            border-radius: 8px;
            cursor: pointer;
        }

        .cancel-btn {
            background: #e5e7eb;
            color: #374151;
            border: none;
            padding: 11px 20px;
            border-radius: 8px;
            cursor: pointer;
            margin-left: 8px;
        }

        /* SEARCH */
        .search-box {
            background: white;
            padding: 20px;
            border-radius: 12px;
            margin-bottom: 25px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.06);
        }

        .search-box input {
            width: 100%;
            padding: 12px;
            border: 1px solid #d8dee9;
            border-radius: 7px;
            font-size: 14px;
        }

        /* TABLE */
        .table-card {
            background: white;
            border-radius: 12px;
            padding: 20px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.06);
            overflow-x: auto;
        }

        table {
            width: 100%;
            border-collapse: collapse;
        }

        th {
            background: #f1f5f9;
            text-align: left;
            padding: 15px;
            font-size: 14px;
        }

        td {
            padding: 15px;
            border-bottom: 1px solid #edf0f5;
            font-size: 14px;
        }

        tr:hover {
            background: #f8fafc;
        }

        .stock {
            font-weight: bold;
        }

        .good {
            color: #16a34a;
        }

        .low {
            color: #f59e0b;
        }
    </style>
</head>

<body>

    <!-- SIDEBAR -->
    <div class="sidebar">

        <div class="logo">
            Stock<span>Sense</span>
        </div>

        <div class="menu">

            <a href="dashboard.html">
                🏠 Dashboard
            </a>

            <a href="products.html" class="active">
                📦 Products
            </a>

            <a href="receipts.html">
                📥 Receipts
            </a>

            <a href="deliveries.html">
                📤 Deliveries
            </a>

            <a href="transfers.html">
                🔄 Transfers
            </a>

            <a href="adjustments.html">
                📝 Adjustments
            </a>

            <a href="ledger.html">
                📊 Stock Ledger
            </a>

            <a href="warehouse.html">
                🏭 Warehouse
            </a>

        </div>

    </div>


    <!-- MAIN -->
    <div class="main">

        <!-- TOPBAR -->
        <div class="topbar">

            <div>
                <h1>Products</h1>
                <p>Manage your inventory products</p>
            </div>

            <button class="add-btn" onclick="showAddProduct()">
                + Add Product
            </button>

        </div>


        <!-- ADD PRODUCT FORM -->
        <div class="form-card" id="addProductForm">

            <h2>Add Product</h2>

            <div class="form-grid">

                <div class="form-group">
                    <label>Product Name</label>

                    <input
                        type="text"
                        id="productName"
                        placeholder="Enter product name"
                    >
                </div>


                <div class="form-group">
                    <label>SKU / Code</label>

                    <input
                        type="text"
                        id="productSKU"
                        placeholder="Enter SKU"
                    >
                </div>


                <div class="form-group">
                    <label>Category</label>

                    <input
                        type="text"
                        id="productCategory"
                        placeholder="Enter category"
                    >
                </div>


                <div class="form-group">
                    <label>Unit</label>

                    <select id="productUnit">

                        <option value="">
                            Select unit
                        </option>

                        <option value="pcs">
                            pcs
                        </option>

                        <option value="kg">
                            kg
                        </option>

                        <option value="litre">
                            litre
                        </option>

                        <option value="box">
                            box
                        </option>

                    </select>
                </div>


                <div class="form-group">
                    <label>Initial Stock</label>

                    <input
                        type="number"
                        id="initialStock"
                        min="0"
                        placeholder="Enter stock"
                    >
                </div>

            </div>


            <div class="form-buttons">

                <button
                    class="save-btn"
                    onclick="addProduct()"
                >
                    Add Product
                </button>

                <button
                    class="cancel-btn"
                    onclick="hideAddProduct()"
                >
                    Cancel
                </button>

            </div>

        </div>


        <!-- SEARCH -->
        <div class="search-box">

            <input
                type="text"
                id="searchInput"
                placeholder="🔍 Search products by name or SKU..."
                onkeyup="searchProducts()"
            >

        </div>


        <!-- PRODUCT TABLE -->
        <div class="table-card">

            <table>

                <thead>

                    <tr>
                        <th>Product Name</th>
                        <th>SKU</th>
                        <th>Category</th>
                        <th>Unit</th>
                        <th>Stock</th>
                        <th>Status</th>
                    </tr>

                </thead>


                <tbody id="productTable">

                    <tr>
                        <td>Steel Rods</td>
                        <td>ST-001</td>
                        <td>Raw Material</td>
                        <td>kg</td>
                        <td class="stock">100</td>
                        <td class="good">● In Stock</td>
                    </tr>


                    <tr>
                        <td>Office Chairs</td>
                        <td>CH-001</td>
                        <td>Furniture</td>
                        <td>pcs</td>
                        <td class="stock">50</td>
                        <td class="good">● In Stock</td>
                    </tr>


                    <tr>
                        <td>Wooden Tables</td>
                        <td>TB-001</td>
                        <td>Furniture</td>
                        <td>pcs</td>
                        <td class="stock">25</td>
                        <td class="low">● Low Stock</td>
                    </tr>

                </tbody>

            </table>

        </div>

    </div>


    <script>

        /* SHOW FORM */

        function showAddProduct() {

            document.getElementById("addProductForm").style.display =
                "block";
        }


        /* HIDE FORM */

        function hideAddProduct() {

            document.getElementById("addProductForm").style.display =
                "none";
        }


        /* ADD PRODUCT */

        function addProduct() {

            const name =
                document.getElementById("productName").value.trim();

            const sku =
                document.getElementById("productSKU").value.trim();

            const category =
                document.getElementById("productCategory").value.trim();

            const unit =
                document.getElementById("productUnit").value;

            const stock =
                document.getElementById("initialStock").value;


            /* CHECK FIELDS */

            if (!name || !sku || !category || !unit || stock === "") {

                alert("Please fill all product details.");

                return;
            }


            /* CHECK STOCK */

            if (Number(stock) < 0) {

                alert("Stock cannot be negative.");

                return;
            }


            /* STATUS */

            let statusText;
            let statusClass;

            if (Number(stock) <= 25) {

                statusText = "● Low Stock";
                statusClass = "low";

            } else {

                statusText = "● In Stock";
                statusClass = "good";

            }


            /* ADD TABLE ROW */

            const table =
                document.getElementById("productTable");

            const row =
                table.insertRow();


            row.innerHTML = `

                <td>${name}</td>

                <td>${sku}</td>

                <td>${category}</td>

                <td>${unit}</td>

                <td class="stock">${stock}</td>

                <td class="${statusClass}">
                    ${statusText}
                </td>

            `;


            /* CLEAR FORM */

            document.getElementById("productName").value = "";

            document.getElementById("productSKU").value = "";

            document.getElementById("productCategory").value = "";

            document.getElementById("productUnit").value = "";

            document.getElementById("initialStock").value = "";


            /* HIDE FORM */

            hideAddProduct();

        }


        /* SEARCH PRODUCTS */

        function searchProducts() {

            const search =
                document.getElementById("searchInput")
                .value
                .toLowerCase();


            const rows =
                document
                .getElementById("productTable")
                .getElementsByTagName("tr");


            for (let i = 0; i < rows.length; i++) {

                const productName =
                    rows[i].cells[0].innerText.toLowerCase();

                const sku =
                    rows[i].cells[1].innerText.toLowerCase();


                if (
                    productName.includes(search) ||
                    sku.includes(search)
                ) {

                    rows[i].style.display = "";

                } else {

                    rows[i].style.display = "none";

                }

            }

        }

    </script>

</body>
</html>

