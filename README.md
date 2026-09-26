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
