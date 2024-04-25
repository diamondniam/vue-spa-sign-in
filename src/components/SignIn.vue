<script>
export default {
  props: ['users', 'hash'],
  data() {
    return {
      pass: '',
      email: '',
      acception: false,
      rejection: false
    }
  },
  methods: {
    compare() {
      if (this.users.get(this.hash(this.email)) === this.hash(this.pass)) {
        this.pass = ''
        this.email = ''
        this.acception = true
        this.rejection = false
      } else {
        this.acception = false
        this.rejection = true
      }
    }
  }
}
</script>

<template>
  <div class="container">
    <div v-show="acception" class="acception">Accepted!</div>
    <div v-show="rejection" class="rejection">Something is wrong.</div>

    <div class="line">
      <div class="title">Email:</div>
      <input type="text" v-model="email" @input="rejection = false; acception = false" placeholder="Enter email...">
    </div>
  
    <div class="line">
      <div class="title">Password:</div>
      <input type="text" v-model="pass" @input="rejection = false; acception = false" placeholder="Enter pass...">
    </div>
  
    <button @click="compare()"></button>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
}

.acception {
  color: green;
}

.rejection {
  color: red;
}

button {
  align-self: center;
}
</style>