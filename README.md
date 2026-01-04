# taxi-booking
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Uttarakhand Taxi Services</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* All your existing CSS remains the same */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        :root {
            --primary: #1e6a57;
            --secondary: #f39c12;
            --light: #f8f9fa;
            --dark: #2c3e50;
            --accent: #e74c3c;
        }

        body {
            background-color: #f5f7f9;
            color: #333;
            line-height: 1.6;
        }

        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header Styles */
        header {
            background: linear-gradient(to right, var(--primary), #2c8c71);
            color: white;
            padding: 15px 0;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .logo h1 {
            font-size: 1.8rem;
            font-weight: 700;
        }

        .logo i {
            font-size: 2rem;
            color: var(--secondary);
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 25px;
        }

        nav a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s;
        }

        nav a:hover {
            color: var(--secondary);
        }

        .cta-button {
            background-color: var(--secondary);
            color: white;
            padding: 10px 20px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s;
        }

        .cta-button:hover {
            background-color: #e67e22;
            transform: translateY(-2px);
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6)), url('https://images.unsplash.com/photo-1587474260584-136574528ed5?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80');
            background-size: cover;
            background-position: center;
            color: white;
            text-align: center;
            padding: 100px 20px;
            margin-bottom: 50px;
        }

        .hero h2 {
            font-size: 3rem;
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
        }

        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 30px;
        }

        /* Section Styles */
        section {
            padding: 60px 0;
        }

        .section-title {
            text-align: center;
            margin-bottom: 40px;
        }

        .section-title h2 {
            font-size: 2.5rem;
            color: var(--primary);
            margin-bottom: 15px;
        }

        .section-title p {
            color: #666;
            max-width: 700px;
            margin: 0 auto;
        }

        /* Services Section */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .service-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s;
        }

        .service-card:hover {
            transform: translateY(-10px);
        }

        .service-img {
            height: 200px;
            background-color: #ddd;
            background-size: cover;
            background-position: center;
        }

        .service-content {
            padding: 20px;
        }

        .service-content h3 {
            color: var(--primary);
            margin-bottom: 10px;
        }

        /* Vehicles Section */
        .vehicles-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 25px;
        }

        .vehicle-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .vehicle-img {
            height: 440px;
            background-color: #eee;
            background-size: contain;
            background-position: center;
            overflow: hidden;
        }

        .vehicle-content {
            padding: 20px;
        }

        .vehicle-content h3 {
            color: var(--dark);
            margin-bottom: 10px;
        }

        .price {
            color: var(--primary);
            font-weight: 700;
            font-size: 1.2rem;
            margin: 10px 0;
        }

        /* Destinations Section */
        .destinations-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .destination-card {
            position: relative;
            height: 300px;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        .destination-img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }

        .destination-card:hover .destination-img {
            transform: scale(1.1);
        }

        .destination-overlay {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: linear-gradient(transparent, rgba(0, 0, 0, 0.8));
            color: white;
            padding: 20px;
        }

        /* Booking Form */
        .booking-form {
            background: white;
            border-radius: 10px;
            padding: 30px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
            max-width: 800px;
            margin: 0 auto;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: var(--dark);
        }

        .form-group input,
        .form-group select,
        .form-group textarea {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 16px;
            background-color: white !important;
        }

        /* Add this to prevent autofill styling */
        input:-webkit-autofill,
        input:-webkit-autofill:hover,
        input:-webkit-autofill:focus,
        input:-webkit-autofill:active {
            -webkit-box-shadow: 0 0 0 30px white inset !important;
            box-shadow: 0 0 0 30px white inset !important;
            -webkit-text-fill-color: #333 !important;
        }

        .form-row {
            display: flex;
            gap: 20px;
        }

        .form-row .form-group {
            flex: 1;
        }

        .submit-btn {
            background-color: var(--primary);
            color: white;
            border: none;
            padding: 15px 30px;
            border-radius: 5px;
            font-size: 18px;
            font-weight: 600;
            cursor: pointer;
            width: 100%;
            transition: background-color 0.3s;
        }

        .submit-btn:hover {
            background-color: #155e48;
        }

        /* WhatsApp Button */
        .whatsapp-float {
            position: fixed;
            width: 60px;
            height: 60px;
            bottom: 40px;
            right: 40px;
            background-color: #25d366;
            color: #FFF;
            border-radius: 50px;
            text-align: center;
            font-size: 30px;
            box-shadow: 2px 2px 3px #999;
            z-index: 100;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s;
        }

        .whatsapp-float:hover {
            background-color: #128C7E;
            transform: scale(1.1);
        }

        /* Packages Section */
        .packages-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
        }

        .package-card {
            background: white;
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        .package-card h4 {
            color: var(--primary);
            margin-bottom: 10px;
        }

        .package-card ul {
            margin-top: 10px;
            color: #444;
        }

        /* Footer */
        footer {
            background-color: var(--dark);
            color: white;
            padding: 50px 0 20px;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-bottom: 30px;
        }

        .footer-column h3 {
            font-size: 1.3rem;
            margin-bottom: 20px;
            color: var(--secondary);
        }

        .footer-column ul {
            list-style: none;
        }

        .footer-column ul li {
            margin-bottom: 10px;
        }

        .footer-column a {
            color: #ddd;
            text-decoration: none;
            transition: color 0.3s;
        }

        .footer-column a:hover {
            color: var(--secondary);
        }

        .social-icons {
            display: flex;
            gap: 15px;
            margin-top: 15px;
        }

        .social-icons a {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            transition: all 0.3s;
        }

        .social-icons a:hover {
            background-color: var(--secondary);
            transform: translateY(-3px);
        }

        .copyright {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 0.9rem;
            color: #aaa;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                gap: 15px;
            }
            
            nav ul {
                gap: 15px;
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .hero h2 {
                font-size: 2.2rem;
            }
            
            .form-row {
                flex-direction: column;
                gap: 0;
            }
            
            .whatsapp-float {
                width: 50px;
                height: 50px;
                bottom: 20px;
                right: 20px;
                font-size: 25px;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container header-content">
            <div class="logo">
                <i class="fas fa-taxi"></i>
                <h1>Uttarakhand Taxi Services</h1>
            </div>
            <nav>
                <ul>
                    <li><a href="#services">Services</a></li>
                    <li><a href="#vehicles">Vehicles</a></li>
                    <li><a href="#destinations">Destinations</a></li>
                    <li><a href="#packages">Packages</a></li>
                    <li><a href="#booking">Book Now</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
            </nav>
            <a href="#booking" class="cta-button">Book Now</a>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <h2>Explore Uttarakhand's Beauty with Comfort</h2>
            <p>Reliable taxi services for all your travel needs across the Devbhoomi. From pilgrimages to adventure trips, we've got you covered.</p>
            <a href="#booking" class="cta-button">Book Your Ride</a>
        </div>
    </section>

    <!-- Services Section -->
    <section id="services">
        <div class="container">
            <div class="section-title">
                <h2>Our Services</h2>
                <p>We offer a wide range of transportation services to make your Uttarakhand journey comfortable and memorable</p>
            </div>
            <div class="services-grid">
                <!-- Accommodation Service -->
                <div class="service-card">
                    <div class="service-img" style="background-image: url('https://images.unsplash.com/photo-1566073771259-6a8506099945?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80');"></div>
                    <div class="service-content">
                        <h3>Accommodation</h3>
                        <p>We provide clean, comfortable and well-maintained accommodation during the entire trip.</p>
                    </div>
                </div>
                
                <!-- Breakfast Service -->
                <div class="service-card">
                    <div class="service-img" style="background-image: url('https://images.unsplash.com/photo-1482049016688-2d3e1b311543?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80');"></div>
                    <div class="service-content">
                        <h3>Breakfast</h3>
                        <p>Nutritious and hygienic breakfast provided daily during the trip.</p>
                    </div>
                </div>
                
                <!-- Transportation Service -->
                <div class="service-card">
                    <div class="service-img" style="background-image: url('https://images.unsplash.com/photo-1558618666-fcd25c85cd64?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80');"></div>
                    <div class="service-content">
                        <h3>Transportation</h3>
                        <p>Comfortable transportation provided in Scorpio or Bolero vehicles for the entire trip.</p>
                    </div>
                </div>

                <!-- Tour Guide Service -->
                <div class="service-card">
                    <div class="service-img" style="background-image: url('gui.webp');"></div>
                    <div class="service-content">
                        <h3>Tour Guide</h3>
                        <p>An experienced local guide will accompany the group throughout the trip, ensuring safety and providing complete information about each destination, temples, and local culture.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Vehicles Section -->
    <section id="vehicles" style="background-color: #eef5f3;">
        <div class="container">
            <div class="section-title">
                <h2>Our Fleet</h2>
                <p>Choose from our well-maintained vehicles for all your travel needs</p>
            </div>
            <div class="vehicles-grid">
                <!-- Scorpio -->
                <div class="vehicle-card">
                    <div class="vehicle-img">
                        <img src="car.jpg" alt="Mahindra Scorpio" style="width:100%; height:100%; object-fit:cover;">
                    </div>
                    <div class="vehicle-content">
                        <h3>Mahindra Scorpio</h3>
                        <p>Best for mountain routes, long journeys and group travel. Comfortable seating for 6-7 passengers.</p>
                        <div class="price">Fixed Package Rates Available</div>
                        <p><strong>Features:</strong> 4WD, AC, Comfort Seats, Luggage Space</p>
                    </div>
                </div>
                
                <!-- Bolero -->
                <div class="vehicle-card">
                    <div class="vehicle-img">
                        <img src="bolero.webp" alt="Mahindra Bolero" style="width:100%; height:100%; object-fit:cover;">
                    </div>
                    <div class="vehicle-content">
                        <h3>Mahindra Bolero</h3>
                        <p>Reliable SUV for hill areas and rough roads. Perfect for adventurous routes.</p>
                        <div class="price">Fixed Package Rates Available</div>
                        <p><strong>Features:</strong> Robust Build, High Ground Clearance, Fuel Efficient</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Destinations Section -->
    <section id="destinations">
        <div class="container">
            <div class="section-title">
                <h2>Popular Destinations</h2>
                <p>Explore the beautiful landscapes and spiritual sites of Uttarakhand with our reliable services</p>
            </div>
            <div class="destinations-grid">
                <!-- Chaudas Valley -->
                <div class="destination-card">
                    <img src="https://images.unsplash.com/photo-1501785888041-af3ef285b470?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Chaudas Valley" class="destination-img">
                    <div class="destination-overlay">
                        <h3>Chaudas Valley</h3>
                        <p>Famous spot: Narayan Ashram</p>
                        <p><strong>Price:</strong> ₹10,000 / booking</p>
                        <p><strong>Duration:</strong> 2-3 Days</p>
                    </div>
                </div>

                <!-- Darma Valley -->
                <div class="destination-card">
                    <img src="https://images.unsplash.com/photo-1509114397022-ed747cca3f65?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Darma Valley" class="destination-img">
                    <div class="destination-overlay">
                        <h3>Darma Valley</h3>
                        <p>Famous spot: Panchachuli Parvat peak point darshan</p>
                        <p><strong>Price:</strong> ₹10,000 / booking</p>
                        <p><strong>Duration:</strong> 3-4 Days</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Packages Section -->
    <section id="packages" style="background-color: #fff;">
        <div class="container">
            <div class="section-title">
                <h2>Special Packages</h2>
                <p>Pre-packed pilgrimage and adventure itineraries with accommodation and guide</p>
            </div>

            <div class="packages-grid">
                <div class="package-card">
                    <h4>Haldwani - Adi Kailash</h4>
                    <p><strong>Price:</strong> ₹25,000 per person (Haldwani to Adi Kailash and back)</p>
                    <p><strong>Duration:</strong> 5-6 Days</p>
                    <ul>
                        <li>Package inclusion: Accommodation, Breakfast, Transportation, Tour Guide</li>
                        <li>Famous spots: Om Parvat, Parvati Kund, Gouri Kund, Adi Kailash</li>
                        <li>Optional: Om Parvat to Lipulekh/Darra (Kailash Mansarovar view point) — Extra charge ₹5,000</li>
                    </ul>
                </div>

                <div class="package-card">
                    <h4>Delhi - Adi Kailash</h4>
                    <p><strong>Price:</strong> ₹50,000 per person (Delhi to Adi Kailash and back)</p>
                    <p><strong>Duration:</strong> 7-8 Days</p>
                    <ul>
                        <li>Package inclusion: Accommodation, Breakfast, Transportation, Tour Guide</li>
                        <li>Famous spots: Om Parvat, Parvati Kund, Gouri Kund, Adi Kailash</li>
                        <li>Optional: Om Parvat to Lipulekh/Darra (Kailash Mansarovar view point) — Extra charge ₹5,000</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- Booking Section -->
    <section id="booking" style="background-color: #eef5f3;">
        <div class="container">
            <div class="section-title">
                <h2>Book Your Taxi</h2>
                <p>Fill out the form below to reserve your vehicle</p>
            </div>
            <div class="booking-form">
                <!-- Simple form without autocomplete issues -->
                <form id="taxiBookingForm">
                    <div class="form-row">
                        <div class="form-group">
                            <label for="name">Full Name *</label>
                            <input type="text" id="name" placeholder="Enter your full name" required>
                        </div>
                        <div class="form-group">
                            <label for="phone">Phone Number *</label>
                            <input type="tel" id="phone" placeholder="Enter 10-digit mobile number" pattern="[0-9]{10}" required>
                        </div>
                    </div>
                    <div class="form-row">
                        <div class="form-group">
                            <label for="email">Email Address</label>
                            <input type="email" id="email" placeholder="Enter your email (optional)">
                        </div>
                        <div class="form-group">
                            <label for="pickup">Pickup Location *</label>
                            <input type="text" id="pickup" placeholder="City/Town/Village" required>
                        </div>
                    </div>
                    <div class="form-row">
                        <div class="form-group">
                            <label for="destination">Destination *</label>
                            <select id="destination" required>
                                <option value="">Select Destination</option>
                                <option value="chaudas-valley">Chaudas Valley (₹10,000)</option>
                                <option value="darma-valley">Darma Valley (₹10,000)</option>
                                <option value="adi-kailash-haldwani">Adi Kailash from Haldwani (₹25,000/person)</option>
                                <option value="adi-kailash-delhi">Adi Kailash from Delhi (₹50,000/person)</option>
                                <option value="other">Other (Custom Quote)</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label for="vehicle">Vehicle Type *</label>
                            <select id="vehicle" required>
                                <option value="">Select Vehicle</option>
                                <option value="scorpio">Scorpio</option>
                                <option value="bolero">Bolero</option>
                                <option value="both">Both (for larger groups)</option>
                            </select>
                        </div>
                    </div>
                    <div class="form-row">
                        <div class="form-group">
                            <label for="date">Pickup Date *</label>
                            <input type="date" id="date" required>
                        </div>
                        <div class="form-group">
                            <label for="time">Pickup Time *</label>
                            <input type="time" id="time" required>
                        </div>
                    </div>
                    <div class="form-row">
                        <div class="form-group">
                            <label for="passengers">Number of Passengers *</label>
                            <input type="number" id="passengers" min="1" max="20" placeholder="1-20" required>
                        </div>
                        <div class="form-group">
                            <label for="days">Number of Days</label>
                            <input type="number" id="days" min="1" max="30" placeholder="Duration in days">
                        </div>
                    </div>
                    <div class="form-group">
                        <label for="message">Special Requests / Additional Information</label>
                        <textarea id="message" rows="3" placeholder="Any special requirements, accommodation preferences, or tour guide requests..."></textarea>
                    </div>
                    <button type="submit" class="submit-btn">Submit Booking Request</button>
                    <p style="text-align: center; margin-top: 15px; font-size: 14px; color: #666;">
                        <i class="fas fa-phone"></i> Need immediate help? Call: <strong>+91 8475922004 / +91 8433217708</strong>
                    </p>
                </form>
            </div>
        </div>
    </section>

    <!-- WhatsApp Float Button -->
    <a href="https://wa.me/918475922004?text=Hello!%20I%20would%20like%20to%20book%20a%20taxi%20service%20in%20Uttarakhand." class="whatsapp-float" target="_blank">
        <i class="fab fa-whatsapp"></i>
    </a>

    <!-- Footer -->
    <footer id="contact">
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>Uttarakhand Taxi Services</h3>
                    <p>Your reliable travel partner in the Devbhoomi. We provide safe, comfortable, and affordable transportation services across Uttarakhand.</p>
                    <div class="social-icons">
                        <a href="https://wa.me/918475922004" target="_blank"><i class="fab fa-whatsapp"></i></a>
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                    </div>
                </div>
                <div class="footer-column">
                    <h3>Quick Links</h3>
                    <ul>
                        <li><a href="#services">Services</a></li>
                        <li><a href="#vehicles">Vehicles</a></li>
                        <li><a href="#destinations">Destinations</a></li>
                        <li><a href="#packages">Packages</a></li>
                        <li><a href="#booking">Booking</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Contact Us</h3>
                    <ul>
                        <li><i class="fas fa-map-marker-alt"></i> Uttarakhand Taxi Services, Dehradun</li>
                        <li><i class="fas fa-phone"></i> +91 8475922004</li>
                        <li><i class="fas fa-phone"></i> +91 8433217708</li>
                        <li><i class="fab fa-whatsapp"></i> WhatsApp: 8475922004</li>
                        <li><i class="fas fa-clock"></i> 24/7 Available</li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Why Choose Us?</h3>
                    <ul>
                        <li><i class="fas fa-check"></i> Experienced Drivers</li>
                        <li><i class="fas fa-check"></i> Mountain Road Experts</li>
                        <li><i class="fas fa-check"></i> Well-Maintained Vehicles</li>
                        <li><i class="fas fa-check"></i> Affordable Fixed Packages</li>
                        <li><i class="fas fa-check"></i> 24/7 Customer Support</li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2025 Uttarakhand Taxi Services. All rights reserved. | Designed for Devbhoomi Explorers</p>
                <p style="margin-top: 10px;">WhatsApp: <strong>8475922004</strong> | Call: <strong>8475922004, 8433217708</strong></p>
            </div>
        </div>
    </footer>

    <script>
        // Form submission handling with WhatsApp integration
        document.getElementById('taxiBookingForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Get form values
            const name = document.getElementById('name').value;
            const phone = document.getElementById('phone').value;
            const email = document.getElementById('email').value || "Not provided";
            const pickup = document.getElementById('pickup').value;
            const destination = document.getElementById('destination').value;
            const vehicle = document.getElementById('vehicle').value;
            const date = document.getElementById('date').value;
            const time = document.getElementById('time').value;
            const passengers = document.getElementById('passengers').value;
            const days = document.getElementById('days').value || "Not specified";
            const message = document.getElementById('message').value || "None";
            
            // Validate phone number
            if (!/^\d{10}$/.test(phone)) {
                alert('Please enter a valid 10-digit phone number.');
                return;
            }
            
            // Validate date (not in past)
            const selectedDate = new Date(date);
            const today = new Date();
            today.setHours(0, 0, 0, 0);
            
            if (selectedDate < today) {
                alert('Please select a future date for your booking.');
                return;
            }
            
            // Create booking message for WhatsApp
            const whatsappMessage = `*🚕 NEW TAXI BOOKING REQUEST - UTTARAKHAND TAXI SERVICES*%0A%0A` +
                `*👤 Customer Details:*%0A` +
                `• *Name:* ${name}%0A` +
                `• *Phone:* ${phone}%0A` +
                `• *Email:* ${email}%0A%0A` +
                `*📍 Trip Details:*%0A` +
                `• *Pickup Location:* ${pickup}%0A` +
                `• *Destination:* ${destination}%0A` +
                `• *Vehicle Type:* ${vehicle}%0A` +
                `• *Pickup Date:* ${date}%0A` +
                `• *Pickup Time:* ${time}%0A` +
                `• *Passengers:* ${passengers}%0A` +
                `• *Duration:* ${days} days%0A%0A` +
                `*📝 Special Requests:*%0A${message}%0A%0A` +
                `*📅 Booking Time:* ${new Date().toLocaleString()}%0A` +
                `*🔢 Booking ID:* UTTS${Date.now().toString().slice(-6)}`;
            
            // Create WhatsApp URL with new number
            const whatsappURL = `https://wa.me/918475922004?text=${whatsappMessage}`;
            
            // Open WhatsApp in new tab
            window.open(whatsappURL, '_blank');
            
            // Show confirmation message
            alert(`✅ Thank you ${name}! Your booking request has been sent to our WhatsApp.\n\nWe will contact you at ${phone} shortly to confirm your booking.\n\nBooking ID: UTTS${Date.now().toString().slice(-6)}`);
            
            // Reset form completely
            this.reset();
            
            // Reset date and time to default
            const tomorrow = new Date();
            tomorrow.setDate(tomorrow.getDate() + 1);
            document.getElementById('date').value = tomorrow.toISOString().split('T')[0];
            document.getElementById('time').value = '09:00';
            
            // Force focus away from form fields
            document.activeElement.blur();
        });

        // Set minimum date to today for the date picker
        const today = new Date();
        document.getElementById('date').min = today.toISOString().split('T')[0];
        
        // Set default date to tomorrow
        const tomorrow = new Date(today);
        tomorrow.setDate(tomorrow.getDate() + 1);
        document.getElementById('date').value = tomorrow.toISOString().split('T')[0];
        
        // Set default time to 9:00 AM
        document.getElementById('time').value = '09:00';

        // Smooth scroll for navigation links
        document.querySelectorAll('nav a, .cta-button').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                const href = this.getAttribute('href');
                if (href.startsWith('#')) {
                    e.preventDefault();
                    const targetElement = document.querySelector(href);
                    if (targetElement) {
                        window.scrollTo({
                            top: targetElement.offsetTop - 80,
                            behavior: 'smooth'
                        });
                    }
                }
            });
        });

        // Auto-fill vehicle based on destination selection
        document.getElementById('destination').addEventListener('change', function() {
            const vehicleSelect = document.getElementById('vehicle');
            if (this.value.includes('valley') || this.value.includes('kailash')) {
                if (vehicleSelect.value === '') {
                    vehicleSelect.value = 'scorpio';
                }
            }
        });

        // Auto-calculate days based on destination
        document.getElementById('destination').addEventListener('change', function() {
            const daysInput = document.getElementById('days');
            const destination = this.value;
            
            if (destination === 'chaudas-valley') {
                daysInput.value = 3;
            } else if (destination === 'darma-valley') {
                daysInput.value = 4;
            } else if (destination === 'adi-kailash-haldwani') {
                daysInput.value = 6;
            } else if (destination === 'adi-kailash-delhi') {
                daysInput.value = 8;
            }
        });

        // Clear form on page load
        window.addEventListener('load', function() {
            document.getElementById('taxiBookingForm').reset();
            document.getElementById('date').value = new Date(Date.now() + 86400000).toISOString().split('T')[0];
            document.getElementById('time').value = '09:00';
        });
    </script>
</body>
</html>
