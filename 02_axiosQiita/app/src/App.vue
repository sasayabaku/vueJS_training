<template>
  <div class="root">
    <APIcall class="APIcall" @loadStart="onLoadStart" @loadComplete="onLoadComplete" /></APIcall>
    <Result :items="items" :loadProgress="loadProgress" /></Result>
  </div>
</template>

<script>
import APIcall from '@/components/APIcall';
import Result from '@/components/Result';

export default {
  data() {
    return {
      items: [],
      loadProgress: false,
    };
  },

  methods: {
    onLoadStart() {
      this.loadProgress = true;
    },

    onLoadComplete({ results }) {
      this.items = results;
      this.loadProgress = false;
    },
  },

  components: {
    APIcall,
    Result
  },
}
</script>

<style scoped>
.clock {
  width: 80%;
  max-width: 500px;
  margin: 30px auto;
}
</style>

<style>
html {
  font-size: 62.5%;
}

body{
  margin: 0;
}

a{
  text-decoration: none;
}

p {
  margin: 0;
}

ul{
  padding: 0;
  margin: 0;
}
</style>
