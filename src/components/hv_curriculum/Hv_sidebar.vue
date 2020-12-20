<template>
  <div class="w3-third">
    <div class="w3-white w3-text-grey w3-card-4" style="position:fixed;">
      <div class="w3-display-container">
        <div class="w3-center w3-container w3-text-black"><br/>
          <img src="https://www.w3schools.com/w3images/avatar_hat.jpg" alt="Avatar" class="img_avatar w3-circle w3-margin-top">
          <h2 :class="`w3-text-${color}`"><b>{{ nameuser }}</b></h2>
        </div>
      </div>
      <div class="w3-container">
        <div v-for="(user, i) in users" :key="`userinfo-${i}`">
          <p><i :class="`${user.icon} w3-margin-right w3-large w3-text-${color}`"></i>{{ user.name }}</p>
        </div>
        <hr />
       
      </div>
    </div>
    <br />
  </div>
</template>

<script>
export default {
  name: "sidebar",
  props: ['color'],
  data() {
    return {
      nameuser: "Alexander Nova Arevalo",
      users: [
        { name: "Developer FrontEnd", icon: "fa fa-briefcase fa-fw" },
        { name: "Colombia", icon: "fa fa-home fa-fw" },
        { name: "alexsk88.dev@gmail.com", icon: "fa fa-envelope fa-fw" },
        { name: "316 885 29 20", icon: "fa fa-phone fa-fw" },
      ],

    };
  },
};
</script>

<style>
.img_avatar {
  width:250px;
  height:250px;
}

</style>
