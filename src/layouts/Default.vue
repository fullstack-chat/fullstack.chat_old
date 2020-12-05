<template>
  <div class="main">
    <Nav :isLogoHidden="hideLogo"/>
    <slot/>
    <div class="footer">
      <span class="copyright-and-docs">© {{new Date().getFullYear()}}&nbsp;•<a href="https://www.notion.so/fullstackchat/Docs-9c3f2a571b6a4801b26ced27eb45cf90" target="_blank">📙 Docs</a></span>
    </div>
  </div>
</template>

<script>
import Nav from '@/components/Nav.vue'

export default {
  components: {
    Nav
  },
  props: {
    hideLogo: Boolean
  }
}
</script>

<style>
body {
  font-family: 'Open Sans', sans-serif;
  margin:0;
  padding: 0px 0px 20px 0px;
  line-height: 1.5;
  background-color: #000F14 !important;
}

h1, h2 {
  font-family: 'Lato', monospace;
  color: white;
}

.layout {
  max-width: 760px;
  margin: 0 auto;
  padding-left: 20px;
  padding-right: 20px;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
  height: 80px;
}

.nav__link {
  margin-left: 20px;
}

.footer {
  display: flex;
  justify-content: center;
  align-content: center;
  padding-top: 20px;
}

.copyright-and-docs {
  color: white;
}

.copyright-and-docs a {
  margin-left: 5px;
}

</style>
