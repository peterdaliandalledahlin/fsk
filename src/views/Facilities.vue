<template>
  <v-container>
      <h1>facilities</h1>
      <!-- <h4>Fjärdhundra sporthall</h4>
      <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2008.2798171226611!2d16.920040015981954!3d59.778037981818116!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x465e41509b37c457%3A0xdc537bf2d1f48b35!2sMellevi%20IP!5e0!3m2!1ssv!2sse!4v1646936066517!5m2!1ssv!2sse" width="100%" height="450" style="border:0;" allowfullscreen="" loading="lazy"></iframe>
      <br /> -->
      <h4>Fjärdhundra sporthall</h4>
      <iframe width="100%" height="450" frameborder="0" scrolling="no" marginheight="0" marginwidth="0" src="https://www.openstreetmap.org/export/embed.html?bbox=16.921826004981998%2C59.77338861073312%2C16.928724646568302%2C59.775165533467806&amp;layer=mapnik&amp;marker=59.774277083923884%2C16.925275325775146" style="border: 1px solid black"></iframe><br/><small><a href="https://www.openstreetmap.org/?mlat=59.77428&amp;mlon=16.92528#map=18/59.77428/16.92528">Visa större karta</a></small>  <h4>Mellevi föreningslokal</h4>
      <br />
      <h4>Lilla hallen</h4>
      <iframe width="100%" height="450" frameborder="0" scrolling="no" marginheight="0" marginwidth="0" src="https://www.openstreetmap.org/export/embed.html?bbox=16.922169327735904%2C59.77470645914839%2C16.929067969322208%2C59.77648331173416&amp;layer=mapnik&amp;marker=59.77559489726438%2C16.925618648529053" style="border: 1px solid black"></iframe><br/><small><a href="https://www.openstreetmap.org/?mlat=59.77559&amp;mlon=16.92562#map=18/59.77559/16.92562">Visa större karta</a></small>
      <br />
      <h4>Mellevi IP</h4>
      <iframe width="100%" height="450" frameborder="0" scrolling="no" marginheight="0" marginwidth="0" src="https://www.openstreetmap.org/export/embed.html?bbox=16.91778659820557%2C59.77742840755262%2C16.924685239791874%2C59.77920511524639&amp;layer=mapnik&amp;marker=59.77831677322198%2C16.92123591899872" style="border: 1px solid black"></iframe><br/><small><a href="https://www.openstreetmap.org/?mlat=59.77832&amp;mlon=16.92124#map=18/59.77832/16.92124">Visa större karta</a></small>
      <br />
      <h4>Idrottsfältet</h4>
      <iframe width="100%" height="450" frameborder="0" scrolling="no" marginheight="0" marginwidth="0" src="https://www.openstreetmap.org/export/embed.html?bbox=16.905673742294315%2C59.77398002864958%2C16.919471025466922%2C59.77753371657244&amp;layer=mapnik&amp;marker=59.775756919903266%2C16.912572383880615" style="border: 1px solid black"></iframe><br/><small><a href="https://www.openstreetmap.org/?mlat=59.77576&amp;mlon=16.91257#map=17/59.77576/16.91257">Visa större karta</a></small>
      <br />
      <h4>Grusplanen</h4>
      <iframe width="100%" height="450" frameborder="0" scrolling="no" marginheight="0" marginwidth="0" src="https://www.openstreetmap.org/export/embed.html?bbox=16.918119192123417%2C59.77141444128147%2C16.931916475296024%2C59.774968402327644&amp;layer=mapnik&amp;marker=59.77318409647388%2C16.92501354191336" style="border: 1px solid black"></iframe><br/><small><a href="https://www.openstreetmap.org/?mlat=59.77318&amp;mlon=16.92501#map=17/59.77319/16.92502">Visa större karta</a></small>
      <v-img
        contain
        :lazy-src="require('../assets/mellevi.jpg')"
        max-width="304"
        :src="require('../assets/mellevi.jpg')"
      ></v-img>
