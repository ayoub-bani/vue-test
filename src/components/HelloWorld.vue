<template>
  <div id="main-title" class="container">
    <h3 class="text-primary">Thursday 11</h3>
    <h1>Today's schedule</h1>
  </div>
  <div id="input" class="container mt-4">
    <div class="input-group input-group-lg bg-white">
      <input
        @keyup.enter="add"
        v-model="task"
        type="text"
        class="form-control border-0 shadow-sm"
        aria-label="Sizing example input"
        aria-describedby="inputGroup-sizing-lg"
        placeholder="What do you wanna accoumplish today"
      />
    </div>
  </div>
  <!-- Loop for todos component -->
  <todos
    v-for="(item, index) in list"
    :key="index"
    :name="item"
    @click="deleteTodos({ item, index })"
  ></todos>
</template>

<script>
import todos from './todos'

export default {
  name: 'HelloWorld',
  components: {
    todos,
  },

  data() {
    return {
      task: '',
      list: [],
    }
  },

  methods: {
    add() {
      this.list.push(this.task)
      this.task = ''
    },
    complete() {},
    deleteTodos({ item, index }) {
      this.list = this.list.filter((todo, i) => todo !== item && i !== index)
    },
  },
}
</script>
