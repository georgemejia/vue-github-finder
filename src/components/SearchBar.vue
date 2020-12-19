<template>
  <div>
    <div class="container">
      <div class="form__control">
        <label class="label">Enter a users username to fetch the users profile</label>
        <input
          v-model="username"
          v-on:keyup="sendValue"
          class="input"
          type="text"
          placeholder="Type username"
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      username: ''
    }
  },

  methods: {
    sendValue() {
      this.$emit('inputValue', this.username)
    }
  }

};
</script>

<style scoped>
.container {
  width: 100%;
  max-width: 700px;
  margin: 50px auto 0 auto;
}

.form__control {
  margin-top: 20px;
}

.label {
  font-size: 0.9rem;
  color: #b8b8b8;
}

.input {
  box-sizing: border-box;
  width: 100%;
  padding: 8px 12px;
  margin-top: 8px;
  font-size: 1rem;
}

.input::placeholder {
  color: #c9c9c9;
}

@media screen and (max-width: 40em) {
  .container {
    width: 90%;
  }
}
</style>