<template>
  <Layout>
    <div class="row justify-content-md-center">
      <div class="col-md-8">
        <!-- Learn how to use images here: https://gridsome.org/docs/images -->
        <g-image alt="fullstack.chat logo" src="/assets/images/logo-2.png" class="logo" />

        <h1>Welcome to fullstack.chat!</h1>
        <div class="text-component">
          We are a welcome and opening community of developers of all skillsets and experience levels. Read and agree to the rules below, then hop in and join the conversation!
        </div>
        <h2>Rules & Code of Conduct</h2>
        <div class="text-component" v-html="$page.rules.content"></div>
        
        <div class="footer" >

          <div class="form-check agree-to-rules-check" >
            <input type="checkbox" class="form-check-input" id="isUserAgreedToRulesCheckbox" v-model="isUserAgreedToRules">
            <label class="form-check-label" for="isUserAgreedToRulesCheckbox">I read and agree to the rules above</label>
          </div>
          <button type="button" class="btn btn-primary" :disabled="!isUserAgreedToRules" @click="goToDiscord">Join the Conversation!</button>
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
  max-width: 200px;
  margin: 20px auto;
  display: block;
}
h1, h2 {
  display: block;
  margin: 0 auto;
  text-align: center;
  padding: 15px 0px;
}
.text-component {
  padding: 15px;
  border: 1px solid #ddd;
  border-radius: 5px;
  background-color: rgba(255, 255, 255, .8);
  font-size: 18px;
  margin: 10px 0px;
}
.agree-to-rules-check {
  margin: 10px 0px;
}
</style>
