<template>
  <div class="home">

    <!-- Splash carousel row -->
    <SplashCarouselRow id="Home" :company_name="company_name" :company_motto="company_motto"/>

    <!-- Contact row  -->
    <ContactRow id="About" :about="about" :contact="contact"/>

    <!-- Services row -->
    <ServicesRow id="Services"/>

    <!-- Quotes row -->
    <QuotesRow/>

    <!-- Call to action row -->
    <CallToActionRow id="Contact" :contact="contact"/>

  </div>
</template>

<script>
// @ is an alias to /src
import ContactRow from '@/components/home/ContactRow.vue'
import ServicesRow from '@/components/home/ServicesRow.vue'
import QuotesRow from '@/components/home/QuotesRow.vue'
import SplashCarouselRow from'@/components/home/SplashCarouselRow.vue'
import CallToActionRow from'@/components/home/CallToActionRow.vue'

export default {
  name: 'home',
  components: {
    ContactRow,
    ServicesRow,
    QuotesRow,
    SplashCarouselRow,
    CallToActionRow
  },

  data: () => ({
    company_name: "Example Company",
    company_motto: "No job too big or small",
    contact: {
      phone: "070-1231-4567",
      areas: "We serve London, Croydon,\n Watford, Chelmsford and Dartford",
      email: "\nexample@example.com",
      hours: "Monday: 9AM – 5PM \n Tuesday: 10AM – 6PM\nWednesday: 9AM – 5PM\nThursday: 10AM – 6PM\nFriday: 10AM – 6PM\nClosed on Statutory Holidays"
    },
    about: {
      title: "EXAMPLE COMPANY SPECIALIZES IN QUALITY RENOVATIONS INVOLVING PAINTING AND TILING",
      text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.",
    }
  })

}
</script>

<style>
 
.row-height{
  min-height: 500px;
}

.xs-text{
  color: white;
  font-size: 35px;
}

.sm-text{
  color: white;
  font-size: 55px;
}

.md-text{
  color: white;
  font-size: 75px;
}

.lg-text{
  color: white;
  font-size: 100px;
  padding: 0;
  margin: 0;
}

 </style>