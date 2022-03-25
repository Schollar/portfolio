<template>
  <section class="banner">
    <section class="info_container">
      <section>
        <!-- m - applies margin, a - applies the spacing for the property in all directions as per vuetify docs, which is why we have some odd class names here -->
        <p class="ma-0 pa-0">Hello, I am</p>
        <h1 class="header ma-0 pa-0">Colton Schollar</h1>
        <h2 class="secondary-text">
          Full Stack Web <span class="dev_span">Developer</span>
        </h2>
      </section>
      <!-- m - applies margin, y - applies the spacing for both *-top and *-bottom thats why class of my-8 here -->
      <router-link :to="{ name: 'Home', hash: '#about' }"
        ><v-btn color="purple" outlined class="btn my-8">
          View more
        </v-btn></router-link
      >
    </section>
  </section>
</template>


<script>
export default {
  name: "top-section",
};
</script>


<style lang="scss" >
.banner {
  text-align: left;
  height: 100vh;
  width: 100vw;
  background-color: darkgray;
  padding: 10%;
}

.info_container {
  height: 100%;
  margin-top: 10%;
}
.header {
  font-size: 3.5em;
  color: purple;
  height: 100%;
}
p {
  margin-left: 25px;
  padding: 0;
  font-size: 1.5em;
  font-weight: bolder;
  color: purple;
}

.dev_span {
  color: orange;
}

.secondary-text {
  color: gray;
}

.btn {
  color: yellow;
}
</style>