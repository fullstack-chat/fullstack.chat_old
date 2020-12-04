<template>
  <div class="container-wrapper">
    <div class="container">
      <div class="col-md-4" v-for="(p, index) in profiles" :key="index">
        <div class="profile-card">
          <div class="header">
            <div class="profile-img"><img class="img-fluid" :src="p.imageUrl" /></div>
            <div class="name">{{ p.name }}</div>
          </div>
          <div class="bio">
            {{ p.bio }}
          </div>
          <div class="links">
            <div class="link" v-for="(s, index) in p.links" :key="index">
              blah
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import profiles from '@/data/profiles.json'

export default {
  data() {
    return {
      profiles
    }
  }
}
</script>

<style scoped>
.profile-card {
  background-color: red;
  margin: 10px;
  padding: 5px;
  border-radius: 15px;
  display: flex;
  flex-direction: column;
}

.profile-img {
  max-height: 100px;
  max-width: 100px;
}

.bio {
  padding: 10px 20px;
}

.links {
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
}

.link {
  border-left: 1px solid blue;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>