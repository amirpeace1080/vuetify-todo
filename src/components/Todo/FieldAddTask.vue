<template>
  <v-text-field
      v-model="newTaskTitle"
      @click:append="addTask"
      @keyup.enter="$store.commit('addTask', newTaskTitle)"
      class="pa-3"
      outlined
      label="Add Task"
      hide-details
      clearable
      append-icon="mdi-plus"></v-text-field>
</template>

<script>
export default {
  data() {
    return {
      newTaskTitle: '',
      
    };
  },
  methods:{
    addTask(){
      this.$store.commit('addTask', this.newTaskTitle)
      this.newTaskTitle = ''
    },
  }
}
</script>

<style>

</style>