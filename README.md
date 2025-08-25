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
nav a { color:white; text-decoration:none; padding:10px 20px; font-weight:600; letter-spacing:1px; border-radius:22px; margin:0 7px; transition:.2s;}
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
.card-icon { font-size:37px; color:#43a047; margin-bottom:5px; }
button {
    background:linear-gradient(to right,#43a047,#56ab2f); color:white; padding:12px; border:none; border-radius:7px;
    cursor:pointer; margin-top:14px; width:100%; font-size:16px; font-weight:600; box-shadow:0 2px 7px rgba(44,120,85,.14); display:flex; align-items:center;justify-content:center;}
button i { margin-right:8px; }

form label { font-weight:600; color:#43a047; }
form input,form textarea { width:90%; border-radius:8px; border:1px solid #dadada; padding:10px; }

/* ---- Modal Styles ---- */
.modal {
    display:none; position:fixed; z-index:999; left:0; top:0; width:100%; height:100%;
    background-color:rgba(0,0,0,0.6);
}
.modal-content {
    background:#fff; border-radius:12px; width:350px; margin:8% auto; padding:25px;
    box-shadow:0 4px 12px rgba(0,0,0,0.3); position:relative;
}
.modal-content h2 { text-align:center; color:#43a047; }
.close-btn {
    position:absolute; right:14px; top:10px; font-size:22px; cursor:pointer; color:#888;
}
.close-btn:hover { color:#000; }
.modal-content input {
    width:95%; margin:10px 0; border:1px solid #ccc; border-radius:6px; padding:10px;
}
.modal-content a { color:#43a047; text-decoration:none; font-size:14px; }
.modal-content a:hover { text-decoration:underline; }
.login-btn, .signup-btn {
    width:100%; background:linear-gradient(to right,#43a047,#56ab2f); border:none;
    color:white; padding:12px; border-radius:8px; font-size:16px; font-weight:bold;
    cursor:pointer; margin-top:10px;
}
.login-btn:hover, .signup-btn:hover { background:#388e3c; }
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
    <a href="javascript:void(0);" onclick="openLogin()"><i class="fas fa-sign-in-alt"></i> Login</a>
    <a href="javascript:void(0);" onclick="openSignup()"><i class="fas fa-user-plus"></i> Sign Up</a>
</nav>

<!-- Sections (same as before)... -->

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

<!-- Contact Form (same as before) -->
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

<!-- Login Modal -->
<div id="loginModal" class="modal">
  <div class="modal-content">
    <span class="close-btn" onclick="closeLogin()">&times;</span>
    <h2><i class="fas fa-user-circle"></i> Login</h2>
    <input type="text" id="username" placeholder="Email or Username" required>
    <input type="password" id="password" placeholder="Password" required>
    <button class="login-btn" onclick="performLogin()"><i class="fas fa-sign-in-alt"></i> Login</button>
    <p style="text-align:center; margin-top:10px;">Don't have an account? 
       <a href="javascript:void(0);" onclick="switchToSignup()">Sign Up</a></p>
  </div>
</div>

<!-- Signup Modal -->
<div id="signupModal" class="modal">
  <div class="modal-content">
    <span class="close-btn" onclick="closeSignup()">&times;</span>
    <h2><i class="fas fa-user-plus"></i> Sign Up</h2>
    <input type="text" id="regName" placeholder="Full Name" required>
    <input type="email" id="regEmail" placeholder="Email" required>
    <input type="tel" id="regPhone" placeholder="Phone Number" required>
    <input type="password" id="regPass" placeholder="Password" required>
    <button class="signup-btn" onclick="performSignup()"><i class="fas fa-user-check"></i> Create Account</button>
    <p style="text-align:center; margin-top:10px;">Already have an account? 
       <a href="javascript:void(0);" onclick="switchToLogin()">Login</a></p>
  </div>
</div>

<script>
function bookService(serviceName) {
    alert("Booking request sent for: " + serviceName);
}
function sendMessage(event) {
    event.preventDefault();
    alert("Your message has been sent. We will contact you soon.");
}

// ---- Login Modal ----
function openLogin() { document.getElementById("loginModal").style.display="block"; }
function closeLogin() { document.getElementById("loginModal").style.display="none"; }
function performLogin() {
    var user=document.getElementById("username").value;
    var pass=document.getElementById("password").value;
    if(user && pass) {
        alert("Welcome back, " + user + "!");
        closeLogin();
    } else { alert("Please enter your login details."); }
}

// ---- Signup Modal ----
function openSignup() { document.getElementById("signupModal").style.display="block"; }
function closeSignup() { document.getElementById("signupModal").style.display="none"; }
function performSignup() {
    var name=document.getElementById("regName").value;
    var email=document.getElementById("regEmail").value;
    var phone=document.getElementById("regPhone").value;
    var pass=document.getElementById("regPass").value;
    if(name && email && phone && pass) {
        alert("Thank you for signing up, " + name + "! Your account has been created.");
        closeSignup();
    } else { alert("Please fill all details to create an account."); }
}

// ---- Switch Between Modals ----
function switchToSignup(){ closeLogin(); openSignup(); }
function switchToLogin(){ closeSignup(); openLogin(); }

// Close modal if click outside
window.onclick=function(event){
    var login=document.getElementById("loginModal");
    var signup=document.getElementById("signupModal");
    if(event.target==login){ login.style.display="none"; }
    if(event.target==signup){ signup.style.display="none"; }
}
</script>
</body>
</html>
