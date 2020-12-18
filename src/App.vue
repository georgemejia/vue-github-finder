<template>
  <div>
    <search-bar v-on:inputValue="getUser($event)" />

    <div v-if="!username">
      <user-default />
    </div>

    <div v-else>
      <github-user :user="user" />
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
  },

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
  padding-top: 50px;
  font-family: sans-serif;
  background-color: #151515;
}
</style>