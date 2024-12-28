<script setup lang="ts">
import DashboardChart from './DashboardChart.vue';
</script>

<template>
  <div class="dashboard">
    <h1>Sales Dashboard</h1>
    <div class="dashboard-grid">
      <div class="chart-card">
        <DashboardChart />
      </div>
    </div>
  </div>
</template>

<style scoped>
.dashboard {
  padding: 20px;
  max-width: 1200px;
  margin: 0 auto;
}

.dashboard-grid {
  display: grid;
  gap: 20px;
  margin-top: 20px;
}

.chart-card {
  background: white;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  overflow: hidden;
}

h1 {
  margin-bottom: 20px;
  color: #2c3e50;
}
</style>