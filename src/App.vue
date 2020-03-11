<template lang="pug">
  #app
    Navigation
    router-view
    Footer
</template>

<script>
import Navigation from "@/components/Navigation"
import Footer from "@/components/Footer"

export default {
  components: {
    Navigation,
    Footer,
  },
}
</script>

<style lang="sass">
  @import url('https://fonts.googleapis.com/css?family=Open+Sans&display=swap')

  *
    margin: 0
    padding: 0
    box-sizing: border-box
    font-family: 'Open Sans', sans-serif
</style>