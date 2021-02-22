<template>
  <v-app id="root">
    <NavComponent></NavComponent>
      <nuxt />
      <Footer />
  </v-app>
</template>


<script>
import NavComponent from '@/components/navs/navbar';
import Footer from '@/components/navs/Footer';
export default {
  name: "default-layout",
  components: {
    NavComponent,
    Footer
  }
}
</script>
