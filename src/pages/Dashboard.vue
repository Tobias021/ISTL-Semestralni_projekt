<template>
  <div>
    <!--Stats cards-->
    <div class="row">
      <div
        class="col-md-6 col-xl-4"
        v-for="stats in statsCards1"
        :key="stats.title"
      >
        <stats-card>
          <div class="stats-card-header" slot="content">
            <h5 class="card-title">{{ stats.uzivatel  }} nahrál/a video:</h5>
            <div slot="prispevek">
              <h3>{{ stats.prispevek }}</h3>
            </div>
          </div>
          <div
            slot="header"
          >
          <img class="img-thumbnail" src="@/assets/img/videoPlaceholder.png"/>
          </div>

          <div class="stats" slot="footer">
            <i :class="stats.footerIcon"></i> {{ stats.footerText }}
          </div>
        </stats-card>
      </div>
      <div
        class="col-md-6 col-xl-3"
        v-for="stats in statsCards"
        :key="stats.title"
      >
      </div>
    </div>
    <div class="row">
      <div
        class="col-md-6 col-xl-3"
        v-for="stats in statsCards2"
        :key="stats.title"
      >
        <stats-card>
          <div class="stats-card-header" slot="content">
            <h5 class="card-title">{{ stats.uzivatel  }} nahrál/a video:</h5>
            <div slot="prispevek">
              <h3>{{ stats.prispevek }}</h3>
            </div>
          </div>
          <div
            class="icon-big text-center"
            :class="`icon-${stats.type}`"
            slot="header"
          >
            <img size="30 %" class="row-cols-3" src="@/assets/img/videoPlaceholder.png"/>
          </div>

          <div class="stats" slot="footer">
            <i :class="stats.footerIcon"></i> {{ stats.footerText }}
          </div>
        </stats-card>
      </div>
      <div
        class="col-md-6 col-xl-3"
        v-for="stats in statsCards"
        :key="stats.title"
      >
      </div>
    </div>
    <div class="row">
      <div
        class="col-md-6 col-xl-3"
        v-for="stats in statsCards3"
        :key="stats.title"
      >
        <stats-card>
          <div class="stats-card-header" slot="content">
            <h5 class="card-title">{{ stats.uzivatel  }} nahrál/a video:</h5>
            <div slot="prispevek">
              <h3>{{ stats.prispevek }}</h3>
            </div>
          </div>
          <div
            class="icon-big text-center"
            :class="`icon-${stats.type}`"
            slot="header"
          >
            <img size="30 %" class="row-cols-3" src="@/assets/img/videoPlaceholder.png"/>
          </div>

          <div class="stats" slot="footer">
            <i :class="stats.footerIcon"></i> {{ stats.footerText }}
          </div>
        </stats-card>
      </div>
      <div
        class="col-md-6 col-xl-3"
        v-for="stats in statsCards"
        :key="stats.title"
      >
      </div>
    </div>
    <!--Charts-->
  </div>
</template>
<script>
import { StatsCard, ChartCard } from "@/components/index";
import Chartist from "chartist";
export default {
  components: {
    StatsCard,
    ChartCard,
  },

  computed: {
  assetsPath() {
    return '@/assets/img/faces/';
  }
},

  /**
   * Chart data used to render stats, charts. Should be replaced with server data
   */
  data() {
    return {
      statsCards1: [
        {
          uzivatel: "Šílenec",
          prispevek: "Letní dobrodružství",
          footerText: "10. července 2021",
          footerIcon: "ti-calendar",
        },
        {
          uzivatel: "Záhadnice",
          prispevek: "Tajemství vesmíru",
          footerText: "5. srpna 2022",
          footerIcon: "ti-calendar",
        },
        {
          uzivatel: "Gurmán",
          prispevek: "Umění haute cuisine",
          footerText: "20. května 2020",
          footerIcon: "ti-calendar",
        },
        {
          uzivatel: "Archeoložka",
          prispevek: "Záhady starověkých civilizací",
          footerText: "12. listopadu 2019",
          footerIcon: "ti-calendar",
        },
        {
          uzivatel: "Melomaniak",
          prispevek: "Nejlepší momenty z koncertu",
          footerText: "27. dubna 2022",
          footerIcon: "ti-calendar",
        },
        {
          uzivatel: "Cestovatelka",
          prispevek: "Průvodce historickými památkami",
          footerText: "3. března 2021",
          footerIcon: "ti-calendar",
        },
      ],
    };
  },
};
</script>
<style>
</style>
