<template>
  <v-app id="inspire">
    <v-navigation-drawer
      v-model="drawer"
      app
    >
      <v-list-item three-line>
        <v-list-item-content>
          <v-list-item-title class="text-h6">
            FSK
          </v-list-item-title>
          <v-list-item-subtitle>
            Fjärdhunda Sport Klubb | Fotboll Handboll Innebandy
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list
        dense
        nav
      >
        <v-list-item
          v-for="item in items"
          :key="item.id"
          link
          :to="item.url"
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
      <v-list dense nav>
        <v-list-item
          link
          href="https://www.netshirt.se/foreningsklader/fjardhundra-sk"
          target="_blank"
          @click="drawer = false"
        >
          <v-list-item-icon>
            <v-icon>mdi-tshirt-crew</v-icon>
          </v-list-item-icon>
          <v-list-item-content> 
            <v-list-item-title>Föreningsshop</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
      <v-list dense nav>
        <v-list-item
          link
          href="https://www.facebook.com/fjardhundra/"
          target="_blank"
          @click="drawer = false"
        >
          <v-list-item-icon>
            <v-icon>mdi-facebook</v-icon>
          </v-list-item-icon>
          <v-list-item-content> 
            <v-list-item-title>Facebook</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar app elevate-on-scroll fade-img-on-scroll>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title>Fjärdhundra SK</v-toolbar-title>
       <v-spacer></v-spacer>
      
      <v-img class="mr-3" :src="require('./assets/clublogo.png')" max-width="35" max-height="35"></v-img>
    </v-app-bar>

    <v-main>
      <TopInformation class="mt-3" />
      <router-view />
      <Footer />
    </v-main>
  </v-app>
</template>

<script>
import TopInformation from './components/TopInformation.vue'
import Footer from './components/Footer.vue'
  export default {
    components: {
      TopInformation, Footer
    },
    data: () => ({
      drawer: null,
      items: [
          { id: 1, title: 'Hem', icon: 'mdi-home', url: '/' },
          { id: 2, title: 'Kontakt', icon: 'mdi-account-box', url: '/contact' },
          { id: 3, title: 'Om oss', icon: 'mdi-information', url: '/about' },
          { id: 4, title: 'Aktuellt', icon: 'mdi-bell-ring', url: '/events' },
          { id: 5, title: 'Fotboll', icon: 'mdi-soccer', url: '/football' },
          { id: 6, title: 'Handboll', icon: 'mdi-handball', url: '/handball' },
          { id: 7, title: 'Innebandy', icon: 'mdi-soccer', url: '/floorball' },
          { id: 9, title: 'Kalender', icon: 'mdi-calendar', url: '/calendar' },
          { id: 10, title: 'Medlemskap', icon: 'mdi-card-account-details', url: '/membership' },
          { id: 11, title: 'Styrelse', icon: 'mdi-account-group', url: '/board' },
          { id: 12, title: 'Sponsorer', icon: 'mdi-cash-100', url: '/sponsors' },
          { id: 13, title: 'Anläggningar', icon: 'mdi-stadium', url: '/facilities' },
          { id: 14, title: 'Medlemsavgifter', icon: 'mdi-wallet-membership', url: '/memberfees' },
        ],
      }),
  }
</script>