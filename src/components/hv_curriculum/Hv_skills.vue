<template>
  <div :class="`w3-container ${color} nmb7`">
    <div class="w3-row">
      <p class="w3-large w3-margin-top">
        <b
          ><i
            :class="`fa fa-asterisk fa-fw w3-margin-right w3-text-${color}`"
          ></i
          >Skills</b
        >
      </p>
      <div
        class="w3-col skill_barras"
        v-for="(skill, i) in skills"
        :key="`skill-${i}`"
      >
        <p>{{ skill.name }}</p>
        <div
          :class="`w3-container w3-center w3-round-xlarge w3-${color}`"
          :style="'width:' + skill.size + ''"
        >
          {{ skill.size }}
        </div>
      </div>
    </div>
    <div></div>

    <div class="w3-row">
      <p class="w3-large">
        <b
          ><i
            :class="`fa fa-asterisk fa-fw w3-margin-right w3-text-${color}`"
          ></i
          >Idiomas</b
        >
      </p>
      <div
        class="w3-col lang_barras"
        v-for="(language, i) in languages"
        :key="`language-${i}`"
      >
        <p>{{ language.name }}</p>
        <div
          :class="`w3-container w3-center w3-round-xlarge w3-${color}`"
          :style="'width:' + language.size + ''"
        >
          {{ language.size }}
        </div>
        <br />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["color"],
  data() {
    return {
      skills: [
        { name: "JavaScript", size: "95%" },
        { name: "HTML / CSS", size: "95%" },
        { name: "Bootstrap", size: "95%" },
        { name: "Angular", size: "94%" },
        { name: "React", size: "79%" },
        { name: "VueJs", size: "95%" },
        { name: "Php", size: "85%" },
        { name: "Ruby", size: "85%" },
        { name: "NodeJs", size: "88%" },
        { name: "Ruby on Rails", size: "84%" },
        { name: "Laravel", size: "89%" },
        { name: "SQL", size: "90%" },
        { name: "MySQL", size: "90%" },
        { name: "PostgreSQL", size: "87%" },
        { name: "MongoDB", size: "83%" },
        { name: "Photoshop / Ilusrator", size: "52%" },
        { name: "Python", size: "55%" },
        { name: "c++", size: "38%" },
      ],
      languages: [
        { name: "Español", size: "100%" },
        { name: "Ingles", size: "68%" },
      ],
    };
  },
};
</script>

<style>
.lang_barras{
  width:44%;
}
.skill_barras{
  width:20%;
} 
@media only screen and (max-width: 600px) {
  .lang_barras {
      width:100%;
  }
  .skill_barras{
    width:100%;
  } 
}
</style>
