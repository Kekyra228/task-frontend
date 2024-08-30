<template>
  <div class="user-items">
    <div 
      v-for="item in itemsChoose" 
      :key="item.id" 
      class="user-item" 
      @click="selectItem(item)"
    >
      {{ item.name }}
    </div>
  </div>
</template>

<script>
export default {
  props: {
    itemsChoose: Array
  },
  methods: {
    selectItem(item) {
        console.log("метод вызван")
      this.$emit('selectItem', item); 
    }
  }
}
</script>

<style scoped>
.user-items {
  padding: 20px;
   height: 300px;
  display: flex;
  flex-wrap: wrap;
  border: 2px solid #000000; 
  gap: 10px;
}

.user-item {
  text-align: center;
  width: 50px;
  height: 50px;
  border: 2px solid #000000; 
  cursor: pointer;
  font-size: 1яpx;

}

.user-item:hover {
  background-color: #f0f0f0;
}
</style>