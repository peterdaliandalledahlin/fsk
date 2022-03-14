<template>
  <v-container>
    <h1>calendar</h1>
    <div v-if="isLoading">
      <v-img
        contain
        :lazy-src="require('../assets/skeleton-loader.gif')"
        :src="require('../assets/skeleton-loader.gif')"
      ></v-img>
    </div>
    <div else>
      <v-simple-table>
    <template v-slot:default>
      <thead>
        <tr>
          <th class="text-left">
            Datum
          </th>
          <th class="text-left">
            Aktivitet
          </th>
        </tr>
      </thead>
      <tbody>
        <tr
          v-for="item in calendar"
          :key="item.name"
        >
          <td>{{item.dayNumber}}{{ item.weekDay }}</td>
          <td>{{ item.list }}</td>
        </tr>
      </tbody>
    </template>
  </v-simple-table>
      <!-- <div v-for="item in calendar" :key="item.result">
        <p>{{ item.result }}</p>
        <p>{{ item.list}}</p>
      </div> -->
    </div>
  </v-container>
</template>

<script>
//import axios from "axios";
import request from 'request';
import * as cheerio from 'cheerio';
export default {
  name: 'calendar',
  data() {
    return {
      calendar: [],
      isLoading: false
    }
  },
  created() {
    //this.fetchUrl();
    //const $ = await this.fetchHTML("https://www.fsk.nu/Event/Month")
    // Print the full HTML
    //console.log(`Site HTML: ${$.html()}\n\n`)

    // Print some specific page content
    //console.log(`First h1 tag: ${$('.fullCalendar').text()}`)
    this.fetchLagetCalendar()
  },
  methods: {
    // async fetchHTML(url) {
    //   const { data } = await axios.get(url)
    //   return cheerio.load(data)
    // },
    fetchLagetCalendar() {
      this.isLoading = true

      // request('https://www.fsk.nu/Event/Month', (error, response, html) => {
      //   if(!error && response.statusCode == 200){
      //     const $ = cheerio.load(html)
      //     $('.fullCalendar').each((i,el) => {
      //       let date = $(el).find('.fullCalendar__date').text().replace(/\r?\n|\r/g, " ");
      //       let dateCleaned = date.replace(/ /g,'');

      //       const title = $(el).children().first().text()

      //       // let time = $(el).find('.fullCalendar__time').text().replace(/\r?\n|\r/g, " ");
      //       // let timeCleaned = time.replace(/ /g,'');

      //       // let text = $(el).find('.fullCalendar__text').text().replace(/\r?\n|\r/g, " ");
      //       // let textCleaned = text.replace(/ /g,'');

      //       let fullText = $(el).find('.fullCalendar__list').text().replace(/\r?\n|\r/g, " ");
      //       let fullTextCleaned = fullText.replace(/\s\s+/g, ' ');

      //       // let sport = $(el).find('.fullCalendar__midText').text().replace(/\r?\n|\r/g, " ");
      //       // let sportCleaned = sport.replace(/ /g,'');
            
      //       this.calendar.push({
      //         dateCleaned, fullTextCleaned
      //       })
      //       console.log(title)
      //       //console.log(fullTextedSorted)
      //       //console.log(this.calendar)
      //     })
      //   }
      // })

      request('https://www.fsk.nu/Event/Month', (error, response, html) => {
        if(!error && response.statusCode == 200){
          this.isLoading = false
          const $ = cheerio.load(html)
          $('.fullCalendar__day').each((index,element) => {
          //   if($(element).find('.fullCalendar__text').children('i').attr('class') === 'fullCalendar__icon--red icon-calendar-empty'){

          //     let date = $(element).find('.fullCalendar__date').text().replace(/\r?\n|\r/g, " ").replace(/\s\s+/g, ' ')
          //   let info = $(element).find('.fullCalendar__text').text().replace(/\r?\n|\r/g, " ").replace(/\s\s+/g, ' ')
          //  const result = date.replace(/(\d{2})/g, '$1 ').replace(/(^\s+|\s+$)/,'')
          //   this.calendar[index] = { result, info }
          //   }
            

            //let date = $(element).find('.fullCalendar__date').text().replace(/\r?\n|\r/g, " ").replace(/\s\s+/g, ' ')
            let weekDay = $(element).find('.fullCalendar__date').children().remove().end().text().replace(/\r?\n|\r/g, " ").trim()
            let weekNumber = $(element).children('span').text()
            let test = $(element).find('.fullCalendar__date').children('span').first().text()
            let dayNumber = $(element).find('.float--right').text()

            
          
           //let result = date.replace(/(\d{1})/g, '$1 ').replace(/(\d{2})/g, '$1 ').replace(/(^\s+|\s+$)/,'')
            //let time = $(element).find('.fullCalendar__time').text().replace(/\r?\n|\r/g, " ").replace(/\s\s+/g, ' ')
            //let info = $(element).find('.fullCalendar__text').text().replace(/\r?\n|\r/g, " ").replace(/\s\s+/g, ' ')
            let list = $(element).find('.fullCalendar__itemInner').text().replace(/\r?\n|\r/g, " ").replace(/\s\s+/g, ' ').trim()
            this.calendar.push({ weekNumber, dayNumber, weekDay, list, test })

            //this.calendar.push(date)

            // const result = this.calendar.filter(checkAdult)
            // function checkAdult(age) {
            //   return age !== 'Träning';
            // }

             //console.log(this.calendar)
         
            //let dateCleaned = date.replace(/ /g,'');

            //const title = $(el).children().first().text()

            // let time = $(el).find('.fullCalendar__time').text().replace(/\r?\n|\r/g, " ");
            // let timeCleaned = time.replace(/ /g,'');

            // let text = $(el).find('.fullCalendar__text').text().replace(/\r?\n|\r/g, " ");
            // let textCleaned = text.replace(/ /g,'');

            //let fullText = $(el).find('.fullCalendar__list').text().replace(/\r?\n|\r/g, " ");
            //let fullTextCleaned = fullText.replace(/\s\s+/g, ' ');

            // let sport = $(el).find('.fullCalendar__midText').text().replace(/\r?\n|\r/g, " ");
            // let sportCleaned = sport.replace(/ /g,'');
            
            // this.calendar.push({
            //   dateCleaned, fullTextCleaned
            // })
            //console.log(title)
            //console.log(fullTextedSorted)
            //console.log(this.calendar)
          })
          console.log(this.calendar)
        }
      })
    }

    

    // fetchUrl() {
    //   axios.get("https://www.fsk.nu/Event/Month").then((response) => {
    //     const $ = cheerio.load(response.data)
    //     const span = $(".fullCalendar")
    //     data.push(span)
    //     console.log(response);
    //   });
    // },
  },
}
</script>

<style>

</style>