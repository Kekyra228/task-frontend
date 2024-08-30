<template>
  <div class="selected-item">
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

</style>