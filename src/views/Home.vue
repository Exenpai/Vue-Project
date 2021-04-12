<template>
  <div>
    <h1>Welcome!</h1>
    <button v-on:click="redirect('/OrderPage')">Order Now</button>
  </div>
</template>

<script>
export default {
  methods: {
    redirect(id) {
      this.$router.push(id);
    },
  },
};
</script>