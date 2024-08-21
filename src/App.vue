<template>
  <Header></Header>
  <router-view />

  <Footer></Footer>
</template>
<script setup>
import Header from "@/components/layout/Header.vue";
import Footer from "@/components/layout/Footer.vue";
</script>

<!-- 
<template>
  <v-layout class="rounded rounded-md">
    <v-app-bar>
      <template v-slot:prepend>
        <v-img
          class="ml-2"
          :width="124"
          aspect-ratio="16/9"
          cover
          src="@/assets/logo.png"
          @click.stop="drawer = !drawer"
        >
        </v-img>
      </template>
    </v-app-bar>
    <v-navigation-drawer
      v-model="drawer"
      :location="$vuetify.display.mobile ? 'bottom' : undefined"
      temporary
    >
      <v-list>
        <v-list-item
          v-for="menu in menuList"
          :key="menu.key"
          :title="menu.title"
          link
          :to="`/${menu.key == 'home' ? '' : menu.key}`"
        ></v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-main>
      <router-view />
    </v-main>
  </v-layout>
</template>

<script setup>
import { ref } from "vue";
const drawer = ref(false);
const menuList = ref([
  {
    title: "Home",
    key: "home",
  },
  {
    title: "About",
    key: "about",
  },
  {
    title: "Services",
    key: "services",
  },
  {
    title: "Blog",
    key: "blog",
  },
  {
    title: "Contact",
    key: "contact",
  },
]);
</script> -->
