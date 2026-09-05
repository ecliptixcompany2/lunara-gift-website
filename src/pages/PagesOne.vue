<template>
  <section class="page-one">

    <!-- Background texture -->
    <div class="noise"></div>

    <!-- Title -->
    <div class="hero-title">
      <h1>for you,</h1>
      <span>always.</span>
    </div>

    <!-- Top heart -->
    <div class="top-heart">♡</div>

    <!-- Memory collage -->
    <div class="memory-area">

      <!-- Letter paper -->
      <div class="letter-paper">
        <p>
          I love you more than<br />
          all the stars in the night,<br />
          and more than all the words<br />
          poetry could ever write.
        </p>

        <span class="letter-heart heart-one">♥</span>
        <span class="letter-heart heart-two">♡</span>
      </div>

      <!-- Polaroid -->
      <div class="polaroid">
        <img
          :src="coverPhoto"
          alt="Our memory"
        />
      </div>

      <!-- Tape -->
      <div class="tape"></div>

    </div>

    <!-- Poetry -->
    <div class="poetry">
      <p>
        Some feelings are too special<br />
        to be said out loud,<br />
        so I made this
      </p>

      <span>just for you.</span>
    </div>

    <!-- Bottom heart -->
    <div class="bottom-heart">♡</div>

    <!-- Swipe indicator -->
    <div class="swipe-indicator">
      <p>swipe to begin</p>

      <div class="swipe-line">
        <span></span>
      </div>
    </div>

  </section>
</template>

<script setup>

// File gambar harus berada di:
// public/images/cover-photo.jpg
//
// Gunakan BASE_URL agar aman jika project menggunakan base path Vite.
const coverPhoto = `${import.meta.env.BASE_URL}images/cover-photo.jpg`

</script>

<style scoped>

@import url('https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@400;500;600&family=Great+Vibes&display=swap');


/* =========================
   RESET
========================= */

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}


/* =========================
   MAIN PAGE
========================= */

.page-one {
  position: relative;

  width: 100%;
  min-height: 100vh;
  min-height: 100svh;

  overflow: hidden;

  display: flex;
  flex-direction: column;
  align-items: center;

  padding: 45px 20px 25px;

  color: #f2e7dd;

  background:
    radial-gradient(
      circle at 80% 10%,
      rgba(115, 35, 40, 0.35),
      transparent 30%
    ),
    radial-gradient(
      circle at 20% 80%,
      rgba(110, 20, 30, 0.25),
      transparent 35%
    ),
    linear-gradient(
      135deg,
      #210407 0%,
      #4a0b12 45%,
      #250407 100%
    );
}


/* =========================
   NOISE
========================= */

.noise {
  position: absolute;

  inset: 0;

  pointer-events: none;

  opacity: 0.15;

  background-image:
    radial-gradient(
      rgba(255, 255, 255, 0.45) 0.5px,
      transparent 0.7px
    );

  background-size: 4px 4px;

  mix-blend-mode: soft-light;
}


/* =========================
   TITLE
========================= */

.hero-title {
  position: relative;

  z-index: 5;

  text-align: center;
}


.hero-title h1 {
  font-family: "Cormorant Garamond", serif;

  font-size: clamp(52px, 8vw, 85px);

  font-weight: 400;

  line-height: 0.85;

  letter-spacing: 1px;

  color: #f3e5d9;
}


.hero-title span {
  display: block;

  margin-top: 12px;

  font-family: "Great Vibes", cursive;

  font-size: clamp(50px, 8vw, 80px);

  line-height: 0.7;

  color: #ead8ca;

  transform: rotate(-5deg);
}


/* =========================
   TOP HEART
========================= */

.top-heart {
  position: relative;

  z-index: 5;

  margin-top: 15px;

  font-size: 35px;

  color: #e8d5c8;

  transform: rotate(-10deg);
}


/* =========================
   MEMORY AREA
========================= */

.memory-area {
  position: relative;

  z-index: 4;

  width: min(88vw, 430px);

  height: 420px;

  margin-top: 15px;
}


/* =========================
   LETTER
========================= */

