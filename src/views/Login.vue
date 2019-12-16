<template>
  <div>
    <form @submit.prevent="login">
      <input type="text" v-model="form.username">
      <input type="password" v-model="form.password">
      <button type="submit">Login</button>
    </form>
  </div>
</template>

<script>
import axios from 'axios'
import Cookies from 'js-cookie'

export default {

  data: () => ({
    form: {
      username: 'mul14',
      password: 'secret',
    }
  }),

  methods: {
    async login() {
      const response = await axios.post('http://localhost:3000/users/login', this.form)

  console.log(response)

      Cookies.set('auth', response.data.data)

      this.$router.push('/admin')
    }
  }

}
</script>
