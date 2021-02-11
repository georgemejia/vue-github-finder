<template>
  <div class="container">

    <div class="row">
      <div class="col__left">
        <img class="user__image" :src="user.avatar_url" alt="This is an unsplash random photo">
        <p class="user__name">{{ user.name }}</p>
        <p class="user__username">{{ user.login }}</p>
        <a class="user__link" :href="user.html_url" target="_blank" rel="noopener noreferrer">View Profile</a>
      </div>

      <div class="col__right">
        <div class="user__stats">
          <span class="user__stat">Following {{ user.following}}</span>
          <span class="user__stat user__stat--purple">Followers {{ user.followers}}</span>
          <span class="user__stat user__stat--blue">Public Repositories {{ user.public_repos }}</span>
        </div>
        <div class="user__info">
          <ul class="user__list">
            <li class="user__list-item user__list-item--radius-top">Website: {{ user.blog }}</li>
            <li class="user__list-item">Location: {{ user.location }}</li>
            <li class="user__list-item">Member since: 2020</li>
            <li class="user__list-item user__list-item--radius-bottom">Twitter: {{ user.twitter_username }}</li>
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
  max-width: 700px;
  margin: 20px auto;
  border-radius: 5px;
  padding: 3em;
  background-color: #212324;
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
  color: #FFFFFF;
  font-size: 0.9rem;
  padding: 0.6em;
  background-color: #36af8b;
  margin-right: 25px;
  border-radius: 5px;
  padding: 5px;
}
.user__stat--purple {
  background-color: #a229a2;
}
.user__stat--blue {
  background-color: #2491c6;
}
.user__list {
  list-style-type: none;
}
.user__list-item {
  padding: 15px 8px;
  color: #fff;
  border: solid 1px#3d4247;
  font-size: 0.9rem;
}
.user__list-item--radius-top {
  border-radius: 5px 5px 0 0;
}
.user__list-item--radius-bottom {
  border-radius: 0 0 5px 5px;
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
  color: #36af8b;
  font-size: 1rem;
  display: inline-block;
  text-decoration: underline;
  text-transform: capitalize;
  border-radius: 10px;
  margin-top: 20px;
}
@media screen and (max-width: 40em) {
  .container {
    width: 90%;
  }
  .row {
    display: grid;
    grid-template-rows: 1fr 1fr;
    grid-template-columns: 1fr;
  }
  .col__right {
    margin-top: 40px;
    display: flex;
    flex-direction: column;
  }
  .user__image {
    width: 100%;
  }
}
@media screen and (max-width: 25em) {
  .user__image {
    margin: 0 auto;
  }
  .user__stats {
    display: flex;
    flex-direction: column;
  }
  .user__stat {
    margin: 5px 0;
  }
}
</style>