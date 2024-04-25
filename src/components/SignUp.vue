<script>
export default {
  props: ['users', 'hash'],
  data() {
    return {
      email: '',
      pass: '',
      errorEmail: '',
      errorPass: []
    }
  },
  methods: {
    checkEmail() {
      if (this.email.includes(' ') || !this.email.includes('@') || !this.email.includes('.')) {
        this.errorEmail = 'Email is not correct.'
      }
    },
    checkPass() {
      let includesNum = false, includesUpperCase = false
      let nums = ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9']

      for (let i = 0; i < this.pass.length; i++) {
        if (nums.includes(this.pass[i])) {
          includesNum = true
        } else if (this.pass[i] == this.pass[i].toUpperCase()) {
          includesUpperCase = true
        }
      }

      if (this.pass.length < 8) {
        this.errorPass.push('Your password must include at least 8 characters.')
      }

      if (!includesNum) {
        this.errorPass.push('Your password must include at least 1 number.')
      }

      if (!includesUpperCase) {
        this.errorPass.push('Your password must include at least 1 uppercase letter.')
      }

      if (this.pass.includes(' ')) {
        this.errorPass.push('Your password must not include space.')
      }
    },
    addUser() {
      if (this.users.get(this.hash(this.email)) === undefined) {
        this.users.set(this.hash(this.email), this.hash(this.pass))
        this.email = ''
        this.pass = ''
      } else {
        this.errorEmail = 'User already exist.'
        this.errorPass = []
      }
    }
  }
}
</script>

<template>
  <div class="container">
    <div class="errorEmail">{{ errorEmail }}</div>
    <div v-for="error in errorPass" :key="error" class="errorPass">{{ error }}</div>

    <div class="line">
      <div class="title">Email:</div>
      <input type="text" v-model="email" @input="errorEmail = ''" placeholder="Enter email...">
    </div>
  
    <div class="line">
      <div class="title">Password:</div>
      <input type="text" v-model="pass" @input="errorPass = []" placeholder="Enter pass...">
    </div>
  
    <button @click="checkEmail(); checkPass(); addUser()"></button>
  </div>
</template>