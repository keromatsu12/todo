<template>
 <footer>
  <div class="footer-container">
    <div class="footer-section">
      <h4>About Us</h4>
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
    </div>
    <div class="footer-section">
      <h4>Links</h4>
      <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">Services</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
    </div>
    <div class="footer-section">
      <h4>Follow Us</h4>
      <div class="social-icons">
        <a href="#"><i class="fab fa-facebook"></i></a>
        <a href="#"><i class="fab fa-twitter"></i></a>
        <a href="#"><i class="fab fa-instagram"></i></a>
      </div>
    </div>
  </div>
  <div class="footer-bottom">
    © 2023 Your Company
  </div>
</footer>

</template>

<script>
export default {

}
</script>

<style scoped>
footer {
  background-color: #333;
  color: #fff;
  padding: 20px 0;
  font-family: 'Avenir', sans-serif;
}

.footer-container {
  display: flex;
  justify-content: space-between;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.footer-section {
  flex: 1;
  padding: 0 20px;
}

.footer-section h4 {
  border-bottom: 2px solid #555;
  padding-bottom: 10px;
  margin-bottom: 20px;
}

.footer-section ul {
  list-style: none;
  padding: 0;
}

.footer-section ul li {
  margin-bottom: 10px;
}

.footer-section ul li a {
  text-decoration: none;
  color: #fff;
  transition: color 0.3s;
}

.footer-section ul li a:hover {
  color: #ddd;
}

.social-icons a {
  margin-right: 15px;
  font-size: 24px;
  color: #fff;
  transition: color 0.3s;
}

.social-icons a:hover {
  color: #ddd;
}

.footer-bottom {
  text-align: center;
  margin-top: 20px;
}
</style>

