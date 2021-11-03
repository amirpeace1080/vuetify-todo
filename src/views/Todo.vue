<template>
  <div class="home">

    <ListTasks
      v-if="$store.state.tasks.length"
    />

    <NoTasks
      v-else
    />

    <ButtonDoneSorting
      v-if="$store.state.sorting"
    />

  </div>
</template>

<script>
import ListTasks from './../components/Todo/ListTasks.vue'
import NoTasks from './../components/Todo/NoTasks.vue'
import ButtonDoneSorting from './../components/Todo/ButtonDoneSorting.vue'

export default {
  name: 'Home',
  components:{
    ListTasks,
    NoTasks,
    ButtonDoneSorting
  },
  // components: {
  //   'list-tasks': require('@/components/Todo/ListTasks.vue').default,
  //   'no-tasks': require('@/components/Todo/NoTasks.vue').default,
  //   'button-done-sorting': require('@/components/Todo/ButtonDoneSorting.vue').default
  // }
}
</script>