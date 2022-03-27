<template>
  <div id="about">
    <section class="container">
      <section class="text_container">
        <h2>ABOUT ME</h2>
        <p>
          Full Stack Web Developer looking to continuously learn new and
          exciting things related to programming. I am very passionate about
          coding with a big willingness to learn as much as I can.
        </p>
        <p>
          Currently exploring the world of VueJS for front end web systems,
          paired with python and flask for backend systems. I love everything
          about Javascript and have been really diving deep into it.
        </p>
        <p>
          Things I enjoy the most are spending time with my wonderful children,
          learning and coding anything I can come up with.
        </p>
      </section>
      <section class="image_container">
        <v-img src="../assets/me.jpg" width="500px"> </v-img>
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
  place-items: center;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
}
.text_container {
  width: 65%;
}

#about {
  height: auto;
  background-color: white;

  h2 {
    font-weight: bold;
    color: #f15152;
    padding-top: 15px;
  }
  p {
    padding: 10px 10px 10px 0px;
    font-weight: 400;
    color: #778da9;
    font-size: 1em;
  }
}
.image_container {
  margin-top: 5%;
  width: 65%;
}
.v-image {
  filter: grayscale(0.75);
  width: 90% !important;
  place-self: center;
}

@media screen and (min-width: 700px) {
  #about {
    p {
      font-size: 1.5em;
    }
  }
  .v-image {
    width: 1000% !important;
  }
}
</style>