<template>
  <div class="relativeBgAbout flex items-top justify-center min-h-screen bg-gray-100 sm:items-center sm:pt-0">
    <div class="max-w-4xl mx-auto sm:px-6 lg:px-8 bg-glass p-8">
      <div class="mt-8 overflow-hidden sm:rounded-lg p-6 anti-design-container">
        <Intro
          title="Ваша дорога к успеху начинается здесь в автошколе"
          topic="Почему выбирают нас"
          paragraph="Мы предлагаем обучение с профессиональными инструкторами, которые используют персонализированные методы для эффективного освоения вождения. Учитесь на современных автомобилях с передовыми системами безопасности, получая максимум комфорта и уверенности. Наши пакетные предложения и скидки делают обучение доступным и выгодным. Отличные отзывы наших выпускников подтверждают высокое качество нашего сервиса."
        /><br>
      </div>
      <benefitsList :promotions="postsLoaded" />
    </div>
  </div>
</template>

<script>

import Intro from '~/components/UI/Intro.vue';
import benefitsList from '~/components/Benefits/BenefitsList.vue';
export default {
  components: {
   Intro, benefitsList
  },
  methods: {
    onSubmit (user) {
      console.log('User added!')

    }
  },
  computed: {
    postsLoaded () {
      return this.$store.getters.getPostsLoaded
    }
  },
    name: 'About'
  }
</script>


<style>

.relativeBgAbout {
  background-image: url('@/assets/img/default_bg.png'); /* Укажите путь к вашему изображению */
  background-size: cover;
  background-position: center;
}

.bg-glass {
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(3px);
  -webkit-backdrop-filter: blur(3px);
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.anti-design-container {
  background: linear-gradient(135deg, #ffdd00, #ff5e00, #ff0080, #ff00ff);
  color: #1a1a1a;
  font-family: 'Comic Sans MS', cursive, sans-serif;
  border: 3px dashed #ff00ff;
  border-radius: 20px;
  padding: 20px;
  text-align: center;
  transform: rotate(-2deg);
}

.anti-design-container h1, .anti-design-container p {
  color: #1a1a1a;
  text-shadow: 2px 2px 0 #ff00ff;
}

.anti-design-container h1 {
  font-size: 2.5rem;
}

.anti-design-container p {
  font-size: 1.2rem;
}

.anti-design-container a {
  color: #00ff00;
  text-decoration: underline;
  font-weight: bold;
}

.anti-design-container a:hover {
  color: #ff0000;
}

.anti-design-container::before {
  content: '😎';
  font-size: 3rem;
  position: absolute;
  top: -10px;
  left: -10px;
}

.anti-design-container::after {
  content: '🔥';
  font-size: 3rem;
  position: absolute;
  bottom: -10px;
  right: -10px;
}

hstack {
  display: flex;
  flex-direction: row;
  gap: 1rem;
}


</style>
