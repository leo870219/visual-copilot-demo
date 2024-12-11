<template>
  <article
    class="flex flex-col items-start p-8 bg-white rounded-[30px] text-zinc-800 w-[360px] min-h-[320px] max-h-screen overflow-auto"
    role="article"
    aria-labelledby="testimonial-quote"
  >
    <StarRating :rating="rating" class="mb-4" />
    <blockquote :id="`testimonial-quote-${id}`" class="self-stretch text-2xl leading-9 flex-grow">
      {{ testimonialText }}
    </blockquote>
    <div class="flex gap-3 mt-6" role="contentinfo" aria-label="Testimonial author information">
      <img
        loading="lazy"
        :src="authorImage"
        class="object-cover shrink-0 w-10 h-10 rounded-full"
        :alt="`Profile photo of ${authorName}`"
      />
      <div class="flex flex-col justify-center">
        <div class="text-sm font-bold">{{ authorName }}</div>
        <div class="text-xs text-zinc-600">{{ authorTitle }}</div>
      </div>
    </div>
  </article>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import StarRating from './StarRating.vue'
import type { Testimonial } from '../types/TestimonialTypes'

export default defineComponent({
  name: 'TestimonialCard',
  components: {
    StarRating,
  },
  props: {
    id: {
      type: [String, Number],
      required: true,
    },
    rating: {
      type: Number,
      required: true,
      validator: (value: number) => value >= 0 && value <= 5,
    },
    testimonialText: {
      type: String,
      required: true,
    },
    authorImage: {
      type: String,
      required: true,
    },
    authorName: {
      type: String,
      required: true,
    },
    authorTitle: {
      type: String,
      required: true,
    },
  },
})
</script>
