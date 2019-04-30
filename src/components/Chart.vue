<template>
  <div class="chartWrapper" width="1000px">
    <canvas id="myChart"></canvas>
  </div>
</template>
<script>
function prepareData(records, key) {
  return records.map(el => ({ t: new Date(el.date).valueOf(), y: el[key] }));
}

function load() {
  const records = this.records;
  const ctx = document.getElementById("myChart").getContext("2d");
  const chart = new Chart(ctx, cfg);
  chart.data.datasets[0].data = prepareData(records, "mood");
  chart.data.datasets[1].data = prepareData(records, "energy");
  chart.update();
}

const cfg = {
  type: "bar",
  data: {
    datasets: [
      {
        label: "Gevoel",
        backgroundColor: "#28a745",
        borderColor: "#28a745",
        data: [],
        type: "bar",
        pointRadius: 0,
        fill: false,
        lineTension: 0,
        borderWidth: 2
      },
      {
        label: "Energie",
        backgroundColor: "#088193",
        borderColor: "#088193",
        data: [],
        type: "bar",
        pointRadius: 0,
        fill: false,
        lineTension: 0,
        borderWidth: 2
      }
    ]
  },
  options: {
    scales: {
      xAxes: [
        {
          type: "time",
          distribution: "series",
          time: {
            unit: "day"
          },
          ticks: {
            source: "data",
            autoSkip: true
          },
          offset: true
        }
      ],
      yAxes: [
        {
          ticks: {
            beginAtZero: true,
            max: 5,
            min: 0,
            stepSize: 1
          },
          scaleLabel: {
            display: true,
            labelString: "Score"
          }
        }
      ]
    },
    tooltips: {
      intersect: false,
      mode: "index",
      callbacks: {
        label: function(tooltipItem, myData) {
          let label = myData.datasets[tooltipItem.datasetIndex].label || "";
          if (label) {
            label += ": ";
          }
          label += parseFloat(tooltipItem.value).toFixed(2);
          return label;
        }
      }
    }
  }
};

export default {
  name: "Chart",
  props: {
    records: Array
  },
  mounted: load
};
</script>
