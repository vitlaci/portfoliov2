<template>
  <div class="tokyo_tm_home">
    <div class="home_content">
      
      <!-- End .avatar -->
      <div class="details">
        <h3 class="name">Laszlo Vitkai</h3>
        <p class="job">
         An enthusiastic web designer, currently based in Denmark.
        </p>

        <Social />
      </div>
      <!-- End .details -->
    </div>
  </div>
</template>

<script>
  import Social from "./Social";
  export default {
    components: {
      Social,
    },
    data() {
      return {
        src1: require("../assets/img/slider/1.jpg"),
      };
    },
  };
</script>

<style lang="scss"></style>
