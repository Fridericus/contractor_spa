<template>
<v-row 
  no-gutters
  class = "py-5 white"
>
  <v-col>
    <v-row 
      v-for="(quote, i) in quotes"
      :key="i"
      no-gutters
      class = "py-4"
    >

      <v-col v-if="!isEven(i)" cols = 3>
      </v-col>

      <v-col cols = 9>

        <v-card
          elevation = 15 
          dark 
          tile 
          :color="quote.color"
          class="quote-card"
        >
          <v-row           
            align="center"
            style="height: 100%"
          >

            <v-col v-if="!isEven(i)" 
              cols=3 
              class="d-none d-md-block"
            >
              <v-list-item-avatar 
                size="77" 
                class="float-right"
              >
                  <v-img
                    class=""
                    :src="quote.src"
                  ></v-img>
              </v-list-item-avatar>
            </v-col>

            <v-col cols = 9>
              <div :class="{'quote-text-left': !isEven(i), 'quote-text-right': isEven(i)}">
                <p class = "headline font-italic font-weight-bold mb-0 d-none d-md-block">{{quote.quote}}</p>
                <p class = "font-italic font-weight-bold mb-0 d-xs-block d-md-none subtitle-2">"My living room walls have never looked this good - thanks babe!"</p>
                <p class = "font-weight-light d-none d-md-block">{{quote.name}}</p>                
                <p class = "body-2 font-weight-light d-xs-block d-md-none">{{quote.name}}</p>                
              </div>
            </v-col>

            <v-col v-if="isEven(i)" 
              cols=2 
              class="d-none d-md-block"
            >
              <v-list-item-avatar 
                size="77"
                class="float-left"
              >
                <v-img
                  class=""
                  :src="quote.src"
                ></v-img>
              </v-list-item-avatar>
            </v-col>

          </v-row>
        </v-card>
      </v-col>

      <v-col v-if="isEven(i)" cols = 3>
      </v-col>

    </v-row>
  </v-col>
</v-row>
</template>

<script>
export default {
  data: () => ({
    rowcCount: 0,
    quotes: [
      {
        name: "Jane Doe - Brixton, London",
        quote: '"My kitchen has never looked this good - highly reccomend!"',
        src: require('../../assets/quote_items/u2.jpg'),
        color: "primary"
      },
      {
        name: "Jon Doe - Grey Edge, Newcastle",
        quote: '"This time we went with Example. Twice as fast and twice the job!"',
        src: require('../../assets/quote_items/u1.jpg'),
        color: "#025CAF"
      },
      {
        name: "Mr Spencer - Grange Highschool, Liverpool",
        quote: '"Polished off all the biscuits in the staff room but otherwise flawless!"',
        src: require('../../assets/quote_items/u3.jpg'),
        color: "#054581"
      }
    ]
  }),
  methods: {
    isEven: (i) => {
      if ( i % 2 == 0) return true;
      else return false;
    }
  }
}

</script>

<style scoped>

.quote-card{
  height: 170px; 
  background: #054581;
}

.quote-text-left{
  text-align: left;
  padding-right: 60px;
}

.quote-text-right{
  text-align: right;
  padding-left: 60px;
}


</style>