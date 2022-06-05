<template>
  <section id="projects">
    <h2 class="">My Projects:</h2>
    <section class="card_container">
      <!-- Loop through projects object and display project info onto page -->
      <v-card
        v-for="project in projects"
        :key="project.name"
        class="project"
        dark
        round
      >
        <v-card-title class="card_title">{{ project.name }}</v-card-title>

        <img :src="project.img_src" class="project_image" />
        <section class="live_link">
          <h2>Live Link:</h2>
          <a :href="project.url" target="_blank">{{ project.url }}</a>
          <section class="code_links">
            <h2>Code Links:</h2>
            <a :href="project.frontend" target="_blank">{{
              project.frontend
            }}</a>
            <a :href="project.backend" target="_blank">{{ project.backend }}</a>
          </section>
          <section class="description">
            <p v-html="project.desc"></p>
          </section>
        </section>
      </v-card>
    </section>
  </section>
</template>

<script>
export default {
  name: "projects-section",
  data() {
    return {
      // Setup projects in an object of objects to loop over and display info onto page.
      projects: {
        arktracker: {
          name: "Ark Tracker",
          url: "https://arktracker.ml",
          backend: "https://github.com/Schollar/arktracker_backend",
          frontend: "https://github.com/Schollar/arktracker_frontend",
          img_src: "/arktracker.png",
          desc: "The goal of this project was to build a web app to help track daily/weekly tasks within the game of Lost Ark.<br><br>Users sign up, then can create one or more characters that they would like to track tasks of.<br><br>This app is mobile to desktop responsive. It was built with VueJs and the help of vuetify for the frontend. Python, flask and MariaDB are the backbone for the backend.<br><br>Deployed to Oracle Cloud server using apache and PM2",
        },
        tweeter: {
          name: "Tweeter",
          url: "https://tweeterproject.ga",
          backend: "https://github.com/Schollar/tweeter_backend",
          frontend: "https://github.com/Schollar/tweeter",
          img_src: "/tweeter.png",
          desc: "Goal of this project was to build a twitter clone. The focus was functionality over design, so the main features of the app are the core showcase.<br><br>Tweeter is mobile to desktop responsive. Front end built using VueJs. Backend is built with Python, Flask and MariaDB.<br><br>Deployed to Oracle Cloud Sever using Apache and PM2.",
        },
        opp: {
          name: "Okotoks Pizza",
          url: "https://pizzaproject.ml",
          frontend: "https://github.com/Schollar/Okotoks_Pizza",
          backend: undefined,
          img_src: "/opp.png",
          desc: "Static Pizza Restraunt Website made with just HTML and CSS. OPP Website is mobile and desktop responsive.<br><br>Deployed to Oracle Cloud server using Apache",
        },
        jstrucking: {
          name: "J & S Transport",
          url: "https://jandshouston.com",
          frontend: "https://github.com/Schollar/jandstransport",
          backend: undefined,
          img_src: "/jandshouston.png",
          desc: "Transport company website based out of Houston TX. Vue frontend project used along with vuetify made to clients needs and wants.  Website is mobile and desktop responsive <br><br>Deployed to Oracle Cloud server using Apache",
        },
        coinprice: {
          name: "Coin Price",
          url: "https://www.coinprice.ml",
          frontend: "https://github.com/Schollar/crypto_converter",
          backend: undefined,
          img_src: "/coinprice.png",
          desc: "Coin Price is a app that users can pick from a list of popular crypto coins and display the price in different currencies. Coin price is both mobile and desktop responsive.<br><br>Deployed to Oracle Cloud server using Apache",
        },
      },
    };
  },
};
</script>
<style lang="scss" scoped>
#projects {
  padding-top: 5%;
  text-align: center;
  display: grid;
  place-items: center;
  margin: 20px;
}

.card_container {
  width: 100%;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 20px;
}

.v-card {
  border: 1px solid black;
  height: 15%;
}
.card_title {
  color: #f15152;
}
.description {
  display: grid;
  color: #f4d8cd;
  margin-bottom: 2.5%;
  width: 90%;
  // I like this better
  text-align: left;
}
.project {
  height: 100%;
}

h2 {
  color: #f15152;
  font-size: 3em;
  margin-bottom: 20px;
}

.code_links {
  display: grid;
  margin-top: 5%;
  text-align: left;
  margin-bottom: 5%;

  > a {
    font-size: smaller;
    margin-bottom: 10px;
    color: #778da9;
    text-decoration: none;
  }
}
.card_title {
  font-size: 2em;
  margin-bottom: 2%;
  display: grid;
  place-items: center;
}
.live_link {
  text-align: left;
  margin-top: 5%;
  margin-left: 5%;
  > a {
    color: #778da9;
    text-decoration: none;
  }
}

.project_image {
  width: 95%;
  object-fit: cover;
  height: 200px;
}

.project:hover {
  transform: scale(1.1);
  transition: 0.3s ease-in-out;
}

@media screen and (min-width: 900px) {
  .code_links {
    a {
      font-size: medium;
      width: 75%;
    }
  }
}
</style>
