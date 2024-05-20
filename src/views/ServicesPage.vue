<template>
  <div>
    <AppHeader />
    <main class="p-4">
      <h1 class="text-2xl font-bold mb-4">Nos Services</h1>
      <p>Découvrez nos services de jardinage.</p>
    </main>
    <AppFooter />
  </div>
</template>

<script>
import AppHeader from "@/components/AppHeader.vue";
import AppFooter from "@/components/AppFooter.vue";

export default {
  name: "ServicesPage",
  components: {
    AppHeader,
    AppFooter,
  },
};
</script>

<style scoped>
/* Styles spécifiques à la page des services */
</style>
