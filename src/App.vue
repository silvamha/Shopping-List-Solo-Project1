<template>
  <h1>{{ header }}</h1>
  <input type="text" v-model="header" />
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
      items: [
        'Chicken',
        'Rice',
        'Sugar',
      ]
    }
  },
}
</script>

<style>
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
</style>