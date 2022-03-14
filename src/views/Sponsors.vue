<template>
  <v-container id="suppliers">
    <v-row class="mt-3">
      <v-col v-for="item in board" :key="item.id" cols="12" sm="4" lg="3">
        <v-card
          class="mx-auto"
          max-width="400"
        >
    <v-img
      contain
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
  name: 'sponsors',
  data() {
    return {
      board: [
                { id: 1, img: require('../assets/ackes.webp'), email: 'info@ackes.nu', phone: '+46171441184', name: 'Ackes Färgcenter', title: 'Ackes Färgcenter', link: 'https://ackes-fargcenter.nordsjoidedesign.se/'},
                { id: 2, img: require('../assets/byggnadsfirma_folkesson.webp'), email: 'tb@byggfolke.se', phone: '+46703179622', name: 'Byggnadsfirma Folkesson AB', title: 'Byggnadsfirma Folkesson AB', link: 'http://www.byggfolke.se/'},
                { id: 3, img: require('../assets/crenna.png'), email: 'order@crenna.se', phone: '+171478051', name: 'Crenna', title: 'Crenna', link: 'https://crenna.se/'},
                { id: 4, img: require('../assets/enkopings_skog_tradgard.jpg'), email: 'enkopingskogochtradgard@outlook.com', phone: '+4617131012', name: 'Enköpings Skog & Trädgård', title: 'Enköpings Skog & Trädgård', link: 'https://enkopingsskogochtradgard.se/'},
                { id: 5, img: require('../assets/golja_bygg_entreprenad.webp'), email: '', phone: '', name: 'Gölja Bygg & Entreprenad', title: 'Gölja Bygg & Entreprenad', link: ''},
                { id: 6, img: require('../assets/jgm_byggservice.png'), email: '', phone: '+4617193110', name: 'JGM Byggservice', title: 'JGM Byggservice', link: ''},
                { id: 7, img: require('../assets/lappset.png'), email: 'sverige@lappset.com', phone: '+4617127080', name: 'Lappset', title: 'Lappset', link: 'https://www.lappset.se/'},
                { id: 8, img: require('../assets/mellersta_gard.webp'), email: '', phone: '', name: 'Mellersta Gård', title: 'Mellersta Gård', link: ''},
                { id: 9, img: require('../assets/silens_svets_smide.png'), email: 'info@silenssmide.com', phone: '+46704920757', name: 'Siléns Svets & Smide', title: 'Siléns Svets & Smide', link: 'https://silenssmide.se/'},
                { id: 10, img: require('../assets/ua_montage.png'), email: '', phone: '+46171477330', name: 'UA Montage', title: 'UA Montage', link: 'https://www.ua-montage.se/'},
                { id: 11, img: require('../assets/gf_100.webp'), email: 'theresa@gf100.se', phone: '+4617180100', name: 'GF 100', title: 'GF 100', link: 'https://www.gf100.se/'},
                { id: 12, img: require('../assets/josefssons.webp'), email: 'info@joshyr.se', phone: '+4617124814', name: 'Josefssons Maskinuthyrning AB', title: 'Josefssons Maskinuthyrning AB', link: 'https://joshyr.se/'},
                { id: 13, img: require('../assets/anderssons_lantbruk.jpg'), email: 'anderssons_lantbruk@hotmail.com', phone: '+46702602649', name: 'Anderssons Lantbruk', title: 'Anderssons Lantbruk', link: 'https://www.facebook.com/anderssonslantbruk/'},
                { id: 14, img: require('../assets/ca_montage.webp'), email: '', phone: '', name: 'CA Montage Christer Abrahamsson', title: 'CA Montage Christer Abrahamsson', link: ''},
                { id: 15, img: require('../assets/dunderbo_gard.webp'), email: '', phone: '', name: 'Dunderbo Gård', title: 'Dunderbo Gård', link: ''},
                { id: 16, img: require('../assets/fastighetsbolaget_malmgarden.webp'), email: '', phone: '+4617127995', name: 'Fastighetsbolaget Malmgården', title: 'Fastighetsbolaget Malmgården', link: ''},
                { id: 17, img: require('../assets/lb_olssons_mekaniska.jpg'), email: 'lbomek@lbomek.se', phone: '+4617191750', name: 'LB Olssons Mekaniska AB', title: 'LB Olssons Mekaniska AB', link: 'https://www.lbomek.se/'},
                { id: 18, img: require('../assets/mellersta_el_ventilation.webp'), email: '', phone: '', name: 'Mellersta El & Ventilation AB', title: 'Mellersta El & Ventilation AB', link: ''},
                { id: 19, img: require('../assets/sparbanken_enkoping.png'), email: '', phone: '+4617185300', name: 'Sparbanken Enköping', title: 'Sparbanken Enköping', link: 'https://www.sparbankenenkoping.se/'},
                { id: 20, img: require('../assets/eneby_entreprenad.webp'), email: '', phone: '', name: 'Eneby Entreprenad', title: 'Eneby Entreprenad', link: ''},
                { id: 21, img: require('../assets/gastre_ventilation.webp'), email: '', phone: '+46708169323', name: 'Gästre Ventilation', title: 'Gästre Ventilation', link: ''},
                { id: 22, img: require('../assets/lindbloms_jordkultur.webp'), email: 'lansfors@hotmail.com', phone: '+45708796854', name: 'Lindbloms Jordkultur', title: 'Lindbloms Jordkultur', link: 'http://www.lansforselvin.se/'},
                { id: 23, img: require('../assets/allbetong_ab.webp'), email: '', phone: '+46704670799', name: 'Allbetong AB', title: 'Allbetong AB', link: 'http://www.allbetong.se/'},
                { id: 24, img: require('../assets/carlsson_ring.webp'), email: 'fastigheter@carlssonring.se', phone: '+4618102030', name: 'Carlsson Ring', title: 'Carlsson Ring', link: 'https://carlssonring.se/'},
                { id: 25, img: require('../assets/enkopings_bygg_inredning.webp'), email: '', phone: '+4617196095', name: 'Enköpings Bygg & Inredning', title: 'Enköpings Bygg & Inredning', link: ''},
                { id: 26, img: require('../assets/fjardhundra_akeri.webp'), email: '', phone: '+4617191133', name: 'Fjärdhundra Åkeri', title: 'Fjärdhundra Åkeri', link: ''},
                { id: 27, img: require('../assets/holmers_transport.webp'), email: '', phone: '', name: 'Holmers Transport', title: 'Holmers Transport', link: ''},
                { id: 28, img: require('../assets/km_eriksson_lantbruk.webp'), email: '', phone: '', name: 'KM Eriksson Lantbruk', title: 'KM Eriksson Lantbruk', link: ''},
                { id: 29, img: require('../assets/marts_bergsprangning.webp'), email: '', phone: '+46706030767', name: 'Mårts Bergsprängning', title: 'Mårts Bergsprängning', link: ''},
                { id: 30, img: require('../assets/refvelsta_godsforvaltning.webp'), email: '', phone: '+4617196119', name: 'Refvelsta Godsförvaltning AB', title: 'Refvelsta Godsförvaltning AB', link: ''},
                { id: 31, img: require('../assets/sok_karlsson_bilservice.jpg'), email: '', phone: '+4617191584', name: 'SÖK Karlsson Bilservice AB', title: 'SÖK Karlsson Bilservice AB', link: ''},
                { id: 32, img: require('../assets/ica_maxi.webp'), email: 'kundkontakt.enkoping@maxi.ica.se', phone: '+46171415600', name: 'ICA Maxi Enköping', title: 'ICA Maxi Enköping', link: 'https://www.ica.se/butiker/maxi/enkoping/maxi-ica-stormarknad-enkoping-10762/start/'},
            ],
    }
  }
}
</script>

<style>

</style>