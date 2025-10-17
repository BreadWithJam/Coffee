<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark-gray fixed-top w-100 px-4">
    <div class="container-fluid">
      <!-- Brand with logo -->
      <a class="navbar-brand d-flex align-items-center fw-bold text-white" href="#">
        <img
          src="/images/logo.png"
          alt="Logo"
          class="brand-logo me-2"
        />
        Brew
      </a>

      <!-- Toggler -->
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarNav"
        aria-controls="navbarNav"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>

      <!-- Navbar links -->
      <div class="collapse navbar-collapse justify-content-center" id="navbarNav">
        <ul class="navbar-nav d-flex gap-4">
          <li class="nav-item">
            <a class="nav-link active" aria-current="page" href="#">Home</a>
          </li>
           <li class="nav-item">
            <a class="nav-link" href="#">Menu</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">About</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Contact</a>
          </li>
        </ul>
      </div>

      <!-- Button-->
      <div class="d-none d-lg-block">
        <button class="btn btn-custom ms-3">Get Started</button>
      </div>
    </div>
  </nav>
</template>

<script setup>
</script>

<style scoped>
.bg-dark-gray {
  background-color: #2b2b2b;
}

.nav-link {
  color: #ccc !important;
  font-size: 1rem;
  letter-spacing: 0.5px;
  transition: color 0.3s;
}

.nav-link:hover {
  color: #ffcc00 !important;
}

.navbar-brand {
  color: white !important;
  font-size: medium;
}

.brand-logo {
  width: 40px;
  height: 40px;
  object-fit: contain;
  transform: scale(1.5);
  transform-origin: left center;
}

.navbar {
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.4);
  padding-top: 0.3rem;
  padding-bottom: 0.3rem;
}


.btn-custom {
  background-color: #ffcc00;
  color: black;
  border: none;
  padding: 6px 16px; 
  font-size: 0.9rem;
  font-weight: normal; 
  border-radius: 20px;
  transition: 0.3s;
}

.btn-custom:hover {
  background-color: #ffaa00;
}
</style>
