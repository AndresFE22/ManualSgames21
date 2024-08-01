<template>
  <v-app>
    <v-app-bar app>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title>Manual de Usuario SGAMES 21</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-img
        src="@/assets/logosgames21.png"
        class="logo"
        max-width="50"
      ></v-img>
    </v-app-bar>

    <v-navigation-drawer app v-model="drawer" fixed clipped>
      <v-list dense>
        <v-list-item-group v-model="selectedSection">
          <v-list-item v-for="(section, index) in sections" :key="index" @click="scrollToSection(section.id)">
            <v-list-item-content>
              <v-list-item-title>{{ section.title }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>

    <v-main>
      <v-container>
        <div v-for="(section, index) in sections" :key="index" :id="section.id" class="section">
          <h2>{{ section.title }}</h2>
          <p v-html="section.content"></p>
        </div>
      </v-container>
    </v-main>
  </v-app>
</template>
<script>