<template>
  <card class="card" title="Edit Profile">
    <div>
      <form @submit.prevent>
        <div class="row">
          <div class="col-md-5">
            <fg-input
              type="text"
              label="Uživatelské jméno"
              placeholder="Uživ. jm."
              v-model="user.username"
            >
            </fg-input>
          </div>
          <div class="col-md-7">
            <fg-input
              type="email"
              label="E-mail"
              placeholder="moje.jmeno@seznam.cz"
              v-model="user.email"
            >
            </fg-input>
          </div>
        </div>

        <div class="row">
          <div class="col-md-6">
            <fg-input
              type="text"
              label="Jméno"
              placeholder="Adámek"
              v-model="user.firstName"
            >
            </fg-input>
          </div>
          <div class="col-md-6">
            <fg-input
              type="text"
              label="Příjmení"
              placeholder="Vávrů"
              v-model="user.lastName"
            >
            </fg-input>
          </div>
        </div>

        <div class="row">
          <div class="col-md-12">
            <fg-input
              type="text"
              label="Adresa"
              placeholder="Palachova 1211"
              v-model="user.address"
            >
            </fg-input>
          </div>
        </div>

        <div class="row">
          <div class="col-md-4">
            <fg-input
              type="text"
              label="Město"
              placeholder="Jindřichův hradec"
              v-model="user.city"
            >
            </fg-input>
          </div>
          <div class="col-md-4">
            <fg-input
              type="text"
              label="Země"
              placeholder="Česká republika"
              v-model="user.country"
            >
            </fg-input>
          </div>
          <div class="col-md-4">
            <fg-input
              type="number"
              label="PSČ"
              placeholder="500 00"
              v-model="user.postalCode"
            >
            </fg-input>
          </div>
        </div>

        <div class="row">
          <div class="col-md-12">
            <div class="form-group">
              <label>O mně</label>
              <textarea
                rows="5"
                class="form-control border-input"
                placeholder="Místo pro Váš oslnivý příběh!"
                v-model="user.aboutMe"
              >
              </textarea>
            </div>
          </div>
        </div>
        <div class="text-center">
          <p-button type="info" round @click.native.prevent="updateProfile">
            Update Profile
          </p-button>
        </div>
        <div class="clearfix"></div>
      </form>
    </div>
  </card>
</template>
<script>
export default {
  data() {
    return {
      user: {
        username: "Janek32",
        email: "",
        firstName: "Janek",
        lastName: "Novák",
        address: "",
        city: "Liberec",
        postalCode: "50601",
        aboutMe: ``,
      },
    };
  },
  methods: {
    updateProfile() {
      alert("Your data: " + JSON.stringify(this.user));
    },
  },
};
</script>
<style></style>
