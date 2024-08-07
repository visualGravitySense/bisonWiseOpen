<!-- components/AppSearch.vue -->
<template>
    <div class="form-group">
    <label v-if="label" class="app-input-label">
      <svg v-if="icon" class="app-input-icon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor">
        <!-- SVG Path for search icon -->
        <path d="M11 4a7 7 0 1 1 0 14 7 7 0 0 1 0-14zm0 2a5 5 0 1 0 0 10A5 5 0 0 0 11 6zm1 5h-2v2h2v-2zm0 4h-2v2h2v-2z"/>
      </svg>
      {{ label }}
    </label>
    <input
      :type="type"
      :id="id"
      :required="required"
      class="app-input"
    />
  </div>
</template>

<script>
export default {
  props: {
    type: {
      type: String,
      default: 'text'
    },
    id: {
      type: String,
      default: ''
    },
    required: {
      type: Boolean,
      default: false
    },
    label: {
      type: String,
      default: ''
    },
    icon: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style scoped>
.form-group {
  display: flex;
  align-items: center;
  /* margin-right: 5px; */
  /* max-width: 100px;  Adjust this value as needed */
}

.app-input-label {
  display: flex;
  align-items: center;
  font-weight: bold;
  color: #92ace0;
}

.app-input-icon {
  margin-right: 8px;
  width: 20px;
  height: 20px;
  fill: #ffdc00;
}

.app-input {
  background-color: #0f1624;
  flex: 1;
  padding: 10px;
  border: 1px solid #92ace0;
  border-radius: 50px;
  font-size: 16px;
  width: 150px;
  margin-left: 8px;
  color: #92ace0;
  /* max-width: 100%;  Ensures the input doesn’t exceed its container */
}

.form-group {
  /* max-width: 300px; */
  min-width: 10%;
}
</style>