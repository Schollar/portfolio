<template>
  <section id="contact">
    <section class="container">
      <section class="text_container">
        <h2>
          Contact
          <v-icon> mdi-arrow-right </v-icon>
        </h2>
        <h2>Me</h2>
        <p>Text or Call at:</p>
        <p>(825)345-4205</p>
        <p>
          If you have any questions, or are looking to get a quote done for you
          or your business, please send me a message and I will get back to you
          ASAP.
        </p>
      </section>
      <form ref="form" class="form" @submit.prevent="sendEmail">
        <v-text-field
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
          placeholder="message"
          outlined
        ></v-textarea>
        <v-btn
          outlined
          medium
          @click="sendEmail()"
          :loading="loading"
          class="montserrat btn"
          color="#778DA9"
        >
          Submit
        </v-btn>
      </form>
    </section>
  </section>
</template>

<script>
import emailjs from "emailjs-com";
export default {
  name: "contact-section",
  data() {
    return {
      // Setting up variables, and rules for form inputs, found off vuetify docs
      loading: false,
      name: "",
      nameRules: [(v) => !!v || "Name is required"],
      email: "",
      emailRules: [
        (v) => !!v || "E-mail is required",
        (v) => /.+@.+\..+/.test(v) || "E-mail must be valid",
      ],
      message: "",
      messageRules: [(v) => !!v || "Message cant be empty"],
    };
  },
  methods: {
    // Function that resets the form.
    reset() {
      this.$refs.form.reset();
    },
    // Following EmailJs docs, we send the form content as an object, also send the name and service of my form on the emailJs website, aswell as my userId and the ref to the form
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
      this.reset();
    },
  },
};
</script>

<style scoped lang="scss">
#contact {
  margin-top: 55%;
  display: grid;
  background-color: #343434;
  grid-gap: 25px;
}

.text_container {
  align-self: center;
  margin-left: 15%;
  h2 {
    font-size: 4em;
    color: #f15152;
  }
  .mdi-arrow-right {
    font-size: 1.7em;
    color: #778da9;
  }

  p {
    width: 95%;
    font-weight: bold;
    font-size: 1.5em;
    color: #f4d8cd;
  }
}
.container {
  display: grid;
  place-self: center;
  width: 80%;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  margin-bottom: 5%;
  column-gap: 5%;
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
@media screen and (min-width: 700px) {
  #contact {
    margin-top: 10%;
  }
}
@media screen and (min-width: 915px) {
  #contact {
    margin-top: 0;
  }
  .form {
    place-self: center;
    width: 80%;
  }
}
</style>
