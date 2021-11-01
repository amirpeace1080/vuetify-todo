<template>
    <div>
        <v-list-item @click="$store.commit('doneTask', task.id)"
          :class="{'blue lighten-5' : task.done}">
          <template v-slot>
            <v-list-item-action>
              <v-checkbox 
                :input-value="task.done"
                color="primary"
              ></v-checkbox>
            </v-list-item-action>

            <v-list-item-content>
              <v-list-item-title
                :class="{'text-decoration-line-through' : task.done}"
              >
                {{ task.title }}
              </v-list-item-title>
            </v-list-item-content>


          <v-list-item-action>
            <TaskMenu />
          </v-list-item-action>
          </template>


        </v-list-item>
        <v-divider></v-divider>

        <DialogDelet
          v-if="dialogs.delete"
          @close="dialogs.delete = false"
          :task="task" />
      </div>
</template>

<script>
import DialogDelet from './Dialogs/DialogDelete.vue'
import TaskMenu from './TaskMenu.vue'

export default {
  components:{
    DialogDelet,
    TaskMenu
  },
    props: ['task'],
    data(){
      return{
        dialogs:{
          delete: false
        }
      }
    }
}
</script>

<style>

</style>