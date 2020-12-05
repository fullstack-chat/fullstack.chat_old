<template>
  <div class="container">
    <div class="row nav-row">
      <div class="nav-left">
        <g-link to="/" v-if="!isLogoHidden">
          <img src="/assets/images/logo-2.png" class="img-fluid nav-logo" />
        </g-link>
        <g-link to="/" v-if="!isLogoHidden">
          <span class="title">fullstack.chat</span>
        </g-link>
      </div>
      <div class="nav-right">
        <ul class="nav-links">
          <g-link to="/">Home</g-link><span class="bullet">•</span>
          <g-link to="/profiles">Profiles</g-link><span class="bullet">•</span>
          <a href="https://www.notion.so/fullstackchat/Docs-9c3f2a571b6a4801b26ced27eb45cf90" target="_blank">Docs</a>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    isLogoHidden: Boolean
  }
}
</script>

<style>
.nav-row {
  padding: 10px;
  display: flex;
}

.nav-left, .nav-right {
  flex: 1;
  display: flex;
  flex-direction: row;
  align-items: center;
}

.nav-right {
  display: flex;
  justify-content: flex-end;
  align-items: center;
}

.nav-right ul {
  margin: inherit;
}

.title {
  font-size: 28px;
  color: white;
  padding-left: 20px;
}

.nav-logo {
  max-width: 50px !important;
}

.nav-logo a {
  text-decoration: none !important;
}

.nav-left a:hover {
  text-decoration: none !important;
}

.nav-links a {
  color: white;
  text-decoration: none;
  font-size: 18px;
}

.nav-links a:hover {
  color: white;
  text-decoration: underline;
}

.bullet {
  color: white;
  padding: 0px 7px;
}
</style>