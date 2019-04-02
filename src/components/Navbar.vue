<template>
  <nav>
    <v-toolbar app clipped-right>
      <v-btn icon flat color="dark-gray" @click="toggleNav()">
        <v-icon>menu</v-icon>
      </v-btn>
      <v-toolbar-title class="text-uppercase grey--text">
        <span class="font-weight-light">Todo</span>
        <span>Ninja</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn flat color="gray" class="grey--text">
        <span>Sign Out</span>
        <v-icon right>exit_to_app</v-icon>
      </v-btn>
      <v-btn icon color="dark-grey" @click="toggleNotepad()">
        <v-icon>more_vert</v-icon>
      </v-btn>
    </v-toolbar>
    <v-navigation-drawer v-model="showNav" dark app></v-navigation-drawer>
    <v-navigation-drawer v-model="showNotepad" right app clipped z-index="-100" class="grey lighten-4"></v-navigation-drawer>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      showNav: false,
      showNotepad: false
    };
  },
  methods: {
    toggleNotepad() {
      this.showNotepad = !this.showNotepad;
      if (this.showNotepad) {
        this.showNav = false;
      }
    },
    toggleNav() {
      this.showNav = !this.showNav;
      if (this.showNav) {
        this.showNotepad = false;
      }
    }
  }
};
</script>

<style>
</style>
