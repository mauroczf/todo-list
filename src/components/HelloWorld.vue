<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <form @submit.prevent="add()">
      <input type="text" v-model="task">
      <button type="submit">Add</button>
    </form>
    <ul>
      <li v-for = "t in tasks" :key="t">{{t}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      task: '',
      tasks: [],
    }
  },
  methods: {
    add() {
      if (this.task.trim()){
        this.tasks.push(this.task);
        this.task = ' ';
      }
    }
  }
}
</script>

