<template>
  <div class="w3-container w3-card w3-white">
    <h2 class="w3-text-grey w3-padding-16">
      <i :class="`fa fa-certificate fa-fw w3-margin-right w3-xxlarge w3-text-${color}`"></i>Education
    </h2>
    <div class="w3-container" v-for="(study, i) in studies" :key="`study-${i}`">
      <h5 class="w3-opacity"><b>{{study.title}}</b></h5>
      <h6 :class="`w3-text-${color}`">
        <i class="fa fa-calendar fa-fw w3-margin-right"></i>{{study.datestart}} - {{study.dateend}}
      </h6>
      <p>{{study.des}}</p>
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
        {title:"Universidad Católica de Colombia", datestart:"2017", dateend:"2022", des:"Ingenieria de Sistemas"},
        {title:"Corporación Universitaria Uniminuto", datestart:"2013", dateend:"2016", des:"Tecnologo en Sistemas"},
        {title:"Udemy", datestart:"FOREVER", dateend:"", des:"FOREVER"},
        {title:"Platzi", datestart:"FOREVER", dateend:"", des:"FOREVER"},
        {title:"Gimnasio Campestre", datestart:"2008", dateend:"2013", des:"Bachiller"},
        {title:"Instituto Técnico Comercial de Capellanía", datestart:"2003", dateend:"2008", des:"Bachiller"},
        {title:"Colegio Bilingüe San Francisco de Asís", datestart:"1999", dateend:"2003", des:"Bachiller"},
      ]
    }
  },
};
</script>

<style>
</style>

