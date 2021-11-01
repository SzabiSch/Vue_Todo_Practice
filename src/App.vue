<template>
  <div id="app">
    Hi
    {{ name_first }}

    <ul>
      <li
        v-for="(todo, index) in todos"
        :key="todo.id"
        :class="{ finishedTask: todo.finished }"
      >
        <input type="checkbox" :checked="todo.finished" />
        <a :href="'?id=' + todo.id">zeigen</a> {{ ++index }}.{{ todo.name }}
      </li>
    </ul>
    <button v-on:click="test">TEST</button>
  </div>
</template>

<script>
export default {
  name: "App",
  data: () => ({
    name_first: "Szabi",
    todos: [
      { id: 1, finished: false, name: "VUE JS leren" },
      { id: 2, finished: true, name: "Code Beispiele üben" },
      { id: 3, finished: false, name: "Git commit" },
      { id: 4, finished: true, name: "ein weiteres Todo" },
    ],
  }),
  methods: {
    test() {
      alert("Hallooo!!!");
    },
  },
};
</script>

<style>
.finishedTask {
  text-decoration: line-through;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
