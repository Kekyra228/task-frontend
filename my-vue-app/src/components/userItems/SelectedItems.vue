<template>
  <div class="selected-items">
    <div 
      v-for="item in userItems" 
      :key="item.id" 
      class="selected-item"
    >
      {{ item.name }}
    </div>
    <div class="select-count">
       <p>Selected: {{userItems.length}}/6</p>
    </div>
  </div>
</template>


<script>
export default {
  props: {
    userItems: Array
  }
}
</script>

<style scoped>
  .selected-items{
    display: flex;
    flex-wrap: wrap;
    gap: 3px;
    padding: 20px;
    width: 250px;
    height: auto;
    border: 2px solid #000000; 
    font-size: 12px;
 align-items: flex-start;
  }
  .selected-item {
    text-align: center;
     width: 40px;
    height: 40px;
    border: 2px solid #000000; 
     margin: 0;
  }
  .selected-item:nth-child(-n+6) {
    margin-top: 0; /* убираем отступ для первого ряда */
  }

</style>