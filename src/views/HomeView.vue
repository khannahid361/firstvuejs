<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
    <practicing-hooks-vue />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import PracticingHooksVue from "@/components/PracticingHooks.vue";

export default {
  name: "HomeView",
  data() {},
  components: {
    HelloWorld,
    PracticingHooksVue,
  },
};
</script>
