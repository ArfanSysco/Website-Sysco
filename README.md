# Website-Sysco
Web
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>SysCoffe</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@600;700&display=swap');
  :root {
    --font-primary: 'Poppins', sans-serif;
    --color-bg: #ffffff;
    --color-text-primary: #111827;
    --color-text-secondary: #6b7280;
    --color-primary: #4a2c0a;
    --color-primary-hover: #5c3d14;
    --spacing-sm: 0.75rem;
    --spacing-md: 1.5rem;
    --spacing-lg: 3rem;
    --border-radius: 0.75rem;
    --shadow-light: 0 2px 8px rgba(0,0,0,0.1);
  }
  *, *::before, *::after {
    box-sizing: border-box;
  }
  body {
    margin: 0;
    font-family: var(--font-primary);
    background: var(--color-bg);
    color: var(--color-text-primary);
    line-height: 1.6;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
  }
  a {
    color: inherit;
    text-decoration: none;
  }
  a:focus-visible,
  button:focus-visible {
    outline: 3px solid var(--color-primary);
    outline-offset: 2px;
  }
  header {
    position: sticky;
    top: 0;
    background: var(--color-bg);
    padding: 1rem var(--spacing-md);
    border-bottom: 1px solid #e5e7eb;
    z-index: 10;
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-weight: 700;
    font-size: 1.3rem;
    color: var(--color-primary);
    box-shadow: var(--shadow-light);
  }
  .logo {
    user-select: none;
  }
  nav {
    display: flex;
    gap: 1.5rem;
  }
  nav button, nav a.external-link {
    background: none;
    border: none;
    color: var(--color-text-secondary);
    font-weight: 600;
    font-size: 1rem;
    cursor: pointer;
    padding: 0.25rem 0.5rem;
    border-radius: var(--border-radius);
    transition: color 0.3s ease, background-color 0.3s ease;
  }
  nav button:hover,
  nav button[aria-current="page"],
  nav a.external-link:hover {
    color: var(--color-primary);
    background-color: #f3f4f6;
  }
  nav a.external-link {
    cursor: pointer;
  }
  main {
    flex-grow: 1;
    max-width: 1200px;
    margin: 0 auto;
    padding: var(--spacing-lg) var(--spacing-md);
    width: 100%;
  }
  section {
    display: none;
  }
  section.active {
    display: block;
  }
  /* Hero Section */
  .hero {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    gap: var(--spacing-lg);
  }
  .text-section {
    flex: 1 1 400px;
    max-width: 600px;
  }
  h1 {
    font-size: 3rem;
    font-weight: 700;
    line-height: 1.1;
    margin-bottom: 1rem;
    color: var(--color-primary);
  }
  p.subtitle {
    font-size: 1.25rem;
    color: var(--color-text-secondary);
    margin-bottom: 2.5rem;
  }
  .btn-primary {
    background-color: var(--color-primary);
    color: #fff;
    padding: 0.9rem 2rem;
    font-size: 1.125rem;
    font-weight: 600;
    border: none;
    border-radius: var(--border-radius);
    cursor: pointer;
    box-shadow: var(--shadow-light);
    transition: background-color 0.3s ease, transform 0.3s ease;
  }
  .btn-primary:hover,
  .btn-primary:focus {
    background-color: var(--color-primary-hover);
    transform: scale(1.05);
    outline: none;
  }
  .image-section {
    flex: 1 1 350px;
    max-width: 400px;
    border-radius: var(--border-radius);
    position: relative;
    overflow: hidden;
    box-shadow: var(--shadow-light);
    /* coffee powder sprinkle background */
    background:
      url('https://cdn.pixabay.com/photo/2017/08/06/17/41/coffee-2599237_960_720.png') no-repeat center center,
      radial-gradient(circle at center, #503000 30%, transparent 70%);
    background-blend-mode: multiply;
    background-size: cover, 250% 250%;
    filter: brightness(0.85);
  }
  .coffee-image {
    width: 100%;
    display: block;
    border-radius: var(--border-radius);
    position: relative;
    z-index: 1;
    box-shadow: 0 8px 20px rgba(0,0,0,0.3);
  }
  @media (max-width: 768px) {
    .hero {
      flex-direction: column-reverse;
      text-align: center;
    }
    .text-section, .image-section {
      max-width: 100%;
      flex: none;
    }
    h1 {
      font-size: 2.5rem;
    }
  }
  /* Products Section */
  .products {
    display: grid;
    grid-template-columns: repeat(auto-fit,minmax(220px,1fr));
    gap: var(--spacing-lg);
  }
  .product-card {
    background: #fff;
    border-radius: var(--border-radius);
    box-shadow: var(--shadow-light);
    padding: var(--spacing-md);
    text-align: center;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  .product-card h3 {
    font-size: 1.5rem;
    margin: 0 0 0.5rem 0;
    color: var(--color-primary);
  }
  .product-price {
    font-weight: 700;
    font-size: 1.25rem;
    color: var(--color-primary-hover);
  }
  /* About Section */
  .about {
    max-width: 700px;
    color: var(--color-text-secondary);
    font-size: 1.125rem;
    line-height: 1.6;
  }
</style>
</head>
<body>
<header>
  <div class="logo" aria-label="Premium Coffee Shop Logo">☕ Premium Coffee</div>
  <nav role="navigation" aria-label="Primary Navigation">
    <button type="button" aria-current="page" id="nav-home" aria-controls="home-section" aria-haspopup="true">Home</button>
    <button type="button" id="nav-products" aria-controls="products-section" aria-haspopup="true">Products</button>
    <button type="button" id="nav-about" aria-controls="about-section" aria-haspopup="true">About</button>
    <a href="https://wa.me/081332333310" target="_blank" rel="noopener noreferrer" class="external-link" aria-label="Contact via WhatsApp">Contact</a>
  </nav>
</header>
<main>
  <!-- Home Section -->
  <section id="home-section" class="active" role="region" aria-label="Home Section">
    <div class="hero">
      <div class="text-section">
        <h1>Experience the Richness of Premium Coffee</h1>
        <p class="subtitle">Freshly roasted beans, rich aroma, and exquisite taste delivered to your door.</p>
<a href="https://wa.me/081332333310" target="_blank" rel="noopener noreferrer" class="btn-primary" aria-label="Buy Coffee Now">
  Buy Coffee Now
</a>
      </div>
      <div class="image-section">
        <img
          src="https://images.unsplash.com/photo-1509042239860-f550ce710b93?auto=format&fit=crop&w=800&q=80"
          alt="Cup of freshly brewed coffee"
          class="coffee-image"
          loading="lazy"
        />
      </div>
    </div>
  </section>
  <!-- Products Section -->
  <section id="products-section" role="region" aria-label="Products Section">
    <h2 style="font-weight:700; font-size:2rem; color:var(--color-primary); margin-bottom: var(--spacing-md);">Our Coffee Products</h2>
    <div class="products">
      <article class="product-card" tabindex="0" aria-label="Premium Arabica Coffee for 5 dollars">
        <h3>Premium Arabica Coffee</h3>
        <div class="product-price">$5</div>
      </article>
      <article class="product-card" tabindex="0" aria-label="Classic Espresso Blend for 3 dollars">
        <h3>Classic Espresso Blend</h3>
        <div class="product-price">$3</div>
      </article>
      <article class="product-card" tabindex="0" aria-label="Decaf Medium Roast for 4 dollars">
        <h3>Decaf Medium Roast</h3>
        <div class="product-price">$4</div>
      </article>
    </div>
  </section>
  <!-- About Section -->
  <section id="about-section" role="region" aria-label="About Section" class="about">
    <h2 style="font-weight:700; font-size:2rem; color:var(--color-primary); margin-bottom: var(--spacing-md);">About Us</h2>
    <p>
      Disini Hanya Menjual Produk Coffe Yang Berkualitas Dan Kalo Anda Ingin Membeli Nya Bisa Hubungi Nomor 081332333310 Terimasih.
    </p>
  </section>
</main>
<script>
  (() => {
    const navButtons = {
      home: document.getElementById('nav-home'),
      products: document.getElementById('nav-products'),
      about: document.getElementById('nav-about'),
    };
    const sections = {
      home: document.getElementById('home-section'),
      products: document.getElementById('products-section'),
      about: document.getElementById('about-section'),
    };

    function activateSection(sectionName) {
      Object.keys(sections).forEach(key => {
        const active = key === sectionName;
        sections[key].classList.toggle('active', active);
        navButtons[key].setAttribute('aria-current', active ? 'page' : 'false');
      });
    }

    // Add event listeners for navigation buttons
    Object.entries(navButtons).forEach(([key, btn]) => {
      btn.addEventListener('click', () => {
        activateSection(key);
      });
      btn.addEventListener('keydown', e => {
        if (e.key === 'Enter' || e.key === ' ') {
          e.preventDefault();
          activateSection(key);
        }
      });
    });

    // Initial section
    activateSection('home');
  })();
</script>
</body>
</html>

```
