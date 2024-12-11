<template>
  <main role="main" class="flex overflow-hidden flex-col bg-slate-900 bg-opacity-90 w-screen">
    <section
      aria-label="Hero Section"
      class="flex relative flex-col w-full h-screen max-md:max-w-full"
    >
      <BackgroundImage />
      <div class="flex relative flex-col pt-6 w-full bg-black bg-opacity-50 max-md:max-w-full">
        <HeroContent />
      </div>
    </section>
  </main>
</template>

<script>
import BackgroundImage from './BackgroundImage.vue'
import HeroContent from './HeroContent.vue'

export default {
  name: 'HeroSection',
  components: {
    BackgroundImage,
    HeroContent,
  },
}
</script>
