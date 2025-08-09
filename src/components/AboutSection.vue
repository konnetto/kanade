<script setup>
import { Users, Compass, Share2 } from 'lucide-vue-next'
</script>

<template>
  <section id="about" class="section about">
    <div class="container">
      <h2 class="title" style="font-size:36px;text-align:center">About Konnetto</h2>
      <p class="lead muted">
        Konnetto is a niche platform bringing fans, creators, and communities of Japanese culture closer than ever — from VTubers and cosplayers to artists and event organizers.
      </p>

      <div class="cards">
        <div class="card">
          <div class="c-icon"><Users class="icon" /></div>
          <h3>Connect</h3>
          <p>Build meaningful relationships with fellow fans and creators.</p>
        </div>

        <div class="card">
          <div class="c-icon purple"><Compass class="icon" /></div>
          <h3>Discover</h3>
          <p>Explore new content, events, and communities around Japanese culture.</p>
        </div>

        <div class="card">
          <div class="c-icon blue"><Share2 class="icon" /></div>
          <h3>Share</h3>
          <p>Express your passion and creativity with like-minded enthusiasts.</p>
        </div>
      </div>
    </div>
  </section>
</template>
