<template>
  <v-sheet
    :height="sheetHeight"
    class="overflow-hidden"
    style="position: relative"
  >
    <v-container class="fill-height">
      <v-row align="center" justify="center">
        <!-- <img
          src="../../assets/video.jpg"
          alt="Vidéo de présentation Tut'Up"
          width="100%"
        /> -->

        <div style="width: 100vw !important">
          <div style="padding-top: 56.25%; position: relative">
            <iframe
              class="youtube"
              style="
                position: absolute;
                top: 0;
                left: 0;
                height: 100% !important;
                width: 100% !important;
              "
              src="https://www.youtube.com/embed/SlSpXmzvHLQ?controls=0&autoplay=1&mute=0"
              frameborder="0"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen
              autoplay
            ></iframe>
          </div>
        </div>

        <img
          src="../../assets/down.png"
          alt="scrollDown"
          width="5%"
          style="margin: 20px"
        />
        <!-- <h1 class="display-3 hidden-xs-only">Tut'up</h1>
        <h1 class="text-center display-1 hidden-sm-and-up">
          Bienvenue sur Tut'up, le rendez-vous de la réussite.
        </h1> -->
        <div class="flexContain mainHome">
          <img src="../../assets/qqtutup.jpg" />
          <div>
            <h2>Qu'est-ce que Tut'Up ?</h2>
            <div>
              Tut’Up est une plateforme de mise en relation entre élèves et
              tuteurs volontaires. Elle s’offre aux élèves en difficulté mais
              également à ceux qui veulent consolider leur acquis ou exceller
              dans une matière. En tant que tuteur vous pouvez ici aider un
              élève dans son travail et sa méthodologie, et l’accompagner lors
              des différentes transitions entre les cycles.
            </div>
            <v-btn class="couleurPrimaire" dark v-bind="attrs" v-on="on">
              Créer un compte
            </v-btn>
          </div>
        </div>
        <div class="mainValeur">
          <h2>Nos valeurs</h2>
          <div class="flexContain">
            <div class="valeur">
              <img
                src="../../assets/reactivite.png"
                alt="Valeur1"
                width="50%"
              />
              <div>
                <h3>Réactivité</h3>
                <p>
                  Mise en relation avec des professeurs certifiés le plus en
                  mesure de répondre à vos demandes dans les plus brefs délais.
                </p>
              </div>
            </div>
            <div class="valeur">
              <img
                src="../../assets/icons/confiance.png"
                alt="Valeur2"
                width="50%"
              />
              <div>
                <h3>Confiance</h3>
                <p>
                  Mise en relation avec des professeurs certifiés le plus en
                  mesure de répondre à vos demandes dans les plus brefs délais.
                </p>
              </div>
            </div>
            <div class="valeur">
              <img
                src="../../assets/transmission.png"
                alt="Valeur3"
                width="50%"
              />
              <div>
                <h3>Transmission</h3>
                <p>
                  Mise en relation avec des professeurs certifiés le plus en
                  mesure de répondre à vos demandes dans les plus brefs délais.
                </p>
              </div>
            </div>
          </div>
        </div>
        <div class="flexContain mainHome">
          <div>
            <h2>Pourquoi nous choisir ?</h2>
            <div>
              Tut’Up vous propose un enseignement complémentaire à ceux du
              cursus scolaire. Vous trouverez des tuteurs proches de chez vous
              avec des horaires flexibles. Chez Tut’Up, l’expérience des tuteurs
              en tant qu’ancien élève est importante. Elle lui permet de donner
              des cours variés en fonction du niveau de l’élève et de ses
              objectifs à atteindre, de la 6ème à la terminale.
            </div>
            <v-btn
              class="couleurPrimaire"
              dark
              v-bind="attrs"
              v-on="on"
              to="FAQ"
            >
              Notre FAQ
            </v-btn>
          </div>
          <img src="../../assets/titre.jpg" width="40%" />
        </div>
      </v-row>
    </v-container>
  </v-sheet>
</template>

// <script>
// export default {
//   computed: {
//     sheetHeight() {
//       switch (this.$vuetify.breakpoint.name) {
//         case "xs":
//           return "200px";
//         case "sm":
//           return "300px";
//         case "md":
//           return "300px";
//         case "lg":
//           return "300px";
//         case "xl":
//           return "350px";
//       }
//       return "300px";
//     },
//   },
// };
//
</script>
