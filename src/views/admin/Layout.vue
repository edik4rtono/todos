<template>
  <div>
    Welcome, {{ user.username }}
    <ul>
      <li><router-link :to="{ name: 'home' }">Home</router-link></li>
      <li v-for="menu in user.menus" :key="menu.path">
        {{ menu.label }}
      </li>
      <!-- <li><router-link :to="{ name: 'about' }">About</router-link></li>
      <li><router-link :to="{ name: 'admin_home'}">Admin</router-link></li>
      <li><router-link :to="{ name: 'post_di_admin'}">Admin Post</router-link></li>
      <li><router-link to="/admin/users">Admin Users</router-link></li>
      <li><router-link to="/admin/products">Admin Products</router-link></li> -->
    </ul>

    <h1>Halaman Admin</h1>
    <router-view />
  </div>
</template>

<script>
import Cookies from 'js-cookie'

export default {
  computed: {
    user() {
      return Cookies.getJSON('auth')
    }
  }
}
</script>
