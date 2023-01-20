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
    $route: {
      handler: function (value) {
        this.userId = value.params.user_Id;
        console.log(value.params.user_Id);
      },
      deep: true,
      immediate: true,
    },
  },
};
</script>

<style>
</style>