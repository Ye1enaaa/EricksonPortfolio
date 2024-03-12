<template>
  <q-item class="flex gray-bg">
    <div class="q-pa-xl q-ml-lg q-gutter-y-md">
      <q-item-label class="text-h2">Hi, I'm {{ name }}</q-item-label>
      <!-- <div class="q-mb-sm"></div> -->
      <q-item-label class="text-subtitle1">{{ profession }}</q-item-label>
      <!-- <div class="q-mb-md"></div> -->
      <div class="justified">
        <p>
          {{ description }}
          <br />
          {{ specialization }}
          <br />Want to know me better? Check out my <b>{{ resumeLink }}</b
          >.
        </p>
      </div>
      <!-- <div class="q-mb-sm"></div> -->
      <q-btn elevated color="green" label="Resume" />
    </div>
    <div class="q-pt-lg q-mt-md q-ml-auto q-mr-xl">
      <q-avatar square size="300px">
        <img :src="avatarUrl" />
      </q-avatar>
    </div>
  </q-item>
</template>

<script>
export default {
  name: "ProfileComponent",
  props: {
    name: String,
    profession: String,
    description: String,
    specialization: String,
    resumeLink: String,
    avatarUrl: String,
  },
};
</script>

<style scoped>
.gray-bg {
  background-color: #f8f9fa;
  height: 380px;
}

.justified {
  text-align: start;
  font-size: 16px;
}
</style>
