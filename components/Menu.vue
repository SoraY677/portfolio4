<template>
  <nav>
    <a @click.stop="drawer = !drawer" class="menu-trigger">
      <div class="menu-trigger-inner">
        <img
          src="/moon.svg"
          height="30px"
          width="30px"
          class="menu-icon"
          alt="月のメニューアイコン"
        />
        <p class="menu-supplement mb-0 text-center">menu</p>
      </div>
    </a>

    <v-navigation-drawer
      v-model="drawer"
      fixed
      left
      temporary
      width="100%"
      class="menu-container"
    >
      <v-container class="pa-10 panel-full menu-content">
        <section class="flex justify-center align-center">
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
        </section>
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
          name: "Top",
          path: "/",
        },
        {
          name: "Blog",
          path: "/blog",
        },
        {
          name: "Work",
          path: "/work",
        },
        {
          name: "Contact",
          path: "/contact",
        },
      ],
    };
  },
  methods: {
    test(toPath) {
      if (this.$route.path == toPath) this.drawer = false;
      else this.$router.push(toPath);
    },
  },
};
</script>

<style scoped>
.menu-trigger {
  position: fixed;
  display: flex;
  z-index: 201;
  top: 0;
  right: 0;
  padding: 2px;
  border-radius: 0 0 0 10px;
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
  height: 3em !important;
  width: 3em !important;
  transition-duration: 0.3s;
}
.menu-supplement {
  color: var(--bg-color);
  font-size: 0.9em;
}

.menu-container {
  z-index: 200;
}

.menu-content {
  display: flex;
  background-color: var(--main-color);
  justify-content: center;
  align-items: center;
}

.panel-full {
  min-width: 100vw;
  height: 100vh;
  margin-right: 0;
  margin-left: 0;
  padding: 0;
}

.wh-full {
  width: 100%;
  height: 100%;
}

.list-container {
  border: 3px solid var(--bg-color);
  border-radius: 30px;
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
