<template>
  <div
    class="flex relative flex-col items-start pt-14 pr-20 pl-1 w-screen h-screen pb-24 max-md:pr-5 max-md:max-w-full"
  >
    <CompanyLogo />
    <HeroText />
  </div>
</template>

<script>
import CompanyLogo from './CompanyLogo.vue'
import HeroText from './HeroText.vue'

export default {
  name: 'HeroContent',
  components: {
    CompanyLogo,
    HeroText,
  },
}
</script>
