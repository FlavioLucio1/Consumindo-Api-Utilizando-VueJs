
<template>
  <v-app id="inspire">

    <!-- Menu -->
    <v-navigation-drawer 
     v-model="drawer"
      app
    >
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="text-h6">
            Menu
          </v-list-item-title>
         <!-- <v-list-item-subtitle>
            Menu do aplicativo
          </v-list-item-subtitle> -->
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

    <!-- End menu -->


  <!--  <v-app-bar app>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title>Lista de empreendimentos</v-toolbar-title>
    </v-app-bar>
-->

      <!-- Start Top Bar -->
     <v-app-bar
      app
      prominent
      color="#fcb69f"
      dark
      src="./assets/cityBG.jpg"
    >
      <template v-slot:img="{ props }">
        <v-img
          v-bind="props"
          gradient="to top right, rgba(19,84,122,.5), rgba(128,208,199,.8)"
        ></v-img>
      </template>

      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
     
      <v-app-bar-title class="my-9 justify-center text-no-wrap"><b>API de Empreendimentos</b></v-app-bar-title>
      

    </v-app-bar>


    <!-- Start Body -->
    <v-main>
      <router-view/>
    </v-main>

    <!-- End Body -->

  </v-app>
</template>

<script>
  export default {
    data: () => ({ drawer: null,
    items: [
          { title: 'Empreendimentos', icon: 'mdi-view-dashboard', to:'/' },
          { title: 'Sobre', icon: 'mdi-help-box',to: '/about' },
        ],
    
    }),
  }
</script>

<style>
.v-app-bar-title__content{
  width: 300px !important;
}
</style>
