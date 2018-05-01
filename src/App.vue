<template>
  <div id="app">
    <Nav class="fixed-top" v-bind:todos="todos"/>
    <div class="container" style="margin-top: 100px;">
      <AddTodo class="mb-3" v-on:add-todo="addTodo"/>
      <Sort class="align-self-center"/>
      <TodoList v-bind:todos="todos"/>
    </div>
    <back-to-top bottom="50px" right="20px" visibleOffset="100">
      <button type="button" class="btn btn-info btn-to-top btn-sm">
        <i class="fa fa-chevron-up"></i>
        Top
      </button>
    </back-to-top>
  </div>
</template>

<script>
import TodoList from './components/TodoList';
import Nav from './components/Nav';
import AddTodo from './components/AddTodo';
import Sort from './components/Sort';

export default {
  name: 'App',
  components: {
    TodoList,
    Nav,
    AddTodo,
    Sort,
  },
  data() {
    return {
      todos: [{
        title: 'Todo A',
        content: 'This is a Todo',
        done: false,
      },
      {
        title: 'Todo B',
        content: 'This is a Todo',
        done: true,
      },
      {
        title: 'Todo C',
        content: 'This is a Todo',
        done: true,
      },
      {
        title: 'Todo D',
        content: 'This is a Todo',
        done: false,
      },
      {
        title: 'Todo E',
        content: 'This is a Todo',
        done: true,
      },
      ],
    };
  },
  methods: {
    addTodo(newTodo) {
      this.todos.unshift(newTodo);
    },
  },
};
</script>

<style lang="scss">
@import '../node_modules/bootstrap/scss/bootstrap.scss';
</style>
