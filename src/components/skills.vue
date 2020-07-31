<template>
  <main class="hello">
<section class="holder">

<form @submit.prevent="addSkill">
  <input type="text" placeholder="Enter your Skill" v-model="skill" v-validate="'min:5'" name="skill">
  <transition name="alert-in">
<p class="alert" v-if="errors.has('skill')"> {{errors.first('skill')}}  </p>
</transition>

</form>

  <ul>
    <li v-for="(data, index) in SkillSet" :key="index"> {{data.Skill}}</li>
  </ul>
<p>These are the skills you posses</p> 

  
  <!-- <p v-if="SkillSet.length >=1">You have more than one skill</p>
  <p v-else>You have no skills</p>  -->

</section>

 <!-- {{name}}
 {{btnState ? 'the Button is disabled' : "the button is Active"}}
 <button v-on:click="changeName" v-bind:disabled="btnState" >Change State</button> -->
  </main>
</template>

<script>
export default {
  name: 'skills', //this exports the file to other files
  data(){
    return {
      skill: '',
    SkillSet: [
      {"Skill": "Vue.JS"},
      {"Skill": "CSS"},
      {"Skill": "HTML5"}
   ]
    }
  }, //data()


methods: {
  addSkill() {
    this.$validator.validateAll().then(result => {
      if (result) {
 this.SkillSet.push({Skill: this.skill})
    this.skill = '';
      } else {
        alert('Not Valid');
      }
    })
   
  }
}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->

<style src="./skills.css">

</style>
