<template>
  <v-card
    class="mx-auto"
    max-width="300"
    tile
  >
    <v-list dense>
      <v-subheader>Todo List</v-subheader>
      <v-list-item-group v-model="item" color="primary">
        <v-list-item
          v-for="(todo, i) in todoList"
          :key="i"
        >
          <v-list-item-content>
            <v-list-item-title v-text="todo.memo"></v-list-item-title>
          </v-list-item-content>
          <v-list-icon @click="deleteTodo(i)">삭제</v-list-icon>
        </v-list-item>
      </v-list-item-group>
    </v-list>
  </v-card>
</template>

<script>
  export default {
    data: () => ({
      item: 1,
      items: [
        { text: 'Real-Time', icon: 'mdi-clock' },
        { text: 'Audience', icon: 'mdi-account' },
        { text: 'Conversions', icon: 'mdi-flag' },
      ],
    }),
  }
</script>

<script>
    export default {
        props: [ 'todoList' ],
        methods: {
            deleteTodo(index) {
                this.$delete(this.todoList, index)
            }
        }
    }
</script>