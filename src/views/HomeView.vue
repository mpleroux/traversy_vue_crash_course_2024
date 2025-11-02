<script setup>
import Hero from '@/components/Hero.vue';
import HomeCards from '@/components/HomeCards.vue';
import JobListings from '@/components/JobListings.vue';
</script>

<template>
  <Hero title="Traversy Media Jobs Board" subtitle="Built with Vue 3 and Tailwind 4" />
  <HomeCards />
  <JobListings :limit="3" :showButton="true" />
</template>
