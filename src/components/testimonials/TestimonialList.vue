<template>
  <section
    class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-9 px-4"
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

<script>
import TestimonialCard from './TestimonialCard.vue'

export default {
  name: 'TestimonialList',
  components: {
    TestimonialCard,
  },
  props: {
    testimonials: {
      type: Array,
      required: true,
      validator: (testimonials) =>
        testimonials.every(
          (testimonial) =>
            testimonial.id &&
            testimonial.companyLogo &&
            testimonial.companyName &&
            testimonial.rating >= 0 &&
            testimonial.rating <= 5 &&
            testimonial.testimonialText &&
            testimonial.authorImage &&
            testimonial.authorName &&
            testimonial.authorTitle
        ),
    },
  },
}
</script>
