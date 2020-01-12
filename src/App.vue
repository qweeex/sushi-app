<template>
  <v-app>
    <v-navigation-drawer
        temporary
        app
        v-model="drawer"
    >
      <!-- -->

      <v-list flat>
        <v-subheader>МЕНЮ</v-subheader>
        <v-list-item-group v-model="item" color="primary">
          <v-list-item
                  v-for="(item, i) in items"
                  :key="i"
          >
            <v-list-item-content>
              <v-list-item-title v-text="item.text"></v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list-item-group>
      </v-list>

    </v-navigation-drawer>

    <v-app-bar app>
      <!-- -->
      <v-app-bar-nav-icon
        @click="drawer = !drawer"
      ></v-app-bar-nav-icon>
        <v-spacer></v-spacer>
        <v-toolbar-title >
          <img class="toolbar-img" src="https://yaposhka64.ru/assets/template/img/logo.png.webp" alt="">
        </v-toolbar-title>
        <v-spacer></v-spacer>
        <v-btn icon>
          <v-icon>mdi-cart</v-icon>
        </v-btn>
    </v-app-bar>

    <!-- Sizes your content based upon application components -->
    <v-content>

      <!-- Provides the application the proper gutter -->
      <v-container fluid>

        <!-- If using vue-router -->
        <router-view></router-view>
      </v-container>
    </v-content>

    <v-footer app>
      <!-- -->
    </v-footer>
  </v-app>
</template>


<style>
  .toolbar-img{
    max-width: 70%;
    margin: auto;
    display: block;
  }
</style>


<script>

  export default {
    data(){
        return{
          drawer: false,
          item: 1,
          items: [
            {text: 'Жаренные роллы', url: '/hot'},
            {text: 'Запеченные роллы', url: '/fare'},
            {text: 'Суши', url: '/sushi'},
            {text: 'Сеты', url: '/seti'},
            {text: 'Классические роллы', url: '/rolls'},
          ],
        }
    },
    methods:{

    }
  }

</script>

