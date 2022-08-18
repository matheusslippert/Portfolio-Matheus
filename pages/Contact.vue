<template>
  <b-container class="page animate__animated animate__fadeIn">
    <b-row class="justify-content-center">
      <b-col cols="md-6">
        <h2>Get in touch 💌</h2>

        <p class="text-left">
          If you have any question or just want to say hi, i'll try my best to
          get back to you.
        </p>

        <b-alert show variant="success" v-if="showAlert">
          <strong>All done 🎉</strong><br />
          Thanks for reaching out {{ this.formData.name }}, I'll reply as soon
          as i can.
        </b-alert>

           <div
          class="
            social-icons
            animate__animated animate__fadeInUp animate__delay-1s
          "
        >
          <social-link :to="socialLinks.github">
            <GithubIcon />
          </social-link>

          <social-link :to="socialLinks.LinkedinIcon">
            <LinkedinIcon />
          </social-link>
        </div>
      </b-col>
    </b-row>
  </b-container>
</template>
<script>
import GithubIcon from "vue-ionicons/dist/logo-github.vue";
import LinkedinIcon from "vue-ionicons/dist/logo-linkedin.vue";
import TwitterIcon from "vue-ionicons/dist/logo-twitter.vue";
import FacebookIcon from "vue-ionicons/dist/logo-facebook.vue";
import YoutubeIcon from "vue-ionicons/dist/logo-youtube.vue";
import MailIcon from "vue-ionicons/dist/md-mail.vue";

export default {
  components: {
    GithubIcon,
    LinkedinIcon,
    TwitterIcon,
    FacebookIcon,
    YoutubeIcon,
    MailIcon,
  },
  data() {
    return {
      socialLinks: {
        github: "https://github.com/matheusslippert",
        LinkedinIcon: "https://www.linkedin.com/in/matheus-slippert/",
        FacebookIcon: "https://www.facebook.com/matheus.lippert.9",
      },
      showAlert: false,
      formData: {
        name: "",
        email: "",
        message: "",
      },
    };
  },
  methods: {
    async sendMessage(e) {
      const self = this;
      var data = new FormData();

      data.append("Name", self.formData.name);
      data.append("Email", self.formData.email);
      data.append("Message", self.formData.message);

      fetch("https://formspree.io/f/mvodbwva", {
        method: "POST",
        body: data,
        headers: {
          Accept: "application/json",
        },
      }).then((response) => {
        if (response.ok) {
          this.showAlert = true;
          form.reset();
        } else {
          alert("Sending message failed, please try again");
        }
      });
      // .catch(error => {
      //   alert("Sending message failed, please try again");
      // });
    },
  },
  head: {
    title: "Contact - Itsuka",
    meta: [
      {
        hid: "description",
        name: "description",
        content: "Do you have any enquires? Send a message now to my Developer",
      },
      {
        hid: "og:title",
        name: "og:title",
        content: "Contact - Itsuka",
      },
      {
        property: "og:description",
        content: "Do you have any enquires? Send a message now to my Developer",
      },
      {
        hid: "og:image",
        name: "og:image",
        content: require("@/assets/contact.jpg"),
      },
    ],
  },
};
</script>
<style scoped>
.container {
  margin-top: 120px;
}
form {
  margin-top: 40px;
  text-align: left;
}
</style>
