<template>
  <div class="w3-container w3-card w3-white w3-margin-bottom w3-margin-top" >
      <h2 class="w3-text-grey w3-padding-16">
        <i :class="`fa fa-suitcase fa-fw w3-margin-right w3-xxlarge w3-text-${color}`"></i>Portfolio
      </h2>
      <div class="w3-row" >
        <div class="w3-col " style="width: 33%; padding:10px" v-for="(job, i) in jobs" :key="`job-${i}`">
          <div class="w3-card card_portfolio">
            <p>{{job.name}}</p>
            <img  src="https://www.w3schools.com/w3images/avatar_hat.jpg" class="img_portflio" alt="">
            <p>{{job.desc}}</p>
            <button class="w3-btn w3-red">Ir al sitio</button>
            <hr>
            <span v-for="(tag, i) in job.tags" :key="`jobtag-${i}`" :class="`w3-tag w3-${tag.color}`">Angular</span>
          </div>
        </div>
      </div>
    
    </div>
</template>

<script>
export default {
    name:'hveportfolio',
    props: ['color'],
    data() {
      return {
        jobs:[
          {name:'Front End Developer ',current:"true",
          datestart:'Jun 2010 - Mar2012',dateend:'Current',
          desc:`Lorem ipsum dolor sit amet. Praesentium magnam consectetur vel in deserunt aspernatur 
          est reprehenderit sunt hic. 
          Nulla tempora soluta ea et odio, unde doloremque repellendus iure, iste.`,
          tags:[{name:"Angular",color:"red"},{name:"AngPhpular",color:"blue"},{name:"Javascrip",color:"yellow"}]},

          {name:'Graphic Designer ',
          datestart:'Jun 2010 - Mar2012',dateend:'Jun 2010 - Mar2012',
          desc:`Lorem ipsum dolor sit amet. Praesentium magnam consectetur vel in deserunt aspernatur est
           reprehenderit sunt hic. 
          Nulla tempora soluta ea et odio, unde doloremque repellendus iure, iste.`,
          tags:[{name:"Angular",color:"red"},{name:"AngPhpular",color:"blue"},{name:"Javascrip",color:"yellow"}]},
        ]
      }
    },
}
</script>

<style lang="css" scoped>
.img_portflio{
  width: 100%;
}
.card_portfolio{
  padding-top: 10px;
}
.card_portfolio > p {
  margin-left: 10px;
}
.w3-btn{
  border-radius: 10px;
  margin-left: 10px;
  margin-bottom: 10px;
}
.w3-tag{
  border-radius: 10px;
  margin-bottom: 10px;
  margin-left: 8px;
}
</style>