<template>
  <section class="page-two">

    <!-- Background texture -->
    <div class="noise"></div>

    <!-- Decorative flowers -->
    <div class="flower flower-top">✦</div>
    <div class="flower flower-left">❋</div>

    <!-- Title -->
    <div class="hero-title">
      <h1>little moments,</h1>
      <span>big memories.</span>
    </div>

    <!-- Heart -->
    <div class="top-heart">♡</div>

    <!-- Subtitle -->
    <div class="subtitle">
      <p>
        Every laugh, every talk, every glance—
        <br />
        pieces of us I'll always hold close.
      </p>
    </div>


    <!-- MEMORY COLLAGE -->
    <div class="memory-area">

      <!-- LEFT POLAROID / GIRL -->
      <div class="polaroid girl-polaroid">

        <div class="tape tape-girl"></div>

        <div class="photo-frame">
          <img
            :src="girlPhoto"
            alt="Her photo"
          />
        </div>

        <div class="polaroid-caption">
          you <span>♡</span>
        </div>

      </div>


      <!-- RIGHT POLAROID / BOY -->
      <div class="polaroid boy-polaroid">

        <div class="tape tape-boy"></div>

        <div class="photo-frame">
          <img
            :src="boyPhoto"
            alt="His photo"
          />
        </div>

        <div class="polaroid-caption">
          me <span>♡</span>
        </div>

      </div>


      <!-- Decorative letter -->
      <div class="letter-note">

        <div class="letter-title">
          Memories <span>♡</span>
        </div>

        <p>
          Some days become memories,
          <br />
          and some memories
          <br />
          become forever.
        </p>

      </div>


      <!-- Decorative paper -->
      <div class="paper-decoration"></div>

    </div>


    <!-- Bottom decoration -->
    <div class="bottom-decoration">
      <span>♡</span>
    </div>


    <!-- Swipe indicator -->
    <div class="swipe-indicator">

      <p>swipe up</p>

      <div class="swipe-arrow">
        <span></span>
      </div>

    </div>

  </section>
</template>


<script setup>

/*
|--------------------------------------------------------------------------
| IMAGE PATH
|--------------------------------------------------------------------------
|
| Simpan gambar di:
|
| public/images/girl-photo.jpg
| public/images/boy-photo.jpg
|
*/

const girlPhoto = `${import.meta.env.BASE_URL}images/girl-photo.jpg`

const boyPhoto = `${import.meta.env.BASE_URL}images/boy-photo.jpg`

</script>


<style scoped>

@import url(
  'https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@400;500;600&family=Great+Vibes&display=swap'
);


/* =====================================================
   RESET
===================================================== */

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}


/* =====================================================
   MAIN PAGE
===================================================== */

.page-two {
  position: relative;

  width: 100%;
  height: 100%;
  min-height: 100svh;

  overflow: hidden;

  display: flex;
  flex-direction: column;
  align-items: center;

  padding: 40px 20px 30px;

  color: #f3e5dc;

  background:
    radial-gradient(
      circle at 80% 15%,
      rgba(105, 25, 35, 0.3),
      transparent 32%
    ),
    radial-gradient(
      circle at 15% 70%,
      rgba(120, 35, 35, 0.2),
      transparent 35%
    ),
    linear-gradient(
      135deg,
      #200407,
      #4a0b12 55%,
      #250407
    );
}


/* =====================================================
   NOISE
===================================================== */

.noise {
  position: absolute;

  inset: 0;

  pointer-events: none;

  opacity: 0.18;

  background-image:
    radial-gradient(
      rgba(255, 255, 255, 0.35) 0.5px,
      transparent 0.8px
    );

  background-size: 4px 4px;

  mix-blend-mode: soft-light;
}


/* =====================================================
   TITLE
===================================================== */

.hero-title {
  position: relative;

  z-index: 5;

  text-align: center;
}


.hero-title h1 {
  font-family: "Cormorant Garamond", serif;

  font-size: clamp(40px, 7vw, 70px);

  font-weight: 400;

  letter-spacing: 2px;

  line-height: 0.9;

  color: #f0dfd2;
}


.hero-title span {
  display: block;

  margin-top: 5px;

  font-family: "Great Vibes", cursive;

  font-size: clamp(48px, 8vw, 75px);

  line-height: 0.8;

  color: #e8d4c6;

  transform: rotate(-4deg);
}


/* =====================================================
   TOP HEART
===================================================== */

.top-heart {
  position: relative;

  z-index: 5;

  margin-top: 18px;

  font-size: 35px;

  color: #e8d5c7;
}


/* =====================================================
   SUBTITLE
===================================================== */

.subtitle {
  position: relative;

  z-index: 5;

  margin-top: 12px;

  text-align: center;
}


.subtitle p {
  font-family: "Cormorant Garamond", serif;

  font-size: 16px;

  line-height: 1.45;

  letter-spacing: 1px;

  color: rgba(245, 226, 215, 0.9);
}


/* =====================================================
   MEMORY AREA
===================================================== */

.memory-area {
  position: relative;

  z-index: 4;

  width: min(92vw, 470px);

  height: 520px;

  margin-top: 20px;
}


/* =====================================================
   POLAROID GENERAL
===================================================== */

.polaroid {
  position: absolute;

  z-index: 4;

  width: 62%;

  padding: 13px 13px 42px;

  background:
    linear-gradient(
      145deg,
      #6a1b21,
      #3a090e
    );

  box-shadow:
    0 20px 40px rgba(0, 0, 0, 0.45);
}


/* =====================================================
   PHOTO FRAME
===================================================== */

