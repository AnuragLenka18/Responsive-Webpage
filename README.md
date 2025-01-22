# Responsive-Webpage
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsive Webpage</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: Arial, sans-serif;
            display: flex;
            flex-direction: column;
            height: 100vh;
        }

        .navbar {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            background-color: #333;
            color: white;
            padding: 10px 20px;
            z-index: 1000;
        }

        .container {
            display: flex;
            flex: 1;
            margin-top: 50px; /* Adjust for navbar height */
            overflow: hidden;
        }

        .menu {
            width: 200px;
            background-color: #f4f4f4;
            overflow-y: auto;
            transition: width 0.3s;
        }

        .menu.collapsed {
            width: 50px;
        }

        .main {
            flex: 1;
            padding: 20px;
            overflow-y: auto;
        }

        .right-panel {
            width: 300px;
            background-color: #eaeaea;
            overflow-y: auto;
        }

        .footer {
            background-color: #333;
            color: white;
            text-align: center;
            padding: 10px 0;
        }

        .menu-toggle {
            display: none;
            background-color: #444;
            color: white;
            padding: 10px;
            border: none;
            cursor: pointer;
        }

        @media (max-width: 768px) {
            .menu {
                position: absolute;
                top: 50px;
                bottom: 0;
                left: -200px;
            }

            .menu.collapsed {
                left: 0;
            }

            .menu-toggle {
                display: inline-block;
            }

            .main {
                padding-left: 20px;
            }

            .right-panel {
                display: none;
            }
        }
    </style>
</head>
<body>
    <div class="navbar">
        <button class="menu-toggle">☰</button>
        <span>Fixed Navbar</span>
    </div>

    <div class="container">
        <div class="menu" id="menu">
            <ul>
                <li><a href="#">Link 1</a></li>
                <li><a href="#">Link 2</a></li>
                <li><a href="#">Link 3</a></li>
            </ul>
        </div>

        <div class="main">
            <h1>Main Content Area</h1>
            <p>This is the main content area where the bulk of the content will go.</p>
        </div>

        <div class="right-panel">
            <h2>Right Side Panel</h2>
            <p>Additional content or widgets can go here.</p>
        </div>
    </div>

    <div class="footer">
        <p>Footer Content</p>
    </div>

    <script>
        const menuToggle = document.querySelector('.menu-toggle');
        const menu = document.getElementById('menu');

        menuToggle.addEventListener('click', () => {
            menu.classList.toggle('collapsed');
        });
    </script>
</body>
</html>
