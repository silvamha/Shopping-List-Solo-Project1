<template v-cloak>
<shoppinglist></shoppinglist>
</template>

<script>
import Shoppinglist from './components/ShoppingList.vue'
export default {
  name: "App",
  components: {
Shoppinglist
  },

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