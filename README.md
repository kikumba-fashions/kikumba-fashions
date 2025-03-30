<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Explore the latest trends with Kikumba Fashions.">
    <title>Kikumba Fashions - Home</title>
    <link rel="stylesheet" href="css/styles.css">
    <link rel="icon" href="assets/favicon.ico">
</head>
<body>
    <header>
        <nav class="navbar">
            <h1>Kikumba Fashions</h1>
            <ul>
                <li><a href="index.html">Home</a></li>
                <li><a href="products.html">Products</a></li>
                <li><a href="about.html">About</a></li>
                <li><a href="contact.html">Contact</a></li>
            </ul>
        </nav>
    </header>
    <main>
        <section class="hero">
            <h2>Welcome to Kikumba Fashions</h2>
            <p>Discover elegance and style in every piece.</p>
            <a href="products.html" class="btn">Shop Now</a>
        </section>
    </main>
    <footer>
        <p>&copy; 2025 Kikumba Fashions. All rights reserved.</p>
    </footer>
    <script src="js/script.js"></script>
</body>
</html>styles.css (Responsive Styling)/* Reset and base styles */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Arial', sans-serif;
    line-height: 1.6;
}

.navbar {
    display: flex;
    justify-content: space-between;
    padding: 1rem;
    background-color: #333;
    color: white;
}

.navbar ul {
    display: flex;
    list-style: none;
}

.navbar a {
    color: white;
    text-decoration: none;
    margin: 0 1rem;
}

.hero {
    text-align: center;
    padding: 4rem 1rem;
    background: url('../assets/images/hero-bg.jpg') no-repeat center/cover;
    color: white;
}

.btn {
    display: inline-block;
    padding: 0.5rem 1rem;
    background-color: #ff6f61;
    color: white;
    text-decoration: none;
    border-radius: 5px;
}

/* Responsive Design */
@media (max-width: 768px) {
    .navbar {
        flex-direction: column;
        text-align: center;
    }
    .navbar ul {
        flex-direction: column;
        margin-top: 1rem;
    }
    .hero {
        padding: 2rem 0.5rem;
    }
}script.js (Interactivity)// Smooth scrolling for navigation
document.querySelectorAll('a[href^="#"]').forEach(anchor => {
    anchor.addEventListener('click', function(e) {
        e.preventDefault();
        document.querySelector(this.getAttribute('href')).scrollIntoView({
            behavior: 'smooth'
        });
    });
});clients.Hostinggithub.io/kikumba-fashions).Core
