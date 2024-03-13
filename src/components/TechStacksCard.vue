<template>
  <q-card class="my-card">
    <q-img :src="image">
      <div class="text-subtitle2 absolute-top text-center">{{ tech }}</div>
    </q-img>
  </q-card>
</template>
<script>
export default {
  name: "TechStacksCard",
  props: {
    image: String,
    tech: String,
  },
};
</script>
<style scoped>
.my-card {
  width: 100%;
  max-width: 150px;
}
</style>
