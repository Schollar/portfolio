<template>
  <div class="home">
    <about-section></about-section>
  </div>
</template>

<script>
// @ is an alias to /src
import AboutSection from "../components/AboutSection.vue";

export default {
  name: "Home",
  components: {
    AboutSection,
  },
};
</script>
