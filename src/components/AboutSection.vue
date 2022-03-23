<template>
  <div class="about">
    <section class="container">
      <section class="text_container">
        <h2>ABOUT ME</h2>
        <p>
          Full Stack Web Developer looking to continuously learn new and
          exciting things related to programming
        </p>
        <p>THINK OF MORE STUFF TO ADD HERE</p>
        <p>AND MAYBE SOME STUFF HERE</p>
      </section>
      <section class="image_container">
        <v-img src="@/assets/logo.png" max-width="500px" contain> </v-img>
      </section>
    </section>
  </div>
</template>

<script>
export default {
  name: "about-section",
};
</script>


<style lang="scss" scoped >
.container {
  display: grid;
  grid-auto-flow: column;
  place-items: center;
}

.about {
  padding-left: 10%;

  h2 {
    font-weight: bold;
    color: purple;
    padding-top: 15px;
  }
  p {
    padding: 10px 10px 10px 0px;
    font-weight: 400;
    color: gray;
    font-size: 1.3em;
  }
}
</style>