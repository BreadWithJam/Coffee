
<template>
  <div class="container-fluid hero-section">
    <div class="row align-items-center">
      <!-- Left -->
      <div class="col-md-7 text-start left-column">
        <div class="tagline">
          <h1 ref="line1" class="display-3 fw-bold mb-3">Brewed With Passion.</h1>
          <h1 ref="line2" class="display-3 fw-bold mb-3">Served With Love.</h1>
          <p ref="paragraph" class="lead mb-4 yellow">
            The best coffee is here in your city!
          </p>
        </div>
      </div>

      <!-- Right -->
      <div class="col-md-4 text-center d-flex flex-column align-items-center right-column">
        <div class="info-stair d-flex flex-column align-items-start">
          <div ref="info1" class="info-item">
            <img src="/images/yellowBeanpng.png" class="bullet" alt="bean" />
            <p><strong class="yellow">Premium beans:</strong> Sourced from the finest farms, roasted to perfection</p>
          </div>

          <div ref="info2" class="info-item">
            <img src="/images/yellowBeanpng.png" class="bullet" alt="bean" />
            <p><strong class="yellow">Affordable Prices:</strong> Enjoy top-quality coffee without breaking the bank</p>
          </div>

          <div ref="info3" class="info-item">
            <img src="/images/yellowBeanpng.png" class="bullet" alt="bean" />
            <p><strong class="yellow">Made with love:</strong> Every cup is crafted with care and warmth</p>
          </div>
        </div>

        <div class="image-container mt-4">
          <img
            ref="imageRef"
            src="/images/coffee.png"
            alt="Coffee"
            class="hero-image img-fluid"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const line1 = ref(null)
const line2 = ref(null)
const paragraph = ref(null)
const imageRef = ref(null)
const info1 = ref(null)
const info2 = ref(null)
const info3 = ref(null)

// Anmatn
function slideInLeft(el, delay = 0) {
  if (!el) return
  el.style.transform = 'translateX(-50px)' 
  el.style.opacity = 0
  el.style.transition = 'all 1s ease'
  setTimeout(() => {
    el.style.transform = 'translateX(0)'
    el.style.opacity = 1
  }, delay)
}

function slideInRight(el, delay = 0) {
  if (!el) return
  el.style.transform = 'translateX(180px)' 
  el.style.opacity = 0
  el.style.transition = 'all 1s ease'
  setTimeout(() => {
    el.style.transform = 'translateX(0)'
    el.style.opacity = 1
  }, delay)
}

onMounted(() => {
  slideInLeft(line1.value, 0)
  slideInLeft(line2.value, 300)
  slideInLeft(paragraph.value, 600)
  slideInRight(info1.value, 900)
  slideInRight(info2.value, 1200)
  slideInRight(info3.value, 1500)
  slideInRight(imageRef.value, 1800)
})
</script>

<style>
.hero-section {
  height: 100vh;
  background-color: #141414;
  color: white;
  overflow: hidden;
  padding: 0 40px;
}

.left-column {
  padding-left: 80px;
}

.right-column {
  padding-left: 50px; 
}

.tagline {
  text-align: left;
}

.hero-image {
  width: 400px;
  max-width: 100%;
  opacity: 0;
  transform: translateX(180px); 
}

.info-stair {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  margin-bottom: 20px;
}

.info-item {
  display: flex;
  align-items: flex-start;
  gap: 8px;
  max-width: 320px;
  color: #ccc;
  font-size: 1rem;
  line-height: 1.4;
  opacity: 0;
  transition: all 1s ease;
  margin-top: 20px;
  text-align: left;
}

.info-item:first-child {
  margin-top: 0;
}

.info-item p {
  margin: 0;
  width: 270px;
  text-align: justify;
}

.bullet {
  width: 19px;
  height: 16px;
  margin-top: 4px;
}

.yellow {
  color: #ffaa00;
}
</style>
