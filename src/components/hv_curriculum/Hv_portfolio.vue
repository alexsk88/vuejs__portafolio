<template>
  <div class="w3-container w3-card w3-white w3-margin-bottom w3-margin-top">
    <h2 class="w3-text-grey w3-padding-16">
      <i
        :class="
          `fa fa-suitcase fa-fw w3-margin-right w3-xxlarge w3-text-${color}`"></i
      >Portfolio
    </h2>
    <div class="w3-row">
      <div
        class="w3-col job__barras"
        style="padding:10px"
        v-for="(job, i) in jobs"
        :key="`job-${i}`"
      >
        <div class="w3-card card_portfolio w3-center">
          <p>{{ job.name }}</p>
          <img
            src="https://www.w3schools.com/w3images/avatar_hat.jpg"
            class="img_portflio"
            alt=""
          />
          <button
            class="w3-btn w3-blue w3-margin-top"
            @click="modal(i, `block`)"
          >
            Ver Projecto
          </button>

          <div :id="`id0${i}`" class="w3-modal">
            <div class="w3-modal-content">
              <div class="w3-row ">

                <div class="w3-col  w3-padding details__portfolio" >
               
                  <h4><b>Descripcion</b></h4>
                  <p style="text-align: justify">{{ job.desc }}</p> <hr>
                  <button class="w3-btn w3-green w3-block " @click="goto(job.page)">Ir a DEMO</button>
                  <button v-if="job.front" class="w3-btn w3-black w3-block ">Ver Front GitHUB</button>
                  <button v-if="job.back" class="w3-btn w3-black w3-block">Ver Back GitHUB</button>
                  <button v-if="job.monolito" class="w3-btn w3-black w3-block">Ver projecto GitHUB</button>
                  
                  <hr />
                  <div class="w3-border w3-border-light-gray w3-leftbar">
                    <p>Tecnologias</p>
                  <span
                    v-for="(tag, i) in job.tags"
                    :key="`jobtag-${i}`"
                    :class="`w3-tag w3-${tag.color}`"
                    >{{tag.name}}</span
                  >
                  </div>
                  <br><hr>
                  <button @click="modal(i, `none`)" class="w3-btn w3-red w3-block w3-margin-top ">
                   &times; Cerrar</button>
                </div>
                   <div class="w3-col w3-padding images__portfolio" >
                  <h4>{{ job.name }}</h4><hr>
                  <div class="container_images">
                    <img  src="https://www.w3schools.com/w3images/avatar_hat.jpg" class="img__detail" alt="">
                  <img  src="https://www.w3schools.com/w3images/avatar_hat.jpg" class="img__detail" alt="">
                  <img  src="https://www.w3schools.com/w3images/avatar_hat.jpg" class="img__detail" alt="">
                  <img  src="https://www.w3schools.com/w3images/avatar_hat.jpg" class="img__detail" alt="">
                  <img  src="https://www.w3schools.com/w3images/avatar_hat.jpg" class="img__detail" alt="">
                   <button @click="modal(i, `none`)" class="w3-btn w3-red w3-block w3-margin-top btn_cerrar_mobile">
                   &times; Cerrar</button>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "hveportfolio",
  props: ["color"],
  data() {
    return {
      jobs: [
        {
          name: "LiKe Me ",
          current: "true",
          datestart: "Jun 2010 - Mar2012",
          dateend: "Current",
          desc: `Sitio donde podras compartir las fotos de tus viajes con tu amigos !`,
          page:"http://instagromelaravel.herokuapp.com/",
          front:"",
          back:"",
          monolito:"http://instagromelaravel.herokuapp.com/",
          tags: [
            { name: "Php", color: "indigo" },
            { name: "Laravel", color: "indigo" },
            { name: "Javascript", color: "yellow" },
            { name: "HTML / CSS", color: "orange" },
          ],
        },

        {
          name: "Graphic Designer ",
          datestart: "Jun 2010 - Mar2012",
          dateend: "Jun 2010 - Mar2012",
          page:"http://instagromelaravel.herokuapp.com/",
          front:"http://instagromelaravel.herokuapp.com/",
          back:"",
          desc: `Lorem ipsum dolor sit amet. Praesentium magnam consectetur vel in deserunt aspernatur est
           reprehenderit sunt hic. 
          Nulla tempora soluta ea et odio, unde doloremque repellendus iure, iste.`,
          tags: [
            { name: "Angular", color: "red" },
            { name: "AngPhpular", color: "blue" },
            { name: "Javascrip", color: "yellow" },
          ],
        },
      ],
    };
  },
  methods: {
    modal(i, tipo) {
      document.getElementById("id0" + i).style.display = tipo;
    },
    goto(link){
       window.open(link);
    }
  },
};
</script>

<style lang="css" scoped>
.container_images{
  overflow-y:scroll;
  height: 82vh;
}
.img_portflio {
  width: 100%;
}
.img__detail{
  width: 100%;
  height: 400px;
  margin-top: 10px;
  margin-bottom: 10px;
}
.card_portfolio {
  padding-top: 10px;
}
.card_portfolio > p {
  margin-left: 10px;
}
.w3-btn {
  border-radius: 10px;
  margin-left: 10px;
  margin-bottom: 10px;
}
.w3-tag {
  border-radius: 10px;
  margin-bottom: 10px;
  margin-left: 8px;
}
.w3-modal-content {
  border-radius: 30px;
}

.w3-modal{
padding: 10px;
 
}
.w3-modal-content{
  width: 95vw !important;
}
.job__barras{
  width: 33%
}
.images__portfolio{
 width: 70%
}
.details__portfolio{
  width: 30%
}
.w3-btn{
  width: 95%;
}
.btn_cerrar_mobile{
  display: block;
}
@media only screen and (max-width: 600px) {
  .menu__avatat {
     position: relative;
  }
  .job__barras{
    width: 100%
  }
  .container_images{
    overflow: none !important;
    height: auto;
  }
  .w3-modal{
    padding: 0px;
  }
  .w3-modal-content{
    margin-top: 10px;
     margin-bottom: 10px;
  }
  .images__portfolio{
    width: 100%
  }
  .details__portfolio{
    width: 100%
  }
  .btn_cerrar_mobile{
    display: block;
  }
}
</style>
