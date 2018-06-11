<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h1>Add an item to your list</h1>
    <div class="form">
      <input v-model="newItem" type="text" placeholder="Enter a new item">
      <button class="basic" v-on:click="addItem()">Add item</button>
      <button class="red" v-on:click="clearList()">Clear list</button>
    </div>
    <ul>
      <li v-for="(item, index) in items" :key="index">
         {{ item }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'List',
  data() {
    return {
      msg: 'Welcome to the list',
      newItem: '',
      items: [],
    };
  },

  methods: {
    addItem() {
      this.items.push(this.newItem);
      this.newItem = '';
    },

    clearList() {
      this.items = [];
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
input,
button,
submit {
  border: none;
}

h1,
h2 {
  font-weight: normal;
}

a {
  color: #42b983;
}

li {
  list-style-type: none;
  margin: 0.5em;
}

.basic {
  height: 3em;
  width: 10em;
  background: #42b983;
  color: white;
  box-shadow: 0 1px #ffffff inset, 0 1px 3px rgba(66, 185, 131, 0.25);
  text-transform: uppercase;
  font-weight: 900;
  letter-spacing: 0.1em;
  padding: 0.5em;
  margin: 0.5em;
  outline: none;
}

.red {
  height: 3em;
  width: 10em;
  background: #ff0000;
  color: white;
  box-shadow: 0 1px #ffffff inset, 0 1px 3px rgba(255, 0, 0, 0.25);
  text-transform: uppercase;
  font-weight: 900;
  letter-spacing: 0.1em;
  padding: 0.5em;
  margin: 0.5em;
  outline: none;
}

input {
  height: 2em;
  width: 15em;
  box-shadow: 0 1px #ffffff inset, 0 1px 3px rgba(34, 25, 25, 0.4);
  padding: 0.5em;
  margin: 0.5em;
  outline: none;
}
</style>