.photo-frame {
  width: 100%;

  overflow: hidden;

  background: #1c0608;
}


.photo-frame img {
  display: block;

  width: 100%;
  height: 285px;

  object-fit: cover;
  object-position: center;

  filter:
    grayscale(100%)
    contrast(1.05)
    sepia(18%);
}


/* =====================================================
   GIRL POLAROID
===================================================== */

.girl-polaroid {
  top: 10px;
  left: 0;

  transform: rotate(-5deg);
}


/* =====================================================
   BOY POLAROID
===================================================== */

.boy-polaroid {
  top: 160px;
  right: 0;

  z-index: 5;

  transform: rotate(6deg);
}


/* =====================================================
   POLAROID CAPTION
===================================================== */

.polaroid-caption {
  position: absolute;

  left: 0;
  right: 0;

  bottom: 8px;

  text-align: center;

  font-family: "Great Vibes", cursive;

  font-size: 32px;

  color: #f0ddd0;
}


.polaroid-caption span {
  margin-left: 6px;

  font-size: 20px;
}


/* =====================================================
   TAPE
===================================================== */

.tape {
  position: absolute;

  z-index: 10;

  width: 100px;
  height: 30px;

  opacity: 0.45;

  background:
    rgba(201, 164, 130, 0.5);
}


.tape-girl {
  top: -13px;
  left: 50%;

  transform:
    translateX(-50%)
    rotate(-5deg);
}


.tape-boy {
  top: -13px;
  left: 50%;

  transform:
    translateX(-50%)
    rotate(5deg);
}


/* =====================================================
   LETTER NOTE
===================================================== */

.letter-note {
  position: absolute;

  z-index: 7;

  left: 5%;
  bottom: -5px;

  width: 45%;

  min-height: 160px;

  padding: 20px 15px;

  transform: rotate(-7deg);

  background:
    repeating-linear-gradient(
      to bottom,
      transparent 0,
      transparent 27px,
      rgba(95, 45, 40, 0.18) 28px
    ),
    #e8dac8;

  box-shadow:
    8px 12px 25px rgba(0, 0, 0, 0.3);
}


.letter-title {
  margin-bottom: 12px;

  font-family: "Great Vibes", cursive;

  font-size: 27px;

  color: #5e2427;
}


.letter-title span {
  font-size: 18px;
}


.letter-note p {
  font-family: "Cormorant Garamond", serif;

  font-size: 14px;

  line-height: 1.45;

  letter-spacing: 0.5px;

  color: #4c2023;
}


/* =====================================================
   PAPER DECORATION
===================================================== */

.paper-decoration {
  position: absolute;

  z-index: 2;

  top: 90px;
  right: -50px;

  width: 170px;
  height: 230px;

  opacity: 0.5;

  transform: rotate(10deg);

  background:
    repeating-linear-gradient(
      to bottom,
      rgba(100, 55, 50, 0.1) 0,
      rgba(100, 55, 50, 0.1) 1px,
      transparent 1px,
      transparent 28px
    ),
    #d9c5ae;
}


/* =====================================================
   DECORATIVE FLOWERS
===================================================== */

.flower {
  position: absolute;

  z-index: 2;

  color:
    rgba(235, 210, 190, 0.35);

  pointer-events: none;
}


.flower-top {
  top: 15px;
  right: 35px;

  font-size: 24px;
}


.flower-left {
  left: 15px;
  bottom: 220px;

  font-size: 30px;
}


/* =====================================================
   BOTTOM HEART
===================================================== */

.bottom-decoration {
  position: relative;

  z-index: 5;

  margin-top: -5px;

  font-size: 35px;

  color:
    rgba(235, 215, 200, 0.7);
}


/* =====================================================
   SWIPE INDICATOR
===================================================== */

.swipe-indicator {
  position: absolute;

  z-index: 10;

  left: 50%;
  bottom: 28px;

  transform:
    translateX(-50%);

  text-align: center;
}


.swipe-indicator p {
  margin-bottom: 10px;

  font-family: "Cormorant Garamond", serif;

  font-size: 13px;

  letter-spacing: 3px;

  color:
    rgba(240, 220, 205, 0.85);
}


.swipe-arrow {
  position: relative;

  width: 60px;
  height: 25px;

  margin: auto;
}


.swipe-arrow span {
  position: absolute;

  left: 50%;
  top: 8px;

  width: 16px;
  height: 16px;

  border-left:
    1px solid #eadbd0;

  border-top:
    1px solid #eadbd0;

  transform:
    translateX(-50%)
    rotate(45deg);
}


/* =====================================================
   MOBILE SMALL
===================================================== */

@media (max-width: 480px) {

  .page-two {
    padding-left: 15px;
    padding-right: 15px;
  }


  .memory-area {
    width: 94vw;
  }


  .photo-frame img {
    height: 265px;
  }


  .subtitle p {
    font-size: 15px;
  }

}


/* =====================================================
   SHORT SCREEN
===================================================== */

@media (max-height: 800px) {

  .page-two {
    padding-top: 25px;
  }


  .hero-title h1 {
    font-size: 38px;
  }


  .hero-title span {
    font-size: 48px;
  }


  .top-heart {
    margin-top: 10px;
  }


  .memory-area {
    height: 450px;

    margin-top: 10px;
  }


  .photo-frame img {
    height: 235px;
  }


  .boy-polaroid {
    top: 125px;
  }


  .letter-note {
    min-height: 130px;
  }


  .swipe-indicator {
    bottom: 18px;
  }

}

</style>