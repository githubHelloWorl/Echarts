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
          type: "category",
          data: ["A", "B", "C"],
        },
        yAxis: {
          type: "value",
        },
        series: [
          {
            data: [120, 200, 150],
            type: "line",
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
