<template>
  <div :class="`w3-content__app-${theme} `" style="max-width:1400px;">
    <!-- Main -->
    <div class="w3-row content_approw" >
      <sidebar :mode="mode" @mode="changuemode" :color="theme" />
      <hvcontent :color="theme" />
    </div>
  </div>
  <hvfooter :color="color" />
</template>

<script>
import sidebar from "./components/hv_curriculum/Hv_sidebar.vue";
import hvcontent from "./components/hv_curriculum/Hv_content.vue";
import hvfooter from "./components/hv_curriculum/Hv_footer.vue";

export default {
  name: "App",
  data() {
    return {
      color: "light-blue",
      theme: "light",
      mode: true,
    };
  },
  watch: {
    mode: function(params) {
      this.theme = params ? "light" : "dark";
      this.mode= params
     
    },
  },
  components: {
    sidebar,
    hvcontent,
    hvfooter,
  },
  methods:{
    changuemode(mode){
      this.mode = mode

    }
  },
  mounted() {
 
 
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css?family=Montserrat:400,700");
@import url("https://fonts.googleapis.com/css?family=Lato:400,700,400italic,700italic");

.w3-card,
.w3-card-2 {
  border-radius: 30px !important;
}
.w3-card-4,
.w3-hover-shadow:hover {
  box-shadow: 0 4px 10px 0 rgba(0, 0, 0, 0.2), 0 4px 20px 0 rgba(0, 0, 0, 0.19);
  border-radius: 30px !important;
}

.w3-content__app-dark {
  background-color: #06090f;
}
.dark {
  background-color: #06090f !important;
  box-shadow: 0 2px 5px 0 gray, 0 2px 4px 0 gray !important;
  border-radius: 30px !important;
}

.dark > * {
  color: white !important;
}

.w3-content__app-light {
  background-color: #ffffff;
}
.light {
  background-color: #ffffff !important;
  box-shadow: 0 4px 10px 0 rgba(0, 0, 0, 0.2), 0 4px 20px 0 rgba(0, 0, 0, 0.19);
  border-radius: 30px !important;
}
.light > * {
  color: black !important;
}

.w3-btn ,.w3-button{
  outline: none !important;
}

.switch {
  position: relative;
  display: inline-block;
  width: 50px;
  height: 24px;
}

.switch input {
  opacity: 0;
  width: 0;
  height: 0;
}

.slider {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #f7f7f7;
  -webkit-transition: 0.4s;
  transition: 0.4s;
}

.slider:before {
  position: absolute;
  content: "";
  height: 16px;
  width: 16px;
  left: 4px;
  bottom: 4px;
  background-color: #87ceeb !important;
  -webkit-transition: 0.4s;
  transition: 0.4s;
}

input:checked + .slider {
  background-color: black;
}

input:focus + .slider {
  box-shadow: 0 0 1px black;
}

input:checked + .slider:before {
  -webkit-transform: translateX(26px);
  -ms-transform: translateX(26px);
  transform: translateX(26px);
}

/* Rounded sliders */
.slider.round {
  border-radius: 34px;
}

.slider.round:before {
  border-radius: 50%;
}
.content_approw{
  padding-left: 100px;
  padding-right: 100px;
  padding-top: 50px;
}
@media only screen and (max-width: 600px) {
  .content_approw{
    padding: 10px;
  }
}
</style>
