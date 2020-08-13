<template>
  <div class="main">
    <slot/>
  </div>
</template>

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
</style>
