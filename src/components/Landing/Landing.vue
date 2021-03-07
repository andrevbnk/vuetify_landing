<template>
  <div>
    <section>
      <v-parallax src="../../assets/landingPics/dog.jpg" height="600">
        <v-layout
          column
          align-center
          justify-center
          class="white--text"
          style="margin: 0px"
        >
        
          <h1
            class="white--text mb-2 display-1 text-xs-center"
            style="font-weight: 900; text-shadow: 3px 2px #000000"
          >
            We are trying to save lost pets
          </h1>
          <div
            class="white--text subheading mb-3 text-xs-center"
            style="font-weight: 900; text-shadow: 2px 2px #000000"
          >
            Help us!
          </div>
          <v-btn class="blue lighten-2 mt-5" dark large href="/login">
            Get Started
          </v-btn>
        </v-layout>
      </v-parallax>
    </section>

    <section>
      <v-layout column wrap class="my-10" align-center>
        <v-flex xs12 sm4 style="margin-bottom: 100px; margin-top: 100px">
          <div class="text-xs-center">
            <h1 class="headline text-h2">So what is it all about?</h1>
          </div>
        </v-flex>
        <v-flex xs12>
          <v-container grid-list-xl class="mb-10">
            <v-layout row wrap align-center>
              <v-flex xs12 md4>
                <v-card class="elevation-0 transparent">
                  <v-card-title
                    primary-title
                    class="layout justify-center d-flex flex-column"
                  >
                    <v-icon class="mb-8" color="red" x-large>mdi-heart</v-icon>
                    <v-divider></v-divider>

                    <div class="headline text-xs-center text-h4">
                      It is all about love
                    </div>
                  </v-card-title>
                  <v-card-text>
                    We are trying to do out best to help people find their pets and to
                    help pets to find their people
                  </v-card-text>
                </v-card>
              </v-flex>
              <v-flex xs12 md4>
                <v-card class="elevation-0 transparent">
                  <v-card-title
                    primary-title
                    class="layout justify-center d-flex flex-column"
                  >
                    <v-icon class="mb-8" color="green" x-large>mdi-run-fast</v-icon>
                    <v-divider></v-divider>
                    <div class="headline text-xs-center text-h4">Fast analysis</div>
                  </v-card-title>
                  <v-card-text>
                    Time is important for us so we try to analize every advert to find
                    your pet as fast as it possible
                  </v-card-text>
                </v-card>
              </v-flex>
              <v-flex xs12 md4>
                <v-card class="elevation-0 transparent">
                  <v-card-title
                    primary-title
                    class="layout justify-center d-flex flex-column"
                  >
                    <v-icon class="mb-8" color="yellow" x-large
                      >mdi-handshake-outline</v-icon
                    >
                    <v-divider></v-divider>
                    <div class="headline text-xs-center text-h4">Helping in any case</div>
                  </v-card-title>
                  <v-card-text>
                    Even if out users cannot get your pet to you, they will at least try
                    to help you using out notes!
                  </v-card-text>
                </v-card>
              </v-flex>
            </v-layout>
          </v-container>
        </v-flex>
      </v-layout>
    </section>

    <section>
      <v-parallax src="../../assets/landingPics/girlWithCats.jpg" height="380">
        <v-layout column align-center justify-center>
          <div class="headline mb-3 text-xs-center color-stroke text-h3">
            Animal rescue is a platform which will help you to find your pet really fast
          </div>
          <em class="text-h4">Cant wait to see your dog? Time to find it!</em>
          <!--            <v-btn class="blue lighten-2 mt-5" dark large href="/pre-made-themes">-->
          <!--              Get more info-->
          <!--            </v-btn>-->
        </v-layout>
      </v-parallax>
    </section>



  </div>
</template>

<script>
export default {
  name: "Landing",
  data: function () {
    return {
      title: "Endorfine",
      imageLink: {
        main: "@/assets/landingPics/dog.jpg",
        sub_main: "@/assets/landingPics/girlWithCats.jpg",
        logo:
          "https://firebasestorage.googleapis.com/v0/b/endorfinevue.appspot.com/o/assets%2Fandroid-chrome-512x512.png?alt=media&token=8a0a66f6-4741-4ff6-8f28-eb9ec74374df",
        social_cover:
          "https://firebasestorage.googleapis.com/v0/b/endorfinevue.appspot.com/o/assets%2Fo-NIGHTCLUB-facebook.jpg?alt=media&token=cefc5c4c-9714-41da-9c22-f63caf5e89a4",
      },
      email: "",
      emailRules: [
        (v) => {
          return !!v || "E-mail is required";
        },
        (v) =>
          /^\w+([.-]?\w+)*@\w+([.-]?\w+)*(\.\w{2,3})+$/.test(v) || "E-mail must be valid",
      ],
      subscribed: false,
    };
  },
  methods: {
    subscribe: function () {
      this.subscribed = !this.subscribed;
    },
  },

  computed: {
    imgHeight: function () {
      var offset = 320;
      console.log("new image height is " + (this.pageHeight - offset));
      return this.pageHeight - offset;
    },
  },

  mounted: function () {
    this.calculateHeight();
  },
};
</script>

<style scoped>
.finedTitle {
  font-weight: 900;
  text-shadow: 2px 2px #000000;
}

.social-icon {
  font-size: 21px;
  color: white;
}

.color-stroke {
  -webkit-text-stroke: 2px #4c6ac4; /* свойство text-stroke наследуется, применяется ко всем элементам, изменяет текст */

  /* или */

  -webkit-text-stroke-width: 2px;
  -webkit-text-stroke-color: #4c6ac4;
}
</style>
