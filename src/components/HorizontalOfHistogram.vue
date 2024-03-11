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
  name: "HorizontalaOfHistogram",
  data() {
    return {};
  },
  mounted() {
    this.getCharts();
  },
  methods: {
    //，如果想要采用纵向的柱条，只要把本教程中的 X 轴和 Y 轴相反设置即可。
    getCharts() {
      const chartBox = this.$echarts.init(document.getElementById("maychar"));
      const option = {
        yAxis: {
          data: ["Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun"],
        },
        xAxis: {},
        series: [
          {
            type: "bar",
            data: [23, 24, 18, 25, 27, 28, 25],
          },
        ],
      };
      chartBox.setOption(option);
      // 根据页面大小自动响应图表大小
      // window.addEventListener("resize", function () {
      //   chartBox.resize();
      // });
    },
  },
};
</script>
