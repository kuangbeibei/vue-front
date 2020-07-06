<template>
  <div id="app">
    <ul>
      <li v-for="user in users" :key="user.id">
        {{user.name}}
      </li>
    </ul>
  </div>
</template>

<script>
import axios from "axios";
import HelloWorld from './components/HelloWorld.vue';
export default {
  name: 'app',
  data () {
    return {
      users: []
    }
  },
  mounted() {
    axios.get('http://localhost:3000/api/users').then(response => {
      this.users = response.data;
    })
  }
}
</script>

<style>

</style>
