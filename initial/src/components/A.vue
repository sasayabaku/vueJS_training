<template>
  <div>
    <button @click="countUp">add count</button>
    <div>{{ currentCount }}</div>
  </div>
</template>

<script>
  export default {
    computed: {
      currentCount() {
        return this.$store.getters.currentCount;
      }
    },
    methods: {
      countUp() {
        this.$store.dispatch("plusCount");
      }
    }
  }
</script>
