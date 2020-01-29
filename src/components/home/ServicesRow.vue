<template>
  <v-row 
    no-gutters
    align="center"   
    :class="{'pa-12': $vuetify.breakpoint.mdAndUp}"
    class = "grey lighten-3 row-height"
  >
    <v-col 
        v-for="(item,i) in servicesCarouselItems"
        :key="i"
        cols="4"
        class="d-none d-md-block"
    >
      <v-card 
        flat
        tile
        color="#EDEDED"
        class="text-center px-4"
      >
        <v-img
          height="250"
          :src="item.src"
        ></v-img>   

        <v-card-title class="justify-center">{{item.name}}</v-card-title>

        <v-card-text class="pb-0">
          <div>{{item.text}}</div>
        </v-card-text>
        
      </v-card>
    </v-col>

    <v-col
      no-gutters
      align="center"
      justify="center"
      style=""
      class = "d-xs-flex d-md-none"
    >

      <v-carousel 
        @change="currentTitle = servicesCarouselItems[$event].name, currentText = servicesCarouselItems[$event].text"
        height= "50vh"
        transition="scroll-x-transition"
        reverse-transition="scroll-x-reverse-transition"
        cycle
      >
        <v-carousel-item
          v-for="(item,i) in servicesCarouselItems"
          :key="i"
          :src="item.src"
        >
        </v-carousel-item>
      </v-carousel>

      <v-card 
        flat
        tile
        color="#EDEDED"
        class="text-center pa-5"
      >
        <v-card-title class="justify-center">{{currentTitle}}</v-card-title>
        <v-card-text class="">
          <div>{{currentText}}</div>
        </v-card-text>
      </v-card>

    </v-col>
  </v-row>
</template>

<script>
export default {
  data: () => ({
      currentTitle: '',
      currentText: '',
      servicesCarouselItems: [
        {
          name: "Kitchens",
          src: require('../../assets/t4c.jpeg'),
          text: "Small plates, salads & sandwiches an inteimate setting with 12 indoor seats plus patio seating."
        },
        {
          name: "Bathrooms",
          src: require('../../assets/t5c.jpeg'),
          text: "Small plates, salads & sandwiches an inteimate setting with 12 indoor seats plus patio seating."
        },
        {
          name: "Floors",
          src: require('../../assets/k4c.jpeg'),
          text: "Small plates, salads & sandwiches an inteimate setting with 12 indoor seats plus patio seating."
        }
      ],
  })
}
</script>

<style>

</style>