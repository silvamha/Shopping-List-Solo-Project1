<template v-cloak>
  <h1>{{ header }}</h1>
  <input type="text" placeholder="Add An Item" v-model="newItem" @keyup.enter="saveItem" />
  <button class="btn" @click="saveItem">Save Item</button>
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
      header: "Shopping List App",
      newItem: [],
      items: [
        // 'Chicken',
        // 'Rice',
        // 'Sugar',
      ]
    }
  },
  methods: {
    saveItem() {
      this.items.push(this.newItem)
      this.newItem = ''
    }
  }
}
</script>

<style>
body {
  background-color: lightgray;
}

input {
  width: 300px;
  height: 30px;
}

#app {
  display: flex;
  flex-direction: column;
  justify-items: center;
  margin: auto;
  height: 600px;
  width: 600px;
}

.btn {
  height: 30px;
  width: 300px;
  margin-top: 5px;
  border-radius: 5px;
  background-color: blue;
  color: white;
}

[v-cloak] {
  display: none;
}
</style>