<template>
  <div>
    <div v-bind:key="guest.id" v-for="guest in guests">
      <GuestItem v-bind:id="guest.id" v-bind:email="guest.email" v-bind:message="guest.message"
       v-bind:guest="guest" v-on:del-guest="$emit('del-guest', guest.id)"
       v-bind:guests="guests"/>
    </div>
  </div>
</template>

<script>
import GuestItem from './GuestItem.vue';
export default {
  name: "Guests",
  components: {
    GuestItem
  },
  props: ["guests"]
}
</script>

<style scoped>
</style>