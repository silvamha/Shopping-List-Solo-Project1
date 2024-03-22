<template v-cloak>
  <div class="header">
    <h1>{{ header.toLocaleUpperCase() }}</h1>
    <button v-if="state === 'default'" @click="changeState('edit')">Add Item</button>
    <button @click="changeState('default')">Cancel</button>
  </div>

  <div if="state === 'edit'" class="add-item-form">
    <input type="text" placeholder="Add an Item" v-model="newItem" @keyup.enter="saveItem" />
    <button class="btn" @click="saveItem">Save Item</button>
  </div>
  <ul>
    <p v-if="items.length === 0">Nice Job! You bought all you</p>
    <li v-for="item in items">{{ item }}</li>
  </ul>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      state: 'default',
      header: "Shopping List App",
      newItem: '',
      items: [
        // 'Chicken',
        // 'Rice',
        // 'Sugar',
      ]
    }
  },
  methods: {
    saveItem: function () {
      this.items.unshift(this.newItem)
      this.newItem = ''
    },
    changeState: function () {
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

[v-cloak] {
  display: none;
}
</style>