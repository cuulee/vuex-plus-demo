<script>
  import { global } from 'vuex+';
  import itemList from './components/item-list/item-list.vue';

  export default {
    name: 'app',
    methods: {
      // Dispatch action in main instance of item-list-store
      addCounter() {
        this.$store.dispatch(global.api.itemList.act.addItem);
      },
    },
    components: {
      itemList,
    },
    mounted() {
      // console.info('api', global.api, '\nactions', this.$store['_actions']); // eslint-disable-line
    },
  };
</script>

<template>
  <div id="app">
    <header>
      <button @click="addCounter" id="add-new">Add new (mod 3)</button>
    </header>

    <itemList></itemList>
  </div>
</template>

<style scoped>
  #app {
    display: flex;
    flex-direction: column;
  }

  #app > header{
    background-color: #efffef;
    height: 40px;
    text-align: center;
  }

  button#add-new {
    box-sizing: border-box;
    height: 30px;
    margin: 5px;
    border-radius: 4px;
    width: 135px;
    color: #333;
  }
</style>
