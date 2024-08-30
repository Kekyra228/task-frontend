<template>
  <div class="container">
    <div class="top">
      <div class="top-left">
        <SelectedItems :userItems="selectedUserItems" />
      </div>
      <div class="top-right">
        <SelectedItem :item="selectedItem" />
      </div>
    </div>
   <div class="bottom">
      <div class="sidebar-left">
        <UserItems :items="userItems" @selectItems="selectUserItems" /> 
      </div>
      <div class="sidebar-right">
        <ChooseItem :itemsChoose="chooseItem" @selectItem="selectChooseItem" />
      </div>
   </div>
  </div>
</template>

<script>
import UserItems from './userItems/UserItems.vue';
import ChooseItem from './chooseItem/ChooseItem.vue';
import SelectedItems from './userItems/SelectedItems.vue';
import SelectedItem from './chooseItem/SelectedItem.vue';
export default {
  components: {
    UserItems,
    ChooseItem,
    SelectedItems,
    SelectedItem,
  },
  data() {
    return {
      selectedUserItems: [], // лево, выбранные вещи из вещей пользователя снизу слева(отображение сверху слева)
      selectedItem: null, //одна выбранная вещь из правого нижнего блока
        userItems: [ 
      {
        "id": 1,
        "name": "Shoes 1"
    },
    {
        "id": 2,
        "name": "Shoes 2"
    },
    {
        "id": 3,
        "name": "Shoes 3"
    },
    {
        "id": 4,
        "name": "Shoes 4"
    },
    {
        "id": 5,
        "name": "T-shirt 1"
    },
    {
        "id": 6,
        "name": "T-shirt 2"
    },
    {
        "id": 7,
        "name": "T-shirt 3"
    },
    {
        "id": 8,
        "name": "T-shirt 4"
    }
      ], // лево, данные о вещах пользователя снизу слева 
      chooseItem: [
         {
        "id": 11,
        "name": "Jacket 1"
    },
    {
        "id": 12,
        "name": "Jacket 2"
    },
    {
        "id": 13,
        "name": "Jacket 3"
    },
    {
        "id": 14,
        "name": "Jacket 4"
    },
    {
        "id": 15,
        "name": "Hoodie 1"
    },
    {
        "id": 16,
        "name": "Hoodie 2"
    },
    {
        "id": 17,
        "name": "Hoodie 3"
    },
    {
        "id": 18,
        "name": "Hoodie 4"
    }
      ], //вещь на выбор справа снизу(можно выбрать только одну и добавить справа наверх)
    };
  },
  methods: {
    selectUserItems(item) {
    if (!this.selectedUserItems.find(i => i.id === item.id)) {
        console.log(this.selectedUserItems)
       this.selectedUserItems.push(item); // левая часть, добавляем в массив несколько элементов пользователя 
      }
    },
    selectChooseItem(item) {
      this.selectedItem = item; // право, выбираем одну вещь из нижнего правого блока
    },
  },
};
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
}
.top {
  display: flex;
  justify-content: space-between;
}
.bottom {
  display: flex;

}
.sidebar-left, .sidebar-right {
  flex: 1;
  display: flex;
  flex-direction: column;
}
.top-left, .top-right {
  flex: 0;
  display: flex;
  flex-direction: row;
}
</style>