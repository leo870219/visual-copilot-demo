<template>
  <article
    class="flex overflow-hidden flex-col items-start p-8 mx-auto w-full bg-white rounded-[30px] text-zinc-800 max-md:px-5 max-md:mt-9"
  >
    <img
      :src="logo"
      :alt="companyName + ' logo'"
      class="object-contain max-w-full aspect-[5.68] w-[136px]"
    />
    <blockquote class="self-stretch mt-6 text-2xl leading-9">
      {{ testimonialText }}
    </blockquote>
    <footer class="flex gap-3 mt-20 max-md:mt-10">
      <img
        :src="authorImage"
        :alt="authorName"
        class="object-contain shrink-0 w-10 aspect-square rounded-[36px]"
      />
      <div class="flex flex-col self-start">
        <cite class="self-start text-sm font-bold not-italic">{{ authorName }}</cite>
        <div class="text-xs">{{ authorTitle }}</div>
      </div>
    </footer>
  </article>
</template>

<script>
export default {
  name: 'TestimonialCard',
  props: {
    logo: String,
    companyName: String,
    testimonialText: String,
    authorImage: String,
    authorName: String,
    authorTitle: String,
  },
}
</script>
