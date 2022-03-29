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

        <v-img :src="project.img_src" />
        <section class="live_link">
          <h2>Live Link:</h2>
          <a :href="project.url" target="_blank">{{ project.url }}</a>
          <section class="code_links">
            <h2>Code Links:</h2>
            <a :href="project.url" target="_blank">{{ project.frontend }}</a>
            <a :href="project.url" target="_blank">{{ project.backend }}</a>
          </section>
          <section class="description">
            <p>{{ project.desc }}</p>
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
        opp: {
          name: "Okotoks Pizza",
          url: "https://pizzaproject.ml",
          frontend: "https://github.com/Schollar/Okotoks_Pizza",
          backend: undefined,
          img_src: "/opp.png",
          desc: "Static Pizza Restraunt Website made with just HTML and CSS. OPP Website is mobile and desktop responsive. Deployed to Oracle Cloud server using Apache",
        },
        tweeter: {
          name: "Tweeter",
          url: "https://tweeterproject.ga",
          backend: "https://github.com/Schollar/tweeter_backend",
          frontend: "https://github.com/Schollar/tweeter",
          img_src: "/tweeter.png",
          desc: "Goal of this project was to build a twitter clone. The focus was functionality over design, so the main features of the app are the core showcase.Tweeter is mobile to desktop responsive. Front end built using VueJs. Backend is built with Python, Flask and MariaDB. Deployed to Oracle Cloud Sever using Apache and PM2.",
        },
        arktracker: {
          name: "Ark Tracker",
          url: "https://arktracker.ml",
          backend: "https://github.com/Schollar/arktracker_backend",
          frontend: "https://github.com/Schollar/arktracker_frontend",
          img_src: "/arktracker.png",
          desc: "The goal of this project was to build a web app to help track daily/weekly tasks within the game of Lost Ark. Users sign up, then can create one or more characters that they would like to track tasks of. This app is mobile to desktop responsive. It was built with VueJs and the help of vuetify for the frontend. Python, flask and MariaDB are the backbone for the backend. Deployed to Oracle Cloud server using apache and PM2",
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
  margin-bottom: 10%;
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
  text-align: center;
}
.project {
  height: auto;
  margin: 2%;
  margin-left: 12px;
  margin-right: 12px;
}
.card_container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  grid-gap: 5%;
}

h2 {
  color: #f15152;
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
    width: 75%;
  }
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
.v-image:hover {
  width: 95%;
  height: 95%;
}

.v-image:hover {
  transform: scale(1.1);
  transition: 0.3s ease-in-out;
  position: absolute;
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
