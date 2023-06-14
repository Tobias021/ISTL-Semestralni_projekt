<template>
  <card class="card-user">
    <div slot="image">
      <img src="@/assets/img/background.jpg" alt="..." />
    </div>
    <div>
      <div class="author">
        <img
          class="avatar border-white"
          src="@/assets/img/faces/face-2.jpg"
          alt="..."
        />
        <h4 style="color:white; margin-top: 10px" class="title">
          Janny Newak
          <br />
          <a href="#">
            <small>@TechMan</small>
          </a>
        </h4>
      </div>
      <p class="description text-center" style="color: white">
        "Kódy se mění,
        <br />
        algoritmy se tvoří,<br />
        technologie nás do budoucnosti vodí"
      </p>
    </div>
    <hr />
    <div class="text-center">
      <div class="row">
        <div
          v-for="(info, index) in details"
          :key="index"
          :class="getClasses(index)"
        >
          <h5>
            <nobr>{{ info.title }}</nobr>
            <br />
            <small><nobr>{{ info.subTitle }}</nobr></small>
          </h5>
        </div>
      </div>
    </div>
  </card>
</template>
<script>
export default {
  data() {
    return {
      details: [
        {
          title: "5",
          subTitle: "Viedeí",
        },
        {
          title: "3,8 GB",
          subTitle: "Využito",
        },
        {
          title: "70 $",
          subTitle: "Proplaceno",
        },
      ],
    };
  },
  methods: {
    getClasses(index) {
      var remainder = index % 3;
      if (remainder === 0) {
        return "col-lg-3 offset-lg-1";
      } else if (remainder === 2) {
        return "col-lg-4";
      } else {
        return "col-lg-3";
      }
    },
  },
};
</script>
<style></style>
