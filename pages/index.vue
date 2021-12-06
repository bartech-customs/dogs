<template>
  <div>
    {{ ip }}
    <button @click="fetchSomething">fetch</button>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  // async asyncData({ $axios }) {
  //   const results = await $axios.$get("/.netlify/functions/node");

  //   // return { results };
  // },
  async asyncData({ $axios }) {
    const joke = await $axios.$get("/.netlify/functions/node");
    console.log(joke);
  },
  async asyncData({ $axios }) {
    const ip = await $axios.$get("http://icanhazip.com");
    return { ip };
  },
  methods: {
    async fetchSomething() {
      const ip = await this.$axios.$get("/.netlify/functions/node");
      console.log(ip);
    },
  },
};
</script>

<style lang="scss" scoped></style>
