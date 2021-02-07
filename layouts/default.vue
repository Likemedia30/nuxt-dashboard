<template>
  <v-app id="root">
    <NavComponent></NavComponent>
      <nuxt />
  </v-app>
</template>


<script>
import NavComponent from '@/components/navs/navbar';
export default {
  name: "default-layout",
  components: {
    NavComponent
  }
}
</script>
