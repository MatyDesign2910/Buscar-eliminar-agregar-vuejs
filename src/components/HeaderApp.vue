<template>
  <div id="header">
    <v-app-bar app color="primary" dark>
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2 mt-8"
          contain
          src="../assets/logo-petshop.png"
          transition="scale-transition"
          width="100"
        />
      </div>

      <v-spacer></v-spacer>
    </v-app-bar>
  </div>
</template>

<script>

export default {
  name: "HeaderApp",
}

</script>