<p>Privatpersoner får ej hyra Mellevi, endast föreningar samt FSKs verksamheter. Vid frågor om lokalen kontakta vår uthyrningsansvarig</p>
<a to="/contact">Uthyrningsansvariga</a>
<a href="https://boka.se/systems/t7xsd275" target="_blank">Boka direkt här</a>
        <v-row class="mt-3">
            <v-col v-for="item in facilities" :key="item.id" cols="12" sm="4" lg="3">
                <v-card
                max-width="344"
            >
                <v-card-text>
                    <div>{{ item.title }}</div>
                    <p class="text-h4 text--primary">
                        {{ item.name }}
                    </p>
                    <p>adjective</p>
                    <div class="text--primary">
                        <ul>
                            <li>{{ item.li1 }}</li>
                            <li>{{ item.li2 }}</li>
                            <li>{{ item.li3 }}</li>
                            <li>{{ item.li4 }}</li>
                            <li>{{ item.li5 }}</li>
                        </ul>
                    </div>
                </v-card-text>
                <v-card-actions>
                <v-btn
                    text
                    color="deep-purple accent-4"
                >
                    Learn More
                </v-btn>
                </v-card-actions>
                </v-card>
    <!-- <v-card
    max-width="344"
  >
    <v-card-text>
      <div>Inomhushall</div>
      <p class="text-h4 text--primary">
        Lilla hallen
      </p>
      <p>adjective</p>
      <div class="text--primary">
          <ul>
              <li>Yta som mindre basketplan</li>
              <li>Används främst under försäsongsträningen</li>
              <li>Vägbeskrivning: Åk Stora Vägen genom Fjärdhundra. Tag av mellan Missionskyrkan och hyreshusen. Följ Björkvägen upp mot hallen.</li>
          </ul>
      </div>
    </v-card-text>
    <v-card-actions>
      <v-btn
        text
        color="deep-purple accent-4"
      >
        Learn More
      </v-btn>
    </v-card-actions>
    </v-card>
    <v-card
    max-width="344"
  >
    <v-card-text>
      <div>Fotbollsplan</div>
      <p class="text-h4 text--primary">
        Mellevi IP
      </p>
      <p>adjective</p>
      <div class="text--primary">
          <ul>
              <li>11-mannaplan 100 x 60 m, underlag: naturgräs</li>
              <li>7-mannaplan 60 x 35 m, underlag: naturgräs</li>
              <li>Fotbollens huvudarena med kiosk och klubbstugan är belägen här.</li>
              <li>Vägbeskrivning: Åk Stora Vägen genom Fjärdhundra samhälle. Tag av mitt i samhället vid hyreshusen. Skyltat "Mellevi IP". Följ Mellevivägen rakt fram.</li>
          </ul>
      </div>
    </v-card-text>
    <v-card-actions>
      <v-btn
        text
        color="deep-purple accent-4"
      >
        Learn More
      </v-btn>
    </v-card-actions>
    </v-card>
    <v-card
    max-width="344"
  >
    <v-card-text>
      <div>Fotbollsplan</div>
      <p class="text-h4 text--primary">
        Idrottsfältet
      </p>
      <p>adjective</p>
      <div class="text--primary">
          <ul>
              <li>11-mannaplan 105 x 65 m, underlag: naturgräs</li>
              <li>7-mannaplan 60 x 45 m, underlag: naturgräs</li>
              <li>Fotbollens huvudarena med kiosk och klubbstugan är belägen här.</li>
              <li>Vägbeskrivning: Parkera vid Fjärdhundrabadet, omklädningsrum intill badet. Planerna ligger bakom badet, gå via elljusspåret till höger om badet.</li>
          </ul>
      </div>
    </v-card-text>
    <v-card-actions>
      <v-btn
        text
        color="deep-purple accent-4"
      >
        Learn More
      </v-btn>
    </v-card-actions>
    </v-card>
    <v-card
    max-width="344"
  >
    <v-card-text>
      <div>Fotbollsplan</div>
      <p class="text-h4 text--primary">
        Grusplanen
      </p>
      <p>adjective</p>
      <div class="text--primary">
          <ul>
              <li>Isrink med naturis under vintersäsong</li>
              <li>Yta tillgänglig som 5-7-mannaplan, underlag: naturgräs</li>
              <li>Grusplanen har elbelysning</li>
              <li>Vägbeskrivning: Åk Stora Vägen genom Fjärdhundra. Mitt i samhället, tag av vid stora asfaltsplanen före hyreshusen. Följ Åke Wassings väg och ni kommer rakt på grusplanen. Parkering vid Fjärdhundra Sporthall.</li>
          </ul>
      </div>
    </v-card-text>
    <v-card-actions>
      <v-btn
        text
        color="deep-purple accent-4"
      >
        Learn More
      </v-btn>
    </v-card-actions>
    </v-card> -->
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
export default {
    name: 'facilities',
    data() {
        return {
            facilities: [
                { id: 1, icon: 'mdi-stadium', title: 'Inomhushall', name: 'Fjärdhundra sporthall', li1: 'Planstorlek 40 x 20 m', li2: 'Publikkapacitet: 150 personer', li3: 'Kiosk med servering', li4: 'Hemmaarena för innebandy och handboll', li5: 'Vägbeskrivning: Åk Stora Vägen genom Fjärdhundra. Mitt i samhället, tag av vid stora asfaltsplanen före hyreshusen. Följ Åke Wassings väg och Sporthallen ligger på vänster sida.'},
                { id: 2, icon: 'mdi-stadium', title: 'Inomhushall', name: 'Lilla hallen', li1: 'Yta som mindre basketplan', li2: 'Används främst under försäsongsträningen', li3: 'Vägbeskrivning: Åk Stora Vägen genom Fjärdhundra. Tag av mellan Missionskyrkan och hyreshusen. Följ Björkvägen upp mot hallen.', li4: '', li5: ''},
                { id: 3, icon: 'mdi-stadium', title: 'Fotbollsplan', name: 'Mellevi IP', li1: '11-mannaplan 100 x 60 m, underlag: naturgräs', li2: '7-mannaplan 60 x 35 m, underlag: naturgräs', li3: 'Fotbollens huvudarena med kiosk och klubbstugan är belägen här.', li4: 'Vägbeskrivning: Åk Stora Vägen genom Fjärdhundra samhälle. Tag av mitt i samhället vid hyreshusen. Skyltat "Mellevi IP". Följ Mellevivägen rakt fram.', li5: ''},
                { id: 4, icon: 'mdi-stadium', title: 'Fotbollsplan', name: 'Idrottsfältet', li1: '11-mannaplan 105 x 65 m, underlag: naturgräs', li2: '7-mannaplan 60 x 45 m, underlag: naturgräs', li3: 'Fotbollens huvudarena med kiosk och klubbstugan är belägen här.', li4: 'Vägbeskrivning: Parkera vid Fjärdhundrabadet, omklädningsrum intill badet. Planerna ligger bakom badet, gå via elljusspåret till höger om badet.', li5: ''},
                { id: 5, icon: 'mdi-stadium', title: 'Fotbollsplan', name: 'Grusplanen', li1: 'Isrink med naturis under vintersäsong', li2: 'Yta tillgänglig som 5-7-mannaplan, underlag: naturgräs', li3: 'Grusplanen har elbelysning', li4: 'Vägbeskrivning: Åk Stora Vägen genom Fjärdhundra. Mitt i samhället, tag av vid stora asfaltsplanen före hyreshusen. Följ Åke Wassings väg och ni kommer rakt på grusplanen. Parkering vid Fjärdhundra Sporthall.', li5: ''},
            ],
        }
    }

}
</script>

<style>

</style>