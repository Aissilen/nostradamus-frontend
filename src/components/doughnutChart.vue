<template>
  <Doughnut
    :chart-options="chartOptions"
    :chart-data="chartData"
    :chart-id="chartId"
    :dataset-id-key="datasetIdKey"
    :plugins="plugins"
    :css-classes="cssClasses"
    :styles="styles"
    :width="width"
    :height="height"
  />
</template>

<script>
import { Doughnut } from 'vue-chartjs'
import { Chart as ChartJS, Title, Tooltip, Legend, ArcElement, CategoryScale, LinearScale } from 'chart.js'

ChartJS.register(Title, Tooltip, Legend, ArcElement, CategoryScale, LinearScale)

export default {
  name: 'DoughnutChart',
  components: { Doughnut },
  props: {
    chartTitle: String,
    chartId: {
      type: String,
      default: 'doughnut-chart'
    },
    datasetIdKey: {
      type: String,
      default: 'label'
    },
    width: {
      type: Number,
      default: 250
    },
    height: {
      type: Number,
      default: 150
    },
    cssClasses: {
      default: '',
      type: String
    },
    styles: {
      type: Object,
      default: () => {}
    },
    plugins: {
      type: Object,
      default: () => {}
    }
  },
  data() {
    return {
      chartData: {
        labels: ['40-55 лет', '30-40 лет', '18-30 лет', '14-18 лет'],
        datasets: [
            {
                backgroundColor: ['#41B883', '#E46651', '#00D8FF', '#DD1B16'],
                data: [40, 20, 80, 10]
            }
        ]
      },
      chartOptions: {
        responsive: false,
        plugins: {
            title: {
                display: true,
                text: this.chartTitle
            },
            legend: {
                display: true,
                position: 'left',
            },
        }
      }
    }
  },
  created() {
    // ❌ warning, props are readonly!
    console.log(this.chartTitle);
  }
}
</script>