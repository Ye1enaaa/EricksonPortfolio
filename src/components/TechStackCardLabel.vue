<template>
  <div class="q-pt-sm q-pl-lg q-ml-xl q-gutter-y-sm">
    <q-item class="tech-stack-label">
      {{ roles }}
    </q-item>
  </div>
</template>
<script>
export default {
  name: "TechStackCardLabel",
  props: {
    roles: String,
  },
};
</script>
<style>
.tech-stack-label {
  font-size: 17px;
}
</style>
