<template>
  <!-- Right Column -->
  <div class="w3-twothird">
    <hvexperience :color="color"/>
    <hveduaction :color="color"/>
    <hvportfolio :color="color"/>
    <hvskills :color="color"/>
  </div>

</template>

<script>
import hveduaction from './Hv_education'
import hvexperience from './Hv_experience.vue';
import hvportfolio from './Hv_portfolio.vue';
import hvskills from './Hv_skills.vue';
export default {
  name: "content",
  props: ['color'],
  components: {hveduaction,hvexperience,hvportfolio,hvskills}
};
</script>

<style>

</style>