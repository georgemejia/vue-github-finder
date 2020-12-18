<template>
  <div class="container">
    <div class="row">

      <div class="col__left">
        <img class="user__image" :src="user.avatar_url" alt="This is an unsplash random photo">
        <p class="user__name">{{ user.name }}</p>
        <p class="user__username">{{ user.login }}</p>
        <a class="user__link" :href="user.html_url" target="_blank" rel="noopener noreferrer">view more</a>
      </div>

      <div class="col__right">
        <div class="user__stats">
          <span class="user__stat">Following {{ user.following}}</span>
          <span class="user__stat">Followers {{ user.followers}}</span>
          <span class="user__stat">Repositories {{ user.public_repos }}</span>
        </div>
        <div class="user__info">
          <ul class="user__list">
            <li class="user__list-item">Website: {{ user.blog }}</li>
            <li class="user__list-item">Location: {{ user.location }}</li>
            <li class="user__list-item">Member since: 2020</li>
            <li class="user__list-item">Twitter: {{ user.twitter_username }}</li>
          </ul>
        </div>
      </div>

    </div>
  </div>
</template>

<script>
export default {
  props: {
    user: Object
  },
}
</script>

<style scoped>
.container {
  width: 100%;
  max-width: 600px;
  margin: 50px auto;
}
.row {
  display: grid;
  grid-template-columns: 1fr 3fr;
  column-gap: 20px;
}
.col__left {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}
.user__info {
  margin-top: 25px;
}
.user__stat {
  font-size: 0.7rem;
  padding: 0.3em;
  background-color: #55d48a;
  margin-right: 5px;
}
.user__list {
  list-style-type: none;
}
.user__list-item {
  padding: 15px 8px;
  color: #fff;
  border: solid 1px #2c2d2e;
  font-size: 0.9rem;
}
.user__image {
  max-width: 180px;
}
.user__name {
  margin: 20px 0 6px 0;
  color: #FFF;
}
.user__username {
  color: rgb(105, 114, 122);
  font-size: 1rem;
}
.user__link {
  color: #333;
  font-size: 1rem;
  display: inline-block;
  text-decoration: none;
  text-transform: capitalize;
  background-color: #55d48a;
  padding: 0.5em 1.1em;
  border-radius: 10px;
  margin-top: 10px;
}
</style>