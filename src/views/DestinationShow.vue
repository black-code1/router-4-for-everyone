<template>
  <section v-if="destination" class="destination">
    <h1>{{destination.name}}</h1>
    <div class="destination-details">
      <img :src="`/images/${destination.image}`" :alt="destination.name">
      <p>{{destination.description}}</p>
    </div>
  </section>
</template>

<script>
import sourceData from '@/data.json'
export default {
  name: "DestinationShow",

  computed: {
    destinationId(){
      return parseInt(this.$route.params.id)
    },
    destination(){
      return sourceData.destinations.find((destination) => destination.id === this.destinationId)
    }
  },

  async created() {
    const response = await fetch(`https://travel-dummy-api.netlify.app/${this.$route.params.slug}`)
    this.destination = await response.json()
  }
}
</script>

<style scoped>

</style>