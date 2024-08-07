<template>
  <div class="container mx-auto px-4 py-8">
    <!-- Course Header -->
    <div class="course-header flex flex-col lg:flex-row items-center lg:items-start mb-8">
      <div class="course-media w-full lg:w-1/2 lg:pr-8 mb-6 lg:mb-0">
        <img :src="course.image" :alt="course.title" class="rounded-lg shadow-lg w-full">
        <!-- Optionally add a video player here -->
      </div>
      <div class="course-info w-full lg:w-1/2">
        <h1 class="text-3xl font-bold text-gray-900 mb-4">{{ course.title }}</h1>
        <p class="text-gray-700 mb-6">{{ course.description }}</p>
        <div class="author-info flex items-center mb-6">
          <img :src="course.author.image" :alt="course.author.name" class="w-16 h-16 rounded-full mr-4">
          <div>
            <h2 class="text-xl font-semibold">{{ course.author.name }}</h2>
            <p class="text-gray-600">{{ course.author.bio }}</p>
          </div>
        </div>
        <button class="btn-primary">Купить</button>
      </div>
    </div>
    <!-- Course Reviews -->
    <div class="course-reviews mb-8">
      <h2 class="text-2xl font-bold text-gray-900 mb-4">Отзывы студентов</h2>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
        <div v-for="review in course.reviews" :key="review.id" class="review-card p-4 bg-white shadow-lg rounded-lg">
          <p class="text-gray-700 mb-4">{{ review.content }}</p>
          <div class="review-author flex items-center">
            <img :src="review.author.image" :alt="review.author.name" class="w-12 h-12 rounded-full mr-4">
            <div>
              <h3 class="text-lg font-semibold">{{ review.author.name }}</h3>
              <p class="text-gray-600">{{ review.author.profession }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      course: {
        title: 'Название курса',
        description: 'Описание курса',
        image: 'https://via.placeholder.com/600x400',
        author: {
          name: 'Имя автора',
          bio: 'Биография автора',
          image: 'https://via.placeholder.com/150'
        },
        reviews: [
          {
            id: 1,
            content: 'Отличный курс! Очень понравилось.',
            author: {
              name: 'Студент 1',
              profession: 'Профессия',
              image: 'https://via.placeholder.com/100'
            }
          },
          {
            id: 2,
            content: 'Очень информативный курс.',
            author: {
              name: 'Студент 2',
              profession: 'Профессия',
              image: 'https://via.placeholder.com/100'
            }
          },
          {
            id: 3,
            content: 'Понравилось изложение материала.',
            author: {
              name: 'Студент 3',
              profession: 'Профессия',
              image: 'https://via.placeholder.com/100'
            }
          }
        ]
      }
    };
  }
};
</script>

<style scoped>
.container {
  max-width: 1200px;
  margin: 0 auto;
}
.course-header {
  display: flex;
  flex-direction: column;
}
.course-info {
  flex: 1;
}
.author-info img {
  width: 64px;
  height: 64px;
  border-radius: 50%;
}
.review-card {
  display: flex;
  flex-direction: column;
}
.review-author img {
  width: 48px;
  height: 48px;
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
</style>
