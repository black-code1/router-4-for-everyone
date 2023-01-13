<template>
  <div id="nav">
    <router-link id="logo" to="/">Vue School Travel App</router-link>
    <router-link
        v-for="destination in destinations"
        :key="destination.id"
        :to="{name: 'destination.show', params: {id: destination.id, slug:destination.slug}}"
    >
    </router-link>
  </div>
</template>

<script>
import sourecData from '@/data.json'
export default {
  name: "TheNavigation",

  data() {
    return {
      destination: sourecData.destinations
    }
  }
}
</script>

<style scoped>

</style>