<template>
  <div>
    <AddGuest v-on:add-guest="addGuest"/>
    <Guests v-bind:guests="guests" v-on:del-guest="deleteGuest"/>
  </div>
</template>

<script>
import Guests from './components/Guests';
import AddGuest from './components/AddGuest'

export default {
  name: 'App',
  data(){
    return {
      guests:[
        
      ]
    }
  },
  components: {
    Guests,
    AddGuest
  },
  methods:{

    addGuest(newGuest){
      this.guests = [...this.guests,newGuest]
    },
    deleteGuest(id){
      this.guests = this.guests.filter((guest) => guest.id !== id)
    }
  }
};
</script>
