<template>
  <div id="home">
    <navigation-section></navigation-section>
    <top-section></top-section>
    <about-section></about-section>
    <skills-section></skills-section>
  </div>
</template>

<script>
// @ is an alias to /src
import AboutSection from "../components/AboutSection.vue";
import NavigationSection from "../components/NavigationSection.vue";
import TopSection from "../components/TopSection.vue";
import SkillsSection from "../components/SkillsSection.vue";

export default {
  name: "Home",
  components: {
    AboutSection,
    NavigationSection,
    TopSection,
    SkillsSection,
  },
};
</script>
