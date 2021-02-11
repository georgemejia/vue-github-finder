<template>
  <div>
    <div class="container">
      <div class="form__control">
        <label class="label">Enter a username to fetch profile</label>
        <input
          v-model="username"
          v-on:keyup="sendValue"
          class="input"
          type="text"
          placeholder="Type username..."
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
  margin-top: 50px;
}

.label {
  font-size: 0.9rem;
  color: #b8b8b8;
}

.input {
  color: #b8b8b8;
  box-sizing: border-box;
  width: 100%;
  margin-top: 8px;
  font-size: 1rem;
  border: none;
  border-radius: 5px;
  padding: 15px;
  background-color: #212324;
}

.input::placeholder {
  color: #51555c;
}

@media screen and (max-width: 40em) {
  .container {
    width: 90%;
  }
}
</style>