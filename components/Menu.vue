<template>
  <nav>
    <v-app-bar-nav-icon @click.stop="drawer = !drawer" class="menu-trigger">
    </v-app-bar-nav-icon>

    <v-navigation-drawer
      v-model="drawer"
      fixed
      left
      temporary
      width="100%"
      class="menu-container"
    >
      <v-container class="pa-10 panel-full menu-content">
        <h1 class="text-center text-h2">Menu</h1>
        <div class="list-container">
          <v-list
            class="wh-full d-flex justify-center align-center flex-wrap pa-10"
          >
            <v-list-item v-for="item in linkpath" :key="item.id" class="">
              <nuxt-link :to="item.path" class="link-item d-block">{{
                item.name
              }}</nuxt-link>
            </v-list-item>
          </v-list>
        </div>
      </v-container>
    </v-navigation-drawer>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      drawer: false,
      linkpath: [
        {
          name: "トップページ",
          path: "/",
        },
        {
          name: "ほげ",
          path: "/",
        },
        {
          name: "ふが",
          path: "/",
        },
        {
          name: "トップページ",
          path: "/",
        },
      ],
    };
  },
};
</script>

<style scoped>
.menu-trigger {
  position: fixed;
  z-index: 201;
  top: 5px;
  left: 5px;
}

.menu-container {
  z-index: 200;
}

.menu-content {
  background-color: var(--main-color);
}

.panel-full {
  width: 100vw;
  height: 100vh;
}

.wh-full {
  width: 100%;
  height: 100%;
}

.list-container {
  border: 3px solid var(--bg-color);
}

.link-item {
  position: relative;
  z-index: 110;
  width: 100%;
  height: 100%;
  color: var(--bg-color);
  text-decoration: none;
  overflow: hidden;
  text-align: center;
  font-size: 1.2em;
}

.link-item:hover {
  color: var(--main-color);
}

.link-item::before {
  content: "";
  display: block;
  z-index: -1;
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  transition-duration: 0.3s;
  background-color: var(--bg-color);
}

.link-item:hover::before {
  left: 0;
}
</style>
