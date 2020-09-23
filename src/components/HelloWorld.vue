<template>
<v-container>
  <v-layout row wrap>
    <v-flex xs6>
      {{ todoList }}
      <List/>
    </v-flex>
    <v-flex xs6>
      <ListAdd
        @listAdd="listAdd"
        />
    </v-flex>
  </v-layout>
</v-container>  
</template>

<script>
import List from './List'
import ListAdd from './ListAdd'

export default {
  components: {
    List,
    ListAdd
  },
  data () {
    return {
      todoList: []
    }
  },
  methods: {
    listAdd(memo) {
      console.log('받았어')
      this.todoList.push({ memo: memo, status: "created"})
    }
  }
}
</script>