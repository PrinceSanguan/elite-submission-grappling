<template>
  <NavComponent />
  <HeroComponent />
  <VideoComponent />
  <ClientComponent />
</template>

<script>
import NavComponent from "./components/NavComponent.vue";
import HeroComponent from "./components/HeroComponent.vue";
import VideoComponent from "./components/VideoComponent.vue";
import ClientComponent from "./components/ClientComponent.vue";

export default {
  name: "App",
  components: {
    NavComponent,
    HeroComponent,
    VideoComponent,
    ClientComponent,
  },
};
</script>

<style>
@import "@/assets/style.css";
@import "@/assets/responsive.css";
</style>
