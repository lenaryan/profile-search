<template>
  <section id="app">
    <SearchBox />
    <ul class="profiles">
      <ProfileCard v-for="(profile, id) in profiles" v-bind="profile" :key="id" />
    </ul>
  </section>
</template>

<script>
import SearchBox from './components/SearchBox.vue'
import ProfileCard from './components/ProfileCard.vue'

export default {
  name: 'App',
  components: {
    SearchBox,
    ProfileCard
  },
  data() {
    return {
      profiles: []
    }
  },
  mounted() {
    fetch('https://gist.githubusercontent.com/allaud/093aa499998b7843bb10b44ea6ea02dc/raw/c400744999bf4b308f67807729a6635ced0c8644/users.json')
      .then(response => response.json())
      .then(json => this.profiles = json)
      .then(() => console.log('profiles then', this.profiles))
  },
}
</script>

<style scoped>
#app {
  background-color: #fff;
  width: 95%;
  max-width: 564px;
  height: 643px;
  overflow-y: scroll;
  padding: 20px 12px 0;
}

.profiles {
  padding: 0;
  margin: 0;
  list-style: none; 
}
</style>


// TODO: 
// 1. Separate data to not hang up a browser
// 2. Finish moking up