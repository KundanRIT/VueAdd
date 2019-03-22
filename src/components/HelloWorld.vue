<template>
  <div>
    <form @submit.prevent="addItem()">
      <input v-model="newItem" placeholder="Add a new item"/>
      <button type="submit" @click="addItem()" >Add</button>
      <button type="submit" @click="removeLastItem()" >Remove Last Item</button>
      <button type="submit" @click="clearItems()" >Clear</button>
    </form>
    <hr />
    <pre>{{$data}}</pre>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data: function () {
    return {
      newItem: null,
      items: []
    }
  },
  beforeCreate () {
    console.log("before create")
  },
  created () {
    console.log("created")
  },
  methods: {
    addItem: function () {
      if (!this.newItem) {
        return;
      }
      this.items.push(this.newItem);
      this.newItem = null;
    },
    removeLastItem: function () {
      this.items.pop();
    },
    clearItems: function () {
      this.items = [];
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
