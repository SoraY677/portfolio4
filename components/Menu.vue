<template>
  <nav>
    <v-button @click.stop="drawer = !drawer" class="menu-trigger">
      <div class="menu-trigger-inner">
        <img src="/moon.svg" height="30px" width="30px" class="menu-icon" />
        <p class="menu-supplement mb-0 text-center">menu</p>
      </div>
    </v-button>

    <v-navigation-drawer
      v-model="drawer"
      fixed
      left
      temporary
      width="100%"
      class="menu-container"
    >
      <v-container class="pa-10 panel-full menu-content">
        <h1 class="text-bg-color text-center text-h2">Menu</h1>
        <div class="list-container">
          <v-list
            class="wh-full d-flex justify-center align-center flex-wrap pa-10"
          >
            <v-list-item v-for="item in linkpath" :key="item.id" class="">
              <a class="link-item d-block" @click="test(item.path)">{{
                item.name
              }}</a>
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
          path: "/re",
        },
      ],
    };
  },
  methods: {
    test(toPath) {
      if (this.$route.path == toPath) this.drawer = false;
      else this.$router.push(toPath);
      console.log(this.$route.path);
    },
  },
};
</script>

<style scoped>
.menu-trigger {
  position: fixed;
  display: flex;
  z-index: 201;
  top: 0px;
  left: 0px;
  padding: 2px;
  border-radius: 0 0 10px 0;
  justify-content: center;
  align-items: center;
  background-color: var(--main-color);
}

.menu-trigger-inner {
  width: 100%;
  height: 100%;
  padding: 2px;
  transition-duration: 0.3s;
}

.menu-trigger-inner:hover {
  background-color: rgba(250, 250, 250, 0.3);
  box-shadow: 2px 2px 0px 0px var(--bg-color);
}

.menu-icon {
  height: 2em !important;
  width: 2em !important;
  transition-duration: 0.3s;
}
.menu-supplement {
  color: var(--bg-color);
  font-size: 0.4em;
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
  text-align: center;
  overflow: hidden;
  font-size: 1.2em;
}

.link-item:hover {
  color: var(--main-color);
  font-weight: bold;
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
