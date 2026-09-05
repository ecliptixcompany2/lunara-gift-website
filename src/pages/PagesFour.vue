<template>
  <section class="page-four">

    <!-- Background decorations -->
    <div class="glow glow-one"></div>
    <div class="glow glow-two"></div>

    <div class="star star-one">✦</div>
    <div class="star star-two">✧</div>
    <div class="star star-three">✦</div>


    <!-- ========================= -->
    <!-- PROGRESS -->
    <!-- ========================= -->

    <div class="progress">

      <span
        v-for="item in totalSteps"
        :key="item"
        :class="{ active: currentStep >= item }"
      ></span>

    </div>


    <!-- ========================= -->
    <!-- CONTENT -->
    <!-- ========================= -->

    <transition name="fade" mode="out-in">

      <!-- ========================= -->
      <!-- STEP 1 -->
      <!-- ========================= -->

      <div
        v-if="currentStep === 1"
        key="step-one"
        class="content"
      >

        <p class="eyebrow">
          and if I had to choose again...
        </p>


        <h1 class="main-title">
          I'd still
          <span>choose you.</span>
        </h1>


        <div class="heart-large">
          ♡
        </div>


        <p class="small-message">
          In a world full of possibilities,
          somehow my heart would still
          find its way back to you.
        </p>


        <button
          class="next-button"
          @click="nextStep"
        >

          <span>continue</span>

          <i>→</i>

        </button>

      </div>


      <!-- ========================= -->
      <!-- STEP 2 -->
      <!-- ========================= -->

      <div
        v-else-if="currentStep === 2"
        key="step-two"
        class="content"
      >

        <div class="heart-top">
          ♡
        </div>


        <p class="message">
          Not because everything
          is always perfect,
        </p>


        <p class="message">
          but because somehow,
          among all the possibilities
          in this world,
        </p>


        <h2 class="favorite-text">
          you are still
          <br />
          my favorite one.
        </h2>


        <div class="divider">

          <span></span>

          <b>♡</b>

          <span></span>

        </div>


        <div class="button-group">

          <button
            class="back-button"
            @click="previousStep"
          >
            ←
          </button>


          <button
            class="next-button"
            @click="nextStep"
          >

            <span>one more thing</span>

            <i>→</i>

          </button>

        </div>

      </div>


      <!-- ========================= -->
      <!-- STEP 3 -->
      <!-- ========================= -->

      <div
        v-else
        key="step-three"
        class="content final-content"
      >

        <div class="heart-top">
          ♡
        </div>


        <p class="thank-you">
          Thank you for being
          <br />
          part of my story.
        </p>


        <h2 class="hope-text">
          I hope I can stay
          <br />
          in yours too.
        </h2>


        <div class="small-divider">
          ─── ♡ ───
        </div>


        <div class="signature">

          <p>
            with love,
          </p>


          <!-- GANTI DENGAN NAMA PENGIRIM -->
          <h3>
            someone who loves you
          </h3>

        </div>


        <button
          class="restart-button"
          @click="restart"
        >

          ♡ read again

        </button>

      </div>

    </transition>


    <!-- ========================= -->
    <!-- BOTTOM TEXT -->
    <!-- ========================= -->

    <p class="bottom-text">
      the end,
      <span>or maybe just the beginning.</span>
    </p>

  </section>
</template>


<script setup>

import { ref } from 'vue'


/* =========================
   STEP
========================= */

const currentStep = ref(1)

const totalSteps = 3


/* =========================
   NEXT
========================= */

const nextStep = () => {

  if (
    currentStep.value < totalSteps
  ) {

    currentStep.value++

  }

}


/* =========================
   PREVIOUS
========================= */

const previousStep = () => {

  if (
    currentStep.value > 1
  ) {

    currentStep.value--

  }

}


/* =========================
   RESTART
========================= */

const restart = () => {

  currentStep.value = 1

}

</script>


<style scoped>

/* =========================
   GOOGLE FONTS
========================= */

@import url(
  'https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@400;500;600&family=Great+Vibes&display=swap'
);


/* =========================
   MAIN PAGE
========================= */

.page-four {

  position: relative;

  width: 100%;
  height: 100%;

  min-height: 100svh;

  overflow: hidden;

  display: flex;

  flex-direction: column;

  align-items: center;

  justify-content: center;

  padding:

    max(24px, env(safe-area-inset-top))

    24px

    max(24px, env(safe-area-inset-bottom));

  color: #f3e5dc;

  background:

    radial-gradient(
      circle at 50% 20%,
      rgba(115, 30, 42, 0.45),
      transparent 40%
    ),

    radial-gradient(
      circle at 10% 80%,
      rgba(90, 10, 20, 0.3),
      transparent 40%
    ),

    linear-gradient(
      135deg,
      #250407,
      #570c15,
      #260407
    );

}


