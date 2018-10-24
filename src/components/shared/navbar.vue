<template lang="pug">
  .navbar
    .navbar--start
      router-link(to='/') Home
      router-link(to='/') About Us
      router-link(to='/contact') Contact Us
    .navbar--end
      button.btn.btn--green Demo
</template>

<script>
export default {
    name: 'navbar',
}
</script>

<style lang="sass" scoped>
.navbar
  position: sticky
  height: 72px
  width: 100%
  display: flex
  background: rgba(0,0,0,0)
  padding: 10px
  justify-content: center
  align-items: center
  // grid-area: navbar
  a
    height: 100%
    width: 100%
    font-size: 24px
    color: #fff
    text-decoration: none
    &:hover
      border-top: 2px solid #fff
    &:active
      border-top: 2px solid #fff
  &--start
    a
      padding: 20px
  &--end
    margin-left: auto
    .btn
      outline:none
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

