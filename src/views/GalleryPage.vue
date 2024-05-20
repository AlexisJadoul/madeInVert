<template>
  <div>
    <AppHeader />
    <main class="p-4">
      <h1 class="text-2xl font-bold mb-4">Galerie</h1>
      <p>
        Découvrez quelques-unes de nos réalisations en jardinage. Nous sommes
        fiers de chaque projet et de chaque jardin que nous avons transformé.
      </p>
      <div class="space-y-8 mt-8">
        <div
          v-for="n in 9"
          :key="n"
          :class="{
            'flex flex-col md:flex-row items-center bg-gray-200 rounded-lg overflow-hidden shadow-md': true,
            'md:flex-row-reverse': n % 2 === 0,
          }"
        >
          <img
            :src="`https://via.placeholder.com/300?text=Photo+${n}`"
            :alt="`Photo ${n}`"
            class="w-full md:w-1/3 h-48 object-cover"
          />
          <div class="p-4 w-full md:w-2/3">
            <h2 class="text-lg font-semibold">Projet de jardinage {{ n }}</h2>
            <p class="text-gray-600">
              Description du projet de jardinage {{ n }}...
            </p>
          </div>
        </div>
      </div>
    </main>
    <AppFooter />
  </div>
</template>

<script>
import AppHeader from "@/components/AppHeader.vue";
import AppFooter from "@/components/AppFooter.vue";

export default {
  name: "GalleryPage",
  components: {
    AppHeader,
    AppFooter,
  },
};
</script>

<style scoped>
/* Styles spécifiques à la page Galerie */
</style>
