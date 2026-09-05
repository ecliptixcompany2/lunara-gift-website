<template>
  <section class="page-four">

    <!-- Background texture -->
    <div class="noise"></div>

    <!-- Decorative stars -->
    <div class="star star-one">✦</div>
    <div class="star star-two">✧</div>
    <div class="star star-three">✦</div>

    <!-- Top decoration -->
    <div class="top-decoration">
      <span>♡</span>
    </div>


    <!-- MAIN CONTENT -->
    <main class="ending-content">

      <!-- Small text -->
      <p class="small-title">
        and if I had to choose again...
      </p>


      <!-- Main title -->
      <h1>
        I'd still
        <span>choose you.</span>
      </h1>


      <!-- Heart -->
      <div class="main-heart">
        ♡
      </div>


      <!-- Message -->
      <div class="message">

        <p>
          Not because everything is always perfect,
        </p>

        <p>
          but because somehow,
          among all the possibilities
          in this world,
        </p>

        <p class="highlight">
          you are still my favorite one.
        </p>

      </div>


      <!-- Decorative line -->
      <div class="divider">
        <span></span>
        <b>♡</b>
        <span></span>
      </div>


      <!-- Final quote -->
      <div class="final-quote">

        <p>
          Thank you for being
          <br />
          part of my story.
        </p>

        <span>
          I hope I can stay
          <br />
          in yours too.
        </span>

      </div>


      <!-- Signature -->
      <div class="signature">

        <p>with love,</p>

        <!-- Ubah bagian ini dengan nama pengirim -->
        <h2>someone who loves you</h2>

      </div>

    </main>


    <!-- Bottom decoration -->
    <div class="bottom-decoration">

      <div class="heart-line">
        ─── ♡ ───
      </div>

      <p>
        the end,
        <span>or maybe just the beginning.</span>
      </p>

    </div>

  </section>
</template>


<script setup>

/*
|--------------------------------------------------------------------------
| PAGE FOUR
|--------------------------------------------------------------------------
|
| Halaman terakhir.
|
| Kamu bisa mengganti:
|
| "someone who loves you"
|
| dengan nama pengirim website.
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

.page-four {
  position: relative;

  width: 100%;
  min-height: 100vh;
  min-height: 100svh;

  overflow: hidden;

  display: flex;
  flex-direction: column;
  align-items: center;

  padding: 45px 20px 35px;

  color: #f2e5dc;

  background:

    radial-gradient(
      circle at 50% 20%,
      rgba(120, 35, 45, 0.35),
      transparent 35%
    ),

    radial-gradient(
      circle at 10% 85%,
      rgba(100, 20, 30, 0.3),
      transparent 35%
    ),

    radial-gradient(
      circle at 90% 75%,
      rgba(90, 15, 25, 0.25),
      transparent 30%
    ),

    linear-gradient(
      135deg,
      #1b0306,
      #4a0b12 55%,
      #210407
    );
}


/* =====================================================
   NOISE
===================================================== */

.noise {
  position: absolute;

  inset: 0;

  pointer-events: none;

  opacity: 0.16;

  background-image:

    radial-gradient(
      rgba(255, 255, 255, 0.45) 0.5px,
      transparent 0.8px
    );

  background-size: 4px 4px;

  mix-blend-mode: soft-light;
}


/* =====================================================
   DECORATIVE STARS
===================================================== */

.star {
  position: absolute;

  z-index: 2;

  color:
    rgba(240, 220, 205, 0.4);

  pointer-events: none;
}


.star-one {
  top: 80px;
  left: 12%;

  font-size: 20px;
}


.star-two {
  top: 200px;
  right: 10%;

  font-size: 28px;
}


.star-three {
  bottom: 150px;
  left: 8%;

  font-size: 18px;
}


/* =====================================================
   TOP DECORATION
===================================================== */

.top-decoration {
  position: relative;

  z-index: 5;

  font-size: 38px;

  color:
    rgba(240, 220, 205, 0.8);

  transform:
    rotate(-10deg);
}


/* =====================================================
   MAIN CONTENT
===================================================== */

.ending-content {
  position: relative;

  z-index: 5;

  width: 100%;
  max-width: 500px;

  display: flex;
  flex-direction: column;

  align-items: center;

  text-align: center;

  margin-top: 25px;
}


/* =====================================================
   SMALL TITLE
===================================================== */

.small-title {

  font-family:
    "Cormorant Garamond",
    serif;

  font-size: 16px;

  font-style: italic;

  letter-spacing: 2px;

  color:
    rgba(240, 220, 205, 0.75);
}


/* =====================================================
   MAIN TITLE
===================================================== */

.ending-content h1 {

  margin-top: 15px;

  font-family:
    "Cormorant Garamond",
    serif;

  font-size:
    clamp(55px, 11vw, 95px);

  font-weight: 400;

  line-height: 0.85;

  letter-spacing: 1px;

  color: #f2e2d6;
}


