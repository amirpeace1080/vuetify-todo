<template>
  <div>
    <v-menu offset-y>
      <template v-slot:activator="{ on, attrs }">
        <v-btn
        color="primary"
            icon
          v-bind="attrs"
          v-on="on"
        >
            <v-icon>mdi-dots-vertical</v-icon>
        </v-btn>
      </template>
      <v-list>
        <v-list-item
          v-for="(item, index) in items"
          :key="index"
          @click="handleClick(index)"
        >
          <v-list-item-icon>
            <v-icon v-text="item.icon"></v-icon>
          </v-list-item-icon>
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu>

    <DialogDelet
      v-if="dialogs.delete"
      @close="dialogs.delete = false"
      :task="task" />

  </div>
   
</template>

<script>
import DialogDelet from './Dialogs/DialogDelete.vue'

export default {
  components: {
    DialogDelet
  },
  data: () => ({
    props:['task'],
    dialogs:{
        delete: false
      },
    items: [
      {
        title: 'Edit',
        icon: 'mdi-pencil',
        click(){
          console.log('edit');
        }
      },
      {
        title: 'Due date',
        icon: 'mdi-calendar',
        click(){
          console.log('Due date');
        }
      },
      {
        title: 'Delete',
        icon: 'mdi-delete',
        click(){
          this.dialogs.delete = true
        }
      },
    ],
  }),
    methods: {
      handleClick(index){
        this.items[index].click.call(this)
        console.log('dle');
      }
    }
}
</script>

<style>

</style>