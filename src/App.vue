<script setup>
import HeaderNav from './components/HeaderNav.vue'
import HeroSection from './components/HeroSection.vue'
import AboutSection from './components/AboutSection.vue'
import SectionDivider from './components/SectionDivider.vue'
import BenefitsSection from './components/BenefitsSection.vue'
import CommunitySection from './components/CommunitySection.vue'
import CtaSection from './components/CtaSection.vue'
import FooterSection from './components/FooterSection.vue'

console.log('[APP] mounted layout components')
</script>

<template>
  <HeaderNav />
  <HeroSection />
  <AboutSection />
  <SectionDivider />
  <BenefitsSection />
  <CommunitySection />
  <CtaSection />
  <FooterSection />
</template>
