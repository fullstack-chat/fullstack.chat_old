<template>
  <div class="container-wrapper">
    <div class="container">
      <div class="col-md-4" v-for="(p, index) in profiles" :key="index">
        <div class="profile-card">
          <div class="profile-img">
            <img class="img-fluid" :src="p.imageUrl" />
          </div>
          <div class="name">{{ p.name.substring(0, 140) }}</div>
          <div class="bio">
            {{ p.bio }}
          </div>
          <div class="links">
            <div class="link" v-for="(key, index) in p.links" :key="index">
              <a :href="p.links[key]">
                {{ key }}
                <img :src="`/assets/images/socials/${key}.png`" />
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import profiles from '@/data/profiles.json'
import githubLogo from "super-tiny-icons/images/svg/github.svg";

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

.name {
  font-weight: bold;
  font-size: 1.1em;
  text-align: center;
}

.profile-img {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  padding: 10px;
  border-radius: 15px;
}

.profile-img img {
  max-height: 75px;
  max-width: 75px;
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
  width: 100%;
}

.link img {
  max-height: 40px;
  max-width: 40px;
}

.link:first-child {
  border-left: none !important
}
</style>