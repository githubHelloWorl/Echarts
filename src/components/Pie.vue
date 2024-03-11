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
        series: [
          {
            type: "pie",
            data: [
              {
                value: 335,
                name: "直接访问",
              },
              {
                value: 234,
                name: "联盟广告",
              },
              {
                value: 1548,
                name: "搜索引擎",
              },
            ],
            //radius: "20%", // 设置半径大小
            radius: 100, // 直接像素值也行
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
