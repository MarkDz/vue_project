<template>
  <div class="chart">
    <br />
    <p>This is simple chart with randomized data</p>
    <Chart />
  </div>
</template>

<script>
import Chart from "../components/Chart";
export default {
  name: "Employee",
  components: {
    Chart,
  },
};
</script>

<style scoped>
.chart {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>