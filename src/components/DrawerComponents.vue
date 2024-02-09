<template>
  <div class="q-gutter-y-md">
    <div class="text-center">
      <q-avatar size="220px">
        <img src="/profile.png" />
      </q-avatar>
    </div>
    <q-item-label class="quote text-center"
      >Still learning, always learning.</q-item-label
    >
    <div class="q-gutter-x-sm text-center">
      <q-avatar size="40px" color="white">
        <img src="/facebook.svg" />
      </q-avatar>
      <q-avatar size="40px" color="white">
        <img src="/github.svg" />
      </q-avatar>
      <q-avatar size="40px" color="white">
        <img src="/instagram.svg" />
      </q-avatar>
      <q-avatar size="40px" color="white">
        <img src="/linkedin.svg" />
      </q-avatar>
    </div>
    <q-separator color="black" />
  </div>
</template>
<script>
export default {
  name: "DrawerComponents",
};
</script>
<style>
.quote {
  font-size: 18px;
}
</style>
