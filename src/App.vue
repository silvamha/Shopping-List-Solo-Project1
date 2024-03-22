<template>
  <h1>{{ header }}</h1>
  <input type="text" placeholder="Add An Item" v-model="newItem" @keyup.enter="items.push(newItem)"/>
  <button class="btn" @click="items.push(newItem)">Save Item</button>
  <ul>
    <li v-for="item in items">{{ item }}</li>
  </ul>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      header: "Shopping List App",
      newItem:[],
      items: [
        'Chicken',
        'Rice',
        'Sugar',
      ]
    }
  },
  methods:{
    addItems(){
      
    }
  }
}
</script>

<!-- <style>
body {
  background-color: lightgray;
}

input {
  width: 300px;
}

#app {
  display: flex;
  flex-direction: column;
  justify-items: center;

  margin: auto;
  height: 600px;
  width: 600px;
}
</style> -->