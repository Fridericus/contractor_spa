<template>
  <v-row
    no-gutters 
    class="white pb-12" 
    justify="center"
  > 
    <v-col> 
      <v-row class="pa-6">
        <v-col>
          <v-divider></v-divider>
        </v-col>
      </v-row>
      <v-row>
        <v-col>
          <h1>CONTACT US TODAY FOR A FREE QUOTE</h1>
        </v-col>
      </v-row>

      <v-row justify="center">

        <v-col
          cols=9
          class="py-10 form-col-style"
        >
        
          <ContactForm/>

        </v-col>
        <v-col
          cols=3
          align-self="center"
          class="px-4"
        >
          <v-row 
            no-gutters
            justify="center"
            align="center"
          >
            <v-col class = "logo-col-style">
              <v-img src="../../assets/l-logo.png" 
                class="image-style"
              ></v-img>
            </v-col>
          </v-row>

          <v-row 
            style="min-height: 100px;"
          >
          <v-col class=" " >
            <p class="subtitle-2 font-weight-black mb-1">CONTACT US</p>
            <pre class="display-1 font-weight-bold mb-0">{{contact.phone}}</pre>
            <pre class="body-1">{{contact.areas}}</pre>
            <pre class="font-weight-bold ">{{contact.email}}</pre>
            <p class="body-1 font-weight-black mb-1"><br>Open Hours</p>
            <pre class="body-1 mb-0">{{contact.hours}}</pre>
          </v-col>

          </v-row>
        </v-col>
        
      </v-row>
    </v-col>
  </v-row>
</template>

<script>
import ContactForm from '@/components/home/ContactForm.vue'

export default {
  props: ['contact', 'company_name'],
  components: {
    ContactForm,
  },
  data: () => ({

  })
}

</script>

<style scoped>

  .form-col-style{
    max-width: 700px;
  }

  .logo-col-style{
    max-width: 400px;
    text-align: center;
  }

  .logo-col-style .image-style{
    max-width: 150px;
    margin-left: auto;
    margin-right: auto;
  }
</style>