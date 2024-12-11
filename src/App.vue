<script setup>
import TestimonialGrid from './components/testimonials/TestimonialGrid.vue';
import { testimonialData } from './components/testimonials/data/testimonialData';
</script>

<template>
  <TestimonialGrid :testimonials="testimonialData" />
</template>

<style scoped>
 *{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Helvetica';
 }
</style>
