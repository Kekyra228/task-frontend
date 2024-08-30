<template>
  <div class="selected-block">
    <div 
      v-if="item" 
      :key="item.id" 
      class="selected-item"
    >
      {{ item.name }}
    </div>
  </div>
</template>


<script>
export default {
  props: {
    item: Object
  }
}
</script>

<style scoped>
  .selected-block{
    padding: 20px;
    width: 250px;
    height: 250px;
    border: 2px solid #000000; 
    font-size: 12px;
  
  }
  .selected-item{
    text-align: center;
     width: 40px;
    height: 40px;
    border: 2px solid #000000; 
  }
</style>