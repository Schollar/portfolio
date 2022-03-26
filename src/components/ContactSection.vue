<template>
  <section id="contact">
    <section class="text_container">
      <h2>
        Contact
        <v-icon> mdi-arrow-right </v-icon>
      </h2>
      <h2>Me</h2>
      <p>
        If you have any questions, or are looking to get a quote done for you or
        your business, please send me a small message and I will get back to you
        ASAP
      </p>
    </section>
    <form ref="form" class="form" @submit.prevent="sendEmail">
      <v-text-field
        :rules="nameRules"
        v-model="name"
        name="name"
        class="text-field my-8"
        placeholder="name"
        outlined
      >
      </v-text-field>
      <v-text-field
        :rules="emailRules"
        v-model="email"
        name="email"
        class="text-field my-8"
        placeholder="email"
        outlined
      >
      </v-text-field>
      <v-textarea
        :rules="messageRules"
        name="message"
        v-model="message"
        background-color="#d3d3d3"
        class="my-8"
        placeholder="message"
        outlined
      ></v-textarea>
      <v-btn
        outlined
        medium
        @click="sendEmail()"
        :loading="loading"
        class="montserrat btn"
        color="primary"
      >
        Submit
      </v-btn>
    </form>
  </section>
</template>

<script>
import emailjs from "emailjs-com";
export default {
  name: "contact-section",
  data() {
    return {
      loading: false,
      name: "",
      nameRules: [(v) => !!v || "Name is required"],
      email: "",
      emailRules: [
        (v) => !!v || "E-mail is required",
        (v) => /.+@.+/.test(v) || "E-mail must be valid",
      ],
      message: "",
      messageRules: [(v) => !!v || "Message cant be empty"],
    };
  },
  methods: {
    sendEmail() {
      try {
        emailjs.sendForm(
          "contact_service",
          "contact_form",
          this.$refs["form"],
          "DVlO9CMDD-mJLBo1x",
          {
            name: this.name,
            email: this.email,
            message: this.message,
          }
        );
      } catch (error) {
        console.log(error);
      }
      // Reset form field
      this.name = "";
      this.email = "";
      this.message = "";
    },
  },
};
</script>

<style scoped lang="scss">
#contact {
  margin-top: 35%;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  background-color: darkgray;
}

.text_container {
  align-self: center;
  margin-left: 15%;
  h2 {
    font-size: 4em;
  }
  .mdi-arrow-right {
    font-size: 1.7em;
  }

  p {
    width: 95%;
    font-weight: bold;
    font-size: 1.5em;
  }
}

.form {
  .text-field {
    height: 55px;
    background-color: #d3d3d3;
  }

  .btn {
    font-weight: bold;
    border-width: 3px;
  }
}
@media screen and (min-width: 600px) {
  #contact {
    margin-top: 0;
  }
}
</style>
