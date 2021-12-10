<template>
  <div class="container">
    <div class="guest-item" v-bind:class="{'is-complete':guest.completed}">
      <p>
        Email: {{guest.email}}
        <br>Message: {{guest.message}}
        <button @click="$emit('del-guest', guest.id)" class="del">x</button>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "GuestItem",
  props: ["guest", "guests", "email", "id"]
};
</script>

<style scoped>
.guest-item {
  background: #f4f4f4;
  padding: 10px;
  margin: 20px;
  border-bottom: 1px #ccc dotted;
}

.is-complete {
  text-decoration: line-through;
}

.del {
  background: #e75656ec;
  color: #fff;
  border: none;
  padding: 5px 9px;
  border-radius: 50%;
  cursor: pointer;
  float: right;
}
</style>
