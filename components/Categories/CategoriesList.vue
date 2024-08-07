<template>
  <!-- Перечень категорий водительских прав -->
  <div class="mt-10 flex justify-between items-start">
    <div class="cards">
      <CategoryPreview
        v-for="card in cards" :key="card.id"
        :admin="admin"
        :card="card"
      />
    </div>
    
  </div>
</template>


<script>
import CategoryPreview from '~/components/Categories/CategoryPreview.vue';
export default {
  props: {
    cards: {
      type: Array,
      required: true
    },
    admin: {
      type: Boolean,
      default: false
    }
  },
  components: {
    CategoryPreview
  },
  name: 'Categories',
  data() {
    return {


    };
  }
};
</script>

<style >
.cards {
  display: flex;
  gap: 20px;
  flex-wrap: wrap;
}

.social-icons {
  margin-top: 16px;
  margin-left: 20px; /* Adjust this value as needed */
  display: flex;
  flex-direction: column;
  gap: 20px;

}

.social-icon img {
  width: 40px;
  height: 40px;
}
</style>
