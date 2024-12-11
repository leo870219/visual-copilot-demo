<template>
  <section
    class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 p-4 max-w-7xl mx-auto"
    role="region"
    aria-label="Customer testimonials"
  >
    <TestimonialCard
      v-for="testimonial in testimonials"
      :key="testimonial.id"
      v-bind="testimonial"
    />
  </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import TestimonialCard from './TestimonialCard.vue'
import type { Testimonial } from '../types/TestimonialTypes'

export default defineComponent({
  name: 'TestimonialGrid',
  components: {
    TestimonialCard,
  },
  props: {
    testimonials: {
      type: Array as () => Testimonial[],
      required: true,
      validator: (testimonials: Testimonial[]) =>
        testimonials.every(
          (testimonial) =>
            testimonial.id &&
            testimonial.rating >= 0 &&
            testimonial.rating <= 5 &&
            testimonial.testimonialText &&
            testimonial.authorImage &&
            testimonial.authorName &&
            testimonial.authorTitle
        ),
    },
  },
})
</script>
