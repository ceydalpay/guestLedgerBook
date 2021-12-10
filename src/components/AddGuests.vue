<template>
    <div class="container">
        <br>
        <h1 class="text-center">Guest Ledger Book</h1>
        <br><br>
        <form @submit="addGuest">
        <div class="form-group">
            <input required type="text" v-model="email" placeholder="email" name="email" id="" class="form-control">
            <input required type="text" v-model="message" placeholder="message" name="message" id="" class="form-control">
        </div>
        <div class="form-group">
            <button class="btn btn-block btn-danger">
                Add New Record
            </button>
        </div>
        </form>
    </div>
</template>
<script>

export default {
  name: "AddGuest",
  data() {
    return {
      email: '',
      message: '',
      guests:[]
    }
  },
  methods: {
    addGuest(e) {
        e.preventDefault()
      const newGuest = {
        id:Date.now(),
        email: this.email,
        message: this.message,
        completed: false
      }
      // Send up to parent
      this.$emit('add-guest', newGuest);

      this.email = '';
      this.message = '';
    }
  }
}
</script>

<style scoped>

</style>
