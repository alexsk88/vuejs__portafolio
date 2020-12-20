<template>
  <div :class="`w3-container w3-margin-bottom ${color}` ">
    <div class="w3-row">
      <div class="w3-col" style="width:50%">
        <h2 class="w3-text-grey w3-padding-16">
      <i :class="`fa fa-suitcase fa-fw w3-margin-right w3-xxlarge w3-text-light-blue`"></i>Work Experience
    </h2>
      </div>
      <div class="w3-col" style="width:20%">
        <!-- <img src="https://www.w3schools.com/w3images/avatar_hat.jpg" class="img__headercard"  alt=""> -->
      </div>
      
  
    </div>

    <div class="w3-container" v-for="(job, i) in jobs" :key="`job-${i}`">
      <h5 class="w3-opacity">
        <b>{{ job.name }}</b>
      </h5>
      <h6 :class="``">
        <i class="fa fa-calendar fa-fw w3-margin-right w3-text-light-blue"></i
        >{{ job.datestart }} - {{ job.current != "true" ? job.dateend : "" }}
        <span
          v-if="job.current == 'true'"
          :class="`w3-tag w3-light-blue w3-round w3-text-white`"
          >{{ job.dateend }}</span
        >
      </h6>
      <p>{{ job.desc }}</p>
      <hr />
    </div>
  </div>
</template>

<script>
export default {
  name: "hvexperience",
  props: ["color"],
  data() {
    return {
      jobs: [
        {
          name: "Desarollador web Fullstack (e-learning Solutions)",
          datestart: "2020",
          current: "true",
          dateend: "ACTUAL",
          desc: `Desarrollo de funcionalidadaes web con Ruby on Rails( Rest API,ror) y VUEJS`,
        },
        {
          name: "Freelance",
          datestart: "2017",
          dateend: "2019",
          desc: `Desarrollo de aplicaciones web FRONT: React / Vuejs BACK: NodeJS / RoR / Laravel`,
        },

        {
          name: "Maquetador Web (Publicity Stunt)",
          datestart: "2016",
          dateend: "2017",
          desc: `Desarrollar la UI con archivos Photoshop e Ilustrator`,
        },
        {
          name: "Freelance",
          datestart: "2015",
          dateend: "2016",
          desc: `Desarrollo de aplicaciones web con Angular y Firebase, codeigniter`,
        },
        {
          name:"Auxiliar de Soporte (Distribuidora de Ropa Los Pasitos de Nick)",
          datestart: "2014",
          dateend: "2015",
          desc: `Soporte de Equipo de Computo, invenario`,
        },
      ],
    };
  },
};
</script>

<style>
.img__headercard{
  height: 100px;
  width: 500px;
}

</style>
