<template>
  <div class="body">
    <p>Thanks for visiting our website! It will be up and running Soon!</p>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Home",
  async created() {
    try {
      let response = await axios.get('/api/users');
      this.$root.$data.user = response.data.user;
    } catch (error) {
      this.$root.$data.user = null;
    }
  },
  computed: {
    user() {
      return this.$root.$data.user;
    },
  }
}
</script>

<style scoped>
.body {
  text-align: center;
  padding-top: 30px;
  font-size: 50px;
  font-weight: bolder;
}
</style>