/* =========================
   GLOW
========================= */

.glow {

  position: absolute;

  border-radius: 50%;

  pointer-events: none;

  filter: blur(70px);

}


.glow-one {

  width: 250px;

  height: 250px;

  top: -100px;

  right: -100px;

  background:
    rgba(150, 50, 60, 0.2);

}


.glow-two {

  width: 220px;

  height: 220px;

  bottom: -120px;

  left: -100px;

  background:
    rgba(120, 25, 40, 0.25);

}


/* =========================
   STARS
========================= */

.star {

  position: absolute;

  color:
    rgba(245, 220, 210, 0.45);

}


.star-one {

  top: 16%;

  left: 10%;

  font-size: 20px;

}


.star-two {

  top: 25%;

  right: 10%;

  font-size: 26px;

}


.star-three {

  bottom: 18%;

  left: 12%;

  font-size: 18px;

}


/* =========================
   PROGRESS
========================= */

.progress {

  position: absolute;

  top:
    max(
      24px,
      env(safe-area-inset-top)
    );

  left: 50%;

  transform:
    translateX(-50%);

  display: flex;

  gap: 8px;

}


.progress span {

  width: 28px;

  height: 2px;

  border-radius: 20px;

  background:
    rgba(255, 255, 255, 0.2);

  transition:
    0.4s ease;

}


.progress span.active {

  background:
    #ead5c8;

}


/* =========================
   CONTENT
========================= */

.content {

  position: relative;

  z-index: 2;

  width: 100%;

  max-width: 430px;

  display: flex;

  flex-direction: column;

  align-items: center;

  text-align: center;

}


/* =========================
   STEP ONE
========================= */

.eyebrow {

  font-family:
    "Cormorant Garamond",
    serif;

  font-size:
    clamp(15px, 4vw, 19px);

  font-style: italic;

  letter-spacing: 2px;

  color:
    rgba(245, 225, 215, 0.75);

}


.main-title {

  margin-top: 16px;

  font-family:
    "Cormorant Garamond",
    serif;

  font-size:
    clamp(58px, 15vw, 82px);

  font-weight: 400;

  line-height: 0.8;

  color: #f2e1d7;

}


.main-title span {

  display: block;

  margin-top: 18px;

  font-family:
    "Great Vibes",
    cursive;

  font-size:
    clamp(64px, 17vw, 95px);

  color: #e9d2c4;

  transform:
    rotate(-4deg);

}


.heart-large {

  margin-top: 35px;

  font-size:
    clamp(55px, 13vw, 75px);

  line-height: 1;

  color:
    #f0ddd3;

  animation:
    heartbeat
    2.5s
    infinite;

}


.small-message {

  max-width: 310px;

  margin-top: 28px;

  font-family:
    "Cormorant Garamond",
    serif;

  font-size:
    clamp(17px, 4.5vw, 20px);

  line-height: 1.5;

  letter-spacing: 0.5px;

  color:
    rgba(245, 225, 215, 0.85);

}


/* =========================
   HEART
========================= */

.heart-top {

  margin-bottom: 30px;

  font-size: 50px;

  color:
    #ecd8cd;

}


/* =========================
   MESSAGE
========================= */

.message {

  margin-bottom: 18px;

  max-width: 360px;

  font-family:
    "Cormorant Garamond",
    serif;

  font-size:
    clamp(19px, 5vw, 24px);

  line-height: 1.4;

  letter-spacing: 0.8px;

  color:
    rgba(245, 225, 215, 0.9);

}


.favorite-text {

  margin-top: 14px;

  font-family:
    "Great Vibes",
    cursive;

  font-size:
    clamp(42px, 11vw, 62px);

  font-weight: 400;

  line-height: 1.1;

  color: #f0d8ca;

}


/* =========================
   DIVIDER
========================= */

.divider {

  width: 100%;

  margin: 35px 0;

  display: flex;

  align-items: center;

  justify-content: center;

  gap: 15px;

}


.divider span {

  width: 100px;

  height: 1px;

  background:
    rgba(240, 220, 210, 0.45);

}


.divider b {

  font-size: 27px;

  font-weight: 400;

}


/* =========================
   BUTTON
========================= */

