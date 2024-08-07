<template>
  <!-- Promotions List -->
  <div class="mt-10 px-4 sm:px-6 lg:px-8">
    <h1 class="text-3xl font-bold text-gray-900 mb-6 text-center">Boonused ja Kampaaniad</h1>
    
    <!-- <Filter/> -->

    <div class="filter-panel">
    <!-- Category Filter -->
    <div class="filter-item">
      <label for="category" class="filter-label">Категории:</label>
      <select id="category" v-model="selectedCategory" @change="filterCourses" class="filter-select">
        <option value="">Все</option>
        <option v-for="category in categories" :key="category" :value="category">{{ category }}</option>
      </select>
    </div>
    
    <!-- Price Filter -->
    <div class="filter-item">
      <label for="price" class="filter-label">Цена:</label>
      <select id="price" v-model="selectedPrice" @change="filterCourses" class="filter-select">
        <option value="">Все</option>
        <option value="low">Низкая</option>
        <option value="medium">Средняя</option>
        <option value="high">Высокая</option>
      </select>
    </div>

    <!-- Other Filters -->
    <div class="filter-item">
      <label for="other" class="filter-label">Другие:</label>
      <select id="other" v-model="selectedOther" @change="filterCourses" class="filter-select">
        <option value="">Все</option>
        <option value="popular">Популярные</option>
        <option value="new">Новые</option>
        <option value="recommended">Рекомендуемые</option>
      </select>
    </div>

    <AppButton class="filter-button">Filter</AppButton>
  </div>


    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-6">
      <div v-for="promotion in promotions" :key="promotion.id" class="promotion-card bg-white shadow-md hover:shadow-xl transition-shadow duration-300 rounded-lg overflow-hidden">
        <img :src="promotion.image" :alt="promotion.title" class="w-full h-48 object-cover">
        <div class="p-4">
          <h3 class="text-lg font-semibold text-gray-800 mb-2">{{ promotion.title }}</h3>
          <p class="text-gray-600">{{ promotion.description }}</p>
          <nuxt-link :to="'/promotion/' + promotion.id" class="text-blue-500 hover:underline mt-4 inline-block">Узнать больше</nuxt-link>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
 import filter from '~/components/Filter.vue';
  export default {
    components: {filter},
  data() {
    return {
      categories: ['Разработка', 'Дизайн', 'Маркетинг', 'Бизнес'],
        selectedCategory: '',
        selectedPrice: '',
        selectedOther: '',
      promotions: [
        { id: 1, title: 'Промо 1', description: 'Описание промо 1', image: 'https://via.placeholder.com/300x200' },
        { id: 2, title: 'Промо 2', description: 'Описание промо 2', image: 'https://via.placeholder.com/300x200' },
        { id: 3, title: 'Промо 3', description: 'Описание промо 3', image: 'https://via.placeholder.com/300x200' },
        { id: 4, title: 'Промо 4', description: 'Описание промо 4', image: 'https://via.placeholder.com/300x200' },
        { id: 5, title: 'Промо 5', description: 'Описание промо 5', image: 'https://via.placeholder.com/300x200' },
        { id: 6, title: 'Промо 6', description: 'Описание промо 6', image: 'https://via.placeholder.com/300x200' },
        { id: 7, title: 'Промо 7', description: 'Описание промо 7', image: 'https://via.placeholder.com/300x200' },
        { id: 8, title: 'Промо 8', description: 'Описание промо 8', image: 'https://via.placeholder.com/300x200' }
      ]
    };
    
  },
  methods: {
      filterCourses() {
        // Логика фильтрации курсов на основе выбранных параметров
        console.log('Фильтрация по категориям:', this.selectedCategory);
        console.log('Фильтрация по цене:', this.selectedPrice);
        console.log('Фильтрация по другим параметрам:', this.selectedOther);
      }
    }
};
</script>

<style scoped>

.filter-panel {
  background: linear-gradient(135deg, #f0f0f0, #d6d6d6);
  border-radius: 12px;
  padding: 2rem;
  margin-bottom: 1.5rem;
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  box-shadow: 0 8px 15px rgba(0, 0, 0, 0.1);
}

.filter-item {
  flex: 1;
  min-width: 200px;
  background: #fff;
  border: 2px solid #e0e0e0;
  border-radius: 8px;
  padding: 0.75rem;
  position: relative;
}

.filter-label {
  font-weight: bold;
  color: #333;
  margin-bottom: 0.5rem;
  display: block;
  font-size: 1rem;
}

.filter-select {
  width: 100%;
  padding: 0.5rem;
  border-radius: 8px;
  border: 2px solid #ccc;
  font-size: 1rem;
  color: #333;
  background-color: #fafafa;
  transition: border-color 0.3s, background-color 0.3s;
}

.filter-select:focus {
  border-color: #007bff;
  background-color: #fff;
  outline: none;
}

.filter-button {
  margin-top: 1rem;
  background: #007bff;
  color: #fff;
  padding: 0.75rem 1.5rem;
  border: none;
  border-radius: 8px;
  font-size: 1rem;
  cursor: pointer;
  transition: background-color 0.3s, transform 0.2s;
}

.filter-button:hover {
  background-color: #0056b3;
}

.filter-button:active {
  transform: scale(0.98);
}

.promotion-card {
  transition: transform 0.3s;
}
.promotion-card:hover {
  transform: translateY(-5px);
}
</style>
