<template>
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
        >
          <v-list-item-icon>
            <v-icon v-text="item.icon"></v-icon>
          </v-list-item-icon>
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu>
</template>

<script>
export default {
    data: () => ({
      items: [
        {
          title: 'Edit',
          icon: 'mdi-pencil'
        },
        {
          title: 'Due date',
          icon: 'mdi-calendar'
        },
        {
          title: 'Delete',
          icon: 'mdi-delete'
        },
      ],
    }),
}
</script>

<style>

</style>