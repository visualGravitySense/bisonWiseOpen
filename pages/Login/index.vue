<template>
    <div class="container mx-auto px-4 py-8">
      <div class="max-w-lg mx-auto bg-white shadow-lg rounded-lg p-8">
        <!-- Регистрация -->
        <div v-if="currentTab === 'register'" class="mb-8">
          <h1 class="text-2xl font-bold text-gray-900 mb-6">Регистрация</h1>
          <form @submit.prevent="register">
            <div class="mb-4">
              <label for="register-name" class="block text-gray-700 font-semibold mb-2">Имя:</label>
              <input type="text" id="register-name" v-model="registerForm.name" placeholder="Введите ваше имя" class="form-input">
            </div>
            <div class="mb-4">
              <label for="register-email" class="block text-gray-700 font-semibold mb-2">Email:</label>
              <input type="email" id="register-email" v-model="registerForm.email" placeholder="Введите ваш email" class="form-input">
            </div>
            <div class="mb-4">
              <label for="register-password" class="block text-gray-700 font-semibold mb-2">Пароль:</label>
              <input type="password" id="register-password" v-model="registerForm.password" placeholder="Введите ваш пароль" class="form-input">
            </div>
            <button type="submit" class="btn-primary">Регистрация</button>
          </form>
          <p class="mt-4 text-gray-600">
            Уже есть аккаунт? <a @click="currentTab = 'login'" class="text-teal-500 cursor-pointer">Войти</a>
          </p>
        </div>
        
        <!-- Вход -->
        <div v-if="currentTab === 'login'" class="mb-8">
          <h1 class="text-2xl font-bold text-gray-900 mb-6">Вход</h1>
          <form @submit.prevent="login">
            <div class="mb-4">
              <label for="login-email" class="block text-gray-700 font-semibold mb-2">Email:</label>
              <input type="email" id="login-email" v-model="loginForm.email" placeholder="Введите ваш email" class="form-input">
            </div>
            <div class="mb-4">
              <label for="login-password" class="block text-gray-700 font-semibold mb-2">Пароль:</label>
              <input type="password" id="login-password" v-model="loginForm.password" placeholder="Введите ваш пароль" class="form-input">
            </div>
            <button type="submit" class="btn-primary">Войти</button>
          </form>
          <p class="mt-4 text-gray-600">
            Нет аккаунта? <a @click="currentTab = 'register'" class="text-teal-500 cursor-pointer">Зарегистрироваться</a>
          </p>
          <p class="mt-4 text-gray-600">
            <a @click="currentTab = 'forgot'" class="text-teal-500 cursor-pointer">Забыли пароль?</a>
          </p>
        </div>
        
        <!-- Восстановление пароля -->
        <div v-if="currentTab === 'forgot'">
          <h1 class="text-2xl font-bold text-gray-900 mb-6">Восстановление пароля</h1>
          <form @submit.prevent="forgotPassword">
            <div class="mb-4">
              <label for="forgot-email" class="block text-gray-700 font-semibold mb-2">Email:</label>
              <input type="email" id="forgot-email" v-model="forgotForm.email" placeholder="Введите ваш email" class="form-input">
            </div>
            <button type="submit" class="btn-primary">Восстановить пароль</button>
          </form>
          <p class="mt-4 text-gray-600">
            <a @click="currentTab = 'login'" class="text-teal-500 cursor-pointer">Назад к входу</a>
          </p>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        currentTab: 'login', // 'login', 'register', or 'forgot'
        registerForm: {
          name: '',
          email: '',
          password: ''
        },
        loginForm: {
          email: '',
          password: ''
        },
        forgotForm: {
          email: ''
        }
      };
    },
    methods: {
      register() {
        // Логика регистрации
        alert('Регистрация выполнена');
      },
      login() {
        // Логика входа
        alert('Вход выполнен');
      },
      forgotPassword() {
        // Логика восстановления пароля
        alert('Инструкции по восстановлению пароля отправлены');
      }
    }
  };
  </script>
  
  <style scoped>
  .container {
    max-width: 600px;
  }
  .form-input {
    border: 1px solid #ddd;
    border-radius: 0.375rem;
    padding: 0.5rem 1rem;
    width: 100%;
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
  </style>
  