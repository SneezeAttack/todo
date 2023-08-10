<template>

  <img alt="Vue logo" src="./assets/logo.png">
  <TodoList>

  <!--template v-slot:named>
    <h3>A named slot, too!</h3>
  </template>
  <h1>This is a slot!</h1-->

  </TodoList>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import TodoList from './components/TodoList.vue';

@Options({
  components: {
    TodoList,
  },
})
export default class App extends Vue {}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background-color: yellow;
}
</style>
