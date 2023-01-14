<template>
  <div>
    <h1>Greetings, {{username}}</h1>
    <button @click="logout">Logout</button>
    <router-link :to="{name: 'invoices'}">
      <button>Invoices</button>
    </router-link>
  </div>
</template>

<script>
export default {
  name: "Protected",
  data() {
    return {
      username: window.user
    }
  },
  methods: {
    logout() {
      window.user = null
      this.$router.push({name: 'Home'})
      // this.$router.push('/')
      // this.$router.push({name: 'Home', hash: '#logout'})
      // this.$router.push({name: 'Home', query: {logout: null}})
      // this.$router.replace({name: 'Home', query: {logout: null}})

    }
  }
}
</script>

<style scoped>

</style>