.letter-paper {
  position: absolute;

  right: -2%;
  top: 55px;

  width: 60%;
  height: 310px;

  padding: 45px 18px 20px;

  overflow: hidden;

  transform: rotate(4deg);

  background:
    repeating-linear-gradient(
      to bottom,
      transparent 0,
      transparent 30px,
      rgba(130, 55, 55, 0.18) 31px
    ),
    #eee3d5;

  box-shadow:
    8px 12px 30px rgba(0, 0, 0, 0.25);
}


.letter-paper p {
  position: relative;

  z-index: 2;

  font-family: "Great Vibes", cursive;

  font-size: 21px;

  line-height: 1.55;

  color: #6b2529;

  transform: rotate(-2deg);
}


.letter-heart {
  position: absolute;

  color: #72252b;

  font-size: 28px;
}


.heart-one {
  top: 15px;
  right: 20px;
}


.heart-two {
  bottom: 35px;
  right: 30px;
}


/* =========================
   POLAROID
========================= */

.polaroid {
  position: absolute;

  left: 0;
  top: 10px;

  z-index: 3;

  width: 76%;

  padding: 13px 13px 52px;

  transform: rotate(-2deg);

  background:
    linear-gradient(
      145deg,
      #681b20,
      #3d090e
    );

  box-shadow:
    0 25px 45px rgba(0, 0, 0, 0.45);
}


.polaroid img {
  display: block;

  width: 100%;
  height: 325px;

  object-fit: cover;
  object-position: center;

  filter:
    grayscale(100%)
    contrast(1.05)
    sepia(18%);
}


/* =========================
   TAPE
========================= */

.tape {
  position: absolute;

  z-index: 6;

  top: 0;
  right: 28px;

  width: 110px;
  height: 32px;

  opacity: 0.45;

  transform: rotate(12deg);

  background:
    rgba(185, 145, 120, 0.45);
}


/* =========================
   POETRY
========================= */

.poetry {
  position: relative;

  z-index: 5;

  max-width: 330px;

  margin-top: 10px;

  text-align: center;

  color: #eadbd0;
}


.poetry p {
  font-family: "Cormorant Garamond", serif;

  font-size: 18px;

  line-height: 1.3;

  letter-spacing: 1px;
}


.poetry span {
  display: block;

  margin-top: 3px;

  font-family: "Great Vibes", cursive;

  font-size: 30px;

  color: #f0ddd0;
}


/* =========================
   BOTTOM HEART
========================= */

.bottom-heart {
  position: relative;

  z-index: 5;

  margin-top: 8px;

  font-size: 40px;

  color: #ead8c8;

  transform: rotate(-8deg);
}


/* =========================
   SWIPE INDICATOR
========================= */

.swipe-indicator {
  position: absolute;

  left: 50%;
  bottom: 25px;

  z-index: 10;

  transform: translateX(-50%);

  text-align: center;

  color: #eadbd0;
}


.swipe-indicator p {
  margin-bottom: 10px;

  font-family: "Cormorant Garamond", serif;

  font-size: 13px;

  font-style: italic;

  letter-spacing: 2px;

  opacity: 0.85;
}


.swipe-line {
  position: relative;

  width: 170px;
  height: 1px;

  background:
    rgba(240, 220, 205, 0.65);
}


.swipe-line span {
  position: absolute;

  right: 0;
  top: -4px;

  width: 9px;
  height: 9px;

  border-top:
    1px solid #eadbd0;

  border-right:
    1px solid #eadbd0;

  transform:
    rotate(45deg);
}


/* =========================
   RESPONSIVE
========================= */

@media (max-width: 480px) {

  .page-one {
    padding-top: 40px;
  }

  .memory-area {
    height: 400px;
  }

  .letter-paper {
    height: 295px;
  }

  .polaroid img {
    height: 305px;
  }

}


@media (max-height: 750px) {

  .page-one {
    padding-top: 25px;
  }

  .hero-title h1 {
    font-size: 48px;
  }

  .hero-title span {
    font-size: 52px;
  }

  .memory-area {
    height: 340px;

    margin-top: 8px;
  }

  .letter-paper {
    height: 255px;

    top: 40px;
  }

  .polaroid {
    padding-bottom: 40px;
  }

  .polaroid img {
    height: 255px;
  }

  .poetry {
    margin-top: 0;
  }

  .poetry p {
    font-size: 15px;
  }

  .poetry span {
    font-size: 26px;
  }

}

</style>