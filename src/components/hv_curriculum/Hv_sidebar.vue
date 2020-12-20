<template>
  <div class="w3-third">
    <div :class="`w3-text-grey w3-card-4 menu__avatat ${color}`">
      <div class="np6">
        <label class="switch">
          <input type="checkbox" checked v-model="mode" />
          <span class="slider round"></span>
        </label>
        <p
          style="display:inline"
          :class="mode ? 'w3-text-black' : 'w3-text-white'"
        >
          Modo: {{ mode ? "dark" : "light" }}
        </p>
      </div>
      <div class="w3-display-container">
        <div class="w3-center w3-container">
          <br />
          <img
            :src="avatar_s"
            alt="Avatar"
            class="img_avatar w3-circle w3-margin-top"
          />
          <h2>
            <b>{{ nameuser }}</b>
          </h2>
        </div>
      </div>
      <div class="w3-container">
        <div v-for="(user, i) in users" :key="`userinfo-${i}`">
          <p>
            <i :class="`${user.icon} w3-margin-right w3-large w3-text-light-blue`"></i
            >{{ user.name }}
          </p>
        </div>
        <hr />
      </div>
    </div>
    <br />
  </div>
</template>

<script>
import avatar from '../../assets/img/portfolio/avatar.jpeg'
export default {
  name: "sidebar",
  props: ["color"],
  
  data() {
    return {
      mode: true,
      avatar_s: avatar,
      nameuser: "Alexander Nova Arevalo",
      users: [
        { name: "Developer FrontEnd", icon: "fa fa-briefcase fa-fw" },
        { name: "Colombia", icon: "fa fa-home fa-fw" },
        { name: "alexsk88.dev@gmail.com", icon: "fa fa-envelope fa-fw" },
        { name: "316 885 29 20", icon: "fa fa-phone fa-fw" },
      ],
    };
  },
   watch: {
    mode: function(params) {
      this.$emit('mode', params)
      
    },
    mounted() {

    },
  },
};
</script>

<style>
.img_avatar {
  width: 250px;
  height: 250px;
}
.menu__avatat {
  position: fixed;
}
@media only screen and (max-width: 600px) {
  .menu__avatat {
    position: relative;
  }
}
</style>
