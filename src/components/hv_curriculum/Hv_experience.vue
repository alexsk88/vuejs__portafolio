<template>
  <div class="w3-container w3-card w3-white w3-margin-bottom">
      <h2 class="w3-text-grey w3-padding-16">
        <i :class="`fa fa-suitcase fa-fw w3-margin-right w3-xxlarge w3-text-${color}`"></i>Work Experience
      </h2>
      <div class="w3-container" v-for="(job, i) in jobs" :key="`job-${i}`">
        <h5 class="w3-opacity"><b>{{job.name}}</b></h5>
        <h6 :class="`w3-text-${color}`">
          <i class="fa fa-calendar fa-fw w3-margin-right"></i>{{job.datestart}} - {{job.current != 'true' ? job.dateend : ''}}
          <span v-if="job.current == 'true'" :class="`w3-tag w3-${color} w3-round`">{{job.dateend}}</span>
        </h6>
        <p>{{job.desc}}</p>
        <hr />
      </div>
    
    </div>
</template>

<script>
export default {
    name:'hvexperience',
    props: ['color'],
    data() {
      return {
        jobs:[
          {name:'Front End Developer / w3schools.com',current:"true",
          datestart:'Jun 2010 - Mar2012',dateend:'Current',
          desc:`Lorem ipsum dolor sit amet. Praesentium magnam consectetur vel in deserunt aspernatur est reprehenderit sunt hic. 
          Nulla tempora soluta ea et odio, unde doloremque repellendus iure, iste.`},
          {name:'Graphic Designer / designsomething.com',
          datestart:'Jun 2010 - Mar2012',dateend:'Jun 2010 - Mar2012',
          desc:`Lorem ipsum dolor sit amet. Praesentium magnam consectetur vel in deserunt aspernatur est reprehenderit sunt hic. 
          Nulla tempora soluta ea et odio, unde doloremque repellendus iure, iste.`},
        ]
      }
    },
}
</script>

<style>

</style>