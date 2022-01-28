<template>
  <div>
    <Header />
    <v-container class="error">
      <v-row justify="end">
        <v-col md="4">
            Hello
        </v-col>
      </v-row>
    </v-container>
    <!-- <div >
      <h1 v-if="error.statusCode === 404">Page not found</h1>
      <h1 v-else>An error occurred</h1>
      <NuxtLink to="/">Home page</NuxtLink>
    </div> -->
    <Footer />
  </div>
</template>

<script>
export default {
  props: ["error"],
  layout: "error", // you can set a custom layout for the error page
};
</script>
<style scoped>
.error {
  padding-top: 100px;
}
</style>
