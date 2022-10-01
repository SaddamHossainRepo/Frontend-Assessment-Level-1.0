<template>
  <div class="col-md-10">
  <div class="row">
    <div class="col-md-12 d-flex">
      <div class="col-md-6 p-3 gray m-2">
        <h2 class="display-4">Balance</h2>
        <canvas id="donutChart" width="100" height="100"></canvas>
      </div>

      <div class="col-md-6 p-3 gray m-2">
        <h2 class="display-4">Composition</h2>
        <canvas id="areaChart" width="100" height="100"></canvas>
      </div>
    </div>
  </div>
  </div>
</template>

<script>
import Chart from "chart.js/auto";
export default {
  name: "ChartComponent",
  props: {
    msg: String,
  },
  mounted() {
    console.log("component mounted");

    const ctx = document.getElementById("donutChart");
    const ctx2 = document.getElementById("areaChart");

    // myChart;
    const data = {
      labels: ["Red", "Blue", "Yellow"],
      datasets: [
        {
          label: "My First Dataset",
          data: [300, 50, 100],
          backgroundColor: [
            "rgb(255, 99, 132)",
            "rgb(54, 162, 235)",
            "rgb(255, 205, 86)",
          ],
          hoverOffset: 4,
        },
      ],
    };
    new Chart(ctx, {
      type: "doughnut",
      data: data,
    });

    //
    new Chart(ctx2, {
      type: "line",
      data: {
        labels: ["Red", "Blue", "Yellow", "Green", "Purple", "Orange"],
        datasets: [
          {
            label: "# of Votes",
            data: [12, 19, 3, 5, 2, 3],
            backgroundColor: [
              "rgba(255, 99, 132, 0.2)",
              "rgba(54, 162, 235, 0.2)",
              "rgba(255, 206, 86, 0.2)",
              "rgba(75, 192, 192, 0.2)",
              "rgba(153, 102, 255, 0.2)",
              "rgba(255, 159, 64, 0.2)",
            ],
            fill: true,
            borderColor: [
              "rgba(255,99,132,1)",
              "rgba(54, 162, 235, 1)",
              "rgba(255, 206, 86, 1)",
              "rgba(75, 192, 192, 1)",
              "rgba(153, 102, 255, 1)",
              "rgba(255, 159, 64, 1)",
            ],
            borderWidth: 1,
          },
          {
            label: "# of Players",
            data: [1, 20, 1, 2, 5, 8],
            backgroundColor: [
              "rgba(54, 162, 235, 0.2)",
              "rgba(255, 206, 86, 0.2)",
              "rgba(75, 192, 192, 0.2)",
              "rgba(153, 102, 255, 0.2)",
              "rgba(255, 159, 64, 0.2)",
            ],
            fill: true,
            borderColor: [
              "rgba(255,99,132,1)",
              "rgba(54, 162, 235, 1)",
              "rgba(255, 206, 86, 1)",
              "rgba(75, 192, 192, 1)",
              "rgba(153, 102, 255, 1)",
              "rgba(255, 159, 64, 1)",
            ],
            borderWidth: 1,
          },
        ],
      },
      options: {
        scales: {
          yAxes: [
            {
              ticks: {
                beginAtZero: true,
              },
            },
          ],
        },
      },
    });
  },
};
</script>

<style lang="scss" scope>
.gray {
  background-color: #cfcecf;
  border-radius: 5px;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}

canvas {
  height: 100px;
  width: 100px;
}
</style>
