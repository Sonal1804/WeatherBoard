<script>
import { Line } from "vue3-chart-v2";
export default {
  name:'LineChart',
  props: ['tempVar','tempVarDt'],
  extends: Line,
  data() {
    return {
      flag:true,
       loaded: false,
      chartData: {
                  labels: [
                    "10:00 am",
                    "11:00 am",
                    "12:00 pm",
                    "13:00 pm",
                    "14:00 pm",
                    "15:00 pm",
                    "16:00 pm",
                    "17:00 pm",
                  ],
                  datasets: [
                    {
                      label: "Line",
                      data: [240.11, 270.92, 280.67, 230.69, 250.34, 220.81,260.22,280.9],
                      fill: false,
                      tension: 0.1,
                      borderColor: "black",
                      backgroundColor: "black",
                      borderWidth: 1,
                    },
                  ],
      },
      options: {
        responsive: true,
        maintainAspectRatio: false,
        title: {
          display: true,
          text: "Temperature",
          fontColor: "black",
          fontSize: 24,
          position: "left",
          padding: 16,
        },
        
        layout: {
          padding: 12,
        },
        scales: {
          yAxes: [
            {
              ticks: {
                beginAtZero: true,
              },
              gridLines: {
                display: true,
              },
            },
          ],
          xAxes: [
            {
              gridLines: {
                display: false,
              },
            },
          ],
        },
      },
    };
  },  
 async mounted () {
      this.renderChart(this.chartData, this.options);
  }
};
</script>