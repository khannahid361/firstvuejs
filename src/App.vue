<template>
  <nav>
    <router-link to="/">Home</router-link>
    <router-link to="/about">About</router-link>
    <router-link :to="{ name: 'contact' }">Contact</router-link>
    <li v-for="(profile, index) in profiles" :key="index">
      <router-link :to="{ name: 'profile', params: { user_Id: profile } }"
        >Profile {{ profile }}</router-link
      >
    </li>
  </nav>
  <router-view />
  <button @click="forward">Forward</button>
  <button @click="back">Back</button>
  <button @click="about">About</button>
</template>

<script>
export default {
  data() {
    return {
      profiles: [1, 2, 3, 4, 5],
    };
  },
  methods: {
    forward() {
      this.$router.go(1);
    },
    back() {
      this.$router.go(-1);
    },
    about() {
      this.$router.push({ name: "about" });
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
  /* padding :30px; */
  margin: 30px;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
