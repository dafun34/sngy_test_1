<template>
  <v-app>
    <v-main>
      <Table></Table>
    </v-main>
  </v-app>
</template>

<script>
import Table from './components/Table.vue'

export default {
  name: 'App',

  components: {
    Table
  },

  data: () => ({
    //
  }),
};
</script>
