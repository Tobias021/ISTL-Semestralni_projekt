<template>
  <div class="row">
    <div class="col-12">
      <card :title="table1.title" :subTitle="table1.subTitle">
        <div slot="raw-content" class="table-responsive">
          <paper-table :data="table1.data" :columns="table1.columns">
          </paper-table>
        </div>
      </card>
    </div>

    <div class="col-12">
      <div class="row">
        <div class="col-12">
          <chart-card
            title="Kumulované udržení publika v %"
            sub-title="8 minute performance"
            :chart-data="usersChart.data"
            :chart-options="usersChart.options"
          >
          <span slot="footer">
            <i class="ti-reload"></i> Updated 3 minutes ago
          </span>
            <div slot="legend">
              <i class="fa fa-circle text-info"></i> PC
              <i class="fa fa-circle text-danger"></i> Chytré TV
              <i class="fa fa-circle text-warning"></i> Mobilní zař.
            </div>
          </chart-card>
        </div>

        <div class="col-md-6 col-12">
          <chart-card
            title="Struktura publika"
            sub-title="Poměr odebírajících a neodebírajících"
            :chart-data="preferencesChart.data"
            chart-type="Pie"
          >

            <div slot="legend">
              <i class="fa fa-circle text-info"></i> Neodběratelé
              <i class="fa fa-circle text-danger"></i> Embedded
              <i class="fa fa-circle text-warning"></i> Odběratelé
            </div>
          </chart-card>
        </div>

        <div class="col-md-6 col-12">
          <chart-card
            title="Průměrná sledovanost"
            sub-title="Srovnání Vaší průměrné sledovanosti a celkové průměrné sledovanosti"
            :chart-data="activityChart.data"
            :chart-options="activityChart.options"
          >
          <span slot="footer">
          </span>
            <div slot="legend">
              <i class="fa fa-circle text-info"></i> Váš průměr
              <i class="fa fa-circle text-warning"></i> Celkový průměr
            </div>
          </chart-card>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import {ChartCard, PaperTable} from "@/components";
import Chartist from "chartist";
const tableColumns = ["Id", "Name", "Revenue", "Views", "Date"];
const tableData = [
  {
    id: 1,
    name: "10 nejlepších programovacích jazyků v roce 2023",
    revenue: "$36.738",
    views: "19 243",
    date: "18.2.2022",
  },
  {
    id: 2,
    name: "Jak vytvořit aplikaci pomocí React.js",
    revenue: "$23,789",
    views: "18 432",
    date: "28.7.2022",
  },
  {
    id: 3,
    name: "Novinky v oblasti umělé inteligence",
    revenue: "$56,142",
    views: "45 942",
    date: "4.9.2022",
  },
  {
    id: 4,
    name: "Budoucnost blockchain technologie",
    revenue: "$38,735",
    views: "23 782",
    date: "11.2.2023",
  },
  {
    id: 5,
    name: "Jak začít s vývojem mobilních aplikací",
    revenue: "$63,542",
    views: "63 121",
    date: "15.3.2023",
  },
];

export default {
  components: {
    ChartCard,
    PaperTable,
  },
  data() {
    return {
      table1: {
        title: "Tabulka výkonnosti",
        subTitle: "Popis výkonností videí",
        columns: [...tableColumns],
        data: [...tableData],
      },

      usersChart: {
        data: {
          labels: [
            "1:00",
            "2:00",
            "3:00",
            "4:00",
            "5:00",
            "6:00",
            "7:00",
            "8:00",
          ],
          series: [
            [28, 38, 49, 56, 59, 62, 69, 89, 95],
            [6, 15, 19, 24, 38, 43, 53, 64, 74],
            [2, 8, 9, 10, 19, 23, 30, 41, 42],
          ],
        },
        options: {
          low: 0,
          high: 100,
          showArea: true,
          height: "245px",
          axisX: {
            showGrid: false,
          },
          lineSmooth: Chartist.Interpolation.simple({
            divisor: 3,
          }),
          showLine: true,
          showPoint: false,
        },
      },
      activityChart: {
        data: {
          labels: [
            "Jan",
            "Feb",
            "Mar",
            "Apr",
            "Mai",
            "Jun",
            "Jul",
            "Aug",
            "Sep",
            "Oct",
            "Nov",
            "Dec",
          ],
          series: [
            [542, 543, 520, 680, 653, 753, 326, 434, 568, 610, 756, 895],
            [230, 293, 380, 480, 503, 553, 600, 664, 698, 710, 736, 795],
          ],
        },
        options: {
          seriesBarDistance: 10,
          axisX: {
            showGrid: false,
          },
          height: "245px",
        },
      },
      preferencesChart: {
        data: {
          labels: ["62%", "32%", "6%"],
          series: [62, 32, 6],
        },
        options: {},
      },
    };

  },
};
</script>
<style></style>
