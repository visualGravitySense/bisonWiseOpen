<template>
  <header class="bg-gray-900 text-white">
    <div class="container mx-auto px-4 py-4 flex items-center justify-between">
      <!-- Логотип -->
      <div class="logo">
        <nuxt-link to="/">
          <img src="@/static/logo.png" alt="🦬BisonWise" class="h-12" />
        </nuxt-link>
      </div>

      <!-- Поиск -->
       
      <!-- <div class="flex-grow max-w-md mx-4">
        <AppSearch
          type="text"
          id="search"
          required
          placeholder="Поиск..."
          :icon="true"
          class="w-full p-2 border border-gray-700 rounded-lg bg-gray-800 text-white placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-yellow-400"
        />
      </div> -->

      <!-- Меню -->
      <nav class="hidden md:flex items-center space-x-6">
        <nuxt-link v-for="link in links" :key="link.title" :to="link.url" class="text-gray-300 hover:text-yellow-400 transition duration-300">
          {{ link.title }}
        </nuxt-link>
        <nuxt-link to="/login" class="text-yellow-400 border border-yellow-400 px-4 py-2 rounded-md hover:bg-yellow-400 hover:text-gray-900 transition duration-300">Log in</nuxt-link>
        <nuxt-link to="/signup" class="bg-green-600 text-white px-4 py-2 rounded-md hover:bg-green-500 transition duration-300">Join now</nuxt-link>
      </nav>

      <!-- Бургер-меню -->
      <div class="md:hidden flex items-center space-x-4">
        <div class="text-gray-300 hover:text-yellow-400 transition duration-300" @click="toggleMenu">
          <span class="burger-bar"></span>
          <span class="burger-bar"></span>
          <span class="burger-bar"></span>
        </div>
      </div>
    </div>

    <!-- Мобильное меню -->
    <div class="mobile-menu fixed top-0 left-0 w-full bg-gray-900 text-white p-6 space-y-4 md:hidden transition-transform transform translate-y-full" :class="{ 'translate-y-0': isMenuOpen }">
      <nuxt-link v-for="link in links" :key="link.title" :to="link.url" class="block text-gray-300 hover:text-yellow-400 transition duration-300">
        {{ link.title }}
      </nuxt-link>
      <nuxt-link to="/login" class="text-yellow-400 border border-yellow-400 px-4 py-2 rounded-md hover:bg-yellow-400 hover:text-gray-900 transition duration-300">Log in</nuxt-link>
      <nuxt-link to="/signup" class="bg-green-600 text-white px-4 py-2 rounded-md hover:bg-green-500 transition duration-300">Join now</nuxt-link>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      links: [
        { title: 'Категории', url: '/categories' },
        { title: 'О курсах', url: '/teachers' },
        { title: 'О нас', url: '/about' },
      ],
      isMenuOpen: false
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    }
  }
};
</script>

<style scoped>
.burger-bar {
  display: block;
  width: 30px;
  height: 3px;
  background-color: #fff;
  margin: 6px 0;
  transition: 0.4s;
}

.burger-bar:nth-child(1) {
  transform: rotate(0);
}

.burger-bar:nth-child(2) {
  transform: rotate(0);
}

.burger-bar:nth-child(3) {
  transform: rotate(0);
}

.mobile-menu {
  transform: translateY(100%);
}

.mobile-menu.open {
  transform: translateY(0);
}
</style>
