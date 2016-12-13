<template>
  <div>
    <div class="ui fluid action input">
      <input type="text" placeholder="todo description" v-model="newTodo">
      <div class="ui primary button" v-on:click="addTodo">Add todo</div>
    </div>
    <div class="ui segments">
      <div v-for="todo in todos" class="ui segment" v-bind:class="{completed: todo.completed}">
        <div class="ui toggle checkbox">
          <input v-model="todo.completed" type="checkbox">
          <label>{{ todo.text }}</label>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import todo from './todo'
export default {
  components: {
    todo
  },
  data () {
    return {
      todos: [
        { text: 'Learn JavaScript', completed: true },
        { text: 'Learn Vue', completed: false },
        { text: 'Build something awesome', completed: false }
      ],
      newTodo: ''
    }
  },
  methods: {
    addTodo () {
      let todo = {text: this.newTodo, completed: false}
      if(this.newTodo.length > 0) {
        this.todos.push(todo)
        this.newTodo = ''
      }
    }
  }
}
</script>

<style>
  .ui.completed.segment {
    opacity: .6;
  }
</style>
