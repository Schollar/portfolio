<template>
  <div id="home">
    <navigation-section></navigation-section>
    <top-section></top-section>
    <about-section></about-section>
    <skills-section></skills-section>
    <projects-section></projects-section>
    <contact-section></contact-section>
    <footer-section></footer-section>
  </div>
</template>

<script>
// @ is an alias to /src
import AboutSection from "../components/AboutSection.vue";
import NavigationSection from "../components/NavigationSection.vue";
import TopSection from "../components/TopSection.vue";
import SkillsSection from "../components/SkillsSection.vue";
import ProjectsSection from "../components/ProjectsSection.vue";
import ContactSection from "../components/ContactSection.vue";
import FooterSection from "../components/FooterSection.vue";

export default {
  name: "Home",
  components: {
    AboutSection,
    NavigationSection,
    TopSection,
    SkillsSection,
    ProjectsSection,
    ContactSection,
    FooterSection,
  },
};
</script>

<style>
#home {
  background-color: #343434;
}
</style>
