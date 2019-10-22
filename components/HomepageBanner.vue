<template>
    <section class="homepage-banner" :style="{ backgroundImage: 'linear-gradient(rgba(0, 0, 0, 0.4), rgba(0, 0, 0, 0.6)), url(' + banner.image.url + ')' }">
      <!-- Template for page title. -->
      <div class="banner-content container">
        <h1 class="banner-title">
          {{ $prismic.richTextAsPlain(banner.title) }}
        </h1>
        <!-- Template for page tagline. -->
        <h2 class="banner-tagline">{{ $prismic.richTextAsPlain(banner.tagline) }}</h2>
        <prismic-link class="banner-button" :field="banner.button_link">
          {{ $prismic.richTextAsPlain(banner.button_label) }}
        </prismic-link>
      </div>
    </section>
</template>

<script>
export default {
  props: ['banner'],
  name: 'homepage-banner',
}
</script>

<style lang="sass" scoped>
.homepage-banner
  margin: -70px 0 80px
  padding: 10em 0 8em
  background-position: center center
  background-size: cover

  line-height: 1.75
  text-align: center

.banner-content
  text-align: center

.banner-title, .banner-tagline
  font-family: 'Open Sans',sans-serif
  color: #ffffff
  width: 90%
  max-width: 100%
  margin: 0 auto 25px


.banner-title
  font-size: 44px
  font-weight: 900
  line-height: 70px

.banner-tagline
  max-width: 630px
  margin: 0 auto 42px
  font-size: 36px

.banner-button
  background: #ffffff
  border-radius: 7px
  color: #484D52
  font-size: 14px
  font-weight: 700
  padding: 15px 40px
  &:hover
    background: #c8c9cb

@media (max-width: 767px)
  .homepage-banner
    margin: 0 0 40px
    padding: 10em 0 6em
  .banner-title
    font-size: 50px
    line-height: 50px
</style>
