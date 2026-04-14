<script setup>
import HeroSplit from './components/HeroSplit.vue'
import AboutSection from './components/AboutSection.vue'
import ServiceCards from './components/ServiceCards.vue'
import StepFlow from './components/StepFlow.vue'
import TestimonialSlider from './components/TestimonialSlider.vue'
import ContactForm from './components/ContactForm.vue'
import TheFooter from './components/base/TheFooter.vue'
</script>

<template>
  <main>
    <HeroSplit />
    <AboutSection />
    <ServiceCards />
    <StepFlow />
    <TestimonialSlider />
    <ContactForm />
  </main>
  <TheFooter />
</template>
