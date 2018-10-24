<template lang="pug">
  .footy
    .footy--elements
      button.btn.btn--green(to='/contat') Contact
      button.btn.btn--green(to='/contat') News Feed
      button.btn.btn--green(to='/contat') Contact
      button.btn.btn--green(to='/contat') News Feed
</template>

<script>
export default {
    name: 'footy',
}
</script>

<style lang="sass" scoped>
.footy
  grid-area: footer
  padding-top: 20px
  height: 70px
  left: 0
  bottom: 0
  width: 100%
  background: #009FFF
  background: -webkit-linear-gradient(to right, #ec2F4B, #009FFF)
  background: linear-gradient(to right, #ec2F4B, #009FFF)
  color: white
  text-align: center
  &--elements
    display: grid
    grid-template-columns: 1fr 1fr 1fr 1fr
    justify-items: center
    .btn
      outline:none
      text-decoration: none
      height: 40px
      text-align: center
      width: 130px
      border-radius: 40px
      background: #fff
      border: 2px solid #1ECD97
      color: #1ECD97
      letter-spacing: 1px
      text-shadow: 0
      &--green
        background: transparent
        border: 2px solid #1ECD97
        &:hover
          color: #fff
          background: #1ECD97
      &--shadow
        box-shadow: 0 2px 10px rgba(27, 21, 150, 0.67)
</style>

