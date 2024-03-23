<template>
<div class="header">
    <h1>{{ header.toLocaleUpperCase() }}</h1>
    <button v-if="state === 'default'" @click="changeState('edit')">Add Item</button>
    <button @click="changeState('default')">Cancel</button>
  </div>

  <div if="state === 'edit'" class="add-item-form">
    <input type="text" placeholder="Add an Item" v-model="newItem" @keyup.enter="saveItem" />
    <button class="btn" :disabled ="newItem.length === 0" @click="saveItem">Save Item</button>
  </div>
  <ul>
    <p v-if="items.length === 0">Nice Job! You bought all you</p>
    <li v-for="item in items">{{ item}}</li>
  </ul>
</template>

<script>
export default{
    name:"ShoppingList",
    data() {
    return {
      state: 'default',
      header: "Shopping List App",
      newItem: '',
      items: [
        'Chicken',
        'Rice',
        'Sugar',
      ]
    }
  },
  methods: {
    saveItem() {
      this.items.unshift(this.newItem)
      this.newItem = ''
    },
    changeState() {
      this.state = newState
      this.newItem = ''
    }
  }
}


</script>

<style lang="css" scoped>

</style>