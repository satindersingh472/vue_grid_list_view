<template>
<!-- app div is a parent div -->
  <div id="app">
<!-- box will have all the html from component twitter data -->
    <div id="box">
      <twitter-data></twitter-data>
    </div>
  </div>
</template>

<script>
// twitter data component will get imported from src/components/twitterdata
import TwitterData from "@/components/twitterData.vue";

export default {
  name: "App",
  components: {
    TwitterData,
  },
};
</script>

<style scoped>
/* box will have some properties */
#box{
  display: grid;
  grid-auto-flow: row;
}
</style>
