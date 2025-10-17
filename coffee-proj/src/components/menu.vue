<template>
  <div class="menu-section">
    <h2 class="section-title">Explore Recent Products</h2>

    <div id="menuCarousel" class="carousel slide" data-bs-ride="carousel">
      <div class="carousel-inner">
        <div
          v-for="(chunk, index) in chunkedMenu"
          :key="index"
          :class="['carousel-item', { active: index === 0 }]"
        >
          <div class="d-flex justify-content-center align-items-center py-4">
            <div
              v-for="item in chunk"
              :key="item.name"
              class="menu-item-wrapper mx-2"
            >
              <div class="menu-item">
                <div class="image-circle">
                  <img :src="item.image" :alt="item.name" />
                </div>
                <div class="item-info">
                  <h3>{{ item.name }}</h3>
                  <p>{{ item.price }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Carousel chu.x -->
      <button
        class="carousel-control-prev"
        type="button"
        data-bs-target="#menuCarousel"
        data-bs-slide="prev"
      >
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Previous</span>
      </button>
      <button
        class="carousel-control-next"
        type="button"
        data-bs-target="#menuCarousel"
        data-bs-slide="next"
      >
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Next</span>
      </button>
    </div>
  </div>
</template>

<script setup>
import { computed } from 'vue'


const menuItems = [
  { name: 'Espresso', price: 'Php 150.00', image: '/images/latte.png' },
  { name: 'Cappuccino', price: 'Php 150.0', image: '/images/latte.png' },
  { name: 'Latte', price: 'Php 150.0', image: '/images/latte.png' },
  { name: 'Cold Brew', price: 'Php 150.0', image: '/images/latte.png' },
  { name: 'Mocha', price: 'Php 150.0', image: '/images/latte.png' },
  { name: 'Macchiato', price: 'Php 150.0', image: '/images/latte.png' },
]

const chunkedMenu = computed(() => {
  const chunks = []
  for (let i = 0; i < menuItems.length; i += 3) {
    chunks.push(menuItems.slice(i, i + 3))
  }
  return chunks
})
</script>

<style>
.menu-section {
  background-color: #1a1a1a;
  color: white;
  padding: 80px 40px;
  text-align: center;
}

.section-title {
  font-size: 2.5rem;
  margin-bottom: 40px;
  z-index: 1;
  position: relative;
}

.menu-item-wrapper {
  flex: 0 0 33.333%;
  display: flex;
  justify-content: center;
}

.menu-item {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.image-circle {
  width: 150px;
  height: 150px;
  border-radius: 50%;
  background-color: #333333;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 15px;
  overflow: visible;
  position: relative;
}

.image-circle img {
  width: 180px;
  height: auto;
  position: absolute;
  top: -15px;
}

.item-info h3 {
  font-size: 1.2rem;
  margin: 10px 0 0 0;
  color: #ffcc00;
}

.item-info p {
  margin: 0;
  color: #ccc;
}

.carousel-item {
  min-height: 250px;
}
</style>
