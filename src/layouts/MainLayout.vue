<template>
  <q-layout view="lHh Lpr lFf">
    <q-drawer
      class="bg-green-5 flex justify-center"
      v-model="leftDrawerOpen"
      show-if-above
      bordered
    >
      <q-list>
        <q-item-label class="name-label q-pt-sm text-center">
          EricksonDotDev &lt; /&gt;
        </q-item-label>
        <div class="q-pt-sm"></div>
        <drawer-components />
        <important-links
          v-for="(value, index) in buttonLinks"
          :key="index"
          :name="value.name"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>
<style scoped>
.green-bg {
  background-color: lightgreen;
}
.name-label {
  font-size: 20px;
}
</style>

<script>
import DrawerComponents from "src/components/DrawerComponents.vue";
import ImportantLinks from "src/components/ImportantLinks.vue";
import { defineComponent, ref } from "vue";

const buttonLinks = [
  {
    name: "> Projects",
    // link: "https://github.com/Ye1enaaa",
  },
  {
    name: "> Hire Me",
    // link: "https://github.com/Ye1enaaa",
  },
];

export default defineComponent({
  name: "MainLayout",

  components: {
    DrawerComponents,
    ImportantLinks,
  },

  setup() {
    const leftDrawerOpen = ref(false);

    return {
      buttonLinks: buttonLinks,
      leftDrawerOpen,
      toggleLeftDrawer() {
        leftDrawerOpen.value = !leftDrawerOpen.value;
      },
    };
  },
});
</script>
