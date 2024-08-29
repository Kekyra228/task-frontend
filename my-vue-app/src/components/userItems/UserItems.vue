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
  display: flex;
  flex-wrap: wrap;
  border-radius: 1px solid #000;
}

.user-item {
  padding: 10px;
  border: 1px solid #ccc;
  margin: 5px 0;
  cursor: pointer;
}

.user-item:hover {
  background-color: #f0f0f0;
}
</style>