<template>
  <main
    class="app"
    @touchstart="handleTouchStart"
    @touchend="handleTouchEnd"
    @wheel.prevent="handleWheel"
  >
    <div
      class="pages-container"
      :style="{
        transform: `translate3d(0, -${currentPage * 100}dvh, 0)`
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


/* =========================
   HALAMAN SAAT INI
========================= */

const currentPage = ref(0)


/* =========================
   TOTAL HALAMAN
========================= */

const totalPages = 4


/* =========================
   TOUCH POSITION
========================= */

let touchStartY = 0


/* =========================
   LOCK SWIPE
========================= */

let isMoving = false


/* =========================
   TOUCH START
========================= */

const handleTouchStart = (event) => {

  touchStartY = event.touches[0].clientY

}


/* =========================
   TOUCH END
========================= */

const handleTouchEnd = (event) => {

  if (isMoving) return


  const touchEndY =
    event.changedTouches[0].clientY


  const distance =
    touchStartY - touchEndY


  /*
    Minimal jarak swipe.

    Jika terlalu kecil,
    tidak dianggap sebagai swipe.
  */

  const minimumSwipeDistance = 60


  /* =========================
     SWIPE KE ATAS
  ========================= */

  if (distance > minimumSwipeDistance) {

    nextPage()

    return

  }


  /* =========================
     SWIPE KE BAWAH
  ========================= */

  if (distance < -minimumSwipeDistance) {

    previousPage()

  }

}


/* =========================
   NEXT PAGE
========================= */

const nextPage = () => {

  /*
    Mencegah satu swipe
    memindahkan beberapa halaman
  */

  if (isMoving) return


  /*
    Jika sudah halaman terakhir,
    jangan lanjut
  */

  if (
    currentPage.value >=
    totalPages - 1
  ) {

    return

  }


  /*
    Lock
  */

  isMoving = true


  /*
    Pindah hanya satu halaman
  */

  currentPage.value += 1


  /*
    Unlock setelah animasi selesai
  */

  setTimeout(() => {

    isMoving = false

  }, 800)

}


/* =========================
   PREVIOUS PAGE
========================= */

const previousPage = () => {

  /*
    Jika sedang animasi,
    jangan menerima swipe baru
  */

  if (isMoving) return


  /*
    Jika sudah halaman pertama
  */

  if (
    currentPage.value <= 0
  ) {

    return

  }


  /*
    Lock
  */

  isMoving = true


  /*
    Mundur hanya satu halaman
  */

  currentPage.value -= 1


  /*
    Unlock
  */

  setTimeout(() => {

    isMoving = false

  }, 800)

}


/* =========================
   MOUSE WHEEL
   UNTUK TESTING LAPTOP
========================= */

const handleWheel = (event) => {

  if (isMoving) return


  /*
    Scroll ke bawah
  */

  if (event.deltaY > 0) {

    nextPage()

  }


  /*
    Scroll ke atas
  */

  else if (event.deltaY < 0) {

    previousPage()

  }

}

</script>


<style>

/* =========================
   RESET
========================= */

* {

  margin: 0;

  padding: 0;

  box-sizing: border-box;

}


/* =========================
   HTML
========================= */

html {

  width: 100%;

  height: 100%;

  overflow: hidden;

}


/* =========================
   BODY
========================= */

body {

  width: 100%;

  height: 100%;

  overflow: hidden;

}


/* =========================
   VUE APP
========================= */

#app {

  width: 100%;

  height: 100%;

  overflow: hidden;

}


/* =========================
   MAIN APP
========================= */

.app {

  width: 100%;

  /*
    PENTING:

    Gunakan dynamic viewport height.

    Ini mengikuti tinggi area
    yang benar-benar terlihat
    pada iPhone Safari.
  */

  height: 100dvh;


  overflow: hidden;


  /*
    Mencegah browser melakukan
    scroll bawaan
  */

  overscroll-behavior: none;


  /*
    Kita menangani swipe sendiri
  */

  touch-action: pan-x;

}


/* =========================
   PAGES CONTAINER
========================= */

.pages-container {

  width: 100%;

  /*
    Semua halaman tersusun vertikal
  */

  display: flex;

  flex-direction: column;


  /*
    Animasi perpindahan halaman
  */

  transition:

    transform
    0.8s
    cubic-bezier(
      0.77,
      0,
      0.175,
      1
    );


  /*
    Membuat animasi lebih halus
  */

  will-change: transform;

}


/* =========================
   SETIAP HALAMAN
========================= */

.page {

  width: 100%;


  /*
    INI BAGIAN PALING PENTING

    Setiap halaman harus memiliki
    tinggi PERSIS sama dengan
    viewport aplikasi.
  */

  height: 100dvh;


  /*
    Jangan menggunakan 100vh
    atau 100svh di sini.
  */

  flex-shrink: 0;


  overflow: hidden;


  position: relative;

}


/* =========================
   MOBILE FALLBACK
========================= */

@supports not (height: 100dvh) {

  .app {

    height: 100vh;

  }


  .page {

    height: 100vh;

  }

}

</style>