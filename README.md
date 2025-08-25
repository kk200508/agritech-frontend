<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>AgriConnect - Agriculture Services</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<!-- Example for adding icons -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.2/css/all.min.css">
<style>
body { font-family:'Segoe UI', Arial, sans-serif; margin:0; padding:0; background:#f4f7f2; }
header {
    background:linear-gradient(to right,#56ab2f,#a8e063); color:white; padding:0;
    position:relative; min-height:225px; text-align:center; display:flex; flex-direction:column; justify-content:center;
}
.header-content { z-index:2; position:relative; }
.header-graphic {
    position:absolute; left:0; bottom:0; width:100%; height:100%; opacity:0.2;
    background:url('https://images.unsplash.com/photo-1506744038136-46273834b3fb?auto=format&fit=cover&w=1200&q=80') center/cover no-repeat;
}
nav { background:#2e7d32; padding:10px; text-align:center; box-shadow:0 2px 6px rgba(0,0,0,0.07);}
nav a { color:white; text-decoration:none; padding:10px 23px; font-weight:600; letter-spacing:1px; border-radius:22px; margin:0 7px; transition:.2s;}
nav a:hover { background:#43a047; }
section { max-width:900px; margin:25px auto 0 auto; padding:25px; background:white; border-radius:12px; box-shadow:0 2px 20px rgba(44,120,85,.04);}
h2 { margin-top:0; font-size:2rem; }
.service-card {
    background:linear-gradient(135deg,#e8f5e9,#fffde7 65%); border:1px solid #e0e0e0;
    border-radius:14px; box-shadow:0 4px 18px rgba(44,120,85,0.05);
    display:inline-block; width:260px; margin:14px; padding:19px; vertical-align:top; transition:transform .16s;
    position:relative;
}
.service-card:hover { transform:translateY(-5px) scale(1.03);}
.card-icon {
    font-size:37px; color:#43a047; margin-bottom:5px;
}
button {
    background:linear-gradient(to right,#43a047,#56ab2f); color:white; padding:12px; border:none; border-radius:7px;
    cursor:pointer; margin-top:14px; width:100%; font-size:16px; font-weight:600; box-shadow:0 2px 7px rgba(44,120,85,.14); display:flex; align-items:center;justify-content:center;}
button i { margin-right:8px; }

form label { font-weight:600; color:#43a047; }
form input,form textarea { width:90%; border-radius:8px; border:1px solid #dadada; padding:10px;}
</style>
</head>
<body>

<header>
    <div class="header-content">
        <h1 style="font-size:2.5rem; margin-bottom:13px;">AgriConnect</h1>
        <p style="font-size:1.3rem;margin-bottom:5px;">Your One-Stop Agriculture Service Platform</p>
        <span style="font-size:1.1rem;">Connecting Farmers and Services</span>
    </div>
    <div class="header-graphic"></div>
</header>

<nav>
    <a href="#tractors"><i class="fas fa-tractor"></i> Rent Tractors</a>
    <a href="#seeds"><i class="fas fa-seedling"></i> Buy/Sell Seeds</a>
    <a href="#labor"><i class="fas fa-users"></i> Rent Labor</a>
    <a href="#tools"><i class="fas fa-tools"></i> Lease Tools</a>
    <a href="#contact"><i class="fas fa-envelope"></i> Contact</a>
</nav>

<section id="tractors">
    <h2><span style="color:#43a047;"><i class="fas fa-tractor"></i></span> Rent Tractors</h2>
    <div class="service-card">
        <div class="card-icon"><i class="fas fa-tractor"></i></div>
        <h3>John Deere 5050D</h3>
        <p>Rent per day: ₹2,000</p>
        <button onclick="bookService('John Deere Tractor')"><i class="fas fa-calendar-check"></i> Book Now</button>
    </div>
    <div class="service-card">
        <div class="card-icon"><i class="fas fa-tractor"></i></div>
        <h3>Mahindra Arjun 555</h3>
        <p>Rent per day: ₹1,800</p>
        <button onclick="bookService('Mahindra Tractor')"><i class="fas fa-calendar-check"></i> Book Now</button>
    </div>
</section>

<section id="seeds">
    <h2><span style="color:#43a047;"><i class="fas fa-seedling"></i></span> Buy / Sell Seeds</h2>
    <div class="service-card">
        <div class="card-icon"><i class="fas fa-seedling"></i></div>
        <h3>Wheat Seeds (50kg)</h3>
        <p>Price: ₹1,500</p>
        <button onclick="bookService('Wheat Seeds')"><i class="fas fa-shopping-cart"></i> Buy Now</button>
    </div>
    <div class="service-card">
        <div class="card-icon"><i class="fas fa-seedling"></i></div>
        <h3>Rice Seeds (50kg)</h3>
        <p>Price: ₹1,800</p>
        <button onclick="bookService('Rice Seeds')"><i class="fas fa-shopping-cart"></i> Buy Now</button>
    </div>
</section>

<section id="labor">
    <h2><span style="color:#43a047;"><i class="fas fa-users"></i></span> Rent Farm Labor</h2>
    <div class="service-card">
        <div class="card-icon"><i class="fas fa-user-hard-hat"></i></div>
        <h3>Skilled Labor</h3>
        <p>₹600/day</p>
        <button onclick="bookService('Skilled Labor')"><i class="fas fa-user-check"></i> Hire Now</button>
    </div>
    <div class="service-card">
        <div class="card-icon"><i class="fas fa-user"></i></div>
        <h3>Unskilled Labor</h3>
        <p>₹400/day</p>
        <button onclick="bookService('Unskilled Labor')"><i class="fas fa-user-check"></i> Hire Now</button>
    </div>
</section>

<section id="tools">
    <h2><span style="color:#43a047;"><i class="fas fa-tools"></i></span> Lease Agricultural Tools</h2>
    <div class="service-card">
        <div class="card-icon"><i class="fas fa-cogs"></i></div>
        <h3>Rotavator</h3>
        <p>₹500/day</p>
        <button onclick="bookService('Rotavator')"><i class="fas fa-handshake"></i> Lease Now</button>
    </div>
    <div class="service-card">
        <div class="card-icon"><i class="fas fa-cogs"></i></div>
        <h3>Sprayer</h3>
        <p>₹200/day</p>
        <button onclick="bookService('Sprayer')"><i class="fas fa-handshake"></i> Lease Now</button>
    </div>
</section>

<section id="contact">
    <h2><span style="color:#43a047;"><i class="fas fa-envelope"></i></span> Contact Us</h2>
    <form onsubmit="sendMessage(event)">
        <label>Name:</label><br>
        <input type="text" required><br><br>
        <label>Phone:</label><br>
        <input type="tel" required><br><br>
        <label>Message:</label><br>
        <textarea required></textarea><br><br>
        <button type="submit"><i class="fas fa-paper-plane"></i> Send Message</button>
    </form>
</section>

<script>
function bookService(serviceName) {
    alert("Booking request sent for: " + serviceName);
}
function sendMessage(event) {
    event.preventDefault();
    alert("Your message has been sent. We will contact you soon.");
}
</script>
</body>
</html>
