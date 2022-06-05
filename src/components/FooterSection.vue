<template>
  <v-footer id="footer">
    <section class="footer">
      <section class="icons">
        <v-tooltip top>
          <template v-slot:activator="{ on, attrs }">
            <v-btn href="https://www.github.com/schollar" target="_blank">
              <v-icon icon v-bind="attrs" v-on="on"> mdi-github</v-icon>
            </v-btn>
          </template>
          <span>My Github</span>
        </v-tooltip>
        <v-tooltip top>
          <template v-slot:activator="{ on, attrs }">
            <v-btn
              href="https://www.linkedin.com/in/cschollar/"
              target="_blank"
            >
              <v-icon icon v-bind="attrs" v-on="on"> mdi-linkedin</v-icon>
            </v-btn>
          </template>
          <span>My LinkedIn</span>
        </v-tooltip>
        <v-tooltip top>
          <template v-slot:activator="{ on, attrs }">
            <v-btn
              href="https://drive.google.com/file/d/1ZS5bF10NL5S5lurgZ9zZWxUINVSFZ_q8/view?usp=sharing"
              target="_blank"
            >
              <v-icon icon v-bind="attrs" v-on="on"> mdi-file</v-icon>
            </v-btn>
          </template>
          <span>My Resume</span>
        </v-tooltip>
      </section>
      <p class="copyright">
        Colton Schollar
        <v-icon class="copyright_icon" size="18px"> mdi-copyright </v-icon
        >{{ year }}
      </p>
    </section>
  </v-footer>
</template>
<script>
export default {
  name: "footer-section",
  computed: {
    // Function that gets the year, found from vuetify docs
    year() {
      var day = new Date();
      return day.getFullYear();
    },
  },
};
</script>
<style lang="scss" scoped>
#footer {
  background-color: #343434;
  display: grid;
  width: 100vw;
  margin-top: 2%;
}
.footer {
  display: grid;
  grid-auto-flow: column;

  .icons {
    height: auto;
    position: relative;
    text-align: center;
    vertical-align: bottom;
    bottom: 0;
  }
}
.v-btn {
  bottom: 0;
  margin-top: 1.5%;
  margin-left: 2%;
}

.copyright {
  margin-top: 5px;
  font-size: 16px;
  color: #f15152;
  font-weight: bold;
  align-self: start;
  margin-top: 25px;
  margin-bottom: 0 !important;
}
.copyright_icon {
  color: #f15152;
}
</style>
