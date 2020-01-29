<template>
   <!-- Contact and about row for medium and larger devices -->
    <v-row 
      no-gutters 
    >
      <!-- Contact details column -->
      <v-col 
        cols="12"
        md="5"
        class="white"
      >
        <v-row
          no-gutters
          align="center"   
          class="row-height"
        >

          <!-- Larger contact details column -->
          <v-col class="d-none d-md-block contact-style-med" >
            <p class="subtitle-2 font-weight-black mb-1">CONTACT US</p>
            <pre class="display-1 font-weight-bold mb-0">{{contact.phone}}</pre>
            <pre class="body-1">{{contact.areas}}</pre>
            <pre class="font-weight-bold ">{{contact.email}}</pre>
            <p class="body-1 font-weight-black mb-1"><br>Open Hours</p>
            <pre class="body-1 mb-0">{{contact.hours}}</pre>
          </v-col>
          <!-- Mobile contact details column -->
          <v-col class=" d-md-none pa-12 contact-style-mobile" >
            <p class="subtitle-2 font-weight-black mb-1">CONTACT US</p>
            <pre class="display-1 font-weight-bold mb-0">{{contact.phone}}</pre>
            <pre class="body-1">{{contact.areas}}</pre>
            <pre class="font-weight-bold ">{{contact.email}}</pre>
            <p class="body-1 font-weight-black mb-1"><br>Open Hours</p>
            <pre class="body-1 mb-0">{{contact.hours}}</pre>
          </v-col>

        </v-row>

      </v-col>

      <!-- About details column -->
      <v-col 
        cols="12" 
        md="7"
        style = "background: #054581;"
      >
        <v-row 
          no-gutters
          align="center"
          class="row-height"
        >

          <!-- Mobile about column -->
          <v-col class="d-md-none pa-12 mobile-style" >
            <h2 class="font-weight-block white--text mb-1">{{about.title}}</h2>
            <p class="subtitle-1 font-weight-light white--text mb-0">{{about.text}}</p>
          </v-col>

          <!-- Larger about column -->
          <v-col class="d-none d-md-block about-style-med" >
            <h2 class="font-weight-block white--text mb-1">{{about.title}}</h2>
            <p class="subtitle-1 font-weight-light white--text mb-0">{{about.text}}</p>
          </v-col>

        </v-row>

      </v-col>
    </v-row>

</template>

<script>
export default {
  props:['contact','about'],
  data: () => ({

  })
}
</script>

<style scoped>

.contact-style{

}

.contact-style-mobile{

}

.contact-style-med {
  text-align: right; 
  padding-left: 50px; 
  padding-right: 100px;
}

.about-style{

}

.about-style-med{
  text-align: left; 
  padding-left: 100px; 
  padding-right: 100px;
}

.mobile-style{
  text-align: center;
}

.med-style{

}

</style>