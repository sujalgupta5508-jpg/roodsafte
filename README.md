# roodsafte
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Road Safety Awareness</title>
    <style>
        /* --- CSS STYLES --- */
        :root {
            --primary-color: #e74c3c; /* Traffic Red */
            --secondary-color: #f1c40f; /* Caution Yellow */
            --dark-color: #2c3e50;
            --light-bg: #f4f4f4;
            --white: #ffffff;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: var(--light-bg);
            color: #333;
            line-height: 1.6;
        }

        /* Header */
        header {
            background-color: var(--dark-color);
            color: var(--white);
            padding: 1rem 0;
            text-align: center;
        }

        header h1 {
            font-size: 2rem;
            margin-bottom: 5px;
        }

        /* Navigation Bar */
        nav {
            background-color: var(--primary-color);
            display: flex;
            justify-content: center;
            box-shadow: 0 2px 5px rgba(0,0,0,0.2);
        }

        nav button {
            background: none;
            border: none;
            color: var(--white);
            padding: 15px 25px;
            font-size: 1.1rem;
            cursor: pointer;
            transition: background 0.3s;
            font-weight: bold;
        }

        nav button:hover, nav button.active {
            background-color: var(--dark-color);
        }

        /* Main Container */
        .container {
            max-width: 1000px;
            margin: 20px auto;
            padding: 20px;
            background-color: var(--white);
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
            min-height: 400px;
        }

        /* Tab Content Logic */
        .tab-content {
            display: none; /* Hidden by default */
            animation: fadeIn 0.5s;
        }

        .tab-content.active {
            display: block; /* Show when active */
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        /* --- HOME TAB STYLES --- */
        .banner {
            width: 100%;
            height: 250px;
            background-image: url('https://images.unsplash.com/photo-1494976388531-d1058494cdd8?ixlib=rb-1.2.1&auto=format&fit=crop&w=1000&q=80');
            background-size: cover;
            background-position: center;
            border-radius: 8px;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.7);
            font-size: 2.5rem;
            font-weight: bold;
        }

        .intro-text {
            font-size: 1.1rem;
            text-align: justify;
        }

        /* --- RULES TAB STYLES --- */
        .rules-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .rule-card {
            background-color: #fff;
            border: 1px solid #ddd;
            border-radius: 8px;
            padding: 20px;
            text-align: center;
            transition: transform 0.2s;
            border-top: 5px solid var(--secondary-color);
        }

        .rule-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        .icon {
            font-size: 3rem;
            margin-bottom: 10px;
            display: block;
        }

        /* --- CONTACT & TIPS TAB STYLES --- */
        .tips-container {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            margin-bottom: 30px;
        }

        .tips-box {
            flex: 1;
            min-width: 300px;
            background-color: #fff8e1; /* Light yellow */
            padding: 20px;
            border-radius: 8px;
            border-left: 5px solid var(--secondary-color);
        }

        .tips-box h3 {
            margin-bottom: 10px;
            color: var(--dark-color);
        }

        .tips-box ul {
            list-style-type: none;
            padding-left: 0;
        }

        .tips-box li {
            margin-bottom: 8px;
            padding-left: 20px;
            position: relative;
        }

        .tips-box li::before {
            content: "✔";
            color: green;
            position: absolute;
            left: 0;
        }

        /* Form Styles */
        .contact-form {
            max-width: 600px;
            margin: 0 auto;
            background: #f9f9f9;
            padding: 20px;
            border-radius: 8px;
        }

        .form-group {
            margin-bottom: 15px;
        }

        .form-group label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
        }

        .form-group input, .form-group textarea {
            width: 100%;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }

        .submit-btn {
            background-color: var(--primary-color);
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 4px;
            cursor: pointer;
            font-size: 1rem;
            width: 100%;
        }

        .submit-btn:hover {
            background-color: #c0392b;
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 20px;
            background-color: var(--dark-color);
            color: white;
            margin-top: 20px;
        }

        /* Responsive Design */
        @media (max-width: 600px) {
            nav {
                flex-direction: column;
            }
            nav button {
                width: 100%;
                border-bottom: 1px solid rgba(255,255,255,0.1);
            }
            .banner {
                font-size: 1.5rem;
                height: 180px;
            }
        }
    </style>
