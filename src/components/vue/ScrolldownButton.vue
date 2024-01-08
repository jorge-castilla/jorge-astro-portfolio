<script setup>
const props = defineProps({
  left: {
    type: Boolean,
    default: false,
  },
});

const scrollToAbout = () => {
  const about = document.getElementById('SobreMi');
  about.scrollIntoView({ behavior: 'smooth' });
};

</script>
<template>
  <button
    class="absolute bottom-24 rotate-90 md:text-lg text-slate-500 scroll-down-animation"
    :class="left ? '-left-8' : '-right-8'"
    @click="scrollToAbout"
  >
    scroll down
  </button>
</template>

<style scoped>
.scroll-down-animation {
  animation: 3s linear 0s normal scrollDown;
}

@keyframes scrollDown {
  0% {
    opacity: 0;
    transform: translateY(-10px) rotate(90deg);
  }
  60% {
    opacity: 0;
    transform: translateY(-5px) rotate(90deg);
  }
  100% {
    opacity: 1;
    transform: translateY(0px) rotate(90deg);
  }
}
</style>
