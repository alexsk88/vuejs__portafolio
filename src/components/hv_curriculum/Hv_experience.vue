<template>
  <div class="w3-container w3-card w3-white w3-margin-bottom">
    <h2 class="w3-text-grey w3-padding-16">
      <i
        :class="
          `fa fa-suitcase fa-fw w3-margin-right w3-xxlarge w3-text-${color}`
        "
      ></i
      >Work Experience
    </h2>
    <div class="w3-container" v-for="(job, i) in jobs" :key="`job-${i}`">
      <h5 class="w3-opacity">
        <b>{{ job.name }}</b>
      </h5>
      <h6 :class="`w3-text-${color}`">
        <i class="fa fa-calendar fa-fw w3-margin-right"></i
        >{{ job.datestart }} - {{ job.current != "true" ? job.dateend : "" }}
        <span
          v-if="job.current == 'true'"
          :class="`w3-tag w3-${color} w3-round`"
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
          desc: `Desarrollo de funcionalidadaes web con Ruby on Rails y VUEJS, Rest API/SOAP`,
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
          desc: `Desarrollo de aplicaciones web con Angular y Firebase, php`,
        },

        {
          name:"Auxiliar de Soporte (Distribuidora de Ropa Los Pasitos de Nick)",
          datestart: "2014",
          dateend: "2015",
          desc: `Funciones: Manejar Equipo de Computo`,
        },
      ],
    };
  },
};
</script>

<style></style>