</head>
<body>

    <!-- Header -->
    <header>
        <h1>🚦 Road Safety Awareness</h1>
        <p>Be Safe, Stay Alive</p>
    </header>

    <!-- Navigation Bar -->
    <nav>
        <button class="tab-link active" onclick="openTab(event, 'Home')">Home</button>
        <button class="tab-link" onclick="openTab(event, 'Rules')">Road Safety Rules</button>
        <button class="tab-link" onclick="openTab(event, 'Contact')">Contact & Tips</button>
    </nav>

    <!-- Main Content Area -->
    <div class="container">
        
        <!-- Tab 1: Home -->
        <div id="Home" class="tab-content active">
            <div class="banner">
                Drive Safe, Arrive Safe
            </div>
            <div class="intro-text">
                <h2>Why is Road Safety Important?</h2>
                <p>
                    Road safety is a critical issue that affects everyone. Every year, thousands of lives are lost due to traffic accidents. 
                    These accidents not only cause loss of life but also lead to severe injuries and financial burdens on families.
                </p>
                <br>
                <p>
                    By following simple rules and being aware of our surroundings, we can significantly reduce the number of accidents. 
                    Whether you are a driver, a passenger, a cyclist, or a pedestrian, your actions on the road matter. 
                    Let's work together to create a safer environment for everyone.
                </p>
            </div>
        </div>

        <!-- Tab 2: Road Safety Rules -->
        <div id="Rules" class="tab-content">
            <h2>Essential Road Safety Rules</h2>
            <p>Follow these rules to ensure your safety and the safety of others.</p>
            
            <div class="rules-grid">
                <div class="rule-card">
                    <span class="icon">🪖</span>
                    <h3>Wear Helmets</h3>
                    <p>Always wear a helmet while riding a two-wheeler. It protects your head in case of a fall.</p>
                </div>
                <div class="rule-card">
                    <span class="icon">🪢</span>
                    <h3>Use Seat Belts</h3>
                    <p>Fasten your seat belt before starting the car. It is the most effective way to prevent injury.</p>
                </div>
                <div class="rule-card">
                    <span class="icon">🚦</span>
                    <h3>Follow Signals</h3>
                    <p>Never run a red light. Obey traffic signals and signs to maintain order on the road.</p>
                </div>
                <div class="rule-card">
                    <span class="icon">📵</span>
                    <h3>No Mobile Phones</h3>
                    <p>Avoid using your phone while driving. It distracts you and increases the risk of accidents.</p>
                </div>
                <div class="rule-card">
                    <span class="icon">🚗</span>
                    <h3>Obey Speed Limits</h3>
                    <p>Drive within the prescribed speed limits. Speeding reduces reaction time.</p>
                </div>
                <div class="rule-card">
                    <span class="icon">👀</span>
                    <h3>Look Both Ways</h3>
                    <p>Before crossing the road, look left, right, and left again to ensure no vehicles are coming.</p>
                </div>
            </div>
        </div>

        <!-- Tab 3: Contact / Awareness Tips -->
        <div id="Contact" class="tab-content">
            <h2>Awareness Tips</h2>
            
            <div class="tips-container">
                <div class="tips-box">
                    <h3>For Pedestrians</h3>
                    <ul>
                        <li>Use footbridges or zebra crossings whenever available.</li>
                        <li>Do not wear headphones while walking near traffic.</li>
                        <li>Wear bright or reflective clothing at night so drivers can see you.</li>
                    </ul>
                </div>

                <div class="tips-box">
                    <h3>For Cyclists</h3>
                    <ul>
                        <li>Ride on the right side of the road in the same direction as traffic.</li>
                        <li>Use hand signals to indicate turns.</li>
                        <li>Keep a safe distance from large vehicles like trucks and buses.</li>
                    </ul>
                </div>
            </div>

            <hr style="margin: 30px 0; border: 0; border-top: 1px solid #ddd;">

            <h2>Contact Us / Feedback</h2>
            <p style="text-align: center; margin-bottom: 20px;">Have a suggestion or want to report a hazard? Send us a message.</p>
            
            <form class="contact-form" onsubmit="event.preventDefault(); alert('Thank you for your feedback!');">
                <div class="form-group">
                    <label for="name">Name:</label>
                    <input type="text" id="name" name="name" placeholder="Your Name" required>
                </div>
                <div class="form-group">
                    <label for="email">Email:</label>
                    <input type="email" id="email" name="email" placeholder="Your Email" required>
                </div>
                <div class="form-group">
                    <label for="message">Message:</label>
                    <textarea id="message" name="message" rows="4" placeholder="Your message here..." required></textarea>
                </div>
                <button type="submit" class="submit-btn">Send Message</button>
            </form>
        </div>

    </div>

    <!-- JavaScript for Tab Switching -->
    <script>
        function openTab(evt, tabName) {
            // 1. Hide all tab content
            var i, tabcontent, tablinks;
            tabcontent = document.getElementsByClassName("tab-content");
            for (i = 0; i < tabcontent.length; i++) {
                tabcontent[i].style.display = "none";
                tabcontent[i].classList.remove("active");
            }

            // 2. Remove "active" class from all buttons
            tablinks = document.getElementsByClassName("tab-link");
            for (i = 0; i < tablinks.length; i++) {
                tablinks[i].className = tablinks[i].className.replace(" active", "");
            }

            // 3. Show the current tab, and add an "active" class to the button that opened the tab
            document.getElementById(tabName).style.display = "block";
            // Small timeout to allow display:block to apply before adding opacity class for animation
            setTimeout(() => {
                document.getElementById(tabName).classList.add("active");
            }, 10);
            
            evt.currentTarget.className += " active";
        }
    </script>

</body>
</html>
