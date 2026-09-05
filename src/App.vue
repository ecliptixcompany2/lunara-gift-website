<template>
  <main
    class="app"
    @touchstart="handleTouchStart"
    @touchend="handleTouchEnd"
    @wheel="handleWheel"
  >
    <div
      class="pages-container"
      :style="{
        transform: `translateY(-${currentPage * 100}vh)`
      }"
    >
      <!-- ========================= -->
      <!-- HALAMAN 1 -->
      <!-- ========================= -->
      <section class="page">
        <PagesOne />
      </section>


      <!-- ========================= -->
      <!-- HALAMAN 2 -->
      <!-- ========================= -->
      <section class="page">
        <PagesTwo />
      </section>


      <!-- ========================= -->
      <!-- HALAMAN 3 -->
      <!-- ========================= -->
      <section class="page">
        <PagesThree />
      </section>


      <!-- ========================= -->
      <!-- HALAMAN 4 -->
      <!-- ========================= -->
      <section class="page">
              <PagesFour />
      </section>

    </div>
  </main>
</template>


<script setup>
import { ref } from 'vue'

import PagesOne from './pages/PagesOne.vue'
import PagesTwo from './pages/PagesTwo.vue'
import PagesThree from './pages/PagesThree.vue'
import PagesFour from './pages/PagesFour.vue'


// ===============================
// HALAMAN AKTIF
// ===============================

const currentPage = ref(0)


// ===============================
// JUMLAH HALAMAN
// ===============================

const totalPages = 4


// ===============================
// TOUCH
// ===============================

let touchStartY = 0


// ===============================
// LOCK ANIMASI
// ===============================

let isMoving = false

const animationDuration = 700


// ===============================
// PINDAH HALAMAN
// ===============================

const changePage = (direction) => {
  // Jika animasi masih berjalan,
  // jangan izinkan pindah lagi
  if (isMoving) return

  const nextPageNumber = currentPage.value + direction


  // Jangan melewati halaman pertama/terakhir
  if (
    nextPageNumber < 0 ||
    nextPageNumber >= totalPages
  ) {
    return
  }


  // Kunci perpindahan
  isMoving = true

  // Pindah halaman
  currentPage.value = nextPageNumber


  // Buka kembali setelah animasi selesai
  setTimeout(() => {
    isMoving = false
  }, animationDuration)
}


// ===============================
// TOUCH START
// ===============================

const handleTouchStart = (event) => {
  touchStartY = event.touches[0].clientY
}


// ===============================
// TOUCH END
// ===============================

const handleTouchEnd = (event) => {
  if (isMoving) return

  const touchEndY =
    event.changedTouches[0].clientY

  const distance =
    touchStartY - touchEndY


  // Minimal jarak swipe
  const minimumSwipeDistance = 70


  // Swipe ke atas
  if (distance > minimumSwipeDistance) {
    changePage(1)
  }


  // Swipe ke bawah
  if (distance < -minimumSwipeDistance) {
    changePage(-1)
  }
}


// ===============================
// MOUSE WHEEL
// ===============================

const handleWheel = (event) => {
  // Jangan pindah jika sedang animasi
  if (isMoving) return


  // Jangan bereaksi terhadap scroll kecil
  const minimumWheelDistance = 30

  if (
    Math.abs(event.deltaY) <
    minimumWheelDistance
  ) {
    return
  }


  // Scroll ke bawah
  if (event.deltaY > 0) {
    changePage(1)
  }


  // Scroll ke atas
  if (event.deltaY < 0) {
    changePage(-1)
  }
}

</script>


<style>

/* ========================================
   GLOBAL RESET
======================================== */

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}


/* ========================================
   HTML BODY APP
======================================== */

html,
body,
#app {
  width: 100%;
  height: 100%;

  overflow: hidden;
}


/* ========================================
   MAIN APP
======================================== */

.app {
  width: 100%;
  height: 100vh;
  height: 100svh;

  overflow: hidden;

  touch-action: none;
}


/* ========================================
   PAGE CONTAINER
======================================== */

.pages-container {
  width: 100%;

  transition:
    transform 0.7s cubic-bezier(
      0.77,
      0,
      0.175,
      1
    );

  will-change: transform;
}


/* ========================================
   EACH PAGE
======================================== */

.page {
  width: 100%;
  height: 100vh;
  height: 100svh;

  overflow: hidden;
}


/* ========================================
   TEMPORARY PAGE FOUR
======================================== */

.coming-page {
  width: 100%;
  height: 100%;

  display: flex;
  flex-direction: column;

  justify-content: center;
  align-items: center;

  color: white;

  background: linear-gradient(
    135deg,
    #210407,
    #4a0b12,
    #220407
  );
}


.coming-page h1 {
  font-family: Georgia, serif;

  font-size: 50px;

  font-weight: 400;
}


.coming-page p {
  margin-top: 10px;

  font-size: 18px;

  opacity: 0.7;
}

</style>