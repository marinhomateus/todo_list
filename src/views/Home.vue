<template>
  <v-card class="mx-auto">
    <v-text-field
      outlined
      label="Append"
      append-icon="mdi-plus"
      class="pa-3"
    ></v-text-field>
    <v-list flat>
      <v-list-item-group v-model="settings" multiple>
        <div v-for="task in tasks" :key="task.id">
          <v-list-item @click="doneTask(task.id)">
            <template v-slot:default>
              <v-list-item-action>
                <v-checkbox
                  :input-value="task.done"
                  color="primary"
                ></v-checkbox>
              </v-list-item-action>

              <v-list-item-content>
                <v-list-item-title
                  :class="{ 'text-decoration-line-through': task.done }"
                >
                  {{ task.title }}
                </v-list-item-title>
              </v-list-item-content>
              <v-list-item-action>
                <v-btn icon @click.stop="deleteTask(task.id)">
                  <v-icon color="grey lighten-1">mdi-delete-outline</v-icon>
                </v-btn>
              </v-list-item-action>
            </template>
          </v-list-item>
        </div>
      </v-list-item-group>
    </v-list>
  </v-card>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      tasks: [
        {
          id: 1,
          title: "Acordar",
          done: false,
        },
        {
          id: 2,
          title: "Escovar os dentes",
          done: false,
        },
        {
          id: 3,
          title: "Tomar banho",
          done: false,
        },
      ],
    };
  },
  methods: {
    doneTask(id) {
      let task = this.tasks.filter((task) => task.id === id)[0];
      task.done = !task.done;
    },

    deleteTask(id) {
      this.tasks = this.tasks.filter((task) => task.id !== id);
    },
  },
};
</script>
