<template>
<div class="w3-content w3-margin-top" style="max-width:1400px;">
  <!-- Main -->
  <div class="w3-row-padding">
    <sidebar :color="color"/>
    <hvcontent :color="color"/>
  </div>
</div>
<hvfooter :color="color"/>

</template>

<script>
import sidebar from './components/hv_curriculum/Hv_sidebar.vue'
import hvcontent from './components/hv_curriculum/Hv_content.vue'
import hvfooter from './components/hv_curriculum/Hv_footer.vue'


export default {
  name: "App",
  data() {
    return {
      color:"light-blue"
    }
  },
  components: {
    sidebar,
    hvcontent,
    hvfooter
  }

};
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Montserrat:400,700');
@import url('https://fonts.googleapis.com/css?family=Lato:400,700,400italic,700italic');

  .w3-card, .w3-card-4{
  border-radius: 30px !important;
  }

</style>

