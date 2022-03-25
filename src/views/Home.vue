<template>
  <div class="home">
    <navigation-section></navigation-section>
    <about-section></about-section>
  </div>
</template>

<script>
// @ is an alias to /src
import AboutSection from "../components/AboutSection.vue";
import NavigationSection from "../components/NavigationSection.vue";

export default {
  name: "Home",
  components: {
    AboutSection,
    NavigationSection,
  },
};
</script>
