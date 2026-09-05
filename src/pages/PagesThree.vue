<template>
  <section class="page-three">

    <!-- Background texture -->
    <div class="noise"></div>

    <!-- Decorative elements -->
    <div class="star star-one">✦</div>
    <div class="star star-two">✧</div>

    <!-- TITLE -->
    <div class="hero-title">
      <h1>a little letter,</h1>
      <span>for you.</span>
    </div>


    <!-- SMALL HEART -->
    <div class="top-heart">
      ♡
    </div>


    <!-- LETTER AREA -->
    <div class="letter-wrapper">

      <!-- Background paper shadow -->
      <div class="paper-back"></div>


      <!-- MAIN LETTER -->
      <article class="letter">

        <!-- Tape -->
        <div class="tape tape-left"></div>
        <div class="tape tape-right"></div>


        <!-- Letter header -->
        <div class="letter-header">
          <span>To my favorite person,</span>
        </div>


        <!-- Letter content -->
        <div class="letter-content">

          <p class="greeting">
            My dearest,
          </p>

          <p>
            I don't know if words will ever
            be enough to explain how grateful
            I am that our paths crossed.
          </p>

          <p>
            In a world full of temporary things,
            I hope you know that you are one of
            the moments I would choose to keep.
          </p>

          <p>
            Thank you for becoming a part
            of my story, my memories,
            and my favorite little moments.
          </p>

          <p>
            And if life ever gets difficult,
            I hope you remember this—
          </p>

          <p class="highlight">
            somewhere in this world,
            there is someone who is
            always grateful for you.
          </p>

        </div>


        <!-- Signature -->
        <div class="signature">
          <span>with all my heart,</span>
          <strong>always yours ♡</strong>
        </div>


        <!-- Decorative hearts -->
        <div class="letter-heart heart-one">♡</div>
        <div class="letter-heart heart-two">♥</div>

      </article>


      <!-- Decorative envelope -->
      <div class="envelope">

        <div class="envelope-flap"></div>

        <div class="envelope-heart">
          ♡
        </div>

      </div>

    </div>


    <!-- BOTTOM POETRY -->
    <div class="bottom-poetry">

      <p>
        Some things are easier
        <br />
        to write than to say.
      </p>

      <span>
        so this is for you.
      </span>

    </div>


    <!-- Swipe indicator -->
    <div class="swipe-indicator">

      <p>one more swipe</p>

      <div class="swipe-line">
        <span></span>
      </div>

    </div>

  </section>
</template>


<script setup>

/*
|--------------------------------------------------------------------------
| PAGE THREE
|--------------------------------------------------------------------------
|
| Halaman ini tidak menggunakan gambar.
| Semua konten bisa langsung kamu ubah pada bagian HTML.
|
*/

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

.page-three {
  position: relative;

  width: 100%;
  min-height: 100vh;
  min-height: 100svh;

  overflow: hidden;

  display: flex;
  flex-direction: column;
  align-items: center;

  padding: 45px 20px 30px;

  color: #f3e5dc;

  background:

    radial-gradient(
      circle at 80% 15%,
      rgba(115, 35, 45, 0.35),
      transparent 32%
    ),

    radial-gradient(
      circle at 10% 70%,
      rgba(120, 25, 35, 0.25),
      transparent 38%
    ),

    linear-gradient(
      135deg,
      #210407,
      #4a0b12 55%,
      #220407
    );
}


/* =====================================================
   NOISE
===================================================== */

