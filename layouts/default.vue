<template>
  <div id="root">
    <NavComponent></NavComponent>
    <v-app>
      <nuxt />
    </v-app>
  </div>
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
