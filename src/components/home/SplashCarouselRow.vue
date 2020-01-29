<template>
<v-row no-gutters>
  <v-carousel
    height= "80vh"
    transition="scroll-x-transition"
    reverse-transition="scroll-x-reverse-transition"
    cycle
    show-arrows="false"
    prev-icon=""
    next-icon=""
  >
    <v-carousel-item
      v-for="(item,i) in splashCarouselItems"
      :key="i"
      :src="item.src"
      gradient="to top right, rgba(0,0,0,.5), rgba(0,0,0,.5)"
    >
      <v-row 
        justify="center" 
        align="center" 
        style="min-height: 80vh;"
      >
        <v-col cols-12>
          <h1 class="white--text display-1 font-weight-black d-xs-flex  d-sm-none justify-center">{{ company_name }}</h1>
          <h1 class="white--text display-3 font-weight-black d-none d-sm-flex  d-md-none justify-center">{{ company_name }}</h1>
          <h1 class="white--text display-4 font-weight-black d-none d-md-flex justify-center">{{ company_name }}</h1>
          <p class="white--text subtitle-2 font-weight-black d-xs-flex d-sm-none justify-center" style= "padding-top: -10px;" >{{ company_motto }}</p>
          <p class="white--text title font-weight-black d-none d-sm-flex justify-center" style= "padding-top: -10px;" >{{ company_motto }}</p>
        </v-col>
      </v-row>
    </v-carousel-item>
  </v-carousel>
</v-row>
</template>

<script>
export default {
  props: ['company_name', 'company_motto'],
  data: () => ({
    splashCarouselItems: [
      {
        src: require('../../assets/carousel_items/t1.jpg'),
      },
      {
        src: require('../../assets/carousel_items/t2.jpg'),
      },
      {
        src: require('../../assets/carousel_items/t6.jpg'),
      }
    ]
  })
}
</script>

<style>

</style>