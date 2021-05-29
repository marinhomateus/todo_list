<template>
  <v-app id="inspire">
    <v-navigation-drawer 
      v-model="drawer"
      app
    >
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="title ">
            ToDo
          </v-list-item-title>
          <v-list-item-subtitle>
            ToDo using VueJS
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list
        dense
        nav
      >
        <v-list-item
          v-for="item in items"
          :key="item.title"
          :to="item.to"
          link
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar 
      app
      color="#fcb69f"
      shrink-on-scroll
      src="https://i.picsum.photos/id/485/1920/1080.jpg?hmac=o22v7VwPC2dDWI5sS7-jQvMd9OdzCVwcmDdBGRRVZDU"
      scroll-target="#scrolling-techniques-2"
    >
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title class="font-weight-black">TODO LIST</v-toolbar-title>
    </v-app-bar>

    <v-main>
      <router-view></router-view>
    </v-main>
  </v-app>
</template>

<script>
  export default {
    data: () => ({ 
      drawer: null,
      items: [
          { title: 'ToDo', icon: 'mdi-clipboard-list', to: '/' },
          { title: 'About', icon: 'mdi-information-variant', to: '/about' },
        ],
        right: null,
     }),
    
  }
</script>
