<template lang="pug">
  #nav
    router-link.logo( to="/" is="div" )

    .links( :class="{ hidden }" @click="hidden = true" )
      router-link( 
        v-for="link in links" 
        :to="link.path" 
        :key="link.path"
      ) {{ link.name }}

    button.hamburger( @click="hidden = !hidden" )
      .hamburger-symbol( v-if="hidden" )
        span
        span
        span

      .x-symbol( v-else )
        span
        span
</template>

<script>
export default {
  data () {
    return {
      hidden: true,
      links: [
        { path: '/', name: 'Home' },
        { path: '/about', name: 'About' },
        { path: '/contact', name: 'Contact' },
      ],
    }
  }
}
</script>

<style lang="sass" scoped>
  #nav
    display: flex
    justify-content: flex-end
    align-items: center
    height: 80px
    padding: 20px
    
  .logo 
    margin-right: auto
    width: 40px
    height: 40px
    background-color: red

  a
    margin-left: 20px
    font-size: 20px
    color: black
    text-decoration: none

    &:hover
      text-decoration: underline

  .hamburger
    background-color: transparent
    border: none
    outline: none
    width: 40px
    height: 40px
    position: relative
    align-items: center
    cursor: pointer
    z-index: 3
    display: none

    div
      width: 100%
      pointer-events: none

      span
        display: block
        width: 100%
        height: 5px
        background-color: black

    .hamburger-symbol
      span
        margin: 7px 0
      
    .x-symbol
      span
        position: absolute
        transform: rotate(45deg)

      span:first-child
        transform: rotate(-45deg)

  @media (max-width: 600px)
    .hamburger
      display: flex

    .links
      width: 100%
      height: 100vh
      position: fixed
      top: 0
      left: 0
      background-color: white
      z-index: 2
      display: flex
      flex-direction: column
      justify-content: center
      align-items: center
      pointer-events: none

      a
        margin: 10px 0
        font-size: 24px
        pointer-events: all

      &.hidden
        opacity: 0
</style>