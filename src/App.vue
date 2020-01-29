<template>
<div id="app">
  <v-app>
    <NavBar/>
    <div id="app-position" class="mx-auto elevation-10">
      <router-view/>
    </div>
  </v-app>
</div>
</template>

<script>
import NavBar from '@/components/NavBar.vue'
export default {
  components: {
    NavBar
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background: #fafafa;

}

#nav {
  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}

#app-position{
  width: 100vw; 
  max-width: 1920px;
  border-style: solid;
  border-width: 0px 1px 0px 1px;
  border-color: #c7c9cc;
}


</style>
