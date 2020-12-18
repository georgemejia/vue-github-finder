<template>
  <div>
    <div class="container">

      <div class="row">
        <div class="col__left">
          <img class="user__image" src="https://source.unsplash.com/random/180x180" alt="This is an unsplash random photo">
          <p class="user__name">John Doe</p>
          <p class="user__username">johndoegithub</p>
          <a class="user__link" href="#">view more</a>
        </div>

        <div class="col__right">
          <div class="user__stats">
            <span class="user__stat">Following 0</span>
            <span class="user__stat">Followers 0</span>
            <span class="user__stat">Repositories 0</span>
          </div>
          <div class="user__info">
            <ul class="user__list">
              <li class="user__list-item">Website: https://mywebsite.com</li>
              <li class="user__list-item">Location: USA</li>
              <li class="user__list-item">Member since: 2020</li>
              <li class="user__list-item">Twitter: JohnDoeTwitter</li>
            </ul>
          </div>
        </div>
      </div>

    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>
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
.user__name {
  margin: 20px 0 6px 0;
  color: #FFF;
}
.user__username {
  color: #69727a;
  font-size: 1rem;
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
.user__link {
  color: #55d48a;
  font-size: 1rem;
  display: inline-block;
  text-decoration: underline;
  text-transform: capitalize;
  border-radius: 10px;
  margin-top: 20px;
}
</style>