.noise {
  position: absolute;

  inset: 0;

  pointer-events: none;

  opacity: 0.17;

  background-image:

    radial-gradient(
      rgba(255, 255, 255, 0.4) 0.5px,
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

  font-family:
    "Cormorant Garamond",
    serif;

  font-size:
    clamp(40px, 7vw, 72px);

  font-weight: 400;

  letter-spacing: 2px;

  line-height: 0.9;

  color: #f2dfd1;
}


.hero-title span {

  display: block;

  margin-top: 8px;

  font-family:
    "Great Vibes",
    cursive;

  font-size:
    clamp(50px, 9vw, 80px);

  line-height: 0.8;

  color: #ead5c7;

  transform:
    rotate(-4deg);
}


/* =====================================================
   TOP HEART
===================================================== */

.top-heart {

  position: relative;

  z-index: 5;

  margin-top: 15px;

  font-size: 34px;

  color:
    rgba(240, 220, 205, 0.8);
}


/* =====================================================
   LETTER WRAPPER
===================================================== */

.letter-wrapper {

  position: relative;

  z-index: 5;

  width:
    min(88vw, 430px);

  height: 520px;

  margin-top: 15px;
}


/* =====================================================
   BACK PAPER
===================================================== */

.paper-back {

  position: absolute;

  top: 25px;
  left: 50%;

  width: 90%;
  height: 440px;

  transform:
    translateX(-50%)
    rotate(4deg);

  background:

    linear-gradient(
      135deg,
      #d9c5b2,
      #bfa996
    );

  opacity: 0.35;

  box-shadow:

    0 20px 45px
    rgba(0, 0, 0, 0.35);
}


/* =====================================================
   MAIN LETTER
===================================================== */

.letter {

  position: absolute;

  z-index: 3;

  top: 0;
  left: 50%;

  width: 92%;
  height: 455px;

  padding:
    38px
    25px
    30px;

  overflow: hidden;

  transform:
    translateX(-50%)
    rotate(-2deg);

  background:

    repeating-linear-gradient(
      to bottom,

      transparent 0,

      transparent 30px,

      rgba(110, 55, 55, 0.13) 31px
    ),

    linear-gradient(
      135deg,
      #eee2d2,
      #e2d1bd
    );

  box-shadow:

    0 25px 50px
    rgba(0, 0, 0, 0.45);
}


/* =====================================================
   LETTER HEADER
===================================================== */

.letter-header {

  position: relative;

  z-index: 2;

  margin-bottom: 12px;

  text-align: center;

  font-family:
    "Cormorant Garamond",
    serif;

  font-size: 15px;

  font-style: italic;

  letter-spacing: 1px;

  color: #6a3030;
}


/* =====================================================
   LETTER CONTENT
===================================================== */

.letter-content {

  position: relative;

  z-index: 2;

  color: #542326;
}


.letter-content p {

  margin-bottom: 12px;

  font-family:
    "Cormorant Garamond",
    serif;

  font-size: 14px;

  line-height: 1.35;

  letter-spacing: 0.3px;
}


/* =====================================================
   GREETING
===================================================== */

.letter-content .greeting {

  margin-bottom: 12px;

  font-family:
    "Great Vibes",
    cursive;

  font-size: 31px;

  color: #722b30;
}


/* =====================================================
   HIGHLIGHT
===================================================== */

.letter-content .highlight {

  margin-top: 5px;

  font-family:
    "Great Vibes",
    cursive;

  font-size: 22px;

  line-height: 1.2;

  text-align: center;

  color: #762b31;
}


/* =====================================================
   SIGNATURE
===================================================== */

.signature {

  position: absolute;

  z-index: 3;

  right: 25px;
  bottom: 25px;

  text-align: right;

  color: #5e2529;
}


.signature span {

  display: block;

  font-family:
    "Cormorant Garamond",
    serif;

  font-size: 12px;

  font-style: italic;
}


.signature strong {

  display: block;

  margin-top: 3px;

  font-family:
    "Great Vibes",
    cursive;

  font-size: 22px;

  font-weight: 400;
}


/* =====================================================
   LETTER HEARTS
===================================================== */

.letter-heart {

  position: absolute;

  z-index: 1;

  color:
    rgba(120, 35, 40, 0.25);

  pointer-events: none;
}


.heart-one {

  top: 45px;
  right: 20px;

  font-size: 35px;

  transform:
    rotate(15deg);
}


.heart-two {

  left: 15px;
  bottom: 40px;

  font-size: 28px;

  transform:
    rotate(-15deg);
}


/* =====================================================
   TAPE
===================================================== */

.tape {

  position: absolute;

  z-index: 10;

  width: 85px;
  height: 26px;

  opacity: 0.42;

  background:
    rgba(180, 140, 110, 0.55);
}


.tape-left {

  top: -12px;
  left: 25px;

  transform:
    rotate(-10deg);
}


.tape-right {

  top: -12px;
  right: 25px;

  transform:
    rotate(10deg);
}


/* =====================================================
   ENVELOPE
===================================================== */

.envelope {

  position: absolute;

  z-index: 8;

  right: -10px;
  bottom: 5px;

  width: 120px;
  height: 80px;

  transform:
    rotate(8deg);

  background:
    linear-gradient(
      145deg,
      #7b2028,
      #3e090f
    );

  box-shadow:

    0 15px 30px
    rgba(0, 0, 0, 0.4);
}


/* Envelope flap */

.envelope-flap {

  position: absolute;

  top: 0;
  left: 0;

  width: 0;
  height: 0;

  border-left:
    60px solid transparent;

  border-right:
    60px solid transparent;

  border-top:
    45px solid #5d1219;
}


/* Envelope heart */

.envelope-heart {

  position: absolute;

  z-index: 3;

  left: 50%;
  top: 45px;

  transform:
    translateX(-50%);

  font-size: 25px;

  color: #f0d9c9;
}


/* =====================================================
   BOTTOM POETRY
===================================================== */

.bottom-poetry {

  position: relative;

  z-index: 5;

  margin-top: -15px;

  text-align: center;
}


.bottom-poetry p {

  font-family:
    "Cormorant Garamond",
    serif;

  font-size: 17px;

  line-height: 1.3;

  letter-spacing: 1px;

  color:
    rgba(240, 220, 205, 0.9);
}


.bottom-poetry span {

  display: block;

  margin-top: 4px;

  font-family:
    "Great Vibes",
    cursive;

  font-size: 29px;

  color: #ead6c8;
}


/* =====================================================
   STARS
===================================================== */

.star {

  position: absolute;

  z-index: 2;

  color:
    rgba(240, 220, 205, 0.35);

  pointer-events: none;
}


.star-one {

  top: 130px;
  left: 25px;

  font-size: 25px;
}


.star-two {

  right: 25px;
  bottom: 160px;

  font-size: 20px;
}


/* =====================================================
   SWIPE INDICATOR
===================================================== */

.swipe-indicator {

  position: absolute;

  z-index: 10;

  left: 50%;
  bottom: 25px;

  transform:
    translateX(-50%);

  text-align: center;
}


.swipe-indicator p {

  margin-bottom: 10px;

  font-family:
    "Cormorant Garamond",
    serif;

  font-size: 12px;

  font-style: italic;

  letter-spacing: 2px;

  color:
    rgba(240, 220, 205, 0.8);
}


.swipe-line {

  position: relative;

  width: 150px;
  height: 1px;

  background:
    rgba(240, 220, 205, 0.6);
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


/* =====================================================
   MOBILE
===================================================== */

@media (max-width: 480px) {

  .page-three {

    padding-left: 15px;
    padding-right: 15px;
  }


  .letter-wrapper {

    width: 94vw;
  }


  .letter {

    padding-left: 20px;
    padding-right: 20px;
  }


  .letter-content p {

    font-size: 13.5px;
  }

}


/* =====================================================
   SHORT SCREEN
===================================================== */

@media (max-height: 800px) {

  .page-three {

    padding-top: 25px;
  }


  .hero-title h1 {

    font-size: 38px;
  }


  .hero-title span {

    font-size: 48px;
  }


  .top-heart {

    margin-top: 8px;
  }


  .letter-wrapper {

    height: 445px;

    margin-top: 8px;
  }


  .paper-back {

    height: 380px;
  }


  .letter {

    height: 390px;

    padding-top: 28px;
  }


  .letter-content p {

    margin-bottom: 8px;

    font-size: 12px;
  }


  .letter-content .greeting {

    font-size: 26px;
  }


  .letter-content .highlight {

    font-size: 19px;
  }


  .bottom-poetry {

    margin-top: -5px;
  }


  .swipe-indicator {

    bottom: 15px;
  }

}

</style>