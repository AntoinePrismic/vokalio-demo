<template>
  <header class="site-header"> 

    <nav>
      <ul>
        <li v-for="menuLink in menuLinks" :key="menuLink.id">
          <prismic-link :field="menuLink.link">{{ $prismic.richTextAsPlain(menuLink.label) }}</prismic-link>
        </li>
      </ul>
    </nav>
    <nuxt-link to="/" class="logo"></nuxt-link>
  </header>
</template>

<script>
export default {
  props: ['menuLinks'],
  name: 'header-prismic',
}
</script>

<style lang="sass">
.site-header
  height: 74px
  padding: 0
  color: #484d52
  font-weight: 700
  a
    color: #484d52
    font-weight: 700
  nav a:hover
    color: #72767B

.homepage .site-header
  color: #ffffff
  a
    color: #ffffff
  nav a:hover
    color: #c8c9cb

.site-header
  .logo
    display: inline-block
    font-weight: 900
    text-align: center
    background-color: transparent
    background-image: url(https://www.vokal.io/images/logo-white.svg)
    background-position: top right
    background-repeat: no-repeat
    background-size: 100%
    height: 74px
    overflow: hidden
    width: 160px
    float: right
  nav
    float: left
    margin-top: 20px
    ul
      margin: 0
      padding-left: 0
    li
      display: inline-block
      margin-left: 40px
      font-size: 16px
      font-weight: 700
      a
        position: relative
        font-weight: 900
        text-transform: uppercase

@media (max-width: 1060px)
  .site-header
    padding-left: 20px
    padding-right: 20px

@media (max-width: 767px)
  .site-header
    height: auto

  .homepage .site-header
    position: absolute
    left: 0
    right: 0

  .site-header
    .logo
      display: block
      text-align: center
      background-color: transparent
      background-image: url(https://www.vokal.io/images/logo-white.svg)
      background-position: top right
      background-repeat: no-repeat
      background-size: 100%
      height: 74px
      overflow: hidden
      width: 160px
    nav
      float: none
      text-align: center
      li
        display: inline-block
        margin-left: 10px
        margin-right: 10px
</style>


