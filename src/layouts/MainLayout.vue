<template>
  <q-layout view="lHh Lpr lFf">
    <!-- <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title> Erickson Dela Cruz </q-toolbar-title>
      </q-toolbar>
    </q-header> -->

    <q-drawer
      class="bg-green flex justify-center"
      v-model="leftDrawerOpen"
      show-if-above
      bordered
    >
      <q-list>
        <q-item-label class="name-label q-pt-sm text-center">
          EricksonDotDev &lt;/&gt;
        </q-item-label>
        <div class="q-pt-sm"></div>
        <drawer-components />
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
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "MainLayout",

  components: {
    DrawerComponents,
  },

  setup() {
    const leftDrawerOpen = ref(false);

    return {
      // essentialLinks: linksList,
      leftDrawerOpen,
      toggleLeftDrawer() {
        leftDrawerOpen.value = !leftDrawerOpen.value;
      },
    };
  },
});
</script>
