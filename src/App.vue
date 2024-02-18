
<script>
import axios from 'axios';

export default {
  name: 'App',
  data() {
    return {
      mails: []
    };
  },
  mounted() {
    for (let i = 0; i < 10; i++) {
      axios
        .get('https://flynn.boolean.careers/exercises/api/random/mail')
        .then((response) => {
          this.mails.push(response.data.response);
        });
    }
  }
};
</script>

<template>
  <div>
    <h1>Random Mail</h1>
    <ul>
      <li v-for="mail in mails" :key="mail">{{ mail }}</li>
    </ul>
  </div>
</template>

<style scoped>
ul {
  list-style: none;
}



</style>
