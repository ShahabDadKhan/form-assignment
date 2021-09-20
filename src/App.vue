<template>
  <v-app>
    <v-main>
      <the-form />
    </v-main>
  </v-app>
</template>

<script>
import TheForm from "./components/TheForm.vue";
export default {
  components: {
    TheForm,
  },
  name: "App",

  data: () => ({
    //
  }),
};
</script>
