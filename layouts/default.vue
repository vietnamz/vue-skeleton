<template>
  <v-app>
   <TheNavBar/>
    <nuxt/>
  </v-app>
</template>

<script>
    import TheNavBar from "../components/TheNavBar";
    export default {
        name: "default",
        components: {TheNavBar}
    }
</script>

<style scoped>

</style>
