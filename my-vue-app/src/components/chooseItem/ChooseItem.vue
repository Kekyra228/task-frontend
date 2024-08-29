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
      this.$emit('select', item); 
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