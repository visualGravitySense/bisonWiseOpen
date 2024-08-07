<template>
    <div class="filter-panel bg-white shadow-md rounded-lg p-4 mb-6 flex flex-col sm:flex-row items-center justify-between">
      <!-- Category Filter -->
      <div class="flex items-center mb-4 sm:mb-0">
        <label for="category" class="mr-2 text-gray-700 font-semibold">Категории:</label>
        <select id="category" v-model="selectedCategory" @change="filterCourses" class="form-select block w-full sm:w-auto mt-1 text-gray-900">
          <option value="">Все</option>
          <option v-for="category in categories" :key="category" :value="category">{{ category }}</option>
        </select>
      </div>
      <!-- Price Filter -->
      <div class="flex items-center mb-4 sm:mb-0">
        <label for="price" class="mr-2 text-gray-700 font-semibold">Цена:</label>
        <select id="price" v-model="selectedPrice" @change="filterCourses" class="form-select block w-full sm:w-auto mt-1 text-gray-900">
          <option value="">Все</option>
          <option value="low">Низкая</option>
          <option value="medium">Средняя</option>
          <option value="high">Высокая</option>
        </select>
      </div>
      <!-- Other Filters -->
      <div class="flex items-center">
        <label for="other" class="mr-2 text-gray-700 font-semibold">Другие:</label>
        <select id="other" v-model="selectedOther" @change="filterCourses" class="form-select block w-full sm:w-auto mt-1 text-gray-900">
          <option value="">Все</option>
          <option value="popular">Популярные</option>
          <option value="new">Новые</option>
          <option value="recommended">Рекомендуемые</option>
        </select>
      </div>
    </div>
  </template>
  
<script>
//   import filter from '~/components/Filter.vue';
  export default {
    // components: {filter},
    data() {
      return {
        categories: ['Разработка', 'Дизайн', 'Маркетинг', 'Бизнес'],
        selectedCategory: '',
        selectedPrice: '',
        selectedOther: ''
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
  .form-select {
    border: 1px solid #ddd;
    border-radius: 0.375rem;
    padding: 0.5rem 1rem;
    appearance: none;
    background-color: #fff;
    background-image: none;
    background-position: right 0.5rem center;
    background-repeat: no-repeat;
    background-size: 1.5em 1.5em;
    transition: border-color 0.2s;
  }
  .form-select:focus {
    border-color: #a0aec0;
    outline: none;
    box-shadow: 0 0 0 1px #a0aec0;
  }
  </style>
  