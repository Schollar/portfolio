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
  color: purple;
  padding-top: 15px;
  font-weight: bold;
  place-self: center;
  margin-right: 30%;
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
    color: purple;
  }
  p:hover {
    color: gray;
    font-size: 1em;
    font-weight: medium;
  }
}
#skills {
  height: auto;
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
}
</style>