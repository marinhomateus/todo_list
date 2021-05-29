<template>
  <v-card
    class="mx-auto"
  >

    <v-list
      flat
    >

      <v-list-item-group
        v-model="settings"
        multiple
      >
      <div 
        v-for="task in tasks"
        :key="task.id"
      >
        <v-list-item>
          <template v-slot:default="{ active, }">
            <v-list-item-action>
              <v-checkbox
                :input-value="active"
                color="primary"
              ></v-checkbox>
            </v-list-item-action>

            <v-list-item-content>
              <v-list-item-title>{{task.title}}</v-list-item-title>
            </v-list-item-content>
          </template>
        </v-list-item>
      </div>

      </v-list-item-group>
    </v-list>
  </v-card>
</template>

<script>

  export default {
    name: 'Home',
    data()  {
      return  {
        tasks: [
          {
            id: 1,
            title: 'Acordar'
          },
          {
            id: 2,
            title: 'Escovar os dentes'
          },
          {
            id: 3,
            title: 'Tomar banho'
          },
        ]
      }
    }
  }
</script>
