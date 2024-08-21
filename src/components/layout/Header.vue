<template>
  <div class="header-container">
    <div class="store">
      <img src="@/assets/logo.png" alt="logo" />
      <strong>Godzicode</strong>
    </div>
    <div class="menu-container">
      <div
        v-for="menu in menuList"
        :key="menu.key"
        class="menu"
        :class="{ 'menu-active': activeMenu == menu.key }"
        @click="gotoPage(menu.key)"
      >
        <router-link :to="menu.key == 'home' ? '/' : menu.key">
          <span>{{ menu.title }}</span>
        </router-link>
      </div>
    </div>
    <div class="hamburger-menu">
      <v-menu>
        <template v-slot:activator="{ props }">
          <img
            src="@/assets/icons/hamburger.svg"
            alt="hamburger icon"
            v-bind="props"
          />
        </template>
        <v-list>
          <v-list-item v-for="menu in menuList" :key="menu.key">
            <v-list-item-title @click="gotoPage(menu.key)">
              {{ menu.title }}
            </v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </div>
  </div>
</template>
<script setup>
import { ref, computed } from "vue";
import { useRoute, useRouter } from "vue-router";

defineOptions({
  name: "header-wrapper",
});

const route = useRoute();
const router = useRouter();

const activeMenu = computed(() => {
  return route.name;
});
// const showMenu = ref(false);
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

const gotoPage = (pageName) => {
  router.push({ name: pageName });
};
</script>


<style lang="scss" scoped>
.header-container {
  position: fixed;
  top: 0;
  right: 0;
  left: 0;
  z-index: 9999;
  background-color: #ddeefa;

  height: 72px;
  padding: 0px 20px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  box-shadow: 0px 0.5px 10px 0px #6caeed;
  .store {
    display: flex;
    align-items: center;
    gap: 8px;
    color: #6caeed;
    img {
      width: 50px;
      height: 50px;
    }
  }
  .menu-container {
    height: 100%;
    display: flex;
    align-items: center;

    .menu {
      cursor: pointer;
      height: 100%;
      padding: 0px 16px;
      align-content: center;
      a {
        padding: 16px;
        font-weight: 500;
        text-decoration: unset;
        color: #6caeed;
      }
      &-active {
        background-color: #bde0fe;
      }
      &:hover {
        background-color: #bde0fe;
      }
    }

    @media screen and (max-width: 768px) {
      display: none;
    }
  }
  .hamburger-menu {
    cursor: pointer;
    display: none;
    width: 30px;
    height: 30px;

    @media screen and (max-width: 768px) {
      display: flex;
      align-items: center;
      justify-content: center;
    }
  }
}
</style>