<template>
  <section aria-label="Customer Testimonials" class="testimonial-section">
    <div class="flex gap-5 max-md:flex-col">
      <div
        v-for="testimonial in testimonials"
        :key="testimonial.id"
        class="flex flex-col w-[33%] max-md:ml-0 max-md:w-full"
      >
        <TestimonialCard
          :logo="testimonial.logo"
          :company-name="testimonial.companyName"
          :testimonial-text="testimonial.text"
          :author-image="testimonial.authorImage"
          :author-name="testimonial.authorName"
          :author-title="testimonial.authorTitle"
        />
      </div>
    </div>
  </section>
</template>

<script>
import TestimonialCard from './TestimonialCard.vue'
import { testimonialData } from './data/testimonialData'

export default {
  name: 'TestimonialGrid',
  components: {
    TestimonialCard,
  },
  data() {
    return {
      testimonials: testimonialData,
    }
  },
}
</script>
