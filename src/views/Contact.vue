<template lang="pug">
  #contact
    h1 Contact us

    div
      h3 info@info.com 
      h3 (213) 123-4567
</template>

<style lang="sass" scoped>
  #contact
    display: flex
    justify-content: center
    align-items: center
    flex-direction: column
    min-height: calc(100vh - 80px)

  h3
    font-weight: 200
    opacity: 0.7
    display: inline-block
    margin: 0 10px
</style>