<template>
  <div class="container mx-auto px-4 py-8">
    <!-- User Profile -->
    <div class="profile-header mb-8 flex flex-col lg:flex-row items-center lg:items-start">
      <div class="profile-avatar w-full lg:w-1/3 lg:pr-8 mb-6 lg:mb-0 flex justify-center">
        <img :src="user.avatar" :alt="user.name" class="w-32 h-32 rounded-full shadow-lg">
      </div>
      <div class="profile-info w-full lg:w-2/3">
        <h1 class="text-3xl font-bold text-gray-900 mb-4">{{ user.name }}</h1>
        <p class="text-gray-700 mb-4">Email: <span class="font-semibold">{{ user.email }}</span></p>
        <p class="text-gray-700 mb-6">Дата регистрации: <span class="font-semibold">{{ user.registrationDate }}</span></p>
        <button class="btn-primary">Редактировать профиль</button>
      </div>
    </div>
    
    <!-- Purchased Courses -->
    <div class="purchased-courses mb-8">
      <h2 class="text-2xl font-bold text-gray-900 mb-4">Купленные курсы</h2>
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
        <div v-for="course in purchasedCourses" :key="course.id" class="course-card bg-white shadow-lg rounded-lg p-4">
          <img :src="course.image" :alt="course.title" class="w-full h-32 object-cover rounded-lg mb-4">
          <h3 class="text-lg font-semibold text-gray-900 mb-2">{{ course.title }}</h3>
          <p class="text-gray-600 mb-2">{{ course.description }}</p>
          <NuxtLink :to="'/courses/' + course.id" class="text-teal-500 hover:underline">Перейти к курсу</NuxtLink>
        </div>
      </div>
    </div>
    
    <!-- Account Settings -->
    <div class="account-settings">
      <h2 class="text-2xl font-bold text-gray-900 mb-4">Настройки аккаунта</h2>
      <div class="settings-form bg-white shadow-lg rounded-lg p-6">
        <div class="mb-4">
          <label for="change-password" class="block text-gray-700 font-semibold mb-2">Сменить пароль:</label>
          <input type="password" id="change-password" v-model="password" placeholder="Введите новый пароль" class="form-input block w-full">
        </div>
        <div class="mb-4">
          <label for="email-notifications" class="flex items-center">
            <input type="checkbox" id="email-notifications" v-model="emailNotifications" class="form-checkbox">
            <span class="ml-2 text-gray-700">Получать уведомления по email</span>
          </label>
        </div>
        <button @click="saveSettings" class="btn-primary">Сохранить настройки</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      user: {
        name: 'Имя пользователя',
        email: 'user@example.com',
        registrationDate: '01.01.2024',
        avatar: 'https://via.placeholder.com/150'
      },
      purchasedCourses: [
        {
          id: 1,
          title: 'Курс 1',
          description: 'Описание курса 1',
          image: 'https://via.placeholder.com/400x250'
        },
        {
          id: 2,
          title: 'Курс 2',
          description: 'Описание курса 2',
          image: 'https://via.placeholder.com/400x250'
        },
        {
          id: 3,
          title: 'Курс 3',
          description: 'Описание курса 3',
          image: 'https://via.placeholder.com/400x250'
        }
      ],
      password: '',
      emailNotifications: true
    };
  },
  methods: {
    saveSettings() {
      // Логика сохранения настроек
      alert('Настройки сохранены');
    }
  }
};
</script>

<style scoped>
.container {
  max-width: 1200px;
  margin: 0 auto;
}
.profile-header {
  display: flex;
  flex-direction: column;
}
.profile-avatar img {
  width: 128px;
  height: 128px;
  border-radius: 50%;
}
.btn-primary {
  background-color: #4CAF50;
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}
.btn-primary:hover {
  background-color: #45a049;
}
.course-card img {
  border-radius: 0.375rem;
}
.form-input {
  border: 1px solid #ddd;
  border-radius: 0.375rem;
  padding: 0.5rem 1rem;
}
.settings-form {
  padding: 1.5rem;
}
</style>
