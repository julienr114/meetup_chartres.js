<template>
  <div class="ui segment">
    {{ todo.text }}
    <button class="ui mini right floated button" v-on:click="todoToggle">Done</button>
  </div>
</template>

<script>
  export default {
    props: ['value'],
    methods: {
      todoToggle () {
        if (this.todo.done) {
           this.$emit('completedTodo', this.todo)
        } else {
          this.$emit('incompletedTodo', this.todo)
        }
      }
    }
  }
</script>

<style>
</style>
