<template>
  <section class="homepage">
    <!-- Vue tag to add header component -->
    <header-prismic :menuLinks="menu.data.menu_links"/>
    <!-- Button to edit document in dashboard -->
    <prismic-edit-button :documentId="document.id"/>
    <!-- Banner component -->
    <homepage-banner
      v-if="document.data.homepage_banner.length"
      :banner="document.data.homepage_banner[0]"
    />
    <!-- Slices block component -->
    <slices-block
      :slices="document.data.page_content"
    />
  </section>
</template>

<script>
import Prismic from "prismic-javascript"
import PrismicConfig from "~/prismic.config.js"
// Imports for all components
import HeaderPrismic from '~/components/HeaderPrismic.vue'
import HomepageBanner from '~/components/HomepageBanner.vue'
import SlicesBlock from '~/components/SlicesBlock.vue'

export default {
  name: 'Home',
  components: {
    HeaderPrismic,
    HomepageBanner,
    SlicesBlock,
  },
  head () {
    return {
      title: this.document.data.homepage_title,
    }
  },
  async asyncData({context, error, req}) {
    try{
      // Fetching the API object
      const api = await Prismic.getApi(PrismicConfig.apiEndpoint, {req})

      const document = await api.getSingle('homepage')
      const menu = await api.getSingle('menu')

      // Load the edit button
      if (process.client) window.prismic.setupEditButton()

      return {
        document,
        menu
      }
    } catch (e) {
      error({ statusCode: 404, message: 'Page not found' })
    }
  },
}
</script>
