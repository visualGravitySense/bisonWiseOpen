<template>
  <div class="hero-section">
    <div class="hero-background">
      <div class="hero-content">
        <p class="welcome-text">
          <code>Добро пожаловать в автошколу Виктория</code>
        </p>

        <h1 class="hero-title">
          Научитесь водить с
          <span class="confidence">уверенностью</span>
        </h1>

        <p class="description">
          Профессиональные инструктора и гибкий график занятий.
          <a href="" target="_blank" class="register-link">Зарегистрируйтесь</a> сегодня и начните свой путь к безопасному вождению.
        </p>
      </div>

      <!-- <CategoriesList :admin="true" :cards="cards" class="categories-list"/> -->
    </div>
  </div>
</template>

<script>
import CategoriesList from "~/components/Categories/CategoriesList.vue";

export default {
  components: {
    CategoriesList
  },
  data() {
    return {
      cards: [
        { id: 1, title: 'Категория A', description: 'Описание категории A...', image: require('@/assets/img/category_a.png') },
        { id: 2, title: 'Категория B', description: 'Описание категории B...', image: require('@/assets/img/automat_pic.png') },
        { id: 3, title: 'Категория C', description: 'Описание категории C...', image: require('@/assets/img/category_aa.png') }
      ]
    };
  },
  name: 'HeroSection'
}
</script>

<style scoped>
.hero-section {
  position: relative;
  overflow: hidden;
  padding: 6rem 2rem;
  text-align: center;
  color: #fff;
  background: linear-gradient(135deg, rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.3)), url('@/assets/img/default_bg.png') no-repeat center center/cover;
}

.hero-background {
  position: relative;
  z-index: 1;
}

.hero-content {
  position: relative;
  max-width: 800px;
  margin: 0 auto;
  padding: 2rem;
  background: rgba(0, 0, 0, 0.5);
  border-radius: 12px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.3);
}

.welcome-text {
  font-size: 1.25rem;
  margin-bottom: 1rem;
  color: #ff94e3;
  font-weight: 600;
}

.welcome-text code {
  background-color: #5d3753;
  color: #ff94ff;
  font-size: 1rem;
  padding: 0.5rem;
  border-radius: 8px;
}

.hero-title {
  font-size: 3rem;
  line-height: 1.2;
  font-weight: 800;
  margin-bottom: 1rem;
  color: #ffffff;
}

.hero-title .confidence {
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.7);
  color: #ffdc00;
}

.description {
  font-size: 1.125rem;
  margin-bottom: 2rem;
  color: #e0e0e0;
}

.register-link {
  color: #41de73;
  text-decoration: none;
  font-weight: 700;
  transition: color 0.3s ease, text-shadow 0.3s ease;
}

.register-link:hover {
  text-decoration: underline;
  color: #ff5200;
  text-shadow: 0 2px 4px rgba(255, 82, 0, 0.8);
}

.categories-list {
  position: absolute;
  bottom: 0;
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  justify-content: center;
  gap: 1rem;
}
</style>
