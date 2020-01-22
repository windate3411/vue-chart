<template>
  <div id="app">
    <div class="container center">
      <h1>Vue Charts</h1>
      <div class="row justify-content-center align-items-stretch">
        <div class="col-md-5 mr-2">
          <div class="card h-100">
            <BarChart />
          </div>
        </div>
        <div class="col-md-5 mr-2">
          <div class="card h-100">
            <PieChart :chartdata="pieChartData" :options="options" />
          </div>
        </div>
        <div class="col-md-10 mt-3">
          <LineChart :chartdata="lineChartData" :options="options" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import BarChart from './components/BarChart.vue'
import LineChart from './components/LineChart.vue'
import PieChart from './components/PieChart.vue'

export default {
  name: 'app',
  components: {
    BarChart, LineChart, PieChart
  },
  data() {
    return {
      lineChartData: {
        labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
        datasets: [
          {
            label: 'Weight track',
            backgroundColor: "transparent",
            data: [75, 75.6, 77.8, 78.1, 79.1, 80, 78.5],
            borderColor: "rgba(1, 116, 188, 0.50)",
            pointBackgroundColor: "rgba(171, 71, 188, 1)"
          }
        ]
      },
      pieChartData: {
        labels: ['Angular', 'Vue', 'React'],
        datasets: [
          {
            backgroundColor: ['#e74c3c', '#1abc9c', '#3498db'],
            data: [15, 25, 60]
          }
        ]
      },
      options: {
        responsive: true,
        maintainAspectRatio: false
      }
    }
  },
}
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
