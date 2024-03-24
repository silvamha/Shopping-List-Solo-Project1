<template v-cloak>
<!-- <shoppinglist></shoppinglist> -->
<div class="header">
    <h1>{{ header.toLocaleUpperCase() }}</h1>
    <button v-if="state === 'default'" @click="changeState('edit')">Add Item</button>
    <button v-else @click="changeState('default')">Cancel</button>
  </div>

  <!-- Work on the logic below then implement it into the code -->
  <div  class="add-item-form">
    <!-- 
      Work on implementing this code to hide the form when not used
    *****  v-if="state === 'edit'" *****
     -->

    <input type="text" placeholder="Add an Item" v-model="newItem" @keyup.enter="saveItem" />
    <button class="btn" :disabled="newItem.length === 0" @click="saveItem">Save Item</button>
  </div>
  <a v-bind:href="newItem" target="_blank">Dynamic Link</a>
  <ul>
    <p v-if="items.length === 0">Nice Job! You bought all you</p>
    <li v-for="item in items" :class="[item.purchased? 'strikeout' : '']">{{ item.label }}</li>
  </ul>
</template>

<script>
// import Shoppinglist from './components/ShoppingList.vue'
export default {
  name: "App",
//   components: {
// Shoppinglist
//   },
data() {
    return {
      state: 'default',
      header: "Shopping List App",
      newItem: '',
      items: [
        {
          label:'chicken',
          purchased:'true'
        },
        {
          label:'sugar',
          purchased:'false'
        },
        {
          label:'rice',
          purchased:'true'
        }
      ]
    }
  },
  methods: {
    saveItem() {
      this.items.unshift({
        label:this.newItem,
        purchased:false,
      },)
      this.newItem = ''
      console.log(this.items)
    },
    changeState() {
      this.state = newState
      this.newItem = ''
    }
  }
}
</script>

<style lang="css">
body {
  background-color: lightskyblue;
}

#app {
  display: flex;
  flex-direction: column;
  margin: 10px;
  height: 600px;
  width: auto;
  background-color: lightsalmon;
}

h1 {
  margin: auto;
}

.add-item-form {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 300px;
  width: 600px;
  margin: auto;
  background-color: white;
  border-radius: 10px;
}

input {
  width: 300px;
  height: 30px;
}

.btn {
  height: 30px;
  width: 300px;
  margin-top: 5px;
  border-radius: 5px;
  background-color: blue;
  color: white;
}

li {
  list-style: none;
  font-size: 1.5em;
}

.strikeout{
  text-decoration: line-through;
}


[v-cloak] {
  display: none;
}
</style>