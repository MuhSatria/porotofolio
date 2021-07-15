<template>
  <v-app dark>
    <Nuxt />
    <Loading />
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      title: 'Vuetify.js'
    }
  },
  // mounted() {
  //   this.$nextTick(() => {
  //     this.$nuxt.$loading.start()
  //     setTimeout(() => this.$nuxt.$loading.finish(), 2000)
  //   })
  // }
}
</script>