.ending-content h1 span {

  display: block;

  margin-top: 15px;

  font-family:
    "Great Vibes",
    cursive;

  font-size:
    clamp(60px, 13vw, 110px);

  font-weight: 400;

  color: #e8d2c4;

  transform:
    rotate(-4deg);
}


/* =====================================================
   MAIN HEART
===================================================== */

.main-heart {

  margin-top: 25px;

  font-size: 48px;

  color:
    rgba(240, 220, 205, 0.9);

  animation:
    heartbeat 2.5s ease-in-out infinite;
}


@keyframes heartbeat {

  0% {
    transform: scale(1);
  }

  50% {
    transform: scale(1.12);
  }

  100% {
    transform: scale(1);
  }

}


/* =====================================================
   MESSAGE
===================================================== */

.message {

  margin-top: 22px;

  max-width: 340px;
}


.message p {

  margin-bottom: 12px;

  font-family:
    "Cormorant Garamond",
    serif;

  font-size: 18px;

  line-height: 1.35;

  letter-spacing: 0.7px;

  color:
    rgba(242, 225, 215, 0.9);
}


.message .highlight {

  margin-top: 18px;

  font-family:
    "Great Vibes",
    cursive;

  font-size: 32px;

  line-height: 1.1;

  color: #f0d8c8;
}


/* =====================================================
   DIVIDER
===================================================== */

.divider {

  width: 100%;

  max-width: 230px;

  margin: 25px 0;

  display: flex;

  align-items: center;

  justify-content: center;

  gap: 12px;
}


.divider span {

  width: 70px;

  height: 1px;

  background:
    rgba(240, 220, 205, 0.45);
}


.divider b {

  font-size: 23px;

  font-weight: 400;

  color:
    rgba(240, 220, 205, 0.8);
}


/* =====================================================
   FINAL QUOTE
===================================================== */

.final-quote p {

  font-family:
    "Cormorant Garamond",
    serif;

  font-size: 19px;

  line-height: 1.35;

  letter-spacing: 1px;

  color:
    rgba(242, 225, 215, 0.9);
}


.final-quote span {

  display: block;

  margin-top: 12px;

  font-family:
    "Great Vibes",
    cursive;

  font-size: 34px;

  line-height: 1.1;

  color: #e9d3c5;
}


/* =====================================================
   SIGNATURE
===================================================== */

.signature {

  margin-top: 30px;

  text-align: center;
}


.signature p {

  font-family:
    "Cormorant Garamond",
    serif;

  font-size: 14px;

  font-style: italic;

  letter-spacing: 1px;

  color:
    rgba(240, 220, 205, 0.7);
}


.signature h2 {

  margin-top: 5px;

  font-family:
    "Great Vibes",
    cursive;

  font-size: 34px;

  font-weight: 400;

  color: #f0d9cb;
}


/* =====================================================
   BOTTOM DECORATION
===================================================== */

.bottom-decoration {

  position: absolute;

  z-index: 5;

  bottom: 25px;

  left: 50%;

  width: 100%;

  transform:
    translateX(-50%);

  text-align: center;
}


.heart-line {

  font-family:
    "Cormorant Garamond",
    serif;

  font-size: 18px;

  letter-spacing: 3px;

  color:
    rgba(240, 220, 205, 0.65);
}


.bottom-decoration p {

  margin-top: 8px;

  font-family:
    "Cormorant Garamond",
    serif;

  font-size: 13px;

  font-style: italic;

  letter-spacing: 1px;

  color:
    rgba(240, 220, 205, 0.6);
}


.bottom-decoration p span {

  font-family:
    "Great Vibes",
    cursive;

  font-size: 19px;

  color:
    rgba(240, 220, 205, 0.75);
}


/* =====================================================
   MOBILE
===================================================== */

@media (max-width: 480px) {

  .page-four {
    padding-left: 15px;
    padding-right: 15px;
  }


  .message p {
    font-size: 16px;
  }


  .final-quote p {
    font-size: 17px;
  }

}


/* =====================================================
   SHORT SCREEN
===================================================== */

@media (max-height: 800px) {

  .page-four {
    padding-top: 20px;
  }


  .ending-content {
    margin-top: 12px;
  }


  .top-decoration {
    font-size: 30px;
  }


  .small-title {
    font-size: 13px;
  }


  .ending-content h1 {
    font-size: 48px;
  }


  .ending-content h1 span {
    font-size: 60px;
  }


  .main-heart {
    margin-top: 15px;

    font-size: 35px;
  }


  .message {
    margin-top: 15px;
  }


  .message p {
    margin-bottom: 8px;

    font-size: 14px;
  }


  .message .highlight {
    margin-top: 10px;

    font-size: 27px;
  }


  .divider {
    margin: 15px 0;
  }


  .final-quote p {
    font-size: 15px;
  }


  .final-quote span {
    font-size: 27px;
  }


  .signature {
    margin-top: 18px;
  }


  .signature h2 {
    font-size: 28px;
  }


  .bottom-decoration {
    bottom: 12px;
  }

}

</style>