<template>
  <section class='partners_logos content-section'>
    <prismic-rich-text :field="slice.primary.partners_logos_title"/>
    <div class="partners_logos">
      <div v-for="item in slice.items" :key="item.id" class="partners_logos-item">
        <prismic-image :field="item.partner_logo"/>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  props: ['slice'],
  name: 'partners_logos'
}
</script>

<style lang="sass" scoped>
.partners_logos
  display: -webkit-box
  // OLD - iOS 6-, Safari 3.1-6, BB7
  display: -ms-flexbox
  // TWEENER - IE 10
  display: -webkit-flex
  // NEW - Safari 6.1+. iOS 7.1+, BB10
  display: flex
  -webkit-flex-wrap: wrap
  flex-wrap: wrap
  -webkit-justify-content: center
  justify-content: center
  width: 100%

.partners_logos-item
  -webkit-box-flex: 1 1 16%
  -moz-box-flex: 1 1 16%
  -webkit-flex: 1 1 16%
  -ms-flex: 1 1 16%
  flex: 1 1 16%



@media (max-width: 767px)
  .content-section
    margin-bottom: 2rem
  .gallery-item
    -webkit-box-flex: 100%
    -moz-box-flex: 100%
    -webkit-flex: 100%
    -ms-flex: 100%
    flex: 100%
</style>
