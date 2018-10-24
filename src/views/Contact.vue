<template lang="pug">
  .contact
    header.header
      .header-head
        .container
          navbar
      .header-body
        .container
          form#contact-form.has-text-centered(@submit.prevent="checkForm")
            p Dear Company,
            p
              | My
              label(for="name") name
              |  is
              input#your-name(type="text" v-model="name" name="name"  placeholder="(your name here)")
              |  and
            p
              | my
              label(for="email") email address
              |  is
              input#email(type="email" name="email" v-model="email" placeholder="(your email address)")
              | and
            p
              | my
              label(for="phone") phone number
              |  is
              input#email(type="phone" name="phone" v-model="phone" placeholder="(your phone number)")
            p
              | I have a
              label(for="your-message") message
              |  for you,
            p
              textarea#your-message.expanding(v-model="message" name="message" placeholder="(your msg here)")
            span(v-model="symbolsLeft") 
              | {{symbolsLeft}} symbols left
            p
              button(type="submit")
                svg.send-icn(version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" width="100px" height="36px" viewbox="0 0 100 36" enable-background="new 0 0 100 36" xml:space="preserve")
                  path(d="M100,0L100,0 M23.8,7.1L100,0L40.9,36l-4.7-7.5L22,34.8l-4-11L0,30.5L16.4,8.7l5.4,15L23,7L23.8,7.1z M16.8,20.4l-1.5-4.3\
                  l-5.1,6.7L16.8,20.4z M34.4,25.4l-8.1-13.1L25,29.6L34.4,25.4z M35.2,13.2l8.1,13.1L70,9.9L35.2,13.2z")
                small send
    footy
</template>

<script>
import navbar from "@/components/shared/navbar"
import footy from "@/components/shared/footer"
import axios from "axios"
export default {
  name: 'about',
  components: {
    navbar,
    footy
  },
  data() {
    return {
      name: null,
      email: null,
      phone: '+994',
      message: null,
      symbolsLeft: 250
    }
  },
  methods: {
    checkForm(next) {
      !(this.name.length >= 3) ? alert('fuck') : (
         !(this.phone.length >= 11) ? alert('fuck') : (
           this.submitFinally()
         )
      )
      
    },
    submitFinally() {
      axios.post('http://localhost:3000/api/subscription', {
      name: this.name,
      email: this.email,
      phone: this.phone,
      message: this.message
    })
    .then(function (response) {
      alert(response.data);
    })
    .catch(function (error) {
      alert(error);
    });
    }
  },
  watch: {
    message() {
      this.symbolsLeft--
    }
  },
}
</script>


<style lang="sass" scoped>
@import "@/styles/utilities/mixins.sass"
.container
  @include container
.contact
  background: #009FFF
  background: -webkit-linear-gradient(to right, #ec2F4B, #009FFF)
  background: linear-gradient(to right, #ec2F4B, #009FFF)
  color: #fff
  .header
    height: 100vh
  &__form
    height: calc(100vh - 70px)
#contact-form
  max-width: 90%
  margin: 0 auto

label
  font-weight: 400
  cursor: pointer

textarea, input
  border: none
  outline: none
  border-radius: 0
  text-align: center
  background: none
  font-weight: 700
  font-family: 'Lato', georgia
  font-size: 25px
  color: #fff
  max-width: 90%
  padding: 1rem
  border: 2px dashed rgba(255, 255, 255, 0)
  box-sizing: border-box
  cursor: text

textarea
  text-align: left
  resize: none
  width: 90%
  border-color: rgba(255, 255, 255, 0)
  &:focus
    background-color: rgba(255, 255, 255, 0.2)
    border: 2px dashed rgba(255, 255, 255, 1)
    &:required:valid
      border: 2px solid rgba(255, 255, 255, 0)
      border-bottom: 2px solid rgba(255, 255, 255, 0.2)
  &:required:valid
    border-bottom: 2px solid rgba(255, 255, 255, 0.2)

input
  border-bottom: 2px dashed rgba(255, 255, 255, 0.5)
  &:required
    border-bottom: 2px dashed rgba(255, 255, 255, 0.5)

textarea:required
  border-bottom: 2px dashed rgba(255, 255, 255, 0.5)

input
  &:focus
    border-bottom: 2px dashed rgba(255, 255, 255, 1)
    background-color: rgba(255, 255, 255, 0.2)
  &:required
    &:valid
      border-bottom: 2px solid rgba(255, 255, 255, 0.2)
    &:invalid
      color: #fff



.expanding
  vertical-align: top

.send-icn
  fill: rgba(255, 255, 255, 1)
  &:hover
    fill: rgba(0, 0, 0, 1)
    cursor: pointer

button
  background: none
  border: none
  outline: none
  margin: 2vmax
  &:hover small
    opacity: 1

small
  display: block
  opacity: 0

.website
  opacity: 1
  font-size: 16px
  color: white
  position: relative
  text-align: center
  display: block
  margin-top: 7%
  a
    color: white
</style>

