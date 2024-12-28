<script setup lang="ts">
import { use } from "echarts/core";
import { CanvasRenderer } from "echarts/renderers";
import { LineChart } from "echarts/charts";
import {
  TitleComponent,
  TooltipComponent,
  GridComponent,
  LegendComponent,
} from "echarts/components";
import VChart from "vue-echarts";
import { ref } from 'vue';

use([
  CanvasRenderer,
  LineChart,
  TitleComponent,
  TooltipComponent,
  GridComponent,
  LegendComponent,
]);

const chartOptions = ref({
  title: {
    text: 'Monthly Sales Performance',
    left: 'center'
  },
  tooltip: {
    trigger: 'axis'
  },
  legend: {
    data: ['2023', '2024'],
    bottom: 0
  },
  grid: {
    left: '3%',
    right: '4%',
    bottom: '10%',
    containLabel: true
  },
  xAxis: {
    type: 'category',
    data: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun']
  },
  yAxis: {
    type: 'value'
  },
  series: [
    {
      name: '2023',
      type: 'line',
      data: [150, 230, 224, 218, 135, 147],
      smooth: true
    },
    {
      name: '2024',
      type: 'line',
      data: [180, 260, 254, 258, 165, 177],
      smooth: true
    }
  ]
});
</script>

<template>
  <div class="chart-container">
    <v-chart class="chart" :option="chartOptions" autoresize />
  </div>
</template>

<style scoped>
.chart-container {
  width: 100%;
  height: 400px;
  padding: 20px;
}

.chart {
  width: 100%;
  height: 100%;
}
</style>