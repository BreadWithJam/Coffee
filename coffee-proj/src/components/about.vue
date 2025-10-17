<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'

const storesSection = ref(null)
const storesNumber = ref(null)
const storesText = ref(null)
const mapImage = ref(null)

// refs sa bottom
const employeeIcon = ref(null)
const employeeNumber = ref(null)
const employeeText = ref(null)

const storeIcon = ref(null)
const storeNumber = ref(null)
const storeText = ref(null)

function slideInUp(el, delay = 0) {
  if (!el) return
  el.style.transition = 'all 1s ease'
  setTimeout(() => {
    el.style.opacity = 1
    el.style.transform = 'translateY(0)'
  }, delay)
}

function slideInRight(el, delay = 0) {
  if (!el) return
  el.style.transition = 'all 1s ease'
  setTimeout(() => {
    el.style.opacity = 1
    el.style.transform = 'translateX(0)'
  }, delay)
}

function resetAnimations() {
  [storesNumber.value, storesText.value, mapImage.value,
    employeeIcon.value, employeeNumber.value, employeeText.value,
    storeIcon.value, storeNumber.value, storeText.value
  ].forEach(el => {
    if (el) {
      el.style.opacity = 0
      el.style.transform = el === mapImage.value ? 'translateX(100px)' : 'translateY(50px)'
    }
  })
}

function isInViewport(el) {
  if (!el) return false
  const rect = el.getBoundingClientRect()
  const windowHeight = window.innerHeight || document.documentElement.clientHeight
  return rect.top < windowHeight * 0.8 && rect.bottom > 0
}

function handleScroll() {
  if (isInViewport(storesSection.value)) {
    slideInUp(storesNumber.value, 0)
    slideInUp(storesText.value, 300)
    slideInUp(employeeIcon.value, 600)
    slideInUp(employeeNumber.value, 700)
    slideInUp(employeeText.value, 800)
    slideInUp(storeIcon.value, 900)
    slideInUp(storeNumber.value, 1000)
    slideInUp(storeText.value, 1100)
    slideInRight(mapImage.value, 1200)
  } else {
    resetAnimations()
  }
}

onMounted(() => {
  resetAnimations()
  window.addEventListener('scroll', handleScroll)
  handleScroll()
})

onBeforeUnmount(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <div class="stores-section container-fluid py-5" ref="storesSection">
    <div class="row align-items-center justify-content-center">
      <!-- Left Column: Text -->
      <div class="col-7 text-center mb-4 mb-md-0">
        <h1 ref="storesNumber" class="stores-number mb-3">48</h1>
        <p ref="storesText" class="stores-text mb-5">Offline Stores in This Country</p>

        
        <div class="row justify-content-center">
          <div class="col-md-6 mb-4 mb-md-0 text-center">
            <img ref="employeeIcon" src="/images/employee.png" alt="Employees Icon" class="icon mb-2" />
            <h2 ref="employeeNumber" class="stat-number2">120 Employees</h2>
            <p ref="employeeText" class="stat-text">Employees at the bottom Lorem ipsum dolor hgdssdfsgfd lsfhd jfhdyfghgfsghfghs</p>
          </div>
          <div class="col-md-6 text-center">
            <img ref="storeIcon" src="/images/store.png" alt="Store Icon" class="icon storeicon mb-1" />
            <h2 ref="storeNumber" class="stat-number2">10 Years in Business</h2>
            <p ref="storeText" class="stat-text">In business Lorem ipsum dolor hsftsdfhdgf shd shgfsfsgdhsgdssd</p>
          </div>
        </div>
      </div>

      <!-- Right -->
      <div class="col-5 text-center">
        <img ref="mapImage"
             src="/images/map.png"
             alt="Map"
             class="map-image img-fluid" />
      </div>
    </div>
  </div>
</template>

<style>
.stores-section {
  background-color: #1a1a1a;
  color: white;
  padding-top: 80px;
  padding-bottom: 80px;
  min-height: 80vh;
}

.icon, .storeicon, .stores-number, .stores-text, .stat-number2, .stat-text {
  opacity: 0;
  transform: translateY(50px);
  transition: all 1s ease;
}

.map-image {
  max-width: 100%;
  height: auto;
  opacity: 0;
  transform: translateX(100px);
  transition: all 1s ease;
}

.stores-number {
  font-size: 6rem;
  font-weight: bold;
  color: #ffaa00;
}

.stores-text {
  font-size: 2rem;
  color: #ccc;
}

.stat-number2 {
  font-size: 1.5rem;
  font-weight: bold;
  color: #ffaa00;
  margin-bottom: 10px;
}

.stat-text {
  font-size: 1.2rem;
  color: #ccc;
  margin: 0;
}

.icon {
  width: 60px;
  height: auto;
}

.storeicon {
  width: 40px;
  height: auto;
}
</style>
