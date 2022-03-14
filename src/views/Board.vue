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
                { id: 1, img: require('../assets/avatar.webp'), email: 'lisa@ekehult.se', phone: '+46736260079', name: 'Lisa Ekehult', title: 'Ordförande', link: 'https://www.svedbergs.se/'},
                { id: 2, img: require('../assets/avatar.webp'), email: 'eliseg_88@hotmail.com', phone: '', name: 'Elise Gunnarsson', title: 'Sekreterare', link: 'https://www.noro.se/'},
                { id: 3, img: require('../assets/amanda_aspling_lofgren.jpeg'), email: 'amanda.fotboll03@gmai l.com', phone: '+46702064651', name: 'Amanda Aspling Löfgren', title: 'Ledamot', link: 'https://www.moraarmatur.com/sv/'},
                { id: 4, img: require('../assets/avatar.webp'), email: '', phone: '+46708589361', name: 'Monica Enqvist', title: 'Ledamot', link: 'https://www.grohe.sv/'},
                { id: 5, img: require('../assets/avatar.webp'), email: '', phone: '', name: 'Daniel Lindberg', title: 'Ledamot', link: 'https://www.ifo.sv/'},
                { id: 6, img: require('../assets/avatar.webp'), email: 'martin.roth@storaenso.com', phone: '', name: 'Martin Roth', title: 'Ledamot', link: 'https://www.nibe.eu/sv-se'},
                { id: 7, img: require('../assets/avatar.webp'), email: 'reginahandboll@hotmail.se', phone: '', name: 'Regina Maurd', title: 'Vice ordförande, sammankallande handboll', link: 'https://www.gustavsberg.com/se/'},
                { id: 8, img: require('../assets/avatar.webp'), email: '', phone: '', name: 'Mats Mattsson', title: 'Sammankallande badminton', link: 'https://www.ifo.se/ido/#gref'},
                { id: 9, img: require('../assets/avatar.webp'), email: 'jonaslarsson_82@hotmail.com', phone: '+46723262417', name: 'Jonas Hovind', title: 'Ledamot, Uthyrningsansvarig (Mellevi)', link: 'https://ctc.se/'},
                { id: 10, img: require('../assets/avatar.webp'), email: 'hedlund.vanga2@gmail.com', phone: '', name: 'Marcus Hedlund', title: 'Ledamot, Sammankallande fotboll (ungdom)', link: 'https://inr.se/'},
                { id: 11, img: require('../assets/josefin_hedlund.jpeg'), email: 'josefine.e-ahlin@hotmail.com', phone: '+46706526695', name: 'Josefine Hedlund', title: 'Sammankallande fotboll (ungdom)', link: 'https://inr.se/'},
                { id: 12, img: require('../assets/johan_engvall.jpeg'), email: 'engjoh01@gmail.com', phone: '+46761849670', name: 'Johan Engvall', title: 'Ledamot, Sammankallande Anläggningskommitté', link: 'https://inr.se/'},
                { id: 13, img: require('../assets/therese_andersson.jpeg'), email: 'therese.andersson@enkoping.se', phone: '', name: 'Therese Andersson', title: 'Sammankallande Friskvård/Skidor/Gymnastik', link: 'https://inr.se/'},
                { id: 14, img: require('../assets/avatar.webp'), email: 'tomas.e.ahlin@hotmail.com', phone: '', name: 'Tomas Ahlin', title: 'Sammankallande Innebandy', link: 'https://inr.se/'},
                { id: 15, img: require('../assets/avatar.webp'), email: 'jens@allbetong.com', phone: '+46704670799', name: 'Jens Åhlin', title: 'Sammankallande Fotboll (senior)', link: 'https://inr.se/'},
            ],
    }
  }
}
</script>

<style>

</style>