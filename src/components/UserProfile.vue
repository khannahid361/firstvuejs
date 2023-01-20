<template>
  <div id="profile">
    <h2>Hello {{ userId }}'s Profile</h2>
  </div>
</template>

<script>
export default {
  data() {
    return {
      userId: this.$route.params.user_Id,
    };
  },
  methods: {
    updateId() {
      this.userId = this.$route.params.user_Id;
      console.log(this.userId);
    },
  },
  watch: {
    $route: "updateId",
  },
};
</script>

<style>
</style>