.next-button {

  margin-top: 32px;

  padding:
    12px
    18px;

  display: flex;

  align-items: center;

  gap: 14px;

  border: 1px solid
    rgba(240, 220, 210, 0.4);

  border-radius: 50px;

  color: #f1ded4;

  background:
    rgba(255, 255, 255, 0.04);

  backdrop-filter:
    blur(10px);

  font-family:
    "Cormorant Garamond",
    serif;

  font-size: 17px;

  cursor: pointer;

  transition:
    0.3s ease;

}


.next-button:active {

  transform:
    scale(0.95);

  background:
    rgba(255, 255, 255, 0.12);

}


.next-button i {

  font-size: 20px;

  font-style: normal;

}


/* =========================
   BUTTON GROUP
========================= */

.button-group {

  display: flex;

  align-items: center;

  gap: 12px;

}


.button-group .next-button {

  margin-top: 0;

}


.back-button {

  width: 45px;

  height: 45px;

  border-radius: 50%;

  border:
    1px solid
    rgba(240, 220, 210, 0.35);

  background:
    transparent;

  color:
    #f0d8ca;

  font-size: 20px;

  cursor: pointer;

}


.back-button:active {

  transform:
    scale(0.92);

}


/* =========================
   FINAL PAGE
========================= */

.final-content {

  justify-content: center;

}


.thank-you {

  font-family:
    "Cormorant Garamond",
    serif;

  font-size:
    clamp(24px, 6vw, 32px);

  line-height: 1.4;

  letter-spacing: 1px;

  color:
    #f0ded4;

}


.hope-text {

  margin-top: 25px;

  font-family:
    "Great Vibes",
    cursive;

  font-size:
    clamp(43px, 11vw, 62px);

  font-weight: 400;

  line-height: 1.1;

  color:
    #efd7c8;

}


.small-divider {

  margin: 35px 0;

  font-family:
    "Cormorant Garamond",
    serif;

  font-size: 20px;

  letter-spacing: 4px;

  color:
    rgba(240, 220, 210, 0.7);

}


/* =========================
   SIGNATURE
========================= */

.signature p {

  font-family:
    "Cormorant Garamond",
    serif;

  font-size: 17px;

  font-style: italic;

  letter-spacing: 1px;

  color:
    rgba(240, 220, 210, 0.7);

}


.signature h3 {

  margin-top: 10px;

  font-family:
    "Great Vibes",
    cursive;

  font-size:
    clamp(34px, 9vw, 50px);

  font-weight: 400;

  color:
    #f0d8ca;

}


/* =========================
   RESTART
========================= */

.restart-button {

  margin-top: 32px;

  padding:
    11px
    20px;

  border:
    1px solid
    rgba(240, 220, 210, 0.35);

  border-radius: 50px;

  color:
    #f0ded4;

  background:
    rgba(255, 255, 255, 0.04);

  font-family:
    "Cormorant Garamond",
    serif;

  font-size: 16px;

  cursor: pointer;

}


.restart-button:active {

  transform:
    scale(0.95);

}


/* =========================
   BOTTOM TEXT
========================= */

.bottom-text {

  position: absolute;

  bottom:
    max(
      22px,
      env(safe-area-inset-bottom)
    );

  left: 50%;

  transform:
    translateX(-50%);

  width: 100%;

  text-align: center;

  font-family:
    "Cormorant Garamond",
    serif;

  font-size: 13px;

  font-style: italic;

  letter-spacing: 1px;

  color:
    rgba(240, 220, 210, 0.55);

}


.bottom-text span {

  font-family:
    "Great Vibes",
    cursive;

  font-size: 18px;

}


/* =========================
   ANIMATION
========================= */

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


.fade-enter-active,
.fade-leave-active {

  transition:
    opacity 0.35s ease,
    transform 0.35s ease;

}


.fade-enter-from {

  opacity: 0;

  transform:
    translateY(20px);

}


.fade-leave-to {

  opacity: 0;

  transform:
    translateY(-20px);

}


/* =========================
   VERY SHORT MOBILE SCREEN
========================= */

@media (max-height: 650px) {

  .heart-large {

    margin-top: 20px;

    font-size: 48px;

  }


  .small-message {

    margin-top: 18px;

    font-size: 16px;

  }


  .next-button {

    margin-top: 20px;

  }


  .heart-top {

    margin-bottom: 18px;

    font-size: 38px;

  }


  .message {

    margin-bottom: 10px;

    font-size: 18px;

  }


  .divider {

    margin: 20px 0;

  }


  .small-divider {

    margin: 22px 0;

  }


  .hope-text {

    margin-top: 15px;

  }


  .restart-button {

    margin-top: 20px;

  }

}

</style>