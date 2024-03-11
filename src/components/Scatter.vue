<template>
  <div>
    <div
      id="maychar"
      style="width: 1000px; height: 800px; border: solid 1px red"
    ></div>
  </div>
</template>

<script>
export default {
  name: "Histogram",
  data() {
    return {};
  },
  mounted() {
    this.getCharts();
  },
  methods: {
    // 使用柱形图，关于其他配置可以去官网查看
    getCharts() {
      const chartBox = this.$echarts.init(document.getElementById("maychar"));
      const option = {
        xAxis: {
          data: ["Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat"],
        },
        yAxis: {},
        series: [
          {
            type: "scatter",
            data: [220, 182, 191, 234, 290, 330, 310],
          },
        ],
      };
      chartBox.setOption(option);
      // 根据页面大小自动响应图表大小
      // window.addEventListener("resize", function () {
      //   console.log("resize()");
      //   chartBox.resize();
      // });
    },
  },
};
</script>
