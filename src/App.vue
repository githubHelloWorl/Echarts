<template>
  <div>
    <div style="border: solid 1px red; height: 50px; width: 100%">
      <select v-model="flag" style="width: 100px">
        <option label="柱状图" value="0"></option>
        <option label="横向柱状图" value="1"></option>
        <option label="饼图" value="2"></option>
        <option label="折线图" value="3"></option>
        <option label="散点图" value="4"></option>
      </select>
    </div>
    <div>
      <Histogram v-if="flag === '0'" />
      <HorizontalOfHistogram v-else-if="flag === '1'" />
      <Pie v-else-if="flag === '2'" />
      <Line v-else-if="flag === '3'" />
      <Scatter v-else-if="flag === '4'" />
    </div>
  </div>
</template>

<script>
import Histogram from "./components/Histogram.vue";
import HorizontalOfHistogram from "./components/HorizontalOfHistogram.vue";
import Pie from "./components/Pie.vue";
import Line from "./components/Line.vue";
import Scatter from "./components/Scatter.vue";

export default {
  name: "App",
  components: {
    Histogram,
    HorizontalOfHistogram,
    Pie,
    Line,
    Scatter,
  },
  data() {
    return {
      flag: "0",
    };
  },
  watch: {
    flag: {
      handler(newFlag, oldFlag) {
        console.log("newFlag =");
        console.log(newFlag);
      },
      immediate: true,
      deep: true,
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
