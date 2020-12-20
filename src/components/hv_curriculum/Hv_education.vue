<template>
  <div class="w3-container w3-card w3-white">
    <h2 class="w3-text-grey w3-padding-16">
      <i :class="`fa fa-certificate fa-fw w3-margin-right w3-xxlarge w3-text-${color}`"></i>Education
    </h2>
    <div class="w3-container" v-for="(study, i) in studies" :key="`study-${i}`">
      <h5 class="w3-opacity"><b>{{study.title}}</b></h5>
      <h6 :class="`w3-text-${color}`">
        <i class="fa fa-calendar fa-fw w3-margin-right"></i>Forever
      </h6>
      <p>Web Development! All I need to know in one place</p>
      <hr />
    </div>
 
  </div>
</template>

<script>
export default {
  name: "Hv_education",
   props: ['color'],
  data() {
    return {
      studies:[
        {title:"title1", datestart:"", dateend:"", des:""},
        {title:"tile2", datestart:"", dateend:"", des:""},
        {title:"tile3", datestart:"", dateend:"", des:""},
      ]
    }
  },
};
</script>

<style>
</style>

