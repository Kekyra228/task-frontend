<template>
  <div class="user-items">
    <div 
      v-for="item in items" 
      :key="item.id" 
      class="user-item" 
      @click="selectItems(item)"
    >
      {{ item.name }}
    </div>
  </div>
</template>

<script>
export default {
  props: {
    items: Array
  },
  methods: {
    selectItems(item) {
        console.log("метод вызван")
      this.$emit('selectItems', item); 
    }
  }
}
</script>

<style scoped>
.user-items {
  height: 300px;
  display: flex;
  flex-wrap: wrap;
  border: 2px solid #000000; 
    padding: 20px;
    gap: 10px;
}
.user-item {
   text-align: center;
     width: 50px;
    height: 50px;
    border: 2px solid #000000; 
    cursor: pointer;
  font-size: 12px;

}

.user-item:hover {
  background-color: #f0f0f0;
}
</style>