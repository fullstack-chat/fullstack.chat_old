<template>
  <Layout>
    <div class="container-wrapper" >
      <div class="container-fluid">
        <div class="row justify-content-center">
          <div class="col-md-2">
            <g-image alt="fullstack.chat logo" src="/assets/images/logo-2.png" class="logo-sm-screen img-fluid d-block d-lg-none" />
            <g-image alt="fullstack.chat logo" src="/assets/images/logo-2.png" class="logo img-fluid d-none d-lg-block" />
          </div>
          <div class="col-md-6 welcome-col">
            <div class="welcome-content">
              <h1>Welcome to fullstack.chat!</h1>
              <div class="welcome-text">
                We are a welcome and opening community of developers of all skillsets and experience levels. Scoll down to see what our community is all about!
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="container-fluid">
      <div class="row justify-content-md-center">
        <div class="col-md-6">
          <h2>Rules & Code of Conduct</h2>
          <div class="rules-container" v-html="$page.rules.content"></div>
          
          <div class="footer" >
            <div class="form-check agree-to-rules-check" >
              <input type="checkbox" class="form-check-input" id="isUserAgreedToRulesCheckbox" v-model="isUserAgreedToRules">
              <label class="form-check-label" for="isUserAgreedToRulesCheckbox">I read and agree to the rules above</label>
            </div>
            <button type="button" class="btn agree-to-rules-button" :disabled="!isUserAgreedToRules" @click="goToDiscord">Join the Conversation!</button>
          </div>
        </div>
      </div>
    </div>

  </Layout>
</template>

<page-query>
query {
  rules: document (path: "/src/docs/rules/") {
    title
    content
  }
}
</page-query>

<script>
export default {
  metaInfo: {
    title: 'fullstack.chat'
  },
  data: function () {
    return {
      isUserAgreedToRules: false
    }
  },
  methods: {
    goToDiscord: function () {
      window.location = "https://discord.gg/AptKHUS"
    }
  }
}
</script>

<style>
.logo {
  max-width: 250px;
  margin-left: auto;
  display: block;
}

.logo-sm-screen {
  max-width: 250px;
  align-content: right;
  /* margin: 20px auto; */
  margin: 0px auto;
  display: block;
}

.full-height-row {
  height: 100vh;
}

.container-wrapper {
  min-height: 100%;  /* Fallback for browsers do NOT support vh unit */
  min-height: 100vh; /* These two lines are counted as one :-)       */

  display: flex;
  align-items: center;
}

h1, h2 {
  display: block;
  margin: 0 auto;
  padding: 15px 0px;
  border-bottom: 2px solid #FF8500;
}

.welcome-col {
  display: flex;
  flex-direction: row;
}

.welcome-content {
  padding: 0px 20px;
  margin-top: auto;
  margin-bottom: auto;
}

.welcome-text {
  color: white;
  font-size: 22px;
}

.rules-container {
  color: white
}

.agree-to-rules-check {
  color: white;
  margin: 10px 0px;
}

.agree-to-rules-button {
  background-color: #00A8E8 !important;
  color: white !important;
}
</style>
