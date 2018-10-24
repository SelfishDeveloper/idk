<template lang="pug">
  .sliderVue
    section.section.slider
      .section__entry.section__entry--center
        h1.section__title.heading-2.heading-2--black Workspaces
        p.section__text.text.text--light-black We provide high-end solutions for our customers
      input#slide-1.slider__radio(type='radio', name='slider')
      input#slide-2.slider__radio(type='radio', name='slider')
      input#slide-3.slider__radio(type='radio', name='slider', checked='')
      input#slide-4.slider__radio(type='radio', name='slider')
      input#slide-5.slider__radio(type='radio', name='slider')
      .slider__holder
        label.slider__item.slider__item--1.card(for='slide-1')
          .slider__item-content
            img(src='@/assets/img/1.jpeg', alt='')
        label.slider__item.slider__item--2.card(for='slide-2')
          .slider__item-content
            img(src='@/assets/img/2.jpeg', alt='')
        label.slider__item.slider__item--3.card(for='slide-3')
          .slider__item-content
            img(src='@/assets/img/7.jpeg', alt='')
        label.slider__item.slider__item--4.card(for='slide-4')
          .slider__item-content
            img(src='@/assets/img/4.jpeg', alt='')
        label.slider__item.slider__item--5.card(for='slide-5')
          .slider__item-content
            img(src='@/assets/img/5.jpeg', alt='')

</template>


<script>
export default {
    name: "sliderVue"
}
</script>

<style lang="scss" scoped>
@import "styles.scss";

.sliderVue {
  grid-area: images;
  background: #009FFF;
  background: -webkit-linear-gradient(to right, #ec2F4B, #009FFF);
  background: linear-gradient(to right, #ec2F4B, #009FFF);
}


</style>


