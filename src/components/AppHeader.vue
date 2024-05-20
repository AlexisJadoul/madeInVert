<template>
  <header class="bg-green-600 text-white p-4">
    <div class="container mx-auto flex justify-between items-center">
      <div
        @mouseover="hoverLogo = true"
        @mouseleave="hoverLogo = false"
        class="text-2xl font-bold transition-all duration-700 ease-in-out"
        style="width: 200px; white-space: nowrap"
      >
        <span id="text"></span>
        <span id="console" class="console-underscore">_</span>
      </div>
      <nav class="flex-1 text-center">
        <!-- Menu desktop -->
        <ul class="nav-links flex space-x-8 justify-center">
          <li>
            <router-link to="/" class="transition-link">Accueil</router-link>
          </li>
          <li>
            <router-link to="/services" class="transition-link"
              >Services</router-link
            >
          </li>
          <li>
            <router-link to="/gallery" class="transition-link"
              >Galerie</router-link
            >
          </li>
          <li>
            <router-link to="/about" class="transition-link"
              >À propos</router-link
            >
          </li>
          <li>
            <router-link to="/contact" class="transition-link"
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
        <router-link to="/" class="block transition-link">Accueil</router-link>
      </li>
      <li>
        <router-link to="/services" class="block transition-link"
          >Services</router-link
        >
      </li>
      <li>
        <router-link to="/gallery" class="block transition-link"
          >Galerie</router-link
        >
      </li>
      <li>
        <router-link to="/about" class="block transition-link"
          >À propos</router-link
        >
      </li>
      <li>
        <router-link to="/contact" class="block transition-link"
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
  mounted() {
    this.consoleText(["MIV", "MadeInVert"], "text", ["#fff"]);
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
    consoleText(words, id, colors) {
      if (colors === undefined) colors = ["#fff"];
      var visible = true;
      var con = document.getElementById("console");
      var letterCount = 1;
      var x = 1;
      var waiting = false;
      var target = document.getElementById(id);
      if (!target || !con) return; // Vérifier si les éléments existent
      target.setAttribute("style", "color:" + colors[0]);
      window.setInterval(function () {
        if (letterCount === 0 && waiting === false) {
          waiting = true;
          target.innerHTML = words[0].substring(0, letterCount);
          window.setTimeout(function () {
            var usedColor = colors.shift();
            colors.push(usedColor);
            var usedWord = words.shift();
            words.push(usedWord);
            x = 1;
            target.setAttribute("style", "color:" + colors[0]);
            letterCount += x;
            waiting = false;
          }, 1000);
        } else if (letterCount === words[0].length + 1 && waiting === false) {
          waiting = true;
          window.setTimeout(function () {
            x = -1;
            letterCount += x;
            waiting = false;
          }, 1000);
        } else if (waiting === false) {
          target.innerHTML = words[0].substring(0, letterCount);
          letterCount += x;
        }
      }, 120);
      window.setInterval(function () {
        if (visible === true) {
          con.className = "console-underscore hidden";
          visible = false;
        } else {
          con.className = "console-underscore";
          visible = true;
        }
      }, 400);
    },
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css?family=Khula:700");
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap");

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Poppins", sans-serif;
}

.hidden {
  opacity: 0;
}

.console-container {
  font-family: "Khula", sans-serif;
  font-size: 2em;
  text-align: center;
  display: block;
  color: white;
}

.console-underscore {
  display: inline-block;
  position: relative;
  top: -0.14em;
  left: 10px;
}

.nav-links {
  display: flex;
  align-items: center;
  padding: 20px 15px;
}

.nav-links li {
  list-style: none;
  margin: 0 12px;
}

.nav-links li a {
  position: relative;
  color: #fff;
  font-size: 20px;
  font-weight: 500;
  padding: 6px 0;
  text-decoration: none;
}

.nav-links li a:before {
  content: "";
  position: absolute;
  bottom: 0;
  left: 0;
  height: 3px;
  width: 0%;
  background: #34efdf;
  border-radius: 12px;
  transition: all 0.4s ease;
}

.nav-links li a:hover:before {
  width: 100%;
}

.transition-link {
  position: relative;
  color: #fff;
  font-size: 20px;
  font-weight: 500;
  padding: 6px 0;
  text-decoration: none;
}

.transition-link:before {
  content: "";
  position: absolute;
  bottom: 0;
  left: 0;
  height: 3px;
  width: 0%;
  background: #34efdf;
  border-radius: 12px;
  transition: all 0.4s ease;
}

.transition-link:hover:before {
  width: 100%;
}
</style>
