<template>
  <div
    class="
      loader-wrapper
      absolute
      inset-0
      w-screen
      h-screen
      black-bg
      flex
      justify-center
      items-center
    "
  >
    <div class="loader"></div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.loader {
  background: url("https://assets.nflxext.com/en_us/pages/wiplayer/site-spinner.png")
    center center no-repeat;
  background-size: cover;
  width: 6rem;
  height: 6rem;
  animation: netflix-loader-rotate 1s linear infinite;
}

@keyframes netflix-loader-rotate {
  to {
    transform: rotate(360deg);
  }
}

.loader-wrapper {
  z-index: 999;
}
</style>
