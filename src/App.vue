<template>
  <Loader v-if="load" />
  <Header />
  <router-view v-slot="{ Component }">
    <transition name="route" mode="out-in">
      <component :is="Component"></component>
    </transition>
  </router-view>
  <Footer />
</template>

<script>
import Header from "@/components/Header";
import Loader from "@/components/Loader";
import Footer from "@/components/Footer.vue";

export default {
  data: () => {
    return {
      load: false,
    };
  },
  components: {
    Header,
    Loader,
    Footer,
  },
};
</script>

<style scoped>
.route-enter-from {
  opacity: 0;
  transform: scale(1);
}

.route-enter-active {
  transition: all 0.3s ease-out;
}

.route-leave-to {
  opacity: 0;
  transform: scale(1.1);
}

.route-leave-active {
  transition: all 0.3s ease-in;
}
</style>
