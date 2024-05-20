<template>
  <div>
    <AppHeader />
    <main class="p-4">
      <h1 class="text-2xl font-bold">Bienvenue à MadeInVert</h1>
      <p>Bienvenue sur notre site web dédié au jardinage.</p>
    </main>
    <AppFooter />
  </div>
</template>

<script>
import AppHeader from "@/components/AppHeader.vue";
import AppFooter from "@/components/AppFooter.vue";

export default {
  name: "HomePage",
  components: {
    AppHeader,
    AppFooter,
  },
};
</script>

<style scoped>
/* Styles spécifiques à la page d'accueil */
</style>
