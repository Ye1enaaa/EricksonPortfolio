<template>
  <div class="q-pt-md q-pl-lg q-ml-xl q-gutter-y-sm">
    <q-item class="flex q-gutter-x-md">
      <div class="mini-line"></div>
      <!-- <div class="q-ml-md"></div> -->
      <q-item-label class="what-i-do">Who Am I?</q-item-label>
    </q-item>
    <!-- <div class="q-pb-sm"></div> -->
    <q-item
      >I am Erickson Dela Cruz, currently a 4th year BSIT student at University
      of Science and Technology of Southern Philippines.<br />
      I have one year of experience in Web and IoT development.
    </q-item>
    <!-- <q-item class="tech-stack-label"> Frontend Development Tech Stack: </q-item> -->
  </div>
</template>
<script>
export default {
  name: "MoreDetails",
};
</script>
<style scoped>
.mini-line {
  height: 38px;
  width: 10px;
  background-color: #40916c;
}
.what-i-do {
  font-size: 30px;
}

.tech-stack-label {
  font-size: 17px;
}
</style>
