<template>
  <div>
    <v-app-bar 
      app 
      elevation = 8
      class="d-none d-sm-block"
    >
      <v-spacer></v-spacer>
      <v-btn text small href="#Home" >Home</v-btn>
      <v-btn text small href="#Contact" >Contact</v-btn>
      <div>
        <v-img 
        :src="require('@/assets/l-logo.png')"
        contain
        height="70"
        width="70"
        ></v-img>
      </div>
      <v-btn text small href="#Services">Services</v-btn>
      <v-btn text small href="#About">About</v-btn>
      <v-spacer></v-spacer>
    </v-app-bar>

    <v-app-bar 
      app 
      elevation = 8
      class="d-xs-block d-sm-none"
    >

      <v-btn text icon color=black class="" >
          <v-icon>mdi-menu</v-icon>
      </v-btn> 
      <div>
        <v-img 
        :src="require('@/assets/l-logo.png')"
        contain
        height="60"
        width="60"
        class="py-12"
        ></v-img>
      </div>


      <v-spacer></v-spacer>

      <v-btn small outlined color="error" >Free Quote</v-btn>

    </v-app-bar>
  </div>
</template>

<script>
export default {
  name: "NavBar"
}
</script>

<style scoped>


</style>