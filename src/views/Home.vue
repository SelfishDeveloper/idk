<template lang="pug">
  .home
    header.header
      .header-head
        .container
          navbar
      .header-body
        .container
          .content
            .content__first
              h1.header--title
                | Start using our product today
              p.header--text
                | Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis sit amet..
              router-link.btn(to='/') Learn more
            .content__second
              img(src="@/assets/img/5.png")
      .header-footer
    section.section.about
      .about--element
        img(src="@/assets/icons/clipboard.svg")
        p
          | Overview
        p
          | Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis sit amet..
      .about--element
        img(src="@/assets/icons/target.svg")
        p
          | Audience
        p
          | Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis sit amet..
      .about--element
        img(src="@/assets/icons/skills.svg")
        p
          | Competitors
        p
          | Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis sit amet..
    section.section.clients
      .clients--info
        .clients--info--box
          p Dude
        .clients--info--box
          p Clients
        .clients--info--box
          p 450+
    
    //- section.section.slider.has-text-centered
    //-   .slider--entry
    //-     h1.section--title
    //-       | Workspaces
    //-     p.section--text
    //-       | We provide high-end solutions for our customers
    //-   input.slider--radio(type="radio" name="slider" id="slide-1")
    //-   input.slider--radio(type="radio" name="slider" id="slide-2")
    //-   input.slider--radio(type="radio" name="slider" id="slide-3" checked)
    //-   input.slider--radio(type="radio" name="slider" id="slide-4")
    //-   input.slider--radio(type="radio" name="slider" id="slide-5")
    //-   .slider--holder
    //-     label.slider--item.slider--item--1.card(for="slide-1")
    //-       img(src="@/assets/img/1.jpeg")
    //-     label.slider--item.slider--item--2.card(for="slide-2")
    //-       img(src="@/assets/img/1.jpeg")
    //-     label.slider--item.slider--item--3.card(for="slide-3")
    //-       img(src="@/assets/img/1.jpeg")
    //-     label.slider--item.slider--item--4.card(for="slide-4")
    //-       img(src="@/assets/img/1.jpeg")
    //-     label.slider--item.slider--item--5.card(for="slide-5")
    //-       img(src="@/assets/img/1.jpeg")
    //-   .bullets
    //-     label.bullets--item.bullets--item--1(for="slide-1")
    //-     label.bullets--item.bullets--item--2(for="slide-2")
    //-     label.bullets--item.bullets--item--3(for="slide-3")
    //-     label.bullets--item.bullets--item--4(for="slide-4")
    //-     label.bullets---item.bullets--item--5(for="slide-5")
    slider
    footy
</template>

<script>
import navbar from "@/components/shared/navbar"
import footy from "@/components/shared/footer"
import slider from "@/components/shared/slider/slider"
export default {
  name: 'home',
  components: {
    navbar,
    slider,
    footy
  },
  data() {
    return {
    }
  },
  methods: {

  },
};
</script>

<style lang="sass" scoped>
@import "@/styles/utilities/mixins.sass"

$start: 1
$end: 5

.container
  @include container
