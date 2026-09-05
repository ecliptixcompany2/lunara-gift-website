<template>
  <main
    class="app"
    @touchstart="handleTouchStart"
    @touchend="handleTouchEnd"
    @wheel.prevent="handleWheel"
  >

    <!-- ========================= -->
    <!-- MUSIC -->
    <!-- ========================= -->

    <audio
      ref="audioPlayer"
      loop
      preload="auto"
    >
      <source
        src="/music.mp3"
        type="audio/mpeg"
      />
    </audio>


    <!-- ========================= -->
    <!-- MUSIC BUTTON -->
    <!-- ========================= -->

    <button
      class="music-button"
      :class="{ playing: isPlaying }"
      @click="toggleMusic"
      aria-label="Play or pause music"
    >

      <!-- MUSIC OFF -->
      <span v-if="!isPlaying">
        ♫
      </span>


      <!-- MUSIC ON -->
      <span
        v-else
        class="music-playing-icon"
      >
        ♫
      </span>

    </button>


    <!-- ========================= -->
    <!-- PAGES -->
    <!-- ========================= -->

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


/* =========================
   PAGES
========================= */

import PagesOne from './pages/PagesOne.vue'
import PagesTwo from './pages/PagesTwo.vue'
import PagesThree from './pages/PagesThree.vue'
import PagesFour from './pages/PagesFour.vue'


/* =========================
   MUSIC
========================= */

const audioPlayer = ref(null)

const isPlaying = ref(false)


const toggleMusic = async () => {

  if (!audioPlayer.value) return


  if (isPlaying.value) {

    audioPlayer.value.pause()

    isPlaying.value = false

  }

  else {

    try {

      await audioPlayer.value.play()

      isPlaying.value = true

    }

    catch (error) {

      console.error(
        'Music cannot be played:',
        error
      )

    }

  }

}


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

  touchStartY =
    event.touches[0].clientY

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
    Minimal jarak swipe
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
    Jika sudah halaman terakhir
  */

  if (
    currentPage.value >=
    totalPages - 1
  ) {

    return

  }


  /*
    Lock perpindahan
  */

  isMoving = true


  /*
    Pindah tepat satu halaman
  */

  currentPage.value += 1


  /*
    Unlock setelah animasi
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
    Mencegah swipe ganda
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
    Mundur satu halaman
  */

  currentPage.value -= 1


  /*
    Unlock setelah animasi
  */

  setTimeout(() => {

    isMoving = false

  }, 800)

}


/* =========================
   MOUSE WHEEL
   UNTUK LAPTOP
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

  height: 100dvh;

  overflow: hidden;

  overscroll-behavior: none;

  touch-action: pan-x;

  position: relative;

}


/* =========================
   MUSIC BUTTON
========================= */

.music-button {

  position: fixed;

  top: calc(
    env(safe-area-inset-top) + 18px
  );

  right: 18px;

  z-index: 9999;

  width: 46px;

  height: 46px;

  display: flex;

  align-items: center;

  justify-content: center;

  border:

    1px solid
    rgba(255, 235, 225, 0.35);

  border-radius: 50%;

  background:

    rgba(70, 8, 15, 0.55);

  backdrop-filter:

    blur(10px);

  -webkit-backdrop-filter:

    blur(10px);

  color:

    #f3ded5;

  font-size: 21px;

  cursor: pointer;

  transition:

    transform 0.3s ease,
    background 0.3s ease;

}


/* =========================
   MUSIC BUTTON PLAYING
========================= */

.music-button.playing {

  background:

    rgba(110, 25, 35, 0.8);

  animation:

    musicPulse
    2s
    ease-in-out
    infinite;

}


.music-button:active {

  transform:

    scale(0.9);

}


/* =========================
   MUSIC ICON ANIMATION
========================= */

.music-playing-icon {

  animation:

    musicRotate
    2.5s
    linear
    infinite;

}


@keyframes musicPulse {

  0% {

    transform:
      scale(1);

  }

  50% {

    transform:
      scale(1.08);

  }

  100% {

    transform:
      scale(1);

  }

}


@keyframes musicRotate {

  from {

    transform:
      rotate(0deg);

  }

  to {

    transform:
      rotate(360deg);

  }

}


/* =========================
   PAGES CONTAINER
========================= */

.pages-container {

  width: 100%;

  display: flex;

  flex-direction: column;

  transition:

    transform
    0.8s
    cubic-bezier(
      0.77,
      0,
      0.175,
      1
    );

  will-change: transform;

}


/* =========================
   SETIAP HALAMAN
========================= */

.page {

  width: 100%;

  height: 100dvh;

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