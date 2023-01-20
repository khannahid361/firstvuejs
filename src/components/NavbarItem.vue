<template>
  <div>
    <nav>
      <ul>
        <li v-for="link in Pinks" :key="link" @click="deleteNam(link.nam)">
          {{ link.nam }}
        </li>
        <li>lol</li>
        <li>kol</li>
      </ul>
    </nav>
  </div>
</template>

<script>
export default {
  props:['Pinks'],
  data() {
    return {
      home: "Home",
      homelink: "abc.com",
    };
  },
  methods: {
    deleteNam(nam)
    {
      this.$emit('delete',{nam})
    }
  },
};
</script>

<style scoped>
li{
    color:red;
    font-size:20px;
}
</style>