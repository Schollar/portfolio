<template>
  <section id="skills">
    <section class="skills_container">
      <h2>I have experience with:</h2>

      <section class="front_end skill_names">
        <p>HTML</p>
        <p>CSS</p>
        <p>Javascript</p>
        <p>VueJs</p>
      </section>
      <section class="web_server skill_names">
        <p>Google Cloud</p>
        <p>Oracle Cloud</p>
        <p>Bash</p>
        <p>Apache</p>
        <p>PM2</p>
      </section>
      <section class="back_end skill_names">
        <p>Python</p>
        <p>MariaDB</p>
        <p>Flask</p>
        <p>SQL</p>
      </section>
    </section>
  </section>
</template>


<script>
export default {
  name: "skills-section",
};
</script>

<style lang="scss" scoped >
.skills_container {
  display: grid;
  height: auto;
  grid-template-rows: 1fr 2fr 2fr 2fr;
}
h2 {
  color: #f15152;
  padding-top: 15px;
  font-weight: bold;
  place-self: center;
}

.skill_names {
  display: grid;
  grid-auto-flow: column;
  font-size: medium;
  place-self: center;

  p {
    margin-left: 25px;
    padding: 0;
    font-size: 0.75em;
    font-weight: bolder;
    color: #f15152;
  }
  p:hover {
    color: #778da9;
    transform-origin: center;
    transform: scale(1.2);
    cursor: default;
  }
}
.web_server {
  margin-right: 3%;
}
#skills {
  height: auto;
  background-color: white;
  padding-top: 5%;
  padding-bottom: 2.5%;
}
@media screen and (min-width: 600px) {
  .skill_names {
    p {
      font-size: 2em;
    }
    p:hover {
      font-size: 3em;
    }
  }
  h2 {
    margin-right: 30%;
  }
}
</style>