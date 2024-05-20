<template>
  <div>
    <AppHeader />
    <main class="p-4">
      <h1 class="text-2xl font-bold mb-4">Contactez-nous</h1>
      <p>
        Si vous avez des questions, des suggestions ou si vous souhaitez en
        savoir plus sur nos services, n'hésitez pas à nous contacter. Nous
        serons ravis de vous aider.
      </p>
      <form class="mt-8 space-y-4">
        <div>
          <label for="name" class="block text-sm font-medium text-gray-700"
            >Nom</label
          >
          <input
            type="text"
            id="name"
            name="name"
            class="mt-1 p-2 border border-gray-300 rounded-md w-full"
          />
        </div>
        <div>
          <label for="email" class="block text-sm font-medium text-gray-700"
            >Email</label
          >
          <input
            type="email"
            id="email"
            name="email"
            class="mt-1 p-2 border border-gray-300 rounded-md w-full"
          />
        </div>
        <div>
          <label for="message" class="block text-sm font-medium text-gray-700"
            >Message</label
          >
          <textarea
            id="message"
            name="message"
            rows="4"
            class="mt-1 p-2 border border-gray-300 rounded-md w-full"
          ></textarea>
        </div>
        <div>
          <button
            type="submit"
            class="bg-green-600 text-white py-2 px-4 rounded-md hover:bg-green-700"
          >
            Envoyer
          </button>
        </div>
      </form>
    </main>
    <AppFooter />
  </div>
</template>

<script>
import AppHeader from "@/components/AppHeader.vue";
import AppFooter from "@/components/AppFooter.vue";

export default {
  name: "ContactPage",
  components: {
    AppHeader,
    AppFooter,
  },
};
</script>

<style scoped>
/* Styles spécifiques à la page Contact */
</style>
