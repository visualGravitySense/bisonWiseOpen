<template>
  <footer class="footer">
    <div class="footer__container">
      <div class="footer__row">
        <div class="footer__column">
          <div class="footer__logo">
            <nuxt-link to="/">
              <svg width="100" height="45" viewBox="0 0 159 30" fill="none" xmlns="http://www.w3.org/2000/svg">
                <!-- SVG content here -->
              </svg>
            </nuxt-link>
            <p class="footer__description">Автошкола Viktorija: Обучение, которое ведет к мастерству!</p>
          </div>
        </div>
        <div class="footer__column">
          <div class="footer__contact">
            <p><strong>Адрес:</strong> <a href="https://www.google.com/maps/place/Jaama+1a,+N%C3%B5mme,+Tallinn" target="_blank" rel="noopener noreferrer">Jaama 1a (2 этаж), Nõmme, Tallinn</a></p>
            <p><strong>Телефон:</strong> <a href="tel:+37253464508">+372 53464508</a></p>
            <p><strong>Email:</strong> <a href="mailto:info@viktorijaautokool.ee">info@viktorijaautokool.ee</a></p>
          </div>
        </div>
      </div>

      <div class="footer__row">
        <div class="footer__nav">
          <ul class="footer__nav-list">
            <li class="footer__nav-item"><NuxtLink to="/">Главная</NuxtLink></li>
            <li class="footer__nav-item"><NuxtLink to="/about">О нас</NuxtLink></li>
            <li class="footer__nav-item"><NuxtLink to="/services">Услуги</NuxtLink></li>
            <li class="footer__nav-item"><NuxtLink to="/reviews">Отзывы</NuxtLink></li>
            <li class="footer__nav-item"><NuxtLink to="/contact">Контакты</NuxtLink></li>
          </ul>
        </div>
      </div>

      <div class="footer__row footer__social">
        <a href="https://facebook.com" class="footer__social-link" target="_blank" rel="noopener noreferrer">
          <i class="fab fa-facebook-f"></i>
        </a>
        <a href="https://youtube.com" class="footer__social-link" target="_blank" rel="noopener noreferrer">
          <i class="fab fa-youtube"></i>
        </a>
        <a href="https://instagram.com" class="footer__social-link" target="_blank" rel="noopener noreferrer">
          <i class="fab fa-instagram"></i>
        </a>
      </div>
    </div>

    <div class="footer__bottom">
      <p>&copy; 2024 Автошкола Viktorija. Все права защищены.</p>
    </div>
  </footer>
</template>

<script>
export default {
  data() {
    return {
      email: ''
    };
  },
  methods: {
    subscribe() {
      // Логика подписки на новости
      alert(`Вы подписались на новости с email: ${this.email}`);
    }
  }
};
</script>

<style scoped>
.footer {
  background-color: #1a1a1a;
  color: #fff;
  padding: 40px 0;
  font-family: 'Roboto', sans-serif;
}

.footer__container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.footer__row {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  margin-bottom: 20px;
}

.footer__column {
  flex: 1 1 45%;
  margin-bottom: 20px;
}

.footer__logo {
  text-align: center;
}

.footer__logo img {
  max-width: 150px;
}

.footer__description {
  margin-top: 10px;
  font-size: 14px;
  text-align: center;
}

.footer__contact p {
  margin: 5px 0;
}

.footer__contact a {
  color: #fff;
  text-decoration: none;
}

.footer__contact a:hover {
  text-decoration: underline;
}

.footer__nav {
  text-align: center;
}

.footer__nav-list {
  list-style: none;
  padding: 0;
  display: flex;
  justify-content: center;
  gap: 20px;
}

.footer__nav-item a {
  color: #fff;
  text-decoration: none;
  font-weight: 500;
}

.footer__nav-item a:hover {
  text-decoration: underline;
}

.footer__social {
  display: flex;
  justify-content: center;
  gap: 20px;
}

.footer__social-link {
  color: #fff;
  font-size: 24px;
}

.footer__bottom {
  text-align: center;
  margin-top: 20px;
  border-top: 1px solid #444;
  padding-top: 20px;
  font-size: 14px;
  color: #ccc;
}
</style>
