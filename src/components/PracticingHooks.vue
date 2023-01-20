<template>
  <div>
    <input type="text" name="" v-model="term" id="">
    <div v-for="post in searchTerm" :key="post.id">
      <h2>{{ post.title }}</h2>
      <br />
      <p>{{ post.body }}</p>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      posts: [],
      term: "",
    };
  },
  methods: {},
  computed: {
    searchTerm() {
      return this.posts.filter((post) => {
        return post.title.match(this.term);
      });
    },
  },
  beforeCreate() {
    axios
      .get("https://jsonplaceholder.typicode.com/posts")
      .then((response) => {
        this.posts = response.data;
        // console.log(response.data[0].title);
      })
      .catch((error) => {
        alert(error);
      });
  },
};
</script>

<style scoped>
li {
  color: red;
  font-size: 20px;
}
h2 {
  text-decoration: underline;
  color: blue;
}
</style>