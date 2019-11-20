<template>
  <section class='featured_products content-section'>
    <prismic-rich-text :field="slice.primary.featured_products_title"/>
    <div class="featured_products">
      <div v-for="item in slice.items" :key="item.id" class="featured_products-item">
        <prismic-image :field="item.partner_logo"/>
      </div>
    </div>
    <prismic-link class="call-to-action" :field="slice.primary.shop_cta_link">
      {{ slice.primary.shop_cta_label }}
    </prismic-link>
  </section>
</template>
<script>
export default {
  props: ['slice'],
  name: 'featured_products'
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
