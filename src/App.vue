<template>
  <div>
    <h1 class="title">Vue GitHub Finder</h1>
    <p class="text">A simple webapp to search for your favorite GitHub users</p>
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
  background-color: #1a1a1a;
}
.title {
  color: #f0f0f0;
  font-size: 2.5rem;
  font-weight: 700;
  letter-spacing: 1px;
  text-align: center;
  margin-top: 50px;
  margin-bottom: 25px;
}
.text {
  text-align: center;
  color: #30363a;
  font-size: 1rem;
  width: 300px;
  margin: 0 auto;
  line-height: 1.7;
}
</style>