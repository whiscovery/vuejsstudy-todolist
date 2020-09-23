<template>
  <v-app>
    <v-main>
      <TodoMain/>
    </v-main>
  </v-app>
</template>

<script>
import TodoMain from './components/TodoMain';

export default {
  name: 'App',

  components: {
    TodoMain,
  },

  data: () => ({
    //
  }),
};
</script>
