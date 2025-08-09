<script setup>
import { onMounted, ref } from 'vue'
const imgRef = ref(null)

onMounted(() => {
  console.log('[HERO] component mounted')
  imgRef.value?.addEventListener('load', () => {
    console.log('[HERO] image loaded', imgRef.value.naturalWidth, 'x', imgRef.value.naturalHeight)
  })
})
</script>

<template>
  <section class="section hero">
    <div class="container hero-grid">
      <div>
        <h1 class="title">Where Anime Fans &<br>Creators Truly Connect</h1>
        <p class="muted" style="font-size:18px;max-width:640px">
          A vibrant hub for Japanese culture lovers to gather, support, and grow together.
        </p>
        <div style="margin-top:20px">
          <a href="#early" class="btn">Join Early Access <span class="arrow">→</span></a>
        </div>
      </div>

      <div class="hero-visual">
        <img
          ref="imgRef"
          src="https://is3.cloudhost.id/konnetto-asset/landing-page-asset1.png"
          alt="Community artwork" loading="eager"
        />
        <span class="ribbon">Coming Soon!</span>
      </div>
    </div>
  </section>
</template>
