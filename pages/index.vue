<template>
  <section class="cintainer">
    <div>
      <input v-model.trim="todo" @keyup.enter="addTodo()" type="text" />
      <button @click="addTodo()">+ add</button>
    </div>
    <div>
      <ul>
        <template v-for="(item, index) in todos">
          <li :key="index">
            <input type="checkbox" v-model="item.complete" />
            {{ item.title }}
          </li>
        </template>
      </ul>
    </div>
<header>User</header>
<hr>

    <ul>
      <template v-for="(item, index) in users">
        <li :key="index">
          {{ item.name }}
          <p>
            {{ item.email }}
          </p>
        </li>
      </template>
    </ul>
  </section>
</template>

<script>
export default {
  data() {
    return {
      users: [],
      todos: [],
      todo: '',
    }
  },
  mounted() {
    this.todo = 'Test'
    this.addTodo()
    this.getUser()
  },
  methods: {
    addTodo() {
      if (!this.todo) {
        return
      }
      this.todos = [
        ...this.todos,
        {
          id: this.todos.length + 1,
          title: this.todo,
          complete: false,
        },
      ]
      console.log(this.todos)
      this.todo = ''
    },
    async getUser() {
      try {
        const req = await this.$axios.get(
          'https://jsonplaceholder.typicode.com/users'
        )

        this.users = req.data
      } catch (error) {}
    },
  },
}
</script>
<style scoped>
.container {
  max-width: 400px;
  margin: 0 auto;
}
</style>
