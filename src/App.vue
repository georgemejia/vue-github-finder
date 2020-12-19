<template>
  <div>
    <h1 class="title">Vue GitHub Finder</h1>
    <search-bar v-on:inputValue="getUser($event)" />

    <div>
      <div v-if="!username">
        <user-default />
      </div> 
      <div v-else>
        <github-user :user="user" />
      </div>
    </div>

  </div>
</template>

<script>
import axios from 'axios'
import UserDefault from './components/DefaultUser'
import GithubUser from './components/GithubUser'
import SearchBar from './components/SearchBar'

export default {
  components: {
    UserDefault,
    GithubUser,
    SearchBar
  },

  data() {
    return {
      user: {},
      username: '',
    }
  },

  methods: {
    getUser(value) {
      this.username = value

      if (this.username !== '') {
        axios.get(`https://api.github.com/users/${this.username}`, {
          headers: {
            'Authorization': 'bearer' + process.env.CLIENT_ID,
          }
        })
        .then((res) => this.user = res.data)
      }
    }
  }

}
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;700&display=swap");

* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}

body {
  font-family: sans-serif;
  background-color: #151515;
}
.title {
  color: #f0f0f0;
  font-size: 2.5rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 1px;
  background-color: #55d48a;
  padding: 1em;
  text-align: center;
}
</style>