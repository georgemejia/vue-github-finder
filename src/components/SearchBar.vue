<template>
  <div>
    <div class="container">
      <h1 class="title">Vue GitHub Finder</h1>
      <div class="form-control">
        <label class="label">Enter a users name to fetch the users profile</label>
        <input
          v-model="username"
          v-on:keyup="sendValue"
          class="input"
          type="text"
          placeholder="Start typing a name"
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
  max-width: 600px;
  margin: 50px auto 0 auto;
}

.title {
  color: #f0f0f0;
  font-size: 2.5rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 1px;
}

.form-control {
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
</style>