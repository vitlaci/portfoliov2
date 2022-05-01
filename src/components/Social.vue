<template>
  <ul class="social">
    <li v-for="(social, i) in socialList" :key="i">
      <a :href="social.link" target="_blank" rel="noreferrer"
        ><img class="svg" :src="social.src" alt="social"
      /></a>
    </li>
  </ul>
  <!-- End. social -->
</template>

<script>
  export default {
    data() {
      return {
        socialList: [
          {
            link: "https://www.facebook.com/laca.vitkai",
            src: require("../assets/img/svg/social/facebook.svg"),
          },
        ],
      };
    },
  };
</script>

<style lang="scss" scoped></style>
