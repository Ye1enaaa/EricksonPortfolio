<template>
  <div class="">
    <profile-component
      name="Erickson"
      profession="Fullstack Web Developer"
      description="I'm an Aspiring Software Engineer specialized"
      specialization="frontend, backend, and internet of things development."
      resumeLink="online resume"
      avatarUrl="https://scontent.fmnl4-1.fna.fbcdn.net/v/t39.30808-6/428638466_3292971684336985_950038273816050461_n.jpg?_nc_cat=104&ccb=1-7&_nc_sid=5f2048&_nc_eui2=AeHVTjetQMV5ml2-9GwBC2VdvOC7nXVYo8i84LuddVijyBk9ZyIeBVLNcS7ypVFY5k31-kuyTbZoQGskie4SfNCR&_nc_ohc=L312sKcVwh4AX846E7a&_nc_ht=scontent.fmnl4-1.fna&oh=00_AfC_UG5EILArrC9pe8c0bDZZnT3EfvxF8JuLjkdxpIWTxw&oe=65F4B924"
    />
    <div class="flex">
      <more-details />
    </div>
  </div>
</template>

<style scoped>
/* .gray-bg {
  background-color: #f8f9fa;
  height: 380px;
}

.justified {
  text-align: start;
  font-size: 16px;
} */

/* .mini-line {
  height: 40px;
  width: 10px;
  background-color: #40916c;
} */
</style>
<script>
import MoreDetails from "src/components/MoreDetails.vue";
import ProfileComponent from "src/components/ProfileComponent.vue";
import { defineComponent } from "vue";

//import mE from '/me.jpg';
export default defineComponent({
  name: "IndexPage",
  components: {
    ProfileComponent,
    MoreDetails,
  },
});
</script>
