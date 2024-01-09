<template>
  <div id="app">
    <header class="navbar">
      <title>SneakPeak</title>
      <div class="logo">SNEAKPEAK</div>
      <nav>
        <a href="#newReleases">New Releases</a>
        <a href="#exclusive">Exclusive</a>
        <a href="#trending">Trending</a>
        <a href="#sale">Sale</a>
        <a href="#contact">LOG IN</a>
      </nav>
    </header>

    <main>
      <div class="carousel">
        <div class="carousel-images">
          <img src="@/assets/img/jordan1.jpg" alt="Air Jordan 1" />
          <img src="@/assets/img/nikedunk.jpg" alt="Nike Dunk Low" />
          <img src="@/assets/img/jordan4.jpg" alt="Air Jordan 4" />
        </div>
      </div>

      <section class="hero">
        <h1>Welcome to SneakPeak</h1>
        <p>Discover the latest and most exclusive sneakers.</p>
      </section>
    </main>

    <footer class="footer">
      <p>&copy; 2024 SneakPeak. All rights reserved.</p>
    </footer>
  </div>
</template>

<script>
export default {
  name: "App",
  created() {
    document.title = "SneakPeak";
  },
  mounted() {
    let currentIndex = 0;
    const images = document.querySelectorAll(".carousel-images img");
    const imageCount = images.length;

    function changeImage() {
      if (images[currentIndex]) {
        images[currentIndex].classList.remove("active");
      }

      currentIndex = (currentIndex + 1) % imageCount; // Cycle through the images

      images[currentIndex].classList.add("active");
    }

    setInterval(changeImage, 10000); // Change image every 10 seconds

    changeImage(); // Initialize first image
  },
};
</script>

<style>
/* Your CSS goes here */
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background-color: #f4f4f4;
}

.navbar {
  background-color: #333;
  color: white;
  display: flex;
  align-items: center;
  padding: 10px 20px;
}

.navbar .logo {
  font-size: 24px;
  font-weight: bold;
  margin-right: auto;
}

.navbar nav a {
  color: white;
  text-decoration: none;
  padding: 0 15px;
  text-transform: uppercase;
  letter-spacing: 1px;
}

.navbar nav a:hover {
  color: #f4f4f4;
  background-color: #555;
}

.hero {
  text-align: center;
  padding: 50px 20px;
}

.hero h1 {
  margin: 0;
  color: #333;
}

.hero p {
  color: #555;
}

.footer {
  background-color: #333;
  color: white;
  text-align: center;
  padding: 10px 0;
  position: fixed;
  bottom: 0;
  width: 100%;
}

.carousel {
  width: 100%;
  overflow: hidden;
}

.carousel-images img {
  width: 100%;
  display: none;
  transition: opacity 1s ease-in-out;
}

.carousel-images img.active {
  display: block;
  opacity: 1;
}
</style>
