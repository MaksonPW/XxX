<template>
  <v-app>
    <v-navigation-drawer app v-model="drawer" style="background: #7ae3eb" >
      <v-list-item style="background: #11959e">
        <v-list-item-content>
          <v-list-item-title class="title" style="color: #e8dbdb">
          КИПУ
          </v-list-item-title>
          <v-list-item-subtitle style="color: #000000">
          Учебный проект
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>
    <v-divider></v-divider>
    <v-list dense>
      <v-list-item-group>
        <v-list-item style="color: #000000" v-for="link in menu" :key="link.title" :to="link.url">
          <v-list-item-icon>
            <v-icon>{{ link.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>{{ link.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list-item-group>
    </v-list>   
   </v-navigation-drawer>
  <v-app-bar app dark style="background: #28c6d1" >
    <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-spacer></v-spacer>
      <v-toolbar-items class="hidden-sm-and-down">
        <v-btn v-for="link in links" :key="link.title" :to="link.url" text><v-icon left>{{ link.icon }}</v-icon>{{ link.title }}</v-btn>
      </v-toolbar-items>
    </v-app-bar>
  <v-main style="background: #28d2de" >
    <router-view></router-view>
  </v-main>

    
  </v-app>
</template>
<script>
  export default {
  data() {
    return {
      drawer: false,
      links: [
        {title:"Форум", icon:"mdi-forum", url:"/forum"},
        {title:"Регистрация", icon:"mdi-account-plus", url:"/reg"},
        {title:"Вход", icon:"mdi-account-arrow-right", url:"/loggin"},
      ],
      menu: [
        {title:"Статистика", icon:"mdi-badge-account-horizontal", url:"/stats"},
        {title:"Банковские счета", icon:"mdi-bank-outline", url:"/bank"},
        {title:"Защита аккаунта", icon:"mdi-lock-alert", url:"/lock"},
        {title:"Мод", icon:"mdi-cellphone-arrow-down", url:"/mod"},
      ]
      }
    }
  }
</script>