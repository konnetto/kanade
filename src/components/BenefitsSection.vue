<script setup>
import { Heart, Calendar, HandHeart, Image as ImageIcon } from 'lucide-vue-next'
</script>

<template>
  <section id="benefits" class="section benefits">
    <div class="container">
      <h2 class="heading">Key Benefits</h2>

      <div class="grid">
        <div class="card">
          <div class="icon-bubble icon-green"><Heart class="icon" /></div>
          <h4>Meet Like-Minded Fans</h4>
          <p>Connect with people who share your passion for Japanese culture.</p>
        </div>

        <div class="card">
          <div class="icon-bubble icon-pink"><Calendar class="icon" /></div>
          <h4>Discover Local & Online Events</h4>
          <p>Find conventions, watch parties, and virtual meetups near you.</p>
        </div>

        <div class="card">
          <div class="icon-bubble icon-purple"><HandHeart class="icon" /></div>
          <h4>Support Your Favorite Creators</h4>
          <p>Follow, engage with, and support the creators you love.</p>
        </div>

        <div class="card">
          <div class="icon-bubble icon-teal"><ImageIcon class="icon" /></div>
          <h4>Share Your Anime Journey</h4>
          <p>Express yourself through discussions, reviews, and creative content.</p>
        </div>
      </div>
    </div>
  </section>
</template>
