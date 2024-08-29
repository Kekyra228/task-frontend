<template>
  <div class="selected-items">
    <div 
      v-for="item in userItems" 
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
    userItems: Array
  }
}
</script>

<style scoped>

</style>