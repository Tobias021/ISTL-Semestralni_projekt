<template>
  <card class="card" :title="title">
    <div>
      <ul class="list-unstyled team-members">
        <li>
          <div class="row" v-for="member in members" :key="member.name">
            <div class="col-3">
              <div class="avatar">
                <img
                  :src="member.image"
                  alt="Circle Image"
                  class="rounded img-fluid"
                />
              </div>
            </div>
            <div class="col-6">
              {{ member.name }}
              <br />
              <span :class="getStatusClass(member.status)">
                <small>{{ member.status }}</small>
              </span>
            </div>

            <div class="col-3">
              <p-button type="success" outline icon
              @click.native="notifyVue(`top`, `right`)">
                <i class="fa fa-envelope"></i>
              </p-button>
            </div>
          </div>
        </li>
      </ul>
    </div>
  </card>
</template>
<script>
import NotificationTemplate from "@/pages/Notifications/NotificationTemplate.vue";

export default {
  data() {
    return {
      title: "Team members",
      members: [
        {
          image: require("@/assets/img/faces/face-0.jpg"),
          name: "John Mariánek",
          status: "Offline",
        },
        {
          image: require("@/assets/img/faces/face-1.jpg"),
          name: "Jaroslav Bašta",
          status: "Online",
        },
        {
          image: require("@/assets/img/faces/face-1.jpg"),
          name: "Crafák",
          status: "Nerušit",
        },
      ],
    };
  },
  methods: {
    getStatusClass(status) {
      switch (status) {
        case "Offline":
          return "text-muted";
        case "Online":
          return "text-success";
        case "Nerušit":
          return "text-danger";
        default:
          return "text-success";
      }
    },
    notifyVue(verticalAlign, horizontalAlign) {
      const color = Math.floor(Math.random() * 4 + 1);
      this.$notify({
        component: NotificationTemplate,
        icon: "ti-gift",
        horizontalAlign: horizontalAlign,
        verticalAlign: verticalAlign,
        type: this.type[color],
      });
    },
  },
};
</script>
<style></style>