.home
  display: grid
  grid-template-areas: "navbar navbar navbar" "header header header" "about about about" "clients clients clients" "images images images" "footer footer footer"
  .header
    grid-area: header
    height: 100vh
    background-image: url('../assets/bg.jpeg')
    background-size: cover
    &--title
      font-size: 35px
      padding-bottom: 15px
    &--text
      font-size: 16px
    &-head
      width: 100%
    &-body
      width: 100%
      margin-top: 60px
      .content
        display: grid
        grid-template-columns: 1fr 1fr
        justify-items: center
        padding-top: 90px
        grid-gap: 50px
        color: #fff
  .about
    display: grid
    grid-area: about
    grid-template-columns: 1fr 1fr 1fr
    background: #009FFF
    background: -webkit-linear-gradient(to right, #ec2F4B, #009FFF)
    background: linear-gradient(to right, #ec2F4B, #009FFF)
    padding-bottom: 40px
    justify-items: center
    grid-gap: 20px
    &--element
      height: 331px
      background-color: #ffffff
      padding: 40px
      border-radius: 6px
      box-shadow: 5px 10px 30px rgba(41, 26, 204, 0.12)
      img
        margin-bottom: 10px
      p
        margin-bottom: 10px
      &:hover
        background-color: #2b1ecd
        color: #fff
        box-shadow: 5px 10px 30px rgba(41, 26, 204, 0.12)
      .btn
        color: #3b43d9
        margin-top: 25px
        padding: 5px
        border: 1px solid #3b43d9
        border-radius: 2px
        text-decoration: none
        background-color: #fff
        border-color: #3b43d9
  .clients
    display: grid
    grid-area: clients
    background: #009FFF
    background: -webkit-linear-gradient(to right, #ec2F4B, #009FFF)
    background: linear-gradient(to right, #ec2F4B, #009FFF)
    &--info
      height: 92px
      display: grid
      grid-template-columns: 1fr 1fr 1fr
      border: 3px solid #fff
      box-shadow: 5px 10px 30px rgba(41, 26, 204, 0.12)
      &--box
        color: #fff
        justify-self: center
        align-self: center
  @media (min-width: 1200px)
    .about
      &--element
        width: 319px
  .slider
    grid-area: images
    // .bullets
    //   &--item 
    //     @include default-transition()

    //     @for $bullet from 1 through 5 
    //       &--#{$bullet}
    //         #slide-#{$bullet}:checked ~ .bullets
    //           background: #fff
    // &--holder
    //   position: relative
    //   max-width: 600px
    //   // display: grid
    //   // grid-template-columns: repeat(5, 1fr)
    //   justify-content: center
    //   margin: 0 auto
    //   .card
    //     border-radius: 8px
    //     background: #fff
    //     box-shadow: 0 5px 20px 0 rgba(0,0,0,0.05), 0 2px 4px 0 rgba(0,0,0,0.10)
    // &--item
    //   @include default-transition(all)
    //   @for $slide from $start through $end
    //     &--#{$slide}
    //       @for $i from 1 through 5 
    //         @if $i <= $slide - 3 
    //           #slide-#{$i}:checked ~ .slider--holder &
    //             z-index: -1
    //             opacity: 0
    //             transform: translateX(210px) scale(0.65)

    //         @if $i == $slide - 2
    //           #slide-#{$i}:checked ~ .slider--holder & 
    //             z-index: 0

    //             transform: translateX(210px) scale(0.65)

    //             @media (max-width: 900px)
    //               transform: translateX(170px) scale(0.65)
                

    //             @media (max-width: 768px) 
    //               opacity: 0
            
    //         @if $i == $slide - 1 
    //           #slide-#{$i}:checked ~ .slider--holder & 
    //             z-index: 1

    //             transform: translateX(100px) scale(0.85)

    //             @media (max-width: 768px) 
    //               opacity: 0.6

    //         @if $i == $slide 
    //           #slide-#{$i}:checked ~ .slider--holder &
    //             position: relative
    //             z-index: 2
    //             transform: translate(0) scale(1)

    //         @if $i == $slide + 1 
    //           #slide-#{$i}:checked ~ .slider--holder &
    //             z-index: 1
    //             transform: translateX(-100px) scale(0.85)
    //             @media (max-width: 768px) 
    //               opacity: 0.6

    //         @if $i == $slide + 2
    //           #slide-#{$i}:checked ~ .slider--holder & 
    //             z-index: 0

    //             transform: translateX(-210px) scale(0.65)

    //             @media (max-width: 900px)
    //               transform: translateX(-170px) scale(0.65)

    //             @media (max-width: 768px)
    //               opacity: 0

    //         @if $i >= $slide + 3
    //           #slide-#{$i}:checked ~ .slider--holder &
    //             z-index: -1

    //             opacity: 0

    //             transform: translateX(-210px) scale(0.65)
</style>
