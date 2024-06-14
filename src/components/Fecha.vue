<template>
    <div class="card">
      <p>Hoy: {{ currentDate }}</p>
    </div>
  </template>
  
  <script>
  import { ref, onMounted } from 'vue';
  
  export default {
    setup() {
      const currentDate = ref('');
  
      const updateCurrentDate = () => {
        const today = new Date();
        const options = { year: 'numeric', month: 'long', day: 'numeric' };
        currentDate.value = today.toLocaleDateString('es-ES', options);
      };
  
      onMounted(() => {
        updateCurrentDate();
      });
  
      return {
        currentDate
      };
    }
  };
  </script>


<style>
.card {
  position: fixed;
  right: 20px;
  top: 20px;
  padding: 8px;
  background-color: #f8f9fa;
  border: 1px solid #dee2e6;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  font-family: Arial, sans-serif;
  color: #343a40;
}
</style>
