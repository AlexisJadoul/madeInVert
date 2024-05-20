<template>
  <header class="bg-green-600 text-white p-4">
    <div class="container mx-auto flex justify-between items-center">
      <div
        @mouseover="hoverLogo = true"
        @mouseleave="hoverLogo = false"
        class="text-2xl font-bold transition-all duration-700 ease-in-out"
      >
        <span v-if="!hoverLogo">MIV</span>
        <span v-else>MadeInVert</span>
      </div>
      <nav class="flex-1 text-center">
        <!-- Menu desktop -->
        <ul class="hidden md:flex space-x-8 justify-center">
          <li>
            <router-link to="/" class="hover:underline">Accueil</router-link>
          </li>
          <li>
            <router-link to="/services" class="hover:underline"
              >Services</router-link
            >
          </li>
          <li>
            <router-link to="/gallery" class="hover:underline"
              >Galerie</router-link
            >
          </li>
          <li>
            <router-link to="/about" class="hover:underline"
              >À propos</router-link
            >
          </li>
          <li>
            <router-link to="/contact" class="hover:underline"
              >Contact</router-link
            >
          </li>
        </ul>
        <!-- Menu mobile -->
        <div class="md:hidden">
          <button @click="toggleMenu" class="focus:outline-none">
            <svg
              v-if="!isMenuOpen"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
              class="w-6 h-6"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M4 6h16M4 12h16m-7 6h7"
              />
            </svg>
            <svg
              v-else
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
              class="w-6 h-6"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M6 18L18 6M6 6l12 12"
              />
            </svg>
          </button>
        </div>
      </nav>
    </div>
    <!-- Mobile menu -->
    <ul v-if="isMenuOpen" class="md:hidden bg-green-700 p-4 space-y-4">
      <li>
        <router-link to="/" class="block hover:underline">Accueil</router-link>
      </li>
      <li>
        <router-link to="/services" class="block hover:underline"
          >Services</router-link
        >
      </li>
      <li>
        <router-link to="/gallery" class="block hover:underline"
          >Galerie</router-link
        >
      </li>
      <li>
        <router-link to="/about" class="block hover:underline"
          >À propos</router-link
        >
      </li>
      <li>
        <router-link to="/contact" class="block hover:underline"
          >Contact</router-link
        >
      </li>
    </ul>
  </header>
</template>

<script>
export default {
  name: "AppHeader",
  data() {
    return {
      isMenuOpen: false,
      hoverLogo: false,
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
  },
};
</script>

<style scoped>
/* Styles supplémentaires si nécessaire */
</style>
