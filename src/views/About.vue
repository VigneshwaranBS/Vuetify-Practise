<template>
   <main>
     <nav>
      <v-toolbar flat app>
        <v-toolbar-side-icon @click="drawer = !drawer" class="grey--text"></v-toolbar-side-icon>
        <v-toolbar-title class="text-uppercase grey--text">
          <span class="font-weight-light">Todo</span>
          <span>Ninja</span>
        </v-toolbar-title>
        <v-spacer></v-spacer>
        <v-btn flat color="grey">
          <span>Sign Out</span>
          <v-icon right>dashboard</v-icon>
        </v-btn>
      </v-toolbar>
      <v-navigation-drawer app v-model="drawer" class="primary">
        <v-list>
          <v-list-tile v-for="link in links" :key="link.text" router :to="link.route">
            <v-list-tile-action>
              <v-icon class="white--text">{{ link.icon }}</v-icon>
            </v-list-tile-action>
            <v-list-tile-content>
              <v-list-tile-title class="white--text">{{ link.text }}</v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list>
      </v-navigation-drawer>
     
       </nav>
   </main>

</template>

<script>
export default {
name:"About",
data() {
    return {
      drawer: false,
      links: [
        { icon: 'dashboard', text: 'Dashboard', route: '/' },
        { icon: 'folder', text: 'My Projects', route: '/Home' },
        { icon: 'person', text: 'Team', route: '/Home' },
      ]
    }
  }
}
</script>

<style>

</style>