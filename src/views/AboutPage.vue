<template>
  <div>
    <AppHeader />
    <main class="p-4">
      <h1 class="text-2xl font-bold mb-4">À propos de MadeInVert</h1>
      <p>
        Bienvenue chez MadeInVert, votre partenaire de confiance pour tous vos
        besoins en jardinage. Fondée par un passionné de jardinage depuis son
        plus jeune âge, notre entreprise se consacre à transformer vos espaces
        verts en véritables havres de paix.
      </p>
      <p class="mt-4">
        Depuis notre enfance, nous avons toujours été fascinés par la beauté de
        la nature. Notre fondateur a passé de nombreuses heures à explorer les
        jardins et à apprendre les secrets des plantes et des fleurs. Cette
        passion a naturellement évolué en une carrière dédiée à l'art du
        jardinage.
      </p>
      <p class="mt-4">
        Chez MadeInVert, nous croyons que chaque jardin est unique et mérite une
        attention particulière. Nous offrons une gamme complète de services, y
        compris la conception de jardins, l'entretien, et des conseils
        personnalisés pour vous aider à créer et maintenir un espace vert
        magnifique et sain.
      </p>
      <p class="mt-4">
        Rejoignez-nous dans notre aventure pour créer des jardins
        extraordinaires. Nous sommes impatients de travailler avec vous et de
        partager notre passion pour le jardinage.
      </p>
    </main>
    <AppFooter />
  </div>
</template>

<script>
import AppHeader from "@/components/AppHeader.vue";
import AppFooter from "@/components/AppFooter.vue";

export default {
  name: "AboutPage",
  components: {
    AppHeader,
    AppFooter,
  },
};
</script>

<style scoped>
/* Styles spécifiques à la page À propos */
</style>
