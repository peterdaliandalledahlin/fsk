<template>
  <v-container id="suppliers">
    <v-row class="mt-3">
      <v-col v-for="item in board" :key="item.id" cols="12" sm="4" lg="3">
        <v-card
          class="mx-auto"
          max-width="400"
        >
    <v-img
      class="white--text align-end"
      height="200px"
      :src="item.img"
    >
      <!-- <v-card-title>Det här blir en bra dag</v-card-title> -->
    </v-img>

    <v-card-subtitle class="pb-0">
      {{ item.title }}
    </v-card-subtitle>

    <v-card-text class="text--primary">
      <div>{{ item.name }}</div>

      <div>
        <v-icon
            color="green darken-2"
            >
            mdi-phone
        </v-icon>
        {{ item.phone }}
    </div>
    <div>
        <v-icon
            color="green darken-2"
            >
            mdi-email
        </v-icon>
        {{ item.email }}
    </div>
    </v-card-text>

    <v-card-actions>
      <v-btn
        color="#E74C13"
        text
        :href="item.link"
        target="_blank"
      >
        Till hemsidan
      </v-btn>

    </v-card-actions>
  </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
    name: 'board',
  data() {
    return {
      board: [
                { id: 1, img: require('../assets/avatar.webp'), email: 'lisa@ekehult.se', phone: '+46736260079', name: 'Lisa Ekehult', title: 'Ordförande', link: ''},
                { id: 2, img: require('../assets/avatar.webp'), email: 'eliseg_88@hotmail.com', phone: '', name: 'Elise Gunnarsson', title: 'Sekreterare', link: ''},
                { id: 3, img: require('../assets/amanda_aspling_lofgren.jpeg'), email: 'amanda.fotboll03@gmail.com', phone: '+46702064651', name: 'Amanda Aspling Löfgren', title: 'Ledamot', link: ''},
                { id: 4, img: require('../assets/avatar.webp'), email: '', phone: '+46708589361', name: 'Monica Enqvist', title: 'Ledamot', link: ''},
                { id: 5, img: require('../assets/avatar.webp'), email: '', phone: '', name: 'Daniel Lindberg', title: 'Ledamot', link: ''},
                { id: 6, img: require('../assets/avatar.webp'), email: 'martin.roth@storaenso.com', phone: '', name: 'Martin Roth', title: 'Ledamot', link: ''},
                { id: 7, img: require('../assets/avatar.webp'), email: 'reginahandboll@hotmail.se', phone: '', name: 'Regina Maurd', title: 'Vice ordförande, sammankallande handboll', link: ''},
                { id: 8, img: require('../assets/avatar.webp'), email: '', phone: '', name: 'Mats Mattsson', title: 'Sammankallande badminton', link: ''},
                { id: 9, img: require('../assets/avatar.webp'), email: 'jonaslarsson_82@hotmail.com', phone: '+46723262417', name: 'Jonas Hovind', title: 'Ledamot, Uthyrningsansvarig (Mellevi)', link: ''},
                { id: 10, img: require('../assets/avatar.webp'), email: 'hedlund.vanga2@gmail.com', phone: '', name: 'Marcus Hedlund', title: 'Ledamot, Sammankallande fotboll (ungdom)', link: ''},
                { id: 11, img: require('../assets/josefin_hedlund.jpeg'), email: 'josefine.e-ahlin@hotmail.com', phone: '+46706526695', name: 'Josefine Hedlund', title: 'Sammankallande fotboll (ungdom)', link: ''},
                { id: 12, img: require('../assets/johan_engvall.jpeg'), email: 'engjoh01@gmail.com', phone: '+46761849670', name: 'Johan Engvall', title: 'Ledamot, Sammankallande Anläggningskommitté', link: ''},
                { id: 13, img: require('../assets/therese_andersson.jpeg'), email: 'therese.andersson@enkoping.se', phone: '', name: 'Therese Andersson', title: 'Sammankallande Friskvård/Skidor/Gymnastik', link: ''},
                { id: 14, img: require('../assets/avatar.webp'), email: 'tomas.e.ahlin@hotmail.com', phone: '', name: 'Tomas Ahlin', title: 'Sammankallande Innebandy', link: ''},
                { id: 15, img: require('../assets/avatar.webp'), email: 'jens@allbetong.com', phone: '+46704670799', name: 'Jens Åhlin', title: 'Sammankallande Fotboll (senior)', link: ''},
                { id: 16, img: require('../assets/sara_eriksson.jpeg'), email: 'sara@simtuna.com', phone: '+46736135957', name: 'Sara Eriksson', title: 'Valberedning', link: ''},
                { id: 17, img: require('../assets/avatar.webp'), email: 'britta@fsk.nu', phone: '+46703730529', name: 'Britta Jäderblom', title: 'IT ansvarig, medlemsansvarig', link: ''},
                { id: 18, img: require('../assets/avatar.webp'), email: 'tintu_84@hotmail.com', phone: '+46735500226', name: 'Tiina Karlqvist', title: 'Kassa/inköp/serviceansvarig kiosk', link: ''},
                { id: 19, img: require('../assets/avatar.webp'), email: 'helena.hstrom@hotmail.com', phone: '+46702355428', name: 'Helena Ahlin', title: 'Kassa/inköp/serviceansvarig kiosk', link: ''},
                { id: 20, img: require('../assets/avatar.webp'), email: 'emeliehovind@hotmail.com', phone: '+46706460146', name: 'Emelie Hovind Pettersson', title: 'Uthyrningsansvarig Mellevi', link: ''},
                { id: 21, img: require('../assets/avatar.webp'), email: 'anna.frohm@live.se', phone: '+46739986423', name: 'Anna Frohm', title: 'Nyckelansvarig', link: ''},
                { id: 22, img: require('../assets/avatar.webp'), email: 'annika.sodergren74@gmail.com', phone: '+46702451231', name: 'Annika Södergren', title: 'Redovisning/kassör, LOK-ansvarig', link: ''},
                { id: 23, img: require('../assets/avatar.webp'), email: '', phone: '', name: 'Ralf Timmerman', title: 'Revisor', link: ''},
                { id: 24, img: require('../assets/avatar.webp'), email: 'marina.hofberg@gmail.com', phone: '+46708294555', name: 'Marina Eklöf Hofberg', title: 'Revisor', link: ''},
                { id: 25, img: require('../assets/avatar.webp'), email: '', phone: '', name: 'Joakim Andersson', title: 'Tränare', link: ''},
                { id: 26, img: require('../assets/avatar.webp'), email: 'emma@sandelins.se', phone: '+46702639323', name: 'Emma Sandelin', title: 'Tränare', link: ''},
                { id: 27, img: require('../assets/avatar.webp'), email: 'magnuslundin@hotmail.com', phone: '', name: 'Magnus Lundin', title: 'Lagledare', link: ''},
            ],
    }
  }
}
</script>

<style>

</style>