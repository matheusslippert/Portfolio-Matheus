<template>
  <b-row style="margin-left: 0; margin-right: 0">
    <b-col md="4">
      <b-img
        src="https://scontent.fpoa12-1.fna.fbcdn.net/v/t39.30808-6/297059993_2266677816817021_5997854202934730565_n.jpg?_nc_cat=106&ccb=1-7&_nc_sid=730e14&_nc_ohc=Fx-PaNYKPrwAX_6cgQw&_nc_ht=scontent.fpoa12-1.fna&oh=00_AT85E2mTlZK1gZhuVBY04gGOzorrw0QlNstVQxYVaUxT_Q&oe=6303E1AD"
        id="avatar-img"
        alt=""
      />
    </b-col>

    <b-col md="8">
      <h2 class="intro animate__animated animate__fadeInUp animate__fast">
        Olá!,
        <br /><span>eu sou o Matheus</span>.
      </h2>

      <div class="col-md-10 info">
        Texto de introducao aqui
        <br />
        <b-button
          class="
            action-btn
            animate__animated animate__wobble animate__delay-4s animate__fast
          "
          to="/about"
        >
          Sobre mim
        </b-button>

        <b-button
          class="action-btn"
          to="/contact"
          variant="primary"
        >
          Contatos
        </b-button>

        <!-- .SOCIAL LINKS SECTION -->
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
      </div>
    </b-col>
  </b-row>
</template>

<script>
import GithubIcon from "vue-ionicons/dist/logo-github.vue";
import LinkedinIcon from "vue-ionicons/dist/logo-linkedin.vue";
import TwitterIcon from "vue-ionicons/dist/logo-twitter.vue";
import FacebookIcon from "vue-ionicons/dist/logo-facebook.vue";
import YoutubeIcon from "vue-ionicons/dist/logo-youtube.vue";
import MailIcon from "vue-ionicons/dist/md-mail.vue";
import WhatsappIcon from "vue-ionicons/dist/logo-whatsapp.vue";

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
      avatar: require("@/assets/avatar-1.webp"),
      // ADD YOUR SOCIAL LINKS HERE 👇
      socialLinks: {
        github: "https://github.com/matheusslippert",
        LinkedinIcon: "https://www.linkedin.com/in/matheus-slippert/",
        FacebookIcon: "https://www.facebook.com/matheus.lippert.9",
        WhatsappIcon: "",
      },
    };
  },

  head: {
    title: "Portfolio Lippert",
    meta: [
      {
        hid: "description",
        name: "description",
        content:
          "lorem",
      },
      {
        hid: "og:title",
        name: "og:title",
        content: "Matheus Dashbord",
      },
      {
        property: "og:description",
        content:
          "loere",
      },
      {
        hid: "og:image",
        name: "og:image",
        content: "https://scontent.fpoa12-1.fna.fbcdn.net/v/t39.30808-6/297059993_2266677816817021_5997854202934730565_n.jpg?_nc_cat=106&ccb=1-7&_nc_sid=730e14&_nc_ohc=Fx-PaNYKPrwAX_6cgQw&_nc_ht=scontent.fpoa12-1.fna&oh=00_AT85E2mTlZK1gZhuVBY04gGOzorrw0QlNstVQxYVaUxT_Q&oe=6303E1AD",
      },
    ],
  },
  mounted() {
    this.$nextTick(() => {
      this.$nuxt.$loading.start();

      setTimeout(() => this.$nuxt.$loading.finish(), 500);
    });
  },
};
